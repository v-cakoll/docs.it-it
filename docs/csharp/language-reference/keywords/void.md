---
title: void - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- void_CSharpKeyword
- void
helpviewer_keywords:
- void keyword [C#]
ms.assetid: 0d2d8a95-fe20-4fbd-bf5d-c1e54bce71d4
ms.openlocfilehash: 87ccc3a18f0956ffe800ae97598e621e5ca72480
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53238377"
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

`void` si usa inoltre in un contesto unsafe per dichiarare un puntatore a un tipo sconosciuto. Per altre informazioni, vedere [Tipi di puntatori](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).

`void` è un alias per il tipo <xref:System.Void?displayProperty=nameWithType> di .NET Framework.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../../../csharp/language-reference/index.md)  
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
- [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)  
- [Tipi riferimento](../../../csharp/language-reference/keywords/reference-types.md)  
- [Tipi valore](../../../csharp/language-reference/keywords/value-types.md)  
- [Metodi](../../../csharp/programming-guide/classes-and-structs/methods.md)  
- [Codice unsafe e puntatori](../../../csharp/programming-guide/unsafe-code-pointers/index.md)
