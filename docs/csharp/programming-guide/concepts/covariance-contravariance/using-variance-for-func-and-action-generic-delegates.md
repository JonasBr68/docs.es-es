---
title: "Usar la varianza para los delegados genéricos Func y Action (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 1826774f-2b7a-470f-b110-17cfdd6abdae
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1b12a08579f70a07ebb90bfe723209b9f03460e9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="using-variance-for-func-and-action-generic-delegates-c"></a>Usar la varianza para los delegados genéricos Func y Action (C#)
En estos ejemplos se muestra cómo usar la covarianza y la contravarianza en los delegados genéricos `Func` y `Action` para habilitar la reutilización de métodos y proporcionar más flexibilidad en el código.  
  
 Para obtener más información sobre la covarianza y la contravarianza, vea [Varianza en delegados (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)  
  
## <a name="using-delegates-with-covariant-type-parameters"></a>Usar delegados con parámetros de tipo covariante  
 En el ejemplo siguiente se muestran las ventajas de la compatibilidad con la covarianza en los delegados `Func` genéricos. El método `FindByTitle` toma un parámetro del tipo `String` y devuelve un objeto del tipo `Employee`. Pero este método se puede asignar al delegado `Func<String, Person>` porque `Employee` hereda `Person`.  
  
```csharp  
// Simple hierarchy of classes.  
public class Person { }  
public class Employee : Person { }  
class Program  
{  
    static Employee FindByTitle(String title)  
    {  
        // This is a stub for a method that returns  
        // an employee that has the specified title.  
        return new Employee();  
    }  
  
    static void Test()  
    {  
        // Create an instance of the delegate without using variance.  
        Func<String, Employee> findEmployee = FindByTitle;  
  
        // The delegate expects a method to return Person,  
        // but you can assign it a method that returns Employee.  
        Func<String, Person> findPerson = FindByTitle;  
  
        // You can also assign a delegate   
        // that returns a more derived type   
        // to a delegate that returns a less derived type.  
        findPerson = findEmployee;  
  
    }  
}  
```  
  
## <a name="using-delegates-with-contravariant-type-parameters"></a>Usar delegados con parámetros de tipo contravariante  
 En el ejemplo siguiente se muestran las ventajas de la compatibilidad con la contravarianza en los delegados `Action` genéricos. El método `AddToContacts` toma un parámetro del tipo `Person`. Pero este método se puede asignar al delegado `Action<Employee>` porque `Employee` hereda `Person`.  
  
```csharp  
public class Person { }  
public class Employee : Person { }  
class Program  
{  
    static void AddToContacts(Person person)  
    {  
        // This method adds a Person object  
        // to a contact list.  
    }  
  
    static void Test()  
    {  
        // Create an instance of the delegate without using variance.  
        Action<Person> addPersonToContacts = AddToContacts;  
  
        // The Action delegate expects   
        // a method that has an Employee parameter,  
        // but you can assign it a method that has a Person parameter  
        // because Employee derives from Person.  
        Action<Employee> addEmployeeToContacts = AddToContacts;  
  
        // You can also assign a delegate   
        // that accepts a less derived parameter to a delegate   
        // that accepts a more derived parameter.  
        addEmployeeToContacts = addPersonToContacts;  
    }  
}  
```  
  
## <a name="see-also"></a>Vea también  
 [Covarianza y contravarianza (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/index.md)  
 [Genéricos](~/docs/standard/generics/index.md)
