---
title: Override
ms.date: 07/20/2015
f1_keywords:
- Overrides
- vb.Overrides
helpviewer_keywords:
- properties [Visual Basic], redefining
- procedures [Visual Basic], overriding
- procedures [Visual Basic], redefining
- overriding
- Overrides keyword [Visual Basic]
- overriding, Overrides keyword
- properties [Visual Basic], overriding
ms.assetid: 9f5e6144-ce10-465e-842b-1a8f8760af90
ms.openlocfilehash: 657f838b2959a5b6a7cef5ff18295a4ada709e9a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392028"
---
# <a name="overrides-visual-basic"></a>Overrides (Visual Basic)

Specifica che una proprietà o una routine esegue l'override di una proprietà o una routine con nome identico ereditata da una classe base.

## <a name="rules"></a>Regole

- **Contesto della dichiarazione. ** È possibile utilizzare `Overrides` solo in un'istruzione di dichiarazione di proprietà o di routine.

- **Modificatori combinati.** Non è possibile specificare `Overrides` insieme a `Shadows` o `Shared` nella stessa dichiarazione. Poiché un elemento che esegue l'override può essere implicitamente sottoposto a override, non è possibile combinare `Overridable` e `Overrides`.

- **Firme corrispondenti.** La firma di questa dichiarazione deve corrispondere esattamente alla *firma* della proprietà o della routine sottoposta a override. In altre parole, gli elenchi di parametri devono presentare lo stesso numero di parametri, nel medesimo ordine, e contenere gli stessi tipi di dati.

  Oltre alla firma, la dichiarazione che esegue l'override deve anche corrispondere esattamente a quanto segue.

  - Livello di accesso

  - Tipo restituito, se disponibile

- **Firme generiche.** Nel caso di una routine generica la firma include il numero di parametri del tipo. La dichiarazione che esegue l'override, quindi, deve corrispondere alla versione della classe base anche in relazione a tali caratteristiche.

- **Corrispondenze aggiuntive.** Oltre a corrispondere alla firma della versione della classe base, la dichiarazione deve presentare anche le corrispondenze seguenti:

  - Modificatore a livello di accesso (ad esempio [public](public.md))

  - Passaggio del meccanismo di ogni parametro ([ByVal](byval.md) o [ByRef](byref.md))

  - Elenchi di vincoli su ogni parametro di tipo di una routine generica

- **Shadowing e override.** Sebbene lo shadowing e l'override ridefiniscano entrambi un elemento ereditato, tra i due metodi esistono differenze sostanziali. Per ulteriori informazioni, vedere [shadowing in Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).

Se si usa `Overrides`, il compilatore aggiunge implicitamente `Overloads` in modo che le API della libreria funzionino più facilmente con C#.

Il modificatore `Overrides` può essere usato nei contesti seguenti:

- [Istruzione Function](../statements/function-statement.md)

- [Property Statement](../statements/property-statement.md)

- [Istruzione Sub](../statements/sub-statement.md)

## <a name="see-also"></a>Vedere anche

- [MustOverride](mustoverride.md)
- [NotOverridable](notoverridable.md)
- [Overridable](overridable.md)
- [Parole chiave](../keywords/index.md)
- [Shadowing in Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md)
- [Generic Types in Visual Basic](../../programming-guide/language-features/data-types/generic-types.md)
- [Type List](../statements/type-list.md)
