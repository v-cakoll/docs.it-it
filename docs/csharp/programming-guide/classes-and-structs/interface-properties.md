---
title: Proprietà dell'interfaccia (Guida per programmatori C#)
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], on interfaces
- interfaces [C#], properties
ms.assetid: 6503e9ed-33d7-44ec-b4c1-cc16c084b795
ms.openlocfilehash: bfa03c7ebe82f3f6a03666d908a5fa9d4e386172
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33325409"
---
# <a name="interface-properties-c-programming-guide"></a>Proprietà dell'interfaccia (Guida per programmatori C#)
Le proprietà possono essere dichiarate su una [interfaccia](../../../csharp/language-reference/keywords/interface.md). Nell'esempio seguente viene illustrata la funzione di accesso di un indicizzatore di interfaccia:  
  
 [!code-csharp[csProgGuideProperties#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_1.cs)]  
  
 La funzione di accesso di una proprietà di interfaccia non ha un corpo. Lo scopo delle funzioni di accesso, pertanto, è quello di indicare se la proprietà è in lettura-scrittura, in sola lettura o in sola scrittura.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente l'interfaccia `IEmployee` include una proprietà in lettura-scrittura, `Name`, e una proprietà in sola lettura, `Counter`. La classe `Employee` implementa l'interfaccia `IEmployee` e usa le due proprietà. Il programma legge il nome di un nuovo dipendente e il numero corrente di dipendenti e quindi visualizza il nome del dipendente e il relativo numero calcolato.  
  
 È possibile usare il nome completo della proprietà, che fa riferimento all'interfaccia in cui il membro è dichiarato. Ad esempio:  
  
 [!code-csharp[csProgGuideProperties#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_2.cs)]  
  
 Questo meccanismo è denominato [Implementazione esplicita dell'interfaccia](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md). Se la classe `Employee` implementa, ad esempio, due interfacce, `ICitizen` e `IEmployee`, ed entrambe le interfacce includono la proprietà `Name`, sarà necessaria l'implementazione esplicita del membro dell'interfaccia. In altre parole, la dichiarazione di proprietà seguente:  
  
 [!code-csharp[csProgGuideProperties#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_2.cs)]  
  
 implementa la proprietà `Name` nell'interfaccia `IEmployee`, mentre la dichiarazione seguente:  
  
 [!code-csharp[csProgGuideProperties#17](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_3.cs)]  
  
 implementa la proprietà `Name` nell'interfaccia `ICitizen`.  
  
 [!code-csharp[csProgGuideProperties#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_4.cs)]  
  
  **`210 Hazem Abolrous`**    
## <a name="sample-output"></a>Esempio di output  
 `Enter number of employees: 210`  
  
 `Enter the name of the new employee: Hazem Abolrous`  
  
 `The employee information:`  
  
 `Employee number: 211`  
  
 `Employee name: Hazem Abolrous`  
  
## <a name="see-also"></a>Vedere anche  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Proprietà](../../../csharp/programming-guide/classes-and-structs/properties.md)  
 [Uso delle proprietà](../../../csharp/programming-guide/classes-and-structs/using-properties.md)  
 [Confronto tra proprietà e indicizzatori](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md)  
 [Indicizzatori](../../../csharp/programming-guide/indexers/index.md)  
 [Interfacce](../../../csharp/programming-guide/interfaces/index.md)
