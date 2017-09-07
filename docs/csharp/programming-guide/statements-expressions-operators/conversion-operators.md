---
title: Operatori di conversione (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, conversion operators
- conversion operators [C#]
- operators [C#], conversion
- user-defined conversions [C#]
ms.assetid: c5ad73a3-d57b-4d2b-b4c9-24e3c2856efc
caps.latest.revision: 22
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c12fd13d6526d79363f973ce2a944c4823bf4104
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="conversion-operators-c-programming-guide"></a>Operatori di conversione (Guida per programmatori C#)
C# consente ai programmatori di dichiarare conversioni in classi o struct, in modo che sia possibile convertire le classi o gli struct da e/o in altre classi o altri struct oppure tipi di base. Le conversioni vengono definite come operatori e sono denominate in base al tipo di destinazione della conversione. Il tipo dell'argomento da convertire oppure il tipo del risultato della conversione, ma non entrambi, deve essere il tipo contenitore.  
  
 [!code-cs[csProgGuideStatements#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/conversion-operators_1.cs)]  
  
## <a name="conversion-operators-overview"></a>Panoramica degli operatori di conversione  
 Gli operatori di conversione hanno le proprietà seguenti:  
  
-   Le conversioni dichiarate come `implicit` vengono eseguite automaticamente quando è necessario.  
  
-   Le conversioni dichiarate come `explicit` richiedono che venga chiamato un cast.  
  
-   Tutte le conversioni devono essere dichiarate come `static`.  
  
## <a name="related-sections"></a>Sezioni correlate  
 Per ulteriori informazioni:  
  
-   [Uso degli operatori di conversione](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)  
  
-   [Cast e conversioni di tipi](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  
  
-   [Procedura: Implementare conversioni tra struct definite dall'utente](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
-   [explicit](../../../csharp/language-reference/keywords/explicit.md)  
  
-   [implicit](../../../csharp/language-reference/keywords/implicit.md)  
  
-   [static](../../../csharp/language-reference/keywords/static.md)  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Convert>   
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)   
 [Conversioni esplicite concatenate definite dall'utente in C#](http://go.microsoft.com/fwlink/?LinkId=112384)

