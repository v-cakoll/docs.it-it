---
title: void - Riferimenti per C#
ms.date: 07/20/2015
f1_keywords:
- void_CSharpKeyword
- void
helpviewer_keywords:
- void keyword [C#]
ms.assetid: 0d2d8a95-fe20-4fbd-bf5d-c1e54bce71d4
ms.openlocfilehash: 465aaeadca603f14432478a7e5496a9ef4589ebe
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712858"
---
# <a name="void-c-reference"></a>void (Riferimenti per C#)

Quando viene usato come tipo restituito per un metodo `void` specifica che il metodo non restituisce un valore.

L'uso di `void` non è consentito nell'elenco di parametri di un metodo. Un metodo che non accetta parametri e non restituisce alcun valore viene dichiarato come segue:

```csharp
public void SampleMethod()
{
    // Body of the method.
}
```

`void` si usa inoltre in un contesto unsafe per dichiarare un puntatore a un tipo sconosciuto. Per altre informazioni, vedere [Tipi di puntatori](../../programming-guide/unsafe-code-pointers/pointer-types.md).

`void` è un alias per il tipo <xref:System.Void?displayProperty=nameWithType> di .NET Framework.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](index.md)
- [Tipi riferimento](reference-types.md)
- [Tipi valore](value-types.md)
- [Metodi](../../programming-guide/classes-and-structs/methods.md)
- [Codice unsafe e puntatori](../../programming-guide/unsafe-code-pointers/index.md)
