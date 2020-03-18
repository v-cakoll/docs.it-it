---
title: interface - Riferimenti per C#
ms.date: 01/17/2020
f1_keywords:
- interface_CSharpKeyword
helpviewer_keywords:
- interface keyword [C#]
ms.assetid: 7da38e81-4f99-4bc5-b07d-c986b687eeba
ms.openlocfilehash: 473f5f8e226f0a144746ac943afcffdccd4777c7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77625852"
---
# <a name="no-loc-textinterface-c-reference"></a>:::no-loc text="interface":::(Riferimenti per C

Un'interfaccia definisce un contratto. Qualsiasi [`class`](class.md) [`struct`](../builtin-types/struct.md) o che implementa tale contratto deve fornire un'implementazione dei membri definiti nell'interfaccia. A partire dalla versione 8.0 di C, un'interfaccia può definire un'implementazione predefinita per i membri. Può anche [`static`](static.md) definire membri per fornire una singola implementazione per le funzionalità comuni.

Nell'esempio seguente, la classe `ImplementationClass` deve implementare un metodo denominato `SampleMethod` che è privo di parametri e restituisce `void`.

Per altre informazioni e altri esempi, vedere [Interfacce](../../programming-guide/interfaces/index.md).

## <a name="example"></a>Esempio

[!code-csharp[csrefKeywordsTypes#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#14)]

Un'interfaccia può essere un membro di uno spazio dei nomi o di una classe. Una dichiarazione di interfaccia può contenere dichiarazioni (firme senza alcuna implementazione) dei membri seguenti:An interface declaration can contain declarations (signatures without any implementation) of the following members:

- [Metodi](../../programming-guide/classes-and-structs/methods.md)
- [Proprietà](../../programming-guide/classes-and-structs/using-properties.md)
- [Indicizzatori](../../programming-guide/indexers/using-indexers.md)
- [Events](event.md)

Queste dichiarazioni di membro precedenti in genere non contengono un corpo. A partire dalla versione 8.0 di C, un membro di interfaccia può dichiarare un corpo. Questa operazione è denominata *implementazione predefinita*. I membri con corpi consentono all'interfaccia di fornire un'implementazione "predefinita" per classi e struct che non forniscono un'implementazione di override. Inoltre, a partire da C , 8.0, un'interfaccia può includere:In addition, beginning with C's 8.0, an interface may include:

- [Costanti](const.md)
- [Operatori](../operators/operator-overloading.md)
- [Costruttore statico](../../programming-guide/classes-and-structs/constructors.md#static-constructors).
- [Tipi annidati](../../programming-guide/classes-and-structs/nested-types.md)
- [Campi, metodi, proprietà, indicizzatori ed eventi statici](static.md)
- Dichiarazioni di membri utilizzando la sintassi di implementazione esplicita dell'interfaccia.
- Modificatori di accesso espliciti [`public`](access-modifiers.md)(l'accesso predefinito è ).

Le interfacce non possono contenere lo stato dell'istanza. Sebbene i campi statici siano ora consentiti, i campi di istanza non sono consentiti nelle interfacce. [Le proprietà automatiche dell'istanza](../../programming-guide/classes-and-structs/auto-implemented-properties.md) non sono supportate nelle interfacce, in quanto dichiarano in modo implicito un campo nascosto. Questa regola ha un effetto sottile sulle dichiarazioni di proprietà. In una dichiarazione di interfaccia, il codice seguente non dichiara `class` `struct`una proprietà implementata automaticamente come in un oggetto o . Al contrario, dichiara una proprietà che non dispone di un'implementazione predefinita, ma deve essere implementata in qualsiasi tipo che implementa l'interfaccia:Instead, it declares a property that doesn't have a default implementation but must be implemented in any type that implements the interface:

```csharp
public interface INamed
{
  public string Name {get; set;}
}
```

Un'interfaccia può ereditare da una o più interfacce di base. Quando un'interfaccia [esegue l'override](override.md) di un metodo implementato in un'interfaccia di base, deve utilizzare la sintassi di implementazione esplicita [dell'interfaccia.](../../programming-guide/interfaces/explicit-interface-implementation.md)

Quando un elenco di tipi di base contiene interfacce e una classe di base, la classe di base deve precedere le interfacce.

Una classe che implementa un'interfaccia può implementare in modo esplicito i membri di tale interfaccia. Non è possibile accedere a un membro implementato in modo esplicito tramite un'istanza di classe, ma solo tramite un'istanza dell'interfaccia. Inoltre, è possibile accedere ai membri di interfaccia predefiniti solo tramite un'istanza dell'interfaccia.

Per ulteriori informazioni sull'implementazione esplicita dell'interfaccia, vedere [Implementazione esplicita dell'interfaccia](../../programming-guide/interfaces/explicit-interface-implementation.md).

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrata un'implementazione dell'interfaccia. In questo esempio l'interfaccia contiene la dichiarazione di proprietà e la classe contiene l'implementazione. Qualsiasi istanza di una classe che implementa `IPoint` presenta proprietà `x` e `y` di tipo Integer.

[!code-csharp[csrefKeywordsTypes#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#15)]

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Interfaces](~/_csharplang/spec/interfaces.md) della specifica del [linguaggio C'](~/_csharplang/spec/introduction.md) e la specifica della funzionalità per i [membri dell'interfaccia predefinita - C](~/_csharplang/proposals/csharp-8.0/default-interface-methods.md)

## <a name="see-also"></a>Vedere anche

- [Guida di riferimento a C](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](index.md)
- [Tipi di riferimento](reference-types.md)
- [Interfacce](../../programming-guide/interfaces/index.md)
- [Utilizzo delle proprietà](../../programming-guide/classes-and-structs/using-properties.md)
- [Uso degli indicizzatori](../../programming-guide/indexers/using-indexers.md)
- [Interfacce](../../programming-guide/interfaces/index.md)
