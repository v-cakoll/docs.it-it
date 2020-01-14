---
title: Interfacce - Guida per programmatori C#
ms.date: 08/21/2018
helpviewer_keywords:
- interfaces [C#]
- C# language, interfaces
ms.assetid: 2feda177-ce11-432d-81b4-d50f5f35fd37
ms.openlocfilehash: 43e37dc4b0977542add05c8cc13e2d7fa47b19bf
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937497"
---
# <a name="interfaces-c-programming-guide"></a>Interfacce (Guida per programmatori C#)

Un'interfaccia contiene le definizioni per un gruppo di funzionalità correlate che devono essere implementate da una [classe](../../language-reference/keywords/class.md) non astratta o da uno [struct](../../language-reference/keywords/struct.md) .
  
Usando le interfacce, è possibile, ad esempio, includere il comportamento di più origini in una classe. Tale funzionalità è importante in C# perché il linguaggio non supporta l'ereditarietà multipla delle classi. Inoltre è necessario usare un'interfaccia se si vuole simulare l'ereditarietà per le struct, perché non possono effettivamente ereditare da un'altra struct o classe.  
  
Per definire un'interfaccia, si usa la parola chiave [interface](../../language-reference/keywords/interface.md). come nell'esempio riportato di seguito.  
  
 [!code-csharp[csProgGuideInheritance#47](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#47)]  

Il nome di un'interfaccia deve essere un C# [nome di identificatore](../inside-a-program/identifier-names.md)valido. Per convenzione, i nomi di interfaccia iniziano con una lettera `I` maiuscola.

Qualsiasi classe o struct che implementa l'interfaccia <xref:System.IEquatable%601> deve contenere una definizione per un metodo <xref:System.IEquatable%601.Equals%2A> che corrisponde alla firma specificata dall'interfaccia. Di conseguenza, è possibile affidarsi a una classe che implementa `IEquatable<T>` per contenere un metodo `Equals` con cui un'istanza della classe può determinare se sia uguale a un'altra istanza della stessa classe.  
  
La definizione di `IEquatable<T>` non fornisce un'implementazione per `Equals`. Una classe o uno struct può implementare più interfacce, ma una classe può ereditare solo da una singola classe.
  
Per altre informazioni sulle classi astratte, vedere [Classi e membri delle classi astratte e sealed](../classes-and-structs/abstract-and-sealed-classes-and-class-members.md).  
  
Le interfacce possono contenere metodi, proprietà, eventi, indicizzatori o qualsiasi combinazione di questi quattro membri. Per collegamenti a esempi, vedere [Sezioni correlate](./index.md#BKMK_RelatedSections). Un'interfaccia non può contenere costanti, campi, operatori, costruttori di istanze, finalizzatori o tipi. I membri di interfaccia sono automaticamente pubblici e non possono includere modificatori di accesso. I membri non possono nemmeno essere [statici](../../language-reference/keywords/static.md).  
  
Per implementare un membro di interfaccia, il corrispondente membro della classe di implementazione deve essere pubblico e non statico e avere lo stesso nome e la stessa firma del membro di interfaccia.  
  
Quando una classe o una struct implementa un'interfaccia, la classe o la struct deve fornire un'implementazione per tutti i membri definiti dall'interfaccia. L'interfaccia stessa non fornisce funzionalità che una classe o struct possa ereditare come può ereditare le funzionalità delle classi base. Tuttavia, se una classe base implementa un'interfaccia, qualsiasi classe derivata dalla classe base eredita tale implementazione.  
  
Nell'esempio seguente viene illustrata un'implementazione dell'interfaccia <xref:System.IEquatable%601>. La classe di implementazione, `Car`, deve fornire un'implementazione del metodo <xref:System.IEquatable%601.Equals%2A>.  
  
 [!code-csharp[csProgGuideInheritance#48](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#48)]  
  
Le proprietà e gli indicizzatori di una classe possono definire altre funzioni di accesso per una proprietà o un indicizzatore definito in un'interfaccia. Ad esempio, un'interfaccia può dichiarare una proprietà con una funzione di accesso [get](../../language-reference/keywords/get.md). La classe che implementa l'interfaccia può dichiarare la stessa proprietà con una funzione di accesso `get` o [set](../../language-reference/keywords/set.md). Tuttavia, se la proprietà o l'indicizzatore usa l'implementazione esplicita, le funzioni di accesso devono corrispondere. Per altre informazioni sull'implementazione esplicita, vedere [Implementazione esplicita dell'interfaccia](explicit-interface-implementation.md) e [Proprietà dell'interfaccia](../classes-and-structs/interface-properties.md).  

Le interfacce possono ereditare da altre interfacce. Una classe può includere un'interfaccia più volte tramite le classi di base ereditate o tramite le interfacce ereditate da altre interfacce. Tuttavia, la classe può fornire un'implementazione di un'interfaccia solo una volta e solo se la classe dichiara l'interfaccia durante la definizione della classe (`class ClassName : InterfaceName`). Se l'interfaccia viene ereditata perché è stata ereditata una classe base che implementa l'interfaccia, la classe base fornisce l'implementazione dei membri dell'interfaccia. Tuttavia, la classe derivata può reimplementare qualsiasi membro dell'interfaccia invece di usare l'implementazione ereditata.  
  
Una classe base può implementare anche i membri di interfaccia usando membri virtuali. In tal caso, una classe derivata può modificare il comportamento dell'interfaccia eseguendo l'override dei membri virtuali. Per altre informazioni su membri virtuali, vedere [Polimorfismo](../classes-and-structs/polymorphism.md).  
  
## <a name="interfaces-summary"></a>Riepilogo delle interfacce

Un'interfaccia presenta le proprietà seguenti:  

- Un'interfaccia è paragonabile a una classe di base astratta contente solo membri astratti. Qualsiasi classe o struct che implementa l'interfaccia deve implementarne tutti i membri.
- Non è possibile creare direttamente un'istanza di un'interfaccia. I membri vengono implementati da qualsiasi classe o struct che implementa l'interfaccia.
- Le interfacce possono contenere eventi, indicizzatori, metodi e proprietà.
- Le interfacce non contengono implementazioni di metodi C# (in 8,0, le interfacce possono avere un' [implementazione predefinita per i metodi](../../whats-new/csharp-8.md#default-interface-methods)).
- Una classe o struct può implementare più interfacce. Una classe può ereditare una classe base e anche implementare una o più interfacce.

## <a name="in-this-section"></a>In questa sezione

[Implementazione esplicita dell'interfaccia](explicit-interface-implementation.md)  
 Illustra come creare un membro di una classe specifico di un'interfaccia.  
  
 [Come implementare in modo esplicito i membri di interfaccia](how-to-explicitly-implement-interface-members.md)  
 Fornisce un esempio di come implementare in modo esplicito i membri delle interfacce.  
  
 [Come implementare in modo esplicito i membri di due interfacce](how-to-explicitly-implement-members-of-two-interfaces.md)  
 Fornisce un esempio di come implementare in modo esplicito i membri delle interfacce con l'ereditarietà.  
  
## <a name="BKMK_RelatedSections"></a> Sezioni correlate

- [Proprietà dell'interfaccia](../classes-and-structs/interface-properties.md)  
- [Indicizzatori nelle interfacce](../indexers/indexers-in-interfaces.md)  
- [Come implementare gli eventi di interfaccia](../events/how-to-implement-interface-events.md)
- [Classi e struct](../classes-and-structs/index.md)  
- [Ereditarietà](../classes-and-structs/inheritance.md)  
- [Metodi](../classes-and-structs/methods.md)  
- [Polimorfismo](../classes-and-structs/polymorphism.md)  
- [Classi e membri delle classi astratte e sealed](../classes-and-structs/abstract-and-sealed-classes-and-class-members.md)  
- [Proprietà](../classes-and-structs/properties.md)  
- [Eventi](../events/index.md)  
- [Indicizzatori](../indexers/index.md)  
  
## <a name="featured-book-chapter"></a>Capitolo del libro rappresentato

[Interfaces](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652489%28v%3Dorm.10%29) in [Learning C# 3.0: Master the Fundamentals of C# 3.0](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652493%28v%253dorm.10%29)

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Ereditarietà](../classes-and-structs/inheritance.md)
- [Nomi di identificatore](../inside-a-program/identifier-names.md)
