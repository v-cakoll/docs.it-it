---
title: 'Procedura: Usare puntatori per copiare una matrice di byte - Guida per programmatori C#'
ms.custom: seodec18
ms.date: 04/20/2018
helpviewer_keywords:
- byte arrays [C#]
- arrays [C#], byte
- pointers [C#], to copy bytes
ms.openlocfilehash: 49151c6d2a573a24e63f733a5279faeee40de1b7
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53241126"
---
# <a name="how-to-use-pointers-to-copy-an-array-of-bytes--c-programming-guide"></a>Procedura: Usare puntatori per copiare una matrice di byte (Guida per programmatori C#)

Nell'esempio seguente vengono usati i puntatori per copiare i byte da una matrice a un'altra.

In questo esempio viene usata la parola chiave [unsafe](../../language-reference/keywords/unsafe.md), che consente l'uso di puntatori nel metodo `Copy`. Per dichiarare i puntatori nelle matrici di origine e destinazione, viene usata l'istruzione [fixed](../../language-reference/keywords/fixed-statement.md), L'istruzione `fixed` *blocca* la posizione delle matrici di origine e destinazione nella memoria in modo che non vengano rimosse da Garbage Collection. I blocchi di memoria per le matrici vengono rimossi quando il blocco `fixed` è completato. Il metodo `Copy` in questo esempio usa la parola chiave `unsafe`. Deve pertanto essere compilato con l'opzione del compilatore [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md).

L'esempio accede agli elementi di entrambe le matrici usando gli indici invece di un secondo puntatore non gestito. La dichiarazione dei puntatori `pSource` e `pTarget` blocca le matrici. Questa funzionalità è disponibile a partire da C# 7.3.

## <a name="example"></a>Esempio

[!code-csharp[Struct with embedded inline array](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#8)]

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)  
- [Codice unsafe e puntatori](index.md)  
- [-unsafe (opzioni del compilatore C#)](../../language-reference/compiler-options/unsafe-compiler-option.md)  
- [Garbage Collection](../../../standard/garbage-collection/index.md)  
