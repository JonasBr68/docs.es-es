---
title: "IMetaDataAssemblyImport::GetAssemblyProps (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.GetAssemblyProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::GetAssemblyProps
helpviewer_keywords:
- GetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetAssemblyProps method [.NET Framework metadata]
ms.assetid: 0eaa4aa9-9441-444a-920c-e4b2a2db899e
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f3ff9c66d483392823a1cc95163e4d5e7e81a364
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyimportgetassemblyprops-method"></a><span data-ttu-id="5235b-102">IMetaDataAssemblyImport::GetAssemblyProps (Método)</span><span class="sxs-lookup"><span data-stu-id="5235b-102">IMetaDataAssemblyImport::GetAssemblyProps Method</span></span>
<span data-ttu-id="5235b-103">Obtiene el conjunto de propiedades para el ensamblado con la firma de metadatos especificados.</span><span class="sxs-lookup"><span data-stu-id="5235b-103">Gets the set of properties for the assembly with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5235b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5235b-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyProps (  
    [in]  mdAssembly          mda,  
    [out] const void          **ppbPublicKey,   
    [out] ULONG               *pcbPublicKey,  
    [out] ULONG               *pulHashAlgId,  
    [out] LPWSTR              szName,  
    [in] ULONG                cchName,  
    [out] ULONG               *pchName,  
    [out] ASSEMBLYMETADATA    *pMetaData,  
    [out] DWORD               *pdwAssemblyFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5235b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5235b-105">Parameters</span></span>  
 `mda`  
 <span data-ttu-id="5235b-106">[in].</span><span class="sxs-lookup"><span data-stu-id="5235b-106">[in].</span></span> <span data-ttu-id="5235b-107">El `mdAssembly` símbolo (token) de metadatos que representa el ensamblado para el que se va a obtener las propiedades.</span><span class="sxs-lookup"><span data-stu-id="5235b-107">The `mdAssembly` metadata token that represents the assembly for which to get the properties.</span></span>  
  
 `ppbPublicKey`  
 <span data-ttu-id="5235b-108">[out] Un puntero a la clave pública o el token de metadatos.</span><span class="sxs-lookup"><span data-stu-id="5235b-108">[out] A pointer to the public key or the metadata token.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="5235b-109">[out] El número de bytes de la clave pública devuelta.</span><span class="sxs-lookup"><span data-stu-id="5235b-109">[out] The number of bytes in the returned public key.</span></span>  
  
 `pulHashAlgId`  
 <span data-ttu-id="5235b-110">[out] Un puntero al algoritmo utilizado para resumir los archivos en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="5235b-110">[out] A pointer to the algorithm used to hash the files in the assembly.</span></span>  
  
 `szName`  
 <span data-ttu-id="5235b-111">[out] El nombre simple del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="5235b-111">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="5235b-112">[in] El tamaño, en caracteres anchos, de `szName`.</span><span class="sxs-lookup"><span data-stu-id="5235b-112">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="5235b-113">[out] El número de caracteres anchos realmente devueltos en `szName`.</span><span class="sxs-lookup"><span data-stu-id="5235b-113">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="5235b-114">[out] Un puntero a una estructura ASSEMBLYMETADATA que contiene los metadatos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="5235b-114">[out] A pointer to an ASSEMBLYMETADATA structure that contains the assembly metadata.</span></span>  
  
 `pdwAssemblyFlags`  
 <span data-ttu-id="5235b-115">[out] Marcas que describen los metadatos aplicados a un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="5235b-115">[out] Flags that describe the metadata applied to an assembly.</span></span> <span data-ttu-id="5235b-116">Este valor es una combinación de uno o varios [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) valores.</span><span class="sxs-lookup"><span data-stu-id="5235b-116">This value is a combination of one or more [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5235b-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5235b-117">Requirements</span></span>  
 <span data-ttu-id="5235b-118">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5235b-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5235b-119">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5235b-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5235b-120">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5235b-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5235b-121">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5235b-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5235b-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="5235b-122">See Also</span></span>  
 [<span data-ttu-id="5235b-123">IMetaDataAssemblyImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5235b-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)