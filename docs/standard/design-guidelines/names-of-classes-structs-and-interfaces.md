---
title: Nomi di classi, struct e interfacce
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a4f4b9e48587138f3e65c0c6825af0b3e4e8c592
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="names-of-classes-structs-and-interfaces"></a>Nomi di classi, struct e interfacce
Convenzioni di denominazione che seguono si applicano per la denominazione di tipo generale.  
  
 **✓ SI** nome classi e struct con sostantivi o sintagmi nominali, utilizzando il sistema Pascal.  
  
 Consente di distinguere i nomi dei tipi di metodi, denominati con frasi di verbo.  
  
 **✓ SI** nome interfacce aggettivale frasi o occasionalmente con sostantivi o sintagmi nominali.  
  
 Sostantivi e sintagmi nominali devono essere utilizzate raramente e potrebbero indicare che il tipo deve essere una classe astratta e non un'interfaccia.  
  
 **X non** ai nomi delle classi di un prefisso (ad esempio, "C").  
  
 **Provare a ✓** il nome della classe derivata con il nome della classe di base.  
  
 Questo è molto leggibile e illustra chiaramente la relazione. Sono riportati alcuni esempi di questo codice: `ArgumentOutOfRangeException`, che è un tipo di `Exception`, e `SerializableAttribute`, che è un tipo di `Attribute`. Tuttavia, è importante utilizzare valutando questa linea guida; ad esempio, il `Button` classe è un tipo di `Control` evento, sebbene `Control` non viene visualizzato nel relativo nome.  
  
 **✓ SI** prefisso nei nomi di interfaccia con la lettera I, a indicare che il tipo è un'interfaccia.  
  
 Ad esempio, `IComponent` (nome descrittivo), `ICustomAttributeProvider` (sintagma nominale) e `IPersistable` (aggettivo) sono nomi di interfaccia appropriata. Come con gli altri nomi di tipo, evitare di abbreviazioni.  
  
 **✓ SI** assicurarsi che i nomi differiscono solo per la "I" prefisso nel nome dell'interfaccia quando si definisce una coppia: interfaccia della classe in cui la classe è un'implementazione standard dell'interfaccia.  
  
## <a name="names-of-generic-type-parameters"></a>Nomi dei parametri di tipo generico  
 I generics sono stati aggiunti a .NET Framework 2.0. La funzionalità introdotto un nuovo tipo di identificatore denominato *parametro di tipo*.  
  
 **✓ SI** denominare i parametri di tipo generico con nomi descrittivi a meno che non è completamente chiara di un nome di lettera singola e un nome descrittivo non aggiunge valore.  
  
 **Provare a ✓** utilizzando `T` come nome del parametro di tipo per tipi con un parametro di tipo lettera singola.  
  
```  
public int IComparer<T> { ... }  
public delegate bool Predicate<T>(T item);  
public struct Nullable<T> where T:struct { ... }  
```  
  
 **✓ SI** i nomi dei parametri di tipo descrittivo con prefisso `T`.  
  
```  
public interface ISessionChannel<TSession> where TSession : ISession{  
    TSession Session { get; }  
}  
```  
  
 **Provare a ✓** che indica i vincoli posizionati su un parametro di tipo del nome del parametro.  
  
 Ad esempio, un parametro vincolato a `ISession` potrebbe essere denominata `TSession`.  
  
## <a name="names-of-common-types"></a>Nomi di tipi comuni  
 **✓ SI** seguire le linee guida descritte nella tabella seguente per la denominazione di tipi derivati da o implementare determinati tipi di .NET Framework.  
  
|Base Type|Linee guida di tipo derivato implementazione|  
|---------------|------------------------------------------|  
|`System.Attribute`|**✓ SI** aggiungere il suffisso "Attribute" ai nomi delle classi di attributo personalizzato.|  
|`System.Delegate`|**✓ SI** aggiungere il suffisso "EventHandler" ai nomi dei delegati utilizzato negli eventi.<br /><br /> **✓ SI** aggiungere il suffisso "Callback" ai nomi dei delegati diversi da quelli usati come gestori eventi.<br /><br /> **X non** aggiungere il suffisso "Delegato" a un delegato.|  
|`System.EventArgs`|**✓ SI** aggiungere il suffisso "EventArgs".|  
|`System.Enum`|**X non** derivano da questa classe; usare la parola chiave supportata dal linguaggio di invece; ad esempio, in c#, utilizzare il `enum` (parola chiave).<br /><br /> **X non** aggiungere il suffisso "Enum" o "Flag".|  
|`System.Exception`|**✓ SI** aggiungere il suffisso "Exception".|  
|`IDictionary` <br /> `IDictionary<TKey,TValue>`|**✓ SI** aggiungere il suffisso "Dizionario". Si noti che `IDictionary` è un tipo specifico della raccolta, ma questa linea guida ha la precedenza su più generale delle linee guida di raccolte che segue.|  
|`IEnumerable` <br /> `ICollection` <br /> `IList` <br /> `IEnumerable<T>` <br /> `ICollection<T>` <br /> `IList<T>`|**✓ SI** aggiungere il suffisso "Collection".|  
|`System.IO.Stream`|**✓ SI** aggiungere il suffisso "Stream".|  
|`CodeAccessPermission IPermission`|**✓ SI** aggiungere il suffisso "Autorizzazioni".|  
  
## <a name="naming-enumerations"></a>Denominazione delle enumerazioni  
 I nomi dei tipi di enumerazione (detti anche le enumerazioni) in genere devono seguire le regole denominazione di tipo standard (il sistema Pascal, ecc.). Tuttavia, esistono linee guida aggiuntive specifiche per le enumerazioni.  
  
 **✓ SI** utilizzare un nome di tipo singolare per un'enumerazione, a meno che i relativi valori sono i campi di bit.  
  
 **✓ SI** utilizzare un nome di tipo plurale per un'enumerazione con i campi di bit come valori, l'acronimo di enumerazione di flag.  
  
 **X non** utilizzare un suffisso "Enum" nei nomi di tipo enum.  
  
 **X non** utilizzare "Flag" o nomi di tipo suffissi "Flags" nell'enumerazione.  
  
 **X non** usare un prefisso ai nomi di valore di enumerazione (ad esempio, "ad" per le enumerazioni ADO.), "rtf" per le enumerazioni RTF e così via.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)  
 [Convenzioni di denominazione](../../../docs/standard/design-guidelines/naming-guidelines.md)
