---
title: Istruzione goto - Riferimenti per C#
ms.date: 07/20/2015
f1_keywords:
- goto_CSharpKeyword
- goto
helpviewer_keywords:
- goto keyword [C#]
ms.assetid: 2c03c9c1-8119-44ef-b740-fb3d287a42fe
ms.openlocfilehash: 076f793e880a7b4d1e8872d80e88c44cdf077541
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75715280"
---
# <a name="goto-c-reference"></a>goto (Riferimenti per C#)

L'istruzione `goto` passa direttamente il controllo del programma a un'istruzione con etichetta.

L'istruzione `goto` viene generalmente usata per trasferire il controllo a un'etichetta switch case specifica o all'etichetta predefinita di un'istruzione `switch`.

L'istruzione `goto` viene anche usata per uscire da cicli annidati più interni.

## <a name="example"></a>Esempio

Nell'esempio riportato di seguito viene illustrato l'uso di `goto` in un'istruzione [switch](switch.md).

[!code-csharp[csrefKeywordsJump#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#4)]

## <a name="example"></a>Esempio

Nell'esempio riportato di seguito viene illustrato come usare `goto` per uscire da cicli annidati.

[!code-csharp[csrefKeywordsJump#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#5)]

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- [Guida di riferimento a C](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](index.md)
- [Istruzione goto (C++)](/cpp/cpp/goto-statement-cpp)
