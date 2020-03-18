---
title: Modificatore sealed - Riferimenti per C#
ms.date: 07/20/2015
f1_keywords:
- sealed
- sealed_CSharpKeyword
helpviewer_keywords:
- sealed keyword [C#]
ms.assetid: 8e4ed5d3-10be-47db-9488-0da2008e6f3f
ms.openlocfilehash: 686afd5d9d0394bb1a802551b65083732599f384
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713105"
---
# <a name="sealed-c-reference"></a>sealed (Riferimenti per C#)

Quando applicato a una classe, il modificatore `sealed` impedisce che altre classi ereditino da esso. Nell'esempio seguente, la classe `B` eredita dalla classe `A`, ma nessuna classe può ereditare dalla classe `B`.

```csharp
class A {}
sealed class B : A {}
```

È anche possibile usare il modificatore `sealed` su un metodo o su una proprietà che esegue l'override di un metodo o di una proprietà virtuale in una classe di base. In questo modo è possibile consentire alle classi di derivare dalla classe e impedire l'override di proprietà o metodi virtuali specifici.

## <a name="example"></a>Esempio

Nell'esempio seguente, `Z` eredita da `Y` ma `Z` non può eseguire l'override della funzione virtuale `F` dichiarata in `X` e bloccata in `Y`.

[!code-csharp[csrefKeywordsModifiers#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#16)]

Quando si definiscono nuovi metodi o proprietà in una classe, è possibile impedire alle classi derivate di eseguire l'override non dichiarandole come [virtuali](virtual.md).

È un errore usare il modificatore [abstract](abstract.md) con una classe sealed, poiché la classe astratta deve essere ereditata da una classe che fornisce un'implementazione dei metodi o delle proprietà astratti.

Quando applicato a un metodo o a una proprietà, il modificatore `sealed` deve sempre essere usato con [override](override.md).

Poiché gli struct sono sealed in modo implicito, non possono essere ereditati.

Per altre informazioni, vedere [Ereditarietà](../../programming-guide/classes-and-structs/inheritance.md).

Per altri esempi, vedere [Classi e membri delle classi astratte e sealed](../../programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).

## <a name="example"></a>Esempio

[!code-csharp[csrefKeywordsModifiers#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#17)]

Nell'esempio precedente è possibile ereditare dalla classe sealed tramite l'istruzione seguente:

`class MyDerivedC: SealedClass {}   // Error`

Il risultato è un messaggio di errore:

`'MyDerivedC': cannot derive from sealed type 'SealedClass'`

## <a name="remarks"></a>Osservazioni

Per determinare se bloccare una classe, proprietà o metodo, è consigliabile in genere considerare i due punti seguenti:

- I potenziali vantaggi di cui le classi derivate possono usufruire grazie alla possibilità di personalizzare la classe.

- La possibilità che le classi derivate possono modificare le classi in uso in modo tale che non funzionino più correttamente o come previsto.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- [Guida di riferimento a C](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](index.md)
- [Classi statiche e membri di classi statiche](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md)
- [Classi e membri delle classi astratte e sealed](../../programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)
- [Modificatori di accesso](../../programming-guide/classes-and-structs/access-modifiers.md)
- [Modificatori](index.md)
- [prevalere](override.md)
- [Virtuale](virtual.md)
