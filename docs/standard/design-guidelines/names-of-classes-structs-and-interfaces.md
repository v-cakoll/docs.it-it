---
title: Nomi di classi, struct e interfacce
description: Usare queste linee guida per rinominare classi, struct e interfacce come parte delle linee guida per la progettazione di librerie che estendono e interagiscono con le librerie .NET.
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
ms.openlocfilehash: e7eee414c5bf5c69f63543ef240e50a4d2d948a3
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419083"
---
# <a name="names-of-classes-structs-and-interfaces"></a>Nomi di classi, struct e interfacce
Le linee guida per la denominazione che seguono si applicano alla denominazione generale dei tipi.

 ✔️ le classi nome e gli struct con sostantivi o frasi sostantive, usando sistema Pascal.

 In questo modo i nomi dei tipi vengono distinti dai metodi, denominati con frasi del verbo.

 ✔️ le interfacce dei nomi con frasi aggettivali o occasionalmente con sostantivi o frasi sostantive.

 I sostantivi e le frasi sostantivi devono essere usati raramente e potrebbero indicare che il tipo deve essere una classe astratta e non un'interfaccia.

 ❌NON assegnare al nome della classe un prefisso (ad esempio, "C").

 ✔️ CONSIDERARE la fine del nome delle classi derivate con il nome della classe di base.

 Questa operazione è molto leggibile e spiega chiaramente la relazione. Alcuni esempi di questo codice sono: `ArgumentOutOfRangeException` , che è un tipo di `Exception` , e `SerializableAttribute` , che è un tipo di `Attribute` . Tuttavia, è importante usare una ragionevole decisione nell'applicare questa linea guida; ad esempio, la `Button` classe è un tipo di `Control` evento, sebbene `Control` non sia presente nel nome.

 ✔️ i nomi di interfaccia di prefisso con la lettera I, per indicare che il tipo è un'interfaccia.

 Ad esempio, ( `IComponent` sostantivo descrittivo), `ICustomAttributeProvider` (sintagma sostantivo) e `IPersistable` (aggettivo) sono nomi di interfaccia appropriati. Come per gli altri nomi di tipo, evitare abbreviazioni.

 ✔️ Assicurarsi che i nomi si differenziano solo per il prefisso "I" sul nome dell'interfaccia quando si definisce una coppia classe-interfaccia in cui la classe è un'implementazione standard dell'interfaccia.

## <a name="names-of-generic-type-parameters"></a>Nomi dei parametri di tipo generico
 I generics sono stati aggiunti a .NET Framework 2,0. La funzionalità ha introdotto un nuovo tipo di identificatore denominato *parametro di tipo*.

 ✔️ denominare parametri di tipo generico con nomi descrittivi, a meno che un nome di una sola lettera non sia completamente comprensibile e un nome descrittivo non aggiungerebbe valore.

 ✔️ CONSIGLIABILE utilizzare `T` come nome del parametro di tipo per i tipi con un parametro di tipo a lettera singola.

```csharp
public int IComparer<T> { ... }
public delegate bool Predicate<T>(T item);
public struct Nullable<T> where T:struct { ... }
```

 ✔️ i nomi di parametro di tipo descrittivo con `T` .

```csharp
public interface ISessionChannel<TSession> where TSession : ISession {
    TSession Session { get; }
}
```

 ✔️ considerare la possibilità di indicare i vincoli posizionati su un parametro di tipo nel nome del parametro.

 Ad esempio, è possibile chiamare un parametro vincolato a `ISession` `TSession` .

## <a name="names-of-common-types"></a>Nomi dei tipi comuni
 ✔️ seguire le linee guida descritte nella tabella seguente per la denominazione dei tipi derivati da o per l'implementazione di determinati tipi di .NET Framework.

|Base Type|Linee guida sul tipo derivato/di implementazione|
|---------------|------------------------------------------|
|`System.Attribute`|✔️ aggiungere il suffisso "Attribute" ai nomi delle classi di attributi personalizzati.|
|`System.Delegate`|✔️ aggiungere il suffisso "EventHandler" ai nomi dei delegati utilizzati negli eventi.<br /><br /> ✔️ aggiungere il suffisso "callback" ai nomi di delegati diversi da quelli usati come gestori di eventi.<br /><br /> ❌NON aggiungere il suffisso "delegate" a un delegato.|
|`System.EventArgs`|✔️ aggiungere il suffisso "EventArgs".|
|`System.Enum`|❌NON derivare da questa classe; usare invece la parola chiave supportata dal linguaggio; in C#, ad esempio, usare la `enum` parola chiave.<br /><br /> ❌Non aggiungere il suffisso "enum" o "flag".|
|`System.Exception`|✔️ aggiungere il suffisso "Exception".|
|`IDictionary` <br /> `IDictionary<TKey,TValue>`|✔️ aggiungere il suffisso "Dictionary". Si noti che `IDictionary` è un tipo specifico di raccolta, ma questa linea guida ha la precedenza rispetto alle linee guida per le raccolte più generali riportate di seguito.|
|`IEnumerable` <br /> `ICollection` <br /> `IList` <br /> `IEnumerable<T>` <br /> `ICollection<T>` <br /> `IList<T>`|✔️ aggiungere il suffisso "Collection".|
|`System.IO.Stream`|✔️ aggiungere il suffisso "Stream".|
|`CodeAccessPermission IPermission`|✔️ aggiungere il suffisso "permission".|

## <a name="naming-enumerations"></a>Enumerazioni di denominazione
 I nomi dei tipi di enumerazione (detti anche enum) in generale devono rispettare le regole di denominazione dei tipi standard (sistema Pascal e così via). Tuttavia, esistono altre linee guida che si applicano in modo specifico alle enumerazioni.

 ✔️ utilizzare un nome di tipo singolare per un'enumerazione, a meno che i relativi valori non siano campi di bit.

 ✔️ utilizzare un nome di tipo plurale per un'enumerazione con campi di bit come valori, denominati anche enumerazione Flags.

 ❌Non usare un suffisso "enum" nei nomi di tipo enum.

 ❌Non usare suffissi "flag" o "Flags" nei nomi di tipo enum.

 ❌Non usare un prefisso per i nomi dei valori di enumerazione (ad esempio, "ad" per le enumerazioni ADO, "RTF" per le enumerazioni di testo RTF e così via).

 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*

 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*

## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
- [Linee guida per la denominazione](../../../docs/standard/design-guidelines/naming-guidelines.md)
