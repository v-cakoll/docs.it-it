---
title: "Proprietà dell'interfaccia (Guida per programmatori C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- properties [C#], on interfaces
- interfaces [C#], properties
ms.assetid: 6503e9ed-33d7-44ec-b4c1-cc16c084b795
caps.latest.revision: "13"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1da48adf73cccb28d9cff641948db52b40b8c1bb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
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
