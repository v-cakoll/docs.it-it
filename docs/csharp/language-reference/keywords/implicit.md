---
title: implicit (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- implicit
- implicit_CSharpKeyword
helpviewer_keywords:
- implicit keyword [C#]
ms.assetid: 34db590e-eb3a-4f11-88d0-ffb3cd753dab
ms.openlocfilehash: 70379136fd4b14403eac919ac15590250b17b416
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2018
ms.locfileid: "46702697"
---
# <a name="implicit-c-reference"></a>implicit (Riferimenti per C#)

La parola chiave `implicit` viene usata per dichiarare un operatore di conversione implicita di tipi definito dall'utente. È possibile usare questa parola chiave per abilitare le conversioni implicite tra un tipo definito dall'utente e un altro tipo, se è garantito che tale conversione non provoca una perdita di dati.

## <a name="example"></a>Esempio

[!code-csharp[csrefKeywordsConversion#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#5)]

Grazie all'eliminazione dei cast non necessari, le conversioni implicite contribuiscono a migliorare la leggibilità del codice sorgente. Tuttavia, poiché per le conversioni implicite non è necessario eseguire il cast in modo esplicito da un tipo all'altro, è importante assicurarsi di non ottenere risultati imprevisti. In genere, per poter essere usati in modo sicuro senza il controllo del programmatore, gli operatori di conversione implicita non devono generare eccezioni né determinare perdite di dati. Se un operatore di conversione non soddisfa questi requisiti, è opportuno contrassegnarlo come `explicit`. Per altre informazioni, vedere [Uso degli operatori di conversione](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)  
- [Guida per programmatori C#](../../programming-guide/index.md)  
- [Parole chiave di C#](index.md)  
- [explicit](explicit.md)  
- [operatore (Riferimenti per C#)](operator.md)  
- [Procedura: Implementare conversioni tra struct definite dall'utente](../../programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
