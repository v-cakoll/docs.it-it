---
title: object (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- object_CSharpKeyword
- object
helpviewer_keywords:
- object keyword [C#]
ms.assetid: 93f60c0b-e17a-40a9-9362-cca5fb77b0e7
caps.latest.revision: 16
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 0fcced75d3a86fd700e642e48b7e325e554cae53
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="object-c-reference"></a>object (Riferimenti per C#)
Il tipo `object` è un alias di <xref:System.Object> in .NET Framework. Nel sistema di tipi unificato di C#, tutti i tipi, predefiniti e definiti dall'utente, i tipi riferimento e i tipi valore ereditano direttamente o indirettamente da <xref:System.Object>. Alle variabili di tipo `object` è possibile assegnare valori di qualsiasi tipo. Una variabile di un tipo di valore convertita in oggetto viene definita *boxed*. Una variabile di tipo object convertita in un tipo di valore viene definita *unboxed*. Per altre informazioni, vedere [Boxing e unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente descrive come le variabili di tipo `object` possono accettare valori di qualsiasi tipo di dati e come le variabili di tipo `object` possono usare i metodi in <xref:System.Object> da .NET Framework.  
  
 [!code-csharp[csrefKeywordsTypes#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/object_1.cs)]  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)  
 [Tipi riferimento](../../../csharp/language-reference/keywords/reference-types.md)  
 [Tipi valore](../../../csharp/language-reference/keywords/value-types.md)
