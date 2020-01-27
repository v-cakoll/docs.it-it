---
title: Nomi di classi, struct e interfacce
ms.date: 10/22/2008
helpviewer_keywords:
- type names, guidelines
- classes [.NET Framework], names
- enumerations [.NET Framework], names
- names [.NET Framework], interfaces
- common type names
- names [.NET Framework], type names
- names [.NET Framework], classes
- interfaces [.NET Framework], names
- generic type parameters
ms.assetid: 87a4b0da-ed64-43b1-ac43-968576c444ce
ms.openlocfilehash: 2c528348c0e84037a80df9797c56f03b51c73adc
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76727793"
---
# <a name="names-of-classes-structs-and-interfaces"></a>Nomi di classi, struct e interfacce
Le linee guida per la denominazione che seguono si applicano alla denominazione generale dei tipi.

 ✔️ le classi nome e gli struct con sostantivi o frasi sostantive, usando sistema Pascal.

 In questo modo i nomi dei tipi vengono distinti dai metodi, denominati con frasi del verbo.

 ✔️ le interfacce dei nomi con frasi aggettivali o occasionalmente con sostantivi o frasi sostantive.

 I sostantivi e le frasi sostantivi devono essere usati raramente e potrebbero indicare che il tipo deve essere una classe astratta e non un'interfaccia.

 ❌ non assegnano ai nomi di classe un prefisso (ad esempio, "C").

 ✔️ CONSIDERARE la fine del nome delle classi derivate con il nome della classe di base.

 Questa operazione è molto leggibile e spiega chiaramente la relazione. Alcuni esempi di questo codice sono: `ArgumentOutOfRangeException`, che è un tipo di `Exception`e `SerializableAttribute`, che è un tipo di `Attribute`. Tuttavia, è importante usare una ragionevole decisione nell'applicare questa linea guida; ad esempio, la classe `Button` è un tipo di evento di `Control`, anche se `Control` non viene visualizzato nel nome.

 ✔️ i nomi di interfaccia di prefisso con la lettera I, per indicare che il tipo è un'interfaccia.

 Ad esempio, `IComponent` (nome descrittivo), `ICustomAttributeProvider` (sintagma nominale) e `IPersistable` (aggettivo) sono nomi di interfaccia appropriati. Come per gli altri nomi di tipo, evitare abbreviazioni.

 ✔️ Assicurarsi che i nomi si differenziano solo per il prefisso "I" sul nome dell'interfaccia quando si definisce una coppia classe-interfaccia in cui la classe è un'implementazione standard dell'interfaccia.

## <a name="names-of-generic-type-parameters"></a>Nomi dei parametri di tipo generico
 I generics sono stati aggiunti a .NET Framework 2,0. La funzionalità ha introdotto un nuovo tipo di identificatore denominato *parametro di tipo*.

 ✔️ denominare parametri di tipo generico con nomi descrittivi, a meno che un nome di una sola lettera non sia completamente comprensibile e un nome descrittivo non aggiungerebbe valore.

 ✔️ CONSIGLIABILE usare `T` come nome del parametro di tipo per i tipi con un parametro di tipo a lettera singola.

```csharp
public int IComparer<T> { ... }
public delegate bool Predicate<T>(T item);
public struct Nullable<T> where T:struct { ... }
```

 ✔️ i nomi di parametro di tipo descrittivo di prefisso con `T`.

```csharp
public interface ISessionChannel<TSession> where TSession : ISession {
    TSession Session { get; }
}
```

 ✔️ considerare la possibilità di indicare i vincoli posizionati su un parametro di tipo nel nome del parametro.

 Ad esempio, un parametro vincolato a `ISession` potrebbe essere chiamato `TSession`.

## <a name="names-of-common-types"></a>Nomi dei tipi comuni
 ✔️ seguire le linee guida descritte nella tabella seguente per la denominazione dei tipi derivati da o per l'implementazione di determinati tipi di .NET Framework.

|Tipo di base|Linee guida sul tipo derivato/di implementazione|
|---------------|------------------------------------------|
|`System.Attribute`|✔️ aggiungere il suffisso "Attribute" ai nomi delle classi di attributi personalizzati.|
|`System.Delegate`|✔️ aggiungere il suffisso "EventHandler" ai nomi dei delegati utilizzati negli eventi.<br /><br /> ✔️ aggiungere il suffisso "callback" ai nomi di delegati diversi da quelli usati come gestori di eventi.<br /><br /> ❌ non aggiungere il suffisso "delegate" a un delegato.|
|`System.EventArgs`|✔️ aggiungere il suffisso "EventArgs".|
|`System.Enum`|❌ non derivano da questa classe; usare invece la parola chiave supportata dal linguaggio; in C#, ad esempio, usare la parola chiave `enum`.<br /><br /> ❌ non aggiungere il suffisso "enum" o "flag".|
|`System.Exception`|✔️ aggiungere il suffisso "Exception".|
|`IDictionary` <br /> `IDictionary<TKey,TValue>`|✔️ aggiungere il suffisso "Dictionary". Si noti che `IDictionary` è un tipo specifico di raccolta, ma questa guida ha la precedenza sulle linee guida più generali raccolte che seguono.|
|`IEnumerable` <br /> `ICollection` <br /> `IList` <br /> `IEnumerable<T>` <br /> `ICollection<T>` <br /> `IList<T>`|✔️ aggiungere il suffisso "Collection".|
|`System.IO.Stream`|✔️ aggiungere il suffisso "Stream".|
|`CodeAccessPermission IPermission`|✔️ aggiungere il suffisso "permission".|

## <a name="naming-enumerations"></a>Enumerazioni di denominazione
 I nomi dei tipi di enumerazione (detti anche enum) in generale devono rispettare le regole di denominazione dei tipi standard (sistema Pascal e così via). Tuttavia, esistono altre linee guida che si applicano in modo specifico alle enumerazioni.

 ✔️ utilizzare un nome di tipo singolare per un'enumerazione, a meno che i relativi valori non siano campi di bit.

 ✔️ utilizzare un nome di tipo plurale per un'enumerazione con campi di bit come valori, denominati anche enumerazione Flags.

 ❌ non utilizzano un suffisso "enum" nei nomi di tipo enum.

 ❌ non utilizzare suffissi "flag" o "flag" nei nomi dei tipi enum.

 ❌ non utilizzano un prefisso per i nomi dei valori di enumerazione (ad esempio, "ad" per le enumerazioni ADO, "RTF" per le enumerazioni di testo RTF e così via).

 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*

 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*

## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
- [Convenzioni di denominazione](../../../docs/standard/design-guidelines/naming-guidelines.md)
