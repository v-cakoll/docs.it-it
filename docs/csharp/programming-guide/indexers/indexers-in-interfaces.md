---
title: Indicizzatori nelle interfacce (Guida per programmatori C#)
ms.date: 07/20/2015
helpviewer_keywords:
- indexers [C#], in interfaces
- accessors [C#], indexers
ms.assetid: e16b54bd-4a83-4f52-bd75-65819fca79e8
ms.openlocfilehash: cb039755b7440cbfd1f782cc118d11a03b47da04
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="indexers-in-interfaces-c-programming-guide"></a>Indicizzatori nelle interfacce (Guida per programmatori C#)
Gli indicizzatori possono essere dichiarati su una [interfaccia](../../../csharp/language-reference/keywords/interface.md). Le funzioni di accesso degli indicizzatori di interfaccia differiscono dalle funzioni di accesso degli indicizzatori di [classe](../../../csharp/language-reference/keywords/class.md) per gli aspetti seguenti:  
  
-   Le funzioni di accesso di interfaccia non usano modificatori.  
  
-   Una funzione di accesso di interfaccia non include un corpo.  
  
 Lo scopo della funzione di accesso, pertanto, è quello di indicare se l'indicizzatore è in lettura-scrittura, in sola lettura o in sola scrittura.  
  
 Nell'esempio seguente viene illustrata la funzione di accesso di un indicizzatore di interfaccia:  
  
 [!code-csharp[csProgGuideIndexers#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/indexers-in-interfaces_1.cs)]  
  
 È necessario che la firma di un indicizzatore sia diversa dalle firme di tutti gli altri indicizzatori dichiarati nella stessa interfaccia.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come implementare gli indicizzatori di interfaccia.  
  
 [!code-csharp[csProgGuideIndexers#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/indexers-in-interfaces_2.cs)]  
  
 Nell'esempio precedente era possibile adottare l'implementazione esplicita del membro dell'interfaccia usando il nome completo del membro dell'interfaccia. Ad esempio:  
  
```  
public string ISomeInterface.this[int index]   
{   
}   
```  
  
 Il nome completo, tuttavia, è necessario soltanto per evitare l'ambiguità quando la classe implementa più di un'interfaccia con la stessa firma di indicizzatore. Se una classe `Employee` implementa, ad esempio, due interfacce, `ICitizen` e `IEmployee`, ed entrambe le interfacce hanno la stessa firma di indicizzatore, sarà necessaria l'implementazione esplicita del membro dell'interfaccia. In altre parole, la dichiarazione di indicizzatore seguente:  
  
```  
public string IEmployee.this[int index]   
{   
}   
```  
  
 implementa l'indicizzatore nell'interfaccia `IEmployee`, mentre la dichiarazione seguente:  
  
```  
public string ICitizen.this[int index]
{   
}   
```  
  
 implementa l'indicizzatore nell'interfaccia `ICitizen`.  
  
## <a name="see-also"></a>Vedere anche  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Indicizzatori](../../../csharp/programming-guide/indexers/index.md)  
 [Proprietà](../../../csharp/programming-guide/classes-and-structs/properties.md)  
 [Interfacce](../../../csharp/programming-guide/interfaces/index.md)
