---
title: Come usare i puntatori per copiare una matrice di byte (Guida per programmatori C#)
ms.date: 04/20/2018
helpviewer_keywords:
- byte arrays [C#]
- arrays [C#], byte
- pointers [C#], to copy bytes
ms.openlocfilehash: 8c1afc06fb567a923d604ad53dc26f94178a8d60
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397415"
---
# <a name="how-to-use-pointers-to-copy-an-array-of-bytes-c-programming-guide"></a>Come usare i puntatori per copiare una matrice di byte (Guida per programmatori C#)

Nell'esempio seguente vengono usati i puntatori per copiare i byte da una matrice a un'altra.

In questo esempio viene usata la parola chiave [unsafe](../../language-reference/keywords/unsafe.md), che consente l'uso di puntatori nel metodo `Copy`. Per dichiarare i puntatori nelle matrici di origine e destinazione, viene usata l'istruzione [fixed](../../language-reference/keywords/fixed-statement.md), L'istruzione `fixed`*blocca* la posizione delle matrici di origine e destinazione nella memoria in modo che non vengano rimosse da Garbage Collection. I blocchi di memoria per le matrici vengono rimossi quando il blocco `fixed` è completato. Il metodo `Copy` in questo esempio usa la parola chiave `unsafe`. Deve pertanto essere compilato con l'opzione del compilatore [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md).

L'esempio accede agli elementi di entrambe le matrici usando gli indici invece di un secondo puntatore non gestito. La dichiarazione dei puntatori `pSource` e `pTarget` blocca le matrici. Questa funzionalità è disponibile a partire da C# 7.3.

## <a name="example"></a>Esempio

[!code-csharp[Struct with embedded inline array](snippets/FixedKeywordExamples.cs#8)]

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Codice unsafe e puntatori](index.md)
- [-unsafe (opzioni del compilatore C#)](../../language-reference/compiler-options/unsafe-compiler-option.md)
- [Garbage Collection](../../../standard/garbage-collection/index.md)
