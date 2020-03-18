---
title: Parola chiave protected - Riferimenti per C#
ms.date: 07/20/2015
f1_keywords:
- protected
- protected_CSharpKeyword
helpviewer_keywords:
- protected keyword [C#]
ms.assetid: 05ce3794-6675-4025-bddb-eaaa0ec22892
ms.openlocfilehash: bec619d4f49bd26daa742c18c830909c14948adf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713183"
---
# <a name="protected-c-reference"></a>protected (Riferimenti per C#)

La parola chiave `protected` è un modificatore di accesso ai membri.

 > Questa pagina illustra l'accesso `protected`. La `protected` parola chiave fa [`protected internal`](protected-internal.md) [`private protected`](private-protected.md) anche parte dei modificatori di accesso e .

Un membro protetto è accessibile all'interno della classe di appartenenza e dalle istanze della classe derivata.

Per un confronto di `protected` con altri modificatori di accesso, vedere [Livelli di accessibilità](accessibility-levels.md).

## <a name="example"></a>Esempio

Un membro protetto di una classe di base è accessibile in una classe derivata solo se viene eseguito l'accesso tramite il tipo di classe derivata. Si consideri il segmento di codice di esempio seguente:

[!code-csharp[csrefKeywordsModifiers#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#11)]

L'istruzione `a.x = 10` genera un errore perché usata all'interno del metodo statico Main e non in un'istanza della classe B.

I membri struct non possono essere protetti perché struct non può essere ereditato.

## <a name="example"></a>Esempio

In questo esempio la classe `DerivedPoint` è derivata da `Point`. Pertanto, è possibile accedere i membri protetti della classe di base direttamente dalla classe derivata.

[!code-csharp[csrefKeywordsModifiers#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#12)]  

Se si impostano i livelli di accesso di `x` e `y` su [privato](private.md), il compilatore genererà i messaggi di errore seguenti:

`'Point.y' is inaccessible due to its protection level.`

`'Point.x' is inaccessible due to its protection level.`

## <a name="c-language-specification"></a>Specifiche del linguaggio C#  

Per altre informazioni, vedere [Accessibilità dichiarata](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in [Specifica del linguaggio C#](/dotnet/csharp/language-reference/language-specification/introduction). La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.

## <a name="see-also"></a>Vedere anche

- [Guida di riferimento a C](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](index.md)
- [Modificatori di accesso](access-modifiers.md)
- [Livelli di accessibilità](accessibility-levels.md)
- [Modificatori](index.md)
- [pubblico](public.md)
- [Privato](private.md)
- [Interno](internal.md)
- [Problemi di sicurezza per le parole chiave virtuali interne](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))
