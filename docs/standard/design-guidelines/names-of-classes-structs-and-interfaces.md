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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400596"
---
# <a name="names-of-classes-structs-and-interfaces"></a>Nomi di classi, struct e interfacce
Le linee guida per la denominazione che seguono si applicano alla denominazione generale dei tipi.

 ✔️ classi e struct di nome DO con sostantivi o frasi nominali, utilizzando PascalCasing.

 Questo distingue i nomi dei tipi dai metodi, che sono denominati con frasi verbali.

 ✔️ nome DO si interfaccia con frasi aggettive o occasionalmente con sostantivi o frasi sostantive.

 I sostantivi e le frasi nominali devono essere usati raramente e potrebbero indicare che il tipo deve essere una classe astratta e non un'interfaccia.

 ❌NON assegnare un prefisso ai nomi delle classi (ad esempio, "C").

 ✔️ CONSIDER termina il nome delle classi derivate con il nome della classe base.

 Questo è molto leggibile e spiega chiaramente la relazione. Alcuni esempi di questo `ArgumentOutOfRangeException`nel codice sono: `Exception`, `SerializableAttribute`che è una `Attribute`sorta di , e , che è una sorta di . Tuttavia, è importante ritenere un giudizio ragionevole nell'applicare questa linea guida; ad esempio, `Button` la classe `Control` è un `Control` tipo di evento, anche se non viene visualizzato nel nome.

 ✔️ nomi di interfaccia prefisso DO con la lettera I, per indicare che il tipo è un'interfaccia.

 Ad esempio, `IComponent` (sostantivo descrittivo), `ICustomAttributeProvider` (frase nominale) e `IPersistable` (aggettivo) sono nomi di interfaccia appropriati. Come per altri nomi di tipo, evitare le abbreviazioni.

 ✔️ assicurarsi che i nomi differiscano solo per il prefisso "I" sul nome dell'interfaccia quando si definisce una coppia classe-interfaccia in cui la classe è un'implementazione standard dell'interfaccia.

## <a name="names-of-generic-type-parameters"></a>Nomi dei parametri di tipo generico
 I generics sono stati aggiunti a .NET Framework 2.0. La funzionalità ha introdotto un nuovo tipo di identificatore denominato *parametro*di tipo .

 ✔️ parametri di tipo generico del nome DO con nomi descrittivi, a meno che un nome a una lettera sia completamente autoesplicativo e un nome descrittivo non aggiungerebbe valore.

 ✔️ CONSIDER `T` viene utilizzato come nome del parametro di tipo per i tipi con un parametro di tipo a lettera singola.

```csharp
public int IComparer<T> { ... }
public delegate bool Predicate<T>(T item);
public struct Nullable<T> where T:struct { ... }
```

 ✔️ prefisso descrittivo `T`dei nomi dei parametri di tipo descrittivi con .

```csharp
public interface ISessionChannel<TSession> where TSession : ISession {
    TSession Session { get; }
}
```

 ✔️ CONSIDER che indica i vincoli posizionati su un parametro di tipo nel nome del parametro.

 Ad esempio, un `ISession` parametro `TSession`vincolato a potrebbe essere chiamato .

## <a name="names-of-common-types"></a>Nomi dei tipi comuni
 ✔️ seguono le linee guida descritte nella tabella seguente quando si assegnano nomi ai tipi derivati da o implementano determinati tipi .NET Framework.

|Base Type|Derivato/Implementazione di linee guida per i tipi|
|---------------|------------------------------------------|
|`System.Attribute`|✔️ aggiungere il suffisso "Attribute" ai nomi delle classi di attributi personalizzati.|
|`System.Delegate`|✔️ aggiungere il suffisso "EventHandler" ai nomi dei delegati utilizzati negli eventi.<br /><br /> ✔️ aggiungere il suffisso "Callback" ai nomi dei delegati diversi da quelli utilizzati come gestori eventi.<br /><br /> ❌NON aggiungere il suffisso "Delegato" a un delegato.|
|`System.EventArgs`|✔️ aggiungere il suffisso "EventArgs".|
|`System.Enum`|❌NON derivare da questa classe; utilizzare invece la parola chiave supportata dalla tua lingua; ad esempio, in C, `enum` usare la parola chiave .<br /><br /> ❌NON aggiungere il suffisso "Enum" o "Flag".|
|`System.Exception`|✔️ aggiungere il suffisso "Eccezione".|
|`IDictionary` <br /> `IDictionary<TKey,TValue>`|✔️ aggiungere il suffisso "Dizionario". Si `IDictionary` noti che è un tipo specifico di raccolta, ma questa linea guida ha la precedenza sulle linee guida raccolte più generali che seguono.|
|`IEnumerable` <br /> `ICollection` <br /> `IList` <br /> `IEnumerable<T>` <br /> `ICollection<T>` <br /> `IList<T>`|✔️ aggiungere il suffisso "Collection".|
|`System.IO.Stream`|✔️ aggiungere il suffisso "Stream".|
|`CodeAccessPermission IPermission`|✔️ aggiungere il suffisso "Autorizzazione".|

## <a name="naming-enumerations"></a>Denominazione delle enumerazioni
 I nomi dei tipi di enumerazione (denominati anche enumerazioni) in generale devono seguire le regole di denominazione dei tipi standard (PascalCasing e così via). Tuttavia, esistono linee guida aggiuntive che si applicano in modo specifico alle enumerazioni.

 ✔️ utilizzare un nome di tipo singolare per un'enumerazione, a meno che i relativi valori non siano campi di bit.

 ✔️ utilizzare un nome di tipo plurale per un'enumerazione con campi di bit come valori, denominato anche flags enum.

 ❌NON utilizzare un suffisso "Enum" nei nomi dei tipi enum.

 ❌NON utilizzare suffissi "Flag" o "Flags" nei nomi dei tipi enum.

 ❌NON utilizzare un prefisso sui nomi dei valori di enumerazione (ad esempio, "ad" per le enumerazioni ADO, "rtf" per le enumerazioni RTF e così via).

 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*

 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*

## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
- [Convenzioni di denominazione](../../../docs/standard/design-guidelines/naming-guidelines.md)
