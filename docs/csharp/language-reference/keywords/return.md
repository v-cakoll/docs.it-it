---
title: Istruzione return - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- return_CSharpKeyword
- return
helpviewer_keywords:
- return statement [C#]
- return keyword [C#]
ms.assetid: 6da6e152-5b58-4448-8f3f-470dd0617ecd
ms.openlocfilehash: 3e89f2f854d1f66ca2d7bf1cfa5a507c267798f8
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422720"
---
# <a name="return-c-reference"></a>return (Riferimenti per C#)

L'istruzione `return` termina l'esecuzione del metodo in cui viene visualizzata e restituisce il controllo al metodo di chiamata. Può restituire anche un valore facoltativo. Se il metodo è un tipo `void`, l'istruzione `return` può essere omessa.

 Se l'istruzione return è all'interno di un blocco `try`, il blocco `finally`, se presente, verrà eseguito prima che il controllo venga restituito al metodo di chiamata.

## <a name="example"></a>Esempio

 Nell'esempio seguente il metodo `CalculateArea()` restituisce la variabile locale `area` come valore [double](double.md).

[!code-csharp[csrefKeywordsJump#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#6)]  

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](index.md)
- [Istruzione return](/cpp/cpp/return-statement-cpp)
