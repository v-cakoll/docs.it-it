---
title: Istruzione break - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- break
- break_CSharpKeyword
helpviewer_keywords:
- break keyword [C#]
ms.assetid: be2571ed-efb0-4965-b122-81e5b09db0b9
ms.openlocfilehash: 2628da73364cf94a52e2862d349243c100d4afaf
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2019
ms.locfileid: "72179926"
---
# <a name="break-c-reference"></a>break (Riferimenti per C#)

L'istruzione `break` termina il ciclo di inclusione più vicino o l'istruzione [switch](./switch.md) in cui appare. Il controllo viene passato all'istruzione che segue l'istruzione terminata, se presente.

## <a name="example"></a>Esempio

In questo esempio, l'istruzione condizionale contiene un contatore che dovrebbe contare da 1 a 100. L'istruzione `break` tuttavia termina il ciclo dopo 4 conteggi.

[!code-csharp[csrefKeywordsJump#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#1)]

## <a name="example"></a>Esempio

Questo esempio illustra l'uso di `break` in un'istruzione [switch](./switch.md).

[!code-csharp[csrefKeywordsJump#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#2)]

Se è stato immesso `4`, l'output dovrebbe essere simile al seguente:

```console
Enter your selection (1, 2, or 3): 4
Sorry, invalid selection.
```

## <a name="example"></a>Esempio

In questo esempio, l'istruzione `break` viene usata per interrompere un ciclo annidato interno e restituire il controllo al ciclo esterno. Il controllo viene restituito _solo_ un livello verso l'alto nei cicli nidificati.

[!code-csharp[csrefKeywordsJump#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#7)]

## <a name="example"></a>Esempio

In questo esempio, l'istruzione `break` viene utilizzata solo per interrompere il ramo corrente durante ogni iterazione del ciclo. Il ciclo stesso non è influenzato dalle istanze di `break` che appartengono all'istruzione [Switch](./switch.md) nidificata.

[!code-csharp[csrefKeywordsJump#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#8)]

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](./index.md)
- [switch](./switch.md)
