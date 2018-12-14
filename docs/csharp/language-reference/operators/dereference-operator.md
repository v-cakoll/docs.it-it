---
title: -&gt; Operatore (Riferimenti per C#)
ms.date: 11/26/2018
f1_keywords:
- ->_CSharpKeyword
helpviewer_keywords:
- member access operator (->) [C#]
- -> operator [C#]
ms.assetid: e39ccdc1-f1ff-4a92-bf1d-ac2c8c11316a
ms.openlocfilehash: 178724ede105d809bd812461121a38d5a0e90517
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53144130"
---
# <a name="-gt-operator-c-reference"></a>-&gt; Operatore (Riferimenti per C#)

L'operatore di accesso ai membri del puntatore `->` combina il riferimento indiretto al puntatore con l'accesso ai membri.

Se `x` è un puntatore del tipo `T*` e `y` è un membro accessibile di `T`, un'espressione nella forma

```csharp
x->y
```

equivale a

```csharp
(*x).y
```

L'operatore `->` richiede un contesto [unsafe](../keywords/unsafe.md).

Per altre informazioni, vedere [Procedura: Accedere a un membro con un puntatore](../../programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md).

## <a name="operator-overloadability"></a>Overload degli operatori

Non è possibile sottoporre l'operatore `->` a overload.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Accesso ai membri del puntatore](~/_csharplang/spec/unsafe-code.md#pointer-member-access) della [specifica del linguaggio C#](../language-specification/index.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Operatori C#](index.md)
- [Tipi di puntatori](../../programming-guide/unsafe-code-pointers/pointer-types.md)
