---
title: Nomi di classi, struct e interfacce
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c56f840bc5ebd5070c9b686384751acab3f0203
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2018
ms.locfileid: "45972546"
---
# <a name="names-of-classes-structs-and-interfaces"></a>Nomi di classi, struct e interfacce
Convenzioni di denominazione che seguono si applicano per la denominazione di tipo generale.  
  
 **✓ DO** nome classi e struct con sostantivi o sintagmi nominali, utilizzando il sistema Pascal.  
  
 Ciò consente di distinguere i nomi dei tipi dai metodi, denominati con le diciture verbo.  
  
 **✓ DO** nome interfacce Frasario frasi o in alcuni casi con sostantivi o sintagmi nominali.  
  
 Sostantivi che sintagmi nominali devono essere utilizzate raramente e potrebbero indicare che il tipo deve essere una classe astratta e non un'interfaccia.  
  
 **X DO NOT** ai nomi delle classi un prefisso (ad esempio, "C").  
  
 **✓ CONSIDER** terminare il nome della classe derivata con il nome della classe base.  
  
 Questo è molto leggibile e illustra la relazione in modo chiaro. Sono riportati alcuni esempi di questo nel codice: `ArgumentOutOfRangeException`, che è un tipo di `Exception`, e `SerializableAttribute`, che è una sorta di `Attribute`. Tuttavia, è importante usare valutando questa linea guida; ad esempio, il `Button` classe è un tipo di `Control` evento, anche se `Control` non viene visualizzato nel relativo nome.  
  
 **✓ DO** prefisso nei nomi di interfaccia con la lettera I, a indicare che il tipo è un'interfaccia.  
  
 Ad esempio, `IComponent` (nome descrittivo), `ICustomAttributeProvider` (sintagma nominale), e `IPersistable` (aggettivo) sono nomi di interfaccia appropriata. Come con altri nomi di tipo, evitare le abbreviazioni.  
  
 **✓ DO** assicurarsi che i nomi differiscono solo per la "I" prefisso nel nome dell'interfaccia quando si definisce una coppia: interfaccia della classe in cui la classe è un'implementazione standard dell'interfaccia.  
  
## <a name="names-of-generic-type-parameters"></a>Nomi dei parametri di tipo generico  
 I generics sono state aggiunte a .NET Framework 2.0. La funzionalità introdotto un nuovo tipo di identificatore denominato *il parametro di tipo*.  
  
 **✓ DO** denominare i parametri di tipo generico con nomi descrittivi a meno che non è completamente non necessitano di spiegazione un nome di lettera singola e un nome descrittivo non aggiunge valore.  
  
 **✓ CONSIDER** utilizzando `T` come nome del parametro di tipo per tipi con un parametro di tipo lettera singola.  
  
```  
public int IComparer<T> { ... }  
public delegate bool Predicate<T>(T item);  
public struct Nullable<T> where T:struct { ... }  
```  
  
 **✓ DO** i nomi dei parametri di tipo descrittivo con prefisso `T`.  
  
```  
public interface ISessionChannel<TSession> where TSession : ISession {  
    TSession Session { get; }  
}  
```  
  
 **✓ CONSIDER** che indica i vincoli posizionati su un parametro di tipo del nome del parametro.  
  
 Ad esempio, un parametro vincolato a `ISession` potrebbe essere chiamato `TSession`.  
  
## <a name="names-of-common-types"></a>Nomi dei tipi comuni  
 **✓ DO** seguire le linee guida descritte nella tabella seguente, la denominazione dei tipi derivati da o implementare determinati tipi di .NET Framework.  
  
|Base Type|Linee guida di tipo derivato/implementazione|  
|---------------|------------------------------------------|  
|`System.Attribute`|**✓ DO** aggiungere il suffisso "Attribute" ai nomi delle classi di attributi personalizzati.|  
|`System.Delegate`|**✓ DO** aggiungere il suffisso "EventHandler" ai nomi dei delegati vengono utilizzati negli eventi.<br /><br /> **✓ DO** aggiungere il suffisso "Callback" ai nomi dei delegati diversi da quelli usati come gestori eventi.<br /><br /> **X DO NOT** aggiungere il suffisso "Delegato" a un delegato.|  
|`System.EventArgs`|**✓ DO** aggiungere il suffisso "EventArgs."|  
|`System.Enum`|**X DO NOT** derivano da questa classe; usare la parola chiave supportata dal linguaggio di invece; ad esempio, in c#, usare il `enum` (parola chiave).<br /><br /> **X DO NOT** aggiungere il suffisso "Enum" o "Flag".|  
|`System.Exception`|**✓ DO** aggiungere il suffisso "Exception".|  
|`IDictionary` <br /> `IDictionary<TKey,TValue>`|**✓ DO** aggiungere il suffisso "Dizionario". Si noti che `IDictionary` è un tipo specifico della raccolta, ma questa linea guida ha la precedenza su più generale delle linee guida di raccolte che segue.|  
|`IEnumerable` <br /> `ICollection` <br /> `IList` <br /> `IEnumerable<T>` <br /> `ICollection<T>` <br /> `IList<T>`|**✓ DO** aggiungere il suffisso "Collection".|  
|`System.IO.Stream`|**✓ DO** aggiungere il suffisso "Stream".|  
|`CodeAccessPermission IPermission`|**✓ DO** aggiungere il suffisso "Autorizzazioni".|  
  
## <a name="naming-enumerations"></a>Denominazione delle enumerazioni  
 I nomi dei tipi di enumerazione (detti anche enumerazioni) in genere devono seguire le regole di denominazione di tipo standard (il sistema Pascal e così via). Tuttavia, esistono linee guida aggiuntive che si applicano in modo specifico per le enumerazioni.  
  
 **✓ DO** utilizzare un nome di tipo singolare per un'enumerazione, a meno che i relativi valori sono i campi di bit.  
  
 **✓ DO** utilizzi un nome di tipo plurale per un'enumerazione con i campi di bit come valori, collettivamente indicati come enumerazione di flag.  
  
 **X DO NOT** utilizzare un suffisso "Enum" nei nomi dei tipi enum.  
  
 **X DO NOT** utilizzare "Flag" o nomi di tipo suffissi "Flags" nell'enumerazione.  
  
 **X DO NOT** usare un prefisso ai nomi di valore di enumerazione (ad esempio, "ad" per le enumerazioni di ADO.), "rtf" per le enumerazioni RTF e così via.  
  
 *Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)  
- [Convenzioni di denominazione](../../../docs/standard/design-guidelines/naming-guidelines.md)
