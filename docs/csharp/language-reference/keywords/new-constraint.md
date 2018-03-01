---
title: Vincolo new (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- new constraint keyword [C#]
ms.assetid: 58850b64-cb97-4136-be50-1f3bc7fc1da9
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8557e056a664fd470b1f185b619d81235c8fcba7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="new-constraint-c-reference"></a>Vincolo new (Riferimenti per C#)
Il vincolo `new` specifica che qualsiasi argomento di tipo in una dichiarazione di classe generica deve avere un costruttore pubblico senza parametri. Per usare il vincolo new, il tipo non può essere astratto.  
  
## <a name="example"></a>Esempio  
 Applicare il vincolo `new` a un parametro del tipo quando la classe generica crea nuove istanze del tipo, come illustrato nell'esempio seguente:  
  
 [!code-csharp[csrefKeywordsOperator#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_1.cs)]  
  
## <a name="example"></a>Esempio  
 Quando il vincolo `new()` viene usato con altri vincoli, è necessario specificarlo per ultimo:  
  
 [!code-csharp[csrefKeywordsOperator#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_2.cs)]  
  
 Per altre informazioni, vedere [Vincoli sui parametri di tipo](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Collections.Generic>  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)  
 [Parole chiave per gli operatori](../../../csharp/language-reference/keywords/operator-keywords.md)  
 [Generics](../../../csharp/programming-guide/generics/index.md)
