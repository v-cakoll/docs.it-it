---
title: Operatori di conversione (Guida per programmatori C#)
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, conversion operators
- conversion operators [C#]
- operators [C#], conversion
- user-defined conversions [C#]
ms.assetid: c5ad73a3-d57b-4d2b-b4c9-24e3c2856efc
ms.openlocfilehash: cbf6a83d43a1b3a69e82a35d5d0875f62422cd3f
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2018
ms.locfileid: "44183314"
---
# <a name="conversion-operators-c-programming-guide"></a>Operatori di conversione (Guida per programmatori C#)
C# consente ai programmatori di dichiarare conversioni in classi o struct, in modo che sia possibile convertire le classi o gli struct da e/o in altre classi o altri struct oppure tipi di base. Le conversioni vengono definite come operatori e sono denominate in base al tipo di destinazione della conversione. Il tipo dell'argomento da convertire oppure il tipo del risultato della conversione, ma non entrambi, deve essere il tipo contenitore.  
  
 [!code-csharp[csProgGuideStatements#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/conversion-operators_1.cs)]  
  
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

- <xref:System.Convert>  
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
- [Conversioni esplicite concatenate definite dall'utente in C#](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/)
