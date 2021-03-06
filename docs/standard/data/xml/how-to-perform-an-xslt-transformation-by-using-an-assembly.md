---
title: "Cómo realizar una transformación XSLT mediante un ensamblado"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 76ee440b-d134-4f8f-8262-b917ad6dcbf6
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d14c4338290856c09ca1d23ec6acc895450f83ea
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-perform-an-xslt-transformation-by-using-an-assembly"></a>Cómo realizar una transformación XSLT mediante un ensamblado
El compilador XSLT (xsltc.exe) compila hojas de estilo XSLT y genera un ensamblado. Dicho ensamblado se puede pasar directamente al método <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Type%29?displayProperty=nameWithType>.  
  
### <a name="to-copy-the-xml-and-xslt-files-to-your-local-computer"></a>Para copiar los archivos XML y XSLT al ordenador  
  
-   Copie el archivo XSLT en su ordenador y llámelo Transform.xsl.  
  
    ```xml  
    <xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform"  
      xmlns:msxsl="urn:schemas-microsoft-com:xslt"  
      xmlns:user="urn:my-scripts">  
      <msxsl:script language="C#" implements-prefix="user">  
        <![CDATA[  
      public string discount(string price){  
        char[] trimChars = { '$' };  
        //trim leading $, convert price to type double  
        double discount_value = Convert.ToDouble(price.TrimStart(trimChars));  
        //apply 10% discount and round appropriately  
        discount_value = .9*discount_value;  
        //convert value to decimal and format as currency  
        string discount_price = discount_value.ToString("C");  
        return discount_price;  
      }  
      ]]>  
      </msxsl:script>  
      <xsl:template match="catalog">  
        <html>  
          <head></head>  
          <body>  
            <table border="1">  
              <tr>  
                <th align="left">Title</th>  
                <th align="left">Author</th>  
                <th align="left">Genre</th>  
                <th align="left">Publish Date</th>  
                <th align="left">Price</th>  
              </tr>  
              <xsl:for-each select="book">  
                <tr>  
                  <td>  
                    <xsl:value-of select="title"/>  
                  </td>  
                  <td>  
                    <xsl:value-of select="author"/>  
                  </td>  
                  <td>  
                    <xsl:value-of select="genre"/>  
                  </td>  
                  <td>  
                    <xsl:value-of select="publish_date"/>  
                  </td>  
                  <xsl:choose>  
                    <xsl:when test="genre = 'Fantasy'">  
                      <td>  
                        <xsl:value-of select="user:discount(price)"/>  
                      </td>  
                    </xsl:when>  
                    <xsl:otherwise>  
                      <td>  
                        <xsl:value-of select="price"/>  
                      </td>  
                    </xsl:otherwise>  
                  </xsl:choose>  
                </tr>  
              </xsl:for-each>  
            </table>  
          </body>  
        </html>  
      </xsl:template>  
    </xsl:stylesheet>  
    ```  
  
-   Copie el archivo XML en su ordenador y llámelo `books.xml`.  
  
    ```xml  
    <?xml version="1.0"?>  
    <catalog>  
       <book id="bk101">  
          <author>Gambardella, Matthew</author>  
          <title>XML Developer's Guide</title>  
          <genre>Computer</genre>  
          <price>$44.95</price>  
          <publish_date>2000-10-01</publish_date>  
       </book>  
       <book id="bk102">  
          <author>Ralls, Kim</author>  
          <title>Midnight Rain</title>  
          <genre>Fantasy</genre>  
          <price>$5.95</price>  
          <publish_date>2000-12-16</publish_date>  
       </book>  
       <book id="bk103">  
          <author>Corets, Eva</author>  
          <title>Maeve Ascendant</title>  
          <genre>Fantasy</genre>  
          <price>$5.95</price>  
          <publish_date>2000-11-17</publish_date>  
       </book>  
       <book id="bk106">  
          <author>Randall, Cynthia</author>  
          <title>Lover Birds</title>  
          <genre>Romance</genre>  
          <price>$4.95</price>  
          <publish_date>2000-09-02</publish_date>  
       </book>  
       <book id="bk107">  
          <author>Thurman, Paula</author>  
          <title>Splish Splash</title>  
          <genre>Romance</genre>  
          <price>$4.95</price>  
          <publish_date>2000-11-02</publish_date>  
       </book>  
    </catalog>  
    ```  
  
### <a name="to-compile-the-style-sheet-with-the-script-enabled"></a>Para compilar la hoja de estilos con el script habilitado.  
  
1.  Si ejecuta la siguiente instrucción desde la línea de comandos, se crearán dos ensamblados, cuyos nombres son `Transform.dll` y `Transform_Script1.dll` (este es el comportamiento predeterminado. A menos que se especifique lo contrario, el nombre de la clase y del ensamblado será, de forma predeterminada, el nombre de la hoja de estilos principal):  
  
    ```  
    xsltc /settings:script+ Transform.xsl  
    ```  
  
 La siguiente instrucción establece explícitamente el nombre de la clase en Transform:  
  
```  
xsltc /settings:script+ /class:Transform Transform.xsl  
```  
  
### <a name="to-include-the-compiled-assembly-as-a-reference-when-you-compile-your-code"></a>Para incluir el ensamblado compilado como referencia a la hora de compilar el código.  
  
1.  Puede incluir un ensamblado en Visual Studio agregando una referencia en el Explorador de soluciones, o bien desde la línea de comandos.  
  
2.  En C#, utilice lo siguiente en la línea de comandos:  
  
    ```  
    csc myCode.cs /r:system.dll;system.xml.dll;Transform.dll  
    ```  
  
3.  En Visual Basic, utilice lo siguiente en la línea de comandos:  
  
    ```  
    vbc myCode.vb /r:system.dll;system.xml.dll;Transform.dll  
    ```  
  
### <a name="to-use-the-compiled-assembly-in-your-code"></a>Para utilizar el ensamblado compilado en su código.  
  
1.  El siguiente ejemplo muestra cómo ejecutar la transformación XSLT utilizando la hoja de estilos compilada.  
  
 [!code-csharp[XslTransform_XSLTC#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XslTransform_XSLTC/CS/XslTransform_XSLTC.cs#1)]
 [!code-vb[XslTransform_XSLTC#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XslTransform_XSLTC/VB/XslTransform_XSLTC.vb#1)]  
  
 Para vincular dinámicamente el ensamblado compilado, sustituya  
  
```  
xslt.Load(typeof(Transform))  
```  
  
 with  
  
```  
xslt.Load(System.Reflection.Assembly.Load("Transform").GetType("Transform"))  
```  
  
 en el ejemplo anterior. Para obtener más información acerca del método Assembly.Load, vea <xref:System.Reflection.Assembly.Load%2A>  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Xml.Xsl.XslCompiledTransform>  
 [Compilador XSLT (xsltc.exe)](../../../../docs/standard/data/xml/xslt-compiler-xsltc-exe.md)  
 [Transformaciones XSLT](../../../../docs/standard/data/xml/xslt-transformations.md)  
 [Compilar la línea de comandos con csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)
