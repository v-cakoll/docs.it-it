---
title: Parola chiave operator (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- operator_CSharpKeyword
- operator
helpviewer_keywords:
- operator keyword [C#]
ms.assetid: 59218cce-e90e-42f6-a6bb-30300981b86a
ms.openlocfilehash: c3bfada235993670bf158fe9803a09707b2b3251
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2018
ms.locfileid: "42929872"
---
# <a name="operator-c-reference"></a>operator (Riferimenti per C#)

Usare la parola chiave `operator` per eseguire l'overload di un operatore predefinito o specificare una conversione definita dall'utente in una classe o una dichiarazione di struttura.

## <a name="example"></a>Esempio

La classe riportata di seguito è una classe estremamente semplificata per numeri frazionari. La classe esegue l'overload degli operatori `+` e `*` per eseguire addizioni e moltiplicazioni frazionarie e specifica un operatore di conversione che converte un tipo `Fraction` in un tipo `double`.

[!code-csharp[csrefKeywordsConversion#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#6)]

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](index.md)
- [implicit](implicit.md)
- [explicit](explicit.md)
- [Procedura: Implementare conversioni tra struct definite dall'utente](../../programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
