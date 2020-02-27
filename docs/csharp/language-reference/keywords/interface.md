---
title: interface - Riferimenti per C#
ms.date: 01/17/2020
f1_keywords:
- interface_CSharpKeyword
helpviewer_keywords:
- interface keyword [C#]
ms.assetid: 7da38e81-4f99-4bc5-b07d-c986b687eeba
ms.openlocfilehash: 473f5f8e226f0a144746ac943afcffdccd4777c7
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2020
ms.locfileid: "77625852"
---
# <a name="no-loc-textinterface-c-reference"></a>:::no-loc text="interface"::: (C# riferimento)

Un'interfaccia definisce un contratto. Qualsiasi [`class`](class.md) o [`struct`](../builtin-types/struct.md) che implementi il contratto deve fornire un'implementazione dei membri definiti nell'interfaccia. A partire C# da 8,0, un'interfaccia può definire un'implementazione predefinita per i membri. Può inoltre definire [`static`](static.md) membri per fornire una singola implementazione per la funzionalità comune.

Nell'esempio seguente, la classe `ImplementationClass` deve implementare un metodo denominato `SampleMethod` che è privo di parametri e restituisce `void`.

Per altre informazioni e altri esempi, vedere [Interfacce](../../programming-guide/interfaces/index.md).

## <a name="example"></a>Esempio

[!code-csharp[csrefKeywordsTypes#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#14)]

Un'interfaccia può essere un membro di uno spazio dei nomi o di una classe. Una dichiarazione di interfaccia può contenere dichiarazioni (firme senza alcuna implementazione) dei membri seguenti:

- [Metodi](../../programming-guide/classes-and-structs/methods.md)
- [Proprietà](../../programming-guide/classes-and-structs/using-properties.md)
- [Indicizzatori](../../programming-guide/indexers/using-indexers.md)
- [Eventi](event.md)

Queste dichiarazioni di membri precedenti non contengono in genere un corpo. A partire C# da 8,0, un membro di interfaccia può dichiarare un corpo. Si tratta di un' *implementazione predefinita*. I membri con corpi consentono all'interfaccia di fornire un'implementazione "predefinita" per le classi e gli struct che non forniscono un'implementazione di override. Inoltre, a partire da C# 8,0, un'interfaccia può includere:

- [Costanti](const.md)
- [Operatori](../operators/operator-overloading.md)
- [Costruttore statico](../../programming-guide/classes-and-structs/constructors.md#static-constructors).
- [Tipi annidati](../../programming-guide/classes-and-structs/nested-types.md)
- [Campi, metodi, proprietà, indicizzatori ed eventi statici](static.md)
- Dichiarazioni di membri che usano la sintassi di implementazione esplicita dell'interfaccia.
- Modificatori di accesso espliciti (l'accesso predefinito è [`public`](access-modifiers.md)).

Le interfacce non possono contenere lo stato dell'istanza. Mentre i campi statici sono ora consentiti, i campi di istanza non sono consentiti nelle interfacce. Le [proprietà automatiche dell'istanza](../../programming-guide/classes-and-structs/auto-implemented-properties.md) non sono supportate nelle interfacce perché dichiarano in modo implicito un campo nascosto. Questa regola ha un effetto lieve sulle dichiarazioni di proprietà. In una dichiarazione di interfaccia, il codice seguente non dichiara una proprietà implementata automaticamente come in un `class` o `struct`. Dichiara invece una proprietà che non dispone di un'implementazione predefinita, ma che deve essere implementata in qualsiasi tipo che implementi l'interfaccia:

```csharp
public interface INamed
{
  public string Name {get; set;}
}
```

Un'interfaccia può ereditare da una o più interfacce di base. Quando un'interfaccia [esegue l'override di un metodo](override.md) implementato in un'interfaccia di base, deve usare la sintassi di [implementazione esplicita dell'interfaccia](../../programming-guide/interfaces/explicit-interface-implementation.md) .

Quando un elenco di tipi di base contiene interfacce e una classe di base, la classe di base deve precedere le interfacce.

Una classe che implementa un'interfaccia può implementare in modo esplicito i membri di tale interfaccia. Non è possibile accedere a un membro implementato in modo esplicito tramite un'istanza di classe, ma solo tramite un'istanza dell'interfaccia. Inoltre, è possibile accedere ai membri di interfaccia predefiniti solo tramite un'istanza dell'interfaccia.

Per altre informazioni sull'implementazione esplicita dell'interfaccia, vedere [implementazione esplicita dell'interfaccia](../../programming-guide/interfaces/explicit-interface-implementation.md).

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrata un'implementazione dell'interfaccia. In questo esempio l'interfaccia contiene la dichiarazione di proprietà e la classe contiene l'implementazione. Qualsiasi istanza di una classe che implementa `IPoint` presenta proprietà `x` e `y` di tipo Integer.

[!code-csharp[csrefKeywordsTypes#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#15)]

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per ulteriori informazioni, vedere la sezione [interfacce](~/_csharplang/spec/interfaces.md) della [ C# specifica del linguaggio](~/_csharplang/spec/introduction.md) e la specifica della funzionalità per [i membri di C# interfaccia predefiniti-8,0](~/_csharplang/proposals/csharp-8.0/default-interface-methods.md)

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](index.md)
- [Tipi di riferimento](reference-types.md)
- [Interfacce](../../programming-guide/interfaces/index.md)
- [Uso delle proprietà](../../programming-guide/classes-and-structs/using-properties.md)
- [Uso degli indicizzatori](../../programming-guide/indexers/using-indexers.md)
- [Interfacce](../../programming-guide/interfaces/index.md)
