---
title: '- Operatore - - Riferimenti per C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- -_CSharpKeyword
helpviewer_keywords:
- '- operator [C#]'
- subtraction operator (-) [C#]
ms.assetid: 4de7a4fa-c69d-48e6-aff1-3130af970b2d
ms.openlocfilehash: 8cf6e8871a88e2b37b9531ecbd616289523473c7
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333759"
---
# <a name="--operator-c-reference"></a>Operatore - (Riferimenti per C#)

L'operatore `-` ha la funzione di operatore unario o binario.

## <a name="remarks"></a>Note

Gli operatori `-` unari sono predefiniti per tutti i tipi numerici. Il risultato di un'operazione `-` unaria su un tipo numerico corrisponde alla negazione numerica dell'operando.

Gli operatori `-` binari sono predefiniti per tutti i tipi numerici e di enumerazione per sottrarre il secondo operando dal primo.

I tipi delegati offrono anche un operatore `-` binario, che esegue la rimozione dei delegati.

I tipi definiti dall'utente possono eseguire l'overload degli operatori `-` unari e `-` binari. Per altre informazioni, vedere [Parola chiave operator](../keywords/operator.md).

## <a name="example"></a>Esempio

[!code-csharp[csRefOperators#40](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#40)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Operatori C#](index.md)