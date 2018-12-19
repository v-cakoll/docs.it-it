---
title: interface - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- interface_CSharpKeyword
helpviewer_keywords:
- interface keyword [C#]
ms.assetid: 7da38e81-4f99-4bc5-b07d-c986b687eeba
ms.openlocfilehash: 2cb3121907b50d8151257739de0b66fcb597f364
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237896"
---
# <a name="interface-c-reference"></a>interface (Riferimenti per C#)

Un'interfaccia contiene solo le firme di [metodi](../../programming-guide/classes-and-structs/methods.md), [proprietà](../../programming-guide/classes-and-structs/properties.md), [eventi](../../programming-guide/events/index.md) o [indicizzatori](../../programming-guide/indexers/index.md). Una classe o uno struct che implementa l'interfaccia deve implementarne i membri specificati nella definizione dell'interfaccia stessa. Nell'esempio seguente, la classe `ImplementationClass` deve implementare un metodo denominato `SampleMethod` che è privo di parametri e restituisce `void`.

Per altre informazioni e altri esempi, vedere [Interfacce](../../programming-guide/interfaces/index.md).

## <a name="example"></a>Esempio

[!code-csharp[csrefKeywordsTypes#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#14)]

Un'interfaccia può essere membro di uno spazio dei nomi o di una classe e contenere firme dei seguenti membri:

- [Metodi](../../programming-guide/classes-and-structs/methods.md)

- [Proprietà](../../programming-guide/classes-and-structs/using-properties.md)

- [Indicizzatori](../../programming-guide/indexers/using-indexers.md)

- [Eventi](event.md)

Un'interfaccia può ereditare da una o più interfacce di base.

Quando un elenco di tipi di base contiene interfacce e una classe di base, la classe di base deve precedere le interfacce.

Una classe che implementa un'interfaccia può implementare in modo esplicito i membri di tale interfaccia. Non è possibile accedere a un membro implementato in modo esplicito tramite un'istanza di classe, ma solo tramite un'istanza dell'interfaccia.

Per altri dettagli e altri esempi di codice sull'implementazione esplicita delle interfacce, vedere [Implementazione esplicita dell'interfaccia](../../programming-guide/interfaces/explicit-interface-implementation.md).

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrata un'implementazione dell'interfaccia. In questo esempio l'interfaccia contiene la dichiarazione di proprietà e la classe contiene l'implementazione. Qualsiasi istanza di una classe che implementa `IPoint` presenta proprietà `x` e `y` di tipo Integer.

[!code-csharp[csrefKeywordsTypes#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#15)]

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../../../csharp/language-reference/index.md)  
- [Guida per programmatori C#](../../programming-guide/index.md)  
- [Parole chiave di C#](index.md)  
- [Tipi riferimento](reference-types.md)  
- [Interfacce](../../programming-guide/interfaces/index.md)  
- [Uso delle proprietà](../../programming-guide/classes-and-structs/using-properties.md)  
- [Uso degli indicizzatori](../../programming-guide/indexers/using-indexers.md)  
- [class](class.md)  
- [struct](struct.md)  
- [Interfacce](../../programming-guide/interfaces/index.md)
