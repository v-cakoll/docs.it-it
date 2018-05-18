---
title: Implementazione esplicita dell'interfaccia (Guida per programmatori C#)
ms.date: 07/20/2015
helpviewer_keywords:
- explicit interfaces [C#]
- interfaces [C#], explicit
ms.assetid: 181c901f-0d4c-4f29-97fc-895079617bf2
ms.openlocfilehash: 7494f7d6a3897d56419f9d3aa96668fd9dab5f35
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="explicit-interface-implementation-c-programming-guide"></a>Implementazione esplicita dell'interfaccia (Guida per programmatori C#)
Se [class](../../../csharp/language-reference/keywords/class.md) implementa due interfacce che contengono un membro con la stessa firma e quest'ultimo viene implementato nella classe, entrambe le interfacce useranno il membro come propria implementazione. Nell'esempio seguente tutte le chiamate a `Paint` richiamano lo stesso metodo.  
  
 [!code-csharp[csProgGuideInheritance#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_1.cs)]  
  
 Se tuttavia i due membri di [interface](../../../csharp/language-reference/keywords/interface.md) non eseguono la stessa funzione, l'implementazione di una o di entrambe le interfacce potrebbe non risultare corretta. È possibile implementare un membro di interfaccia in modo esplicito, ovvero creando un membro di classe che viene chiamato solo tramite l'interfaccia e che è specifico di tale interfaccia. Per questa operazione è necessario assegnare al membro di classe il nome dell'interfaccia seguito da un punto. Ad esempio:  
  
 [!code-csharp[csProgGuideInheritance#40](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_2.cs)]  
  
 Il membro di classe `IControl.Paint` è disponibile solo tramite l'interfaccia`IControl` e `ISurface.Paint` è disponibile solo tramite `ISurface`. Entrambe le implementazioni del metodo sono separate e nessuna delle due è disponibile direttamente nella classe. Ad esempio:  
  
 [!code-csharp[csProgGuideInheritance#41](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_3.cs)]  
  
 L'implementazione esplicita viene usata anche per risolvere i casi in cui due interfacce dichiarano ognuna membri diversi con lo stesso nome, ad esempio una proprietà e un metodo:  
  
 [!code-csharp[csProgGuideInheritance#42](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_4.cs)]  
  
 Per implementare entrambe le interfacce, una classe deve usare l'implementazione esplicita per la proprietà P o il metodo P oppure per entrambi, in modo da evitare un errore del compilatore. Ad esempio:  
  
 [!code-csharp[csProgGuideInheritance#43](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_5.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Classi e struct](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [Interfacce](../../../csharp/programming-guide/interfaces/index.md)  
 [Ereditarietà](../../../csharp/programming-guide/classes-and-structs/inheritance.md)
