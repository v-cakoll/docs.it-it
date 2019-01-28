---
title: Operatore ^ - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ^_CSharpKeyword
helpviewer_keywords:
- ^ operator [C#]
- bitwise exclusive OR operator [C#]
ms.assetid: b09bc815-570f-4db6-a637-5b4ed99d014a
ms.openlocfilehash: 16419342fec9d6c9845e19e434787c5e4f5a5b12
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54632250"
---
# <a name="-operator-c-reference"></a>Operatore ^ (Riferimenti per C#)

Gli operatori `^` binari sono predefiniti per i tipi integrali e `bool`. Per i tipi integrali, `^` calcola l'operazione di OR esclusivo bit per bit dei relativi operandi. Per gli operandi `bool`, `^` calcola l'operazione di OR esclusivo logico dei relativi operandi, ovvero, il risultato è `true` se e solo se esattamente uno degli operandi è `true`.

## <a name="remarks"></a>Note

I tipi definiti dall'utente possono eseguire l'overload dell'operatore `^` (vedere [operatore](../keywords/operator.md)). Le operazioni sui tipi integrali sono generalmente consentite sull'enumerazione.

## <a name="example"></a>Esempio

[!code-csharp[csRefOperators#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#30)]

Il calcolo di `0xf8 ^ 0x3f` nell'esempio precedente esegue un'operazione di OR esclusivo bit per bit dei due valori binari seguenti, che corrispondono ai valori esadecimali F8 e 3F:

`1111 1000`

`0011 1111`

Il risultato dell'operazione di OR esclusivo è `1100 0111`, ovvero C7 in formato esadecimale.

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Operatori C#](index.md)
