---
title: Interfacce - Guida per programmatori C#
ms.date: 02/20/2020
helpviewer_keywords:
- interfaces [C#]
- C# language, interfaces
ms.assetid: 2feda177-ce11-432d-81b4-d50f5f35fd37
ms.openlocfilehash: 50f2c5fc3570b6d66ed83206660caf4bd02f1f5b
ms.sourcegitcommit: 2543a78be6e246aa010a01decf58889de53d1636
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/17/2020
ms.locfileid: "86441336"
---
# <a name="interfaces-c-programming-guide"></a>Interfacce (Guida per programmatori C#)

Un'interfaccia contiene le definizioni per un gruppo di funzionalità correlate che devono essere implementate da una [classe](../../language-reference/keywords/class.md) non astratta o da uno [struct](../../language-reference/builtin-types/struct.md) . Un'interfaccia può definire `static` metodi, che devono disporre di un'implementazione di. A partire da C# 8,0, un'interfaccia può definire un'implementazione predefinita per i membri. Un'interfaccia non può dichiarare i dati dell'istanza, ad esempio i campi, le proprietà implementate automaticamente o gli eventi di tipo proprietà.

Usando le interfacce, è possibile, ad esempio, includere il comportamento di più origini in una classe. Tale funzionalità è importante in C# perché il linguaggio non supporta l'ereditarietà multipla delle classi. Inoltre è necessario usare un'interfaccia se si vuole simulare l'ereditarietà per le struct, perché non possono effettivamente ereditare da un'altra struct o classe.

Per definire un'interfaccia, è possibile usare la parola chiave [Interface](../../language-reference/keywords/interface.md) , come illustrato nell'esempio seguente.

[!code-csharp[Equatable](~/samples/snippets/csharp/objectoriented/interfaces.cs#Equatable)]

Il nome di un'interfaccia deve essere un nome di [identificatore](../inside-a-program/identifier-names.md)C# valido. Per convenzione, i nomi di interfaccia iniziano con una lettera `I` maiuscola.

Qualsiasi classe o struct che implementa l'interfaccia <xref:System.IEquatable%601> deve contenere una definizione per un metodo <xref:System.IEquatable%601.Equals%2A> che corrisponde alla firma specificata dall'interfaccia. Di conseguenza, è possibile affidarsi a una classe che implementa `IEquatable<T>` per contenere un metodo `Equals` con cui un'istanza della classe può determinare se sia uguale a un'altra istanza della stessa classe.

La definizione di `IEquatable<T>` non fornisce un'implementazione per `Equals` . Una classe o uno struct può implementare più interfacce, ma una classe può ereditare solo da una singola classe.

Per altre informazioni sulle classi astratte, vedere [Classi e membri delle classi astratte e sealed](../classes-and-structs/abstract-and-sealed-classes-and-class-members.md).

Le interfacce possono contenere metodi di istanza, proprietà, eventi, indicizzatori o qualsiasi combinazione di questi quattro tipi di membri. Le interfacce possono contenere costruttori statici, campi, costanti o operatori. Per collegamenti a esempi, vedere [Sezioni correlate](./index.md#BKMK_RelatedSections). Un'interfaccia non può contenere campi di istanza, costruttori di istanza o finalizzatori. I membri di interfaccia sono public per impostazione predefinita.

Per implementare un membro di interfaccia, il corrispondente membro della classe di implementazione deve essere pubblico e non statico e avere lo stesso nome e la stessa firma del membro di interfaccia.

Quando una classe o uno struct implementa un'interfaccia, la classe o lo struct deve fornire un'implementazione per tutti i membri dichiarati dall'interfaccia, ma non fornisce un'implementazione predefinita per. Tuttavia, se una classe base implementa un'interfaccia, qualsiasi classe derivata dalla classe base eredita tale implementazione.

Nell'esempio seguente viene illustrata un'implementazione dell'interfaccia <xref:System.IEquatable%601>. La classe di implementazione, `Car`, deve fornire un'implementazione del metodo <xref:System.IEquatable%601.Equals%2A>.

[!code-csharp[ImplementEquatable](~/samples/snippets/csharp/objectoriented/interfaces.cs#ImplementEquatable)]

Le proprietà e gli indicizzatori di una classe possono definire altre funzioni di accesso per una proprietà o un indicizzatore definito in un'interfaccia. Ad esempio, un'interfaccia può dichiarare una proprietà con una funzione di accesso [get](../../language-reference/keywords/get.md). La classe che implementa l'interfaccia può dichiarare la stessa proprietà con una funzione di accesso `get` o [set](../../language-reference/keywords/set.md). Tuttavia, se la proprietà o l'indicizzatore usa l'implementazione esplicita, le funzioni di accesso devono corrispondere. Per altre informazioni sull'implementazione esplicita, vedere [Implementazione esplicita dell'interfaccia](explicit-interface-implementation.md) e [Proprietà dell'interfaccia](../classes-and-structs/interface-properties.md).

Le interfacce possono ereditare da una o più interfacce. L'interfaccia derivata eredita i membri dalle relative interfacce di base. Una classe che implementa un'interfaccia derivata deve implementare tutti i membri nell'interfaccia derivata, inclusi tutti i membri delle interfacce di base dell'interfaccia derivata. Tale classe può essere convertita in modo implicito nell'interfaccia derivata o in una delle interfacce di base. Una classe può includere un'interfaccia più volte tramite le classi di base ereditate o tramite le interfacce ereditate da altre interfacce. Tuttavia, la classe può fornire un'implementazione di un'interfaccia solo una volta e solo se la classe dichiara l'interfaccia durante la definizione della classe (`class ClassName : InterfaceName`). Se l'interfaccia viene ereditata perché è stata ereditata una classe base che implementa l'interfaccia, la classe base fornisce l'implementazione dei membri dell'interfaccia. Tuttavia, la classe derivata può reimplementare qualsiasi membro dell'interfaccia invece di usare l'implementazione ereditata. Quando le interfacce dichiarano un'implementazione predefinita di un metodo, qualsiasi classe che implementa tale interfaccia eredita tale implementazione. Le implementazioni definite nelle interfacce sono virtuali e la classe di implementazione può eseguire l'override dell'implementazione.

Una classe base può implementare anche i membri di interfaccia usando membri virtuali. In tal caso, una classe derivata può modificare il comportamento dell'interfaccia eseguendo l'override dei membri virtuali. Per altre informazioni su membri virtuali, vedere [Polimorfismo](../classes-and-structs/polymorphism.md).

## <a name="interfaces-summary"></a>Riepilogo delle interfacce

Un'interfaccia presenta le proprietà seguenti:

- Un'interfaccia è in genere simile a una classe di base astratta con solo membri astratti. Qualsiasi classe o struct che implementa l'interfaccia deve implementarne tutti i membri. Facoltativamente, un'interfaccia può definire implementazioni predefinite per alcuni o tutti i relativi membri. Per altre informazioni, vedere [metodi di interfaccia predefiniti](../../tutorials/default-interface-methods-versions.md).
- Non è possibile creare direttamente un'istanza di un'interfaccia. I membri vengono implementati da qualsiasi classe o struct che implementa l'interfaccia.
- Una classe o struct può implementare più interfacce. Una classe può ereditare una classe base e anche implementare una o più interfacce.

## <a name="related-sections"></a><a name="BKMK_RelatedSections"></a>Sezioni correlate

- [Proprietà dell'interfaccia](../classes-and-structs/interface-properties.md)  
- [Indicizzatori nelle interfacce](../indexers/indexers-in-interfaces.md)  
- [Come implementare eventi di interfaccia](../events/how-to-implement-interface-events.md)
- [Classi e struct](../classes-and-structs/index.md)  
- [Ereditarietà](../classes-and-structs/inheritance.md)  
- [Interfacce](../../language-reference/keywords/interface.md)
- [Metodi](../classes-and-structs/methods.md)  
- [Polimorfismo](../classes-and-structs/polymorphism.md)  
- [Classi e membri delle classi astratte e sealed](../classes-and-structs/abstract-and-sealed-classes-and-class-members.md)  
- [Proprietà](../classes-and-structs/properties.md)  
- [Events](../events/index.md)  
- [Indicizzatori](../indexers/index.md)
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Ereditarietà](../classes-and-structs/inheritance.md)
- [Nomi di identificatore](../inside-a-program/identifier-names.md)
