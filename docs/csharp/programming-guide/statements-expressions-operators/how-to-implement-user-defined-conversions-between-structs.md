---
title: "Procedura: Implementare conversioni tra struct definite dall'utente - Guida per programmatori C#"
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- user-defined conversions [C#]
ms.assetid: 97839aef-8fbc-40d5-9769-6b569bc2710b
ms.openlocfilehash: bc792562b4849d402e03328e50dedac030520011
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/01/2019
ms.locfileid: "57201144"
---
# <a name="how-to-implement-user-defined-conversions-between-structs-c-programming-guide"></a>Procedura: Implementare conversioni tra struct definite dall'utente (Guida per programmatori C#)
Questo esempio definisce due struct, `RomanNumeral` e `BinaryNumeral`, e illustra le conversioni tra di loro.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csProgGuideStatements#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#13)]  
  
## <a name="robust-programming"></a>Programmazione efficiente  
  
-   Nell'esempio precedente l'istruzione:  
  
     [!code-csharp[csProgGuideStatements#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#14)]  
  
     esegue una conversione da `RomanNumeral` a `BinaryNumeral`. Poiché non c'è una conversione diretta da `RomanNumeral` a `BinaryNumeral`, vengono usati un cast per la conversione da `RomanNumeral` a `int` e un altro cast per la conversione da `int` a `BinaryNumeral`.  
  
-   Anche l'istruzione  
  
     [!code-csharp[csProgGuideStatements#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#15)]  
  
     esegue una conversione da `BinaryNumeral` a `RomanNumeral`. Poiché `RomanNumeral` definisce una conversione implicita da `BinaryNumeral`, non è necessario il cast.  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../../../csharp/language-reference/index.md)
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)
- [Operatori di conversione](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)
