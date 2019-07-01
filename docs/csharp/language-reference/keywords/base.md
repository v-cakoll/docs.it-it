---
title: Parola chiave base - Riferimenti per C#
ms.custom: seodec18
description: Informazioni sulla parola chiave base, usata per accedere ai membri della classe di base dall'interno di una classe derivata in C#.
ms.date: 07/20/2015
f1_keywords:
- base
- BaseClass.BaseClass
- base_CSharpKeyword
helpviewer_keywords:
- base keyword [C#]
ms.assetid: 8b645dbe-1a33-49b8-8716-1c401f9a5ea5
ms.openlocfilehash: 2ef0d07aed595fa630459171482e0b0849aed877
ms.sourcegitcommit: bab17fd81bab7886449217356084bf4881d6e7c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2019
ms.locfileid: "67401590"
---
# <a name="base-c-reference"></a>base (Riferimenti per C#)

La parola chiave `base` viene usata per accedere ai membri della classe di base dall'interno di una classe derivata:

- Chiamare un metodo sulla classe di base che è stato sostituito da un altro metodo.

- Specificare quale costruttore di classe di base deve essere chiamato durante la creazione di istanze della classe derivata.

Una classe di base di accesso è consentita solo in un costruttore, in un metodo di istanza o in una funzione di accesso alla proprietà dell'istanza.

Non è possibile usare la parola chiave `base` dall'interno di un metodo statico.

La classe di base alla quale si accede è la classe di base specificata nella dichiarazione di classe. Ad esempio, se si specifica `class ClassB : ClassA`, i membri di ClassA sono accessibili da ClassB, indipendentemente dalla classe di base di ClassA.

## <a name="example"></a>Esempio

In questo esempio, la classe di base `Person` e la classe derivata `Employee` hanno un metodo denominato `Getinfo`. Tramite la parola chiave `base` è possibile chiamare il meotod `Getinfo` sulla classe di base, dall'interno della classe derivata.

[!code-csharp[csrefKeywordsAccess#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#1)]

Per altri esempi, vedere [new](new-modifier.md), [virtual](virtual.md) e [override](override.md).

## <a name="example"></a>Esempio

Questo esempio illustra come specificare il costruttore della classe di base chiamato durante la creazione di istanze di una classe derivata.

[!code-csharp[csrefKeywordsAccess#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#2)]

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../../../csharp/language-reference/index.md)
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)
- [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)
- [this](../../../csharp/language-reference/keywords/this.md)
