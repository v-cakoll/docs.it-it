---
title: Parola chiave operator (Riferimenti per C#)
description: Informazioni su come eseguire l'overload di un operatore C# predefinito
ms.date: 08/27/2018
f1_keywords:
- operator_CSharpKeyword
- operator
helpviewer_keywords:
- operator keyword [C#]
ms.assetid: 59218cce-e90e-42f6-a6bb-30300981b86a
ms.openlocfilehash: 1e11d7767b61becc39b1158fae9cb2abe997e4bd
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "43480652"
---
# <a name="operator-c-reference"></a>operator (Riferimenti per C#)

Usare la parola chiave `operator` per eseguire l'overload di un operatore predefinito o specificare una conversione definita dall'utente in una classe o una dichiarazione di struttura.

Per eseguire l'overload di un operatore in una classe o uno struct personalizzati, si crea una dichiarazione dell'operatore nel tipo corrispondente. La dichiarazione dell'operatore che esegue l'overload di un operatore C# predefinito deve soddisfare le regole seguenti:

- Include sia un modificatore `public` che un modificatore `static`.
- Include `operator X` dove `X` è il nome o il simbolo dell'operatore sottoposto a overload.
- Gli operatori unari hanno un parametro, gli operatori binari invece due parametri. In ogni caso, almeno un parametro deve essere dello stesso tipo della classe o struct che dichiara l'operatore.

Per informazioni su come definire gli operatori di conversione, vedere gli articoli sulle parole chiave [explicit](explicit.md) e [implicit](implicit.md).

Per una panoramica degli operatori C# che possono essere sottoposti a overload, vedere l'articolo [Operatori che supportano l'overload](../../programming-guide/statements-expressions-operators/overloadable-operators.md).

## <a name="example"></a>Esempio

L'esempio seguente definisce un tipo `Fraction` che rappresenta i numeri frazionari. La classe esegue l'overload degli operatori `+` e `*` per eseguire addizioni e moltiplicazioni frazionarie e specifica un operatore di conversione che converte un tipo `Fraction` in un tipo `double`.

[!code-csharp[csrefKeywordsConversion#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#6)]

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](index.md)
- [implicit](implicit.md)
- [explicit](explicit.md)
- [Operatori che supportano l'overload](../../programming-guide/statements-expressions-operators/overloadable-operators.md)
- [Procedura: Implementare conversioni tra struct definite dall'utente](../../programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
