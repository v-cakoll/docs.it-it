---
title: Istruzione break (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- break
- break_CSharpKeyword
helpviewer_keywords:
- break keyword [C#]
ms.assetid: be2571ed-efb0-4965-b122-81e5b09db0b9
ms.openlocfilehash: 9dc71cce3cc0ca4035df483d2b3a3ab9a3bab9c5
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2018
ms.locfileid: "47215847"
---
# <a name="break-c-reference"></a>break (Riferimenti per C#)

L'istruzione `break` termina il ciclo di inclusione più vicino o l'istruzione [switch](../../../csharp/language-reference/keywords/switch.md) in cui appare. Il controllo viene passato all'istruzione che segue l'istruzione terminata, se presente.

## <a name="example"></a>Esempio

In questo esempio, l'istruzione condizionale contiene un contatore che dovrebbe contare da 1 a 100. L'istruzione `break` tuttavia termina il ciclo dopo 4 conteggi.

[!code-csharp[csrefKeywordsJump#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#1)]

## <a name="example"></a>Esempio

In questo esempio, l'istruzione `break` viene usata per interrompere un ciclo annidato interno e restituire il controllo al ciclo esterno.

[!code-csharp[csrefKeywordsJump#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#7)]

## <a name="example"></a>Esempio

Questo esempio illustra l'uso di `break` in un'istruzione [switch](../../../csharp/language-reference/keywords/switch.md).

[!code-csharp[csrefKeywordsJump#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#2)]

Se è stato immesso `4`, l'output dovrebbe essere simile al seguente:

```console
Enter your selection (1, 2, or 3): 4
Sorry, invalid selection.
```

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../../../csharp/language-reference/index.md)  
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
- [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)  
- [switch](../../../csharp/language-reference/keywords/switch.md)  
- [Istruzioni di spostamento](../../../csharp/language-reference/keywords/jump-statements.md)  
- [Istruzioni di iterazione](../../../csharp/language-reference/keywords/iteration-statements.md)
