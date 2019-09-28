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
author: KrzysztofCwalina
ms.openlocfilehash: 2ecd708ccb8eb91270e8ef9c174b8d7e599a2629
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "71353716"
---
# <a name="names-of-classes-structs-and-interfaces"></a>Nomi di classi, struct e interfacce
Le linee guida per la denominazione che seguono si applicano alla denominazione generale dei tipi.  
  
 **✓ DO** nome classi e struct con sostantivi o sintagmi nominali, utilizzando il sistema Pascal.  
  
 In questo modo i nomi dei tipi vengono distinti dai metodi, denominati con frasi del verbo.  
  
 **✓ DO** nome interfacce Frasario frasi o in alcuni casi con sostantivi o sintagmi nominali.  
  
 I sostantivi e le frasi sostantivi devono essere usati raramente e potrebbero indicare che il tipo deve essere una classe astratta e non un'interfaccia.  
  
 **X DO NOT** ai nomi delle classi un prefisso (ad esempio, "C").  
  
 **✓ CONSIDER** terminare il nome della classe derivata con il nome della classe base.  
  
 Questa operazione è molto leggibile e spiega chiaramente la relazione. Alcuni esempi di questo codice sono: `ArgumentOutOfRangeException`, che è un tipo di `Exception` e `SerializableAttribute`, che è un tipo di `Attribute`. Tuttavia, è importante usare una ragionevole decisione nell'applicare questa linea guida; ad esempio, la classe `Button` è un tipo di evento `Control`, sebbene `Control` non venga visualizzato nel nome.  
  
 **✓ DO** prefisso nei nomi di interfaccia con la lettera I, a indicare che il tipo è un'interfaccia.  
  
 Ad esempio, `IComponent` (nome descrittivo), `ICustomAttributeProvider` (sintagma sostantivo) e `IPersistable` (aggettivo) sono nomi di interfaccia appropriati. Come per gli altri nomi di tipo, evitare abbreviazioni.  
  
 **✓ DO** assicurarsi che i nomi differiscono solo per la "I" prefisso nel nome dell'interfaccia quando si definisce una coppia: interfaccia della classe in cui la classe è un'implementazione standard dell'interfaccia.  
  
## <a name="names-of-generic-type-parameters"></a>Nomi dei parametri di tipo generico  
 I generics sono stati aggiunti a .NET Framework 2,0. La funzionalità ha introdotto un nuovo tipo di identificatore denominato *parametro di tipo*.  
  
 **✓ DO** denominare i parametri di tipo generico con nomi descrittivi a meno che non è completamente non necessitano di spiegazione un nome di lettera singola e un nome descrittivo non aggiunge valore.  
  
 **✓ CONSIDER** utilizzando `T` come nome del parametro di tipo per tipi con un parametro di tipo lettera singola.  
  
```csharp  
public int IComparer<T> { ... }  
public delegate bool Predicate<T>(T item);  
public struct Nullable<T> where T:struct { ... }  
```  
  
 **✓ DO** i nomi dei parametri di tipo descrittivo con prefisso `T`.  
  
```csharp  
public interface ISessionChannel<TSession> where TSession : ISession {  
    TSession Session { get; }  
}  
```  
  
 **✓ CONSIDER** che indica i vincoli posizionati su un parametro di tipo del nome del parametro.  
  
 Ad esempio, un parametro vincolato a `ISession` potrebbe essere chiamato `TSession`.  
  
## <a name="names-of-common-types"></a>Nomi dei tipi comuni  
 **✓ DO** seguire le linee guida descritte nella tabella seguente, la denominazione dei tipi derivati da o implementare determinati tipi di .NET Framework.  
  
|Base Type|Linee guida sul tipo derivato/di implementazione|  
|---------------|------------------------------------------|  
|`System.Attribute`|**✓ DO** aggiungere il suffisso "Attribute" ai nomi delle classi di attributi personalizzati.|  
|`System.Delegate`|**✓ DO** aggiungere il suffisso "EventHandler" ai nomi dei delegati vengono utilizzati negli eventi.<br /><br /> **✓ DO** aggiungere il suffisso "Callback" ai nomi dei delegati diversi da quelli usati come gestori eventi.<br /><br /> **X DO NOT** aggiungere il suffisso "Delegato" a un delegato.|  
|`System.EventArgs`|**✓ DO** aggiungere il suffisso "EventArgs."|  
|`System.Enum`|**X DO NOT** derivano da questa classe; usare la parola chiave supportata dal linguaggio di invece; ad esempio, in c#, usare il `enum` (parola chiave).<br /><br /> **X DO NOT** aggiungere il suffisso "Enum" o "Flag".|  
|`System.Exception`|**✓ DO** aggiungere il suffisso "Exception".|  
|`IDictionary` <br /> `IDictionary<TKey,TValue>`|**✓ DO** aggiungere il suffisso "Dizionario". Si noti che `IDictionary` è un tipo specifico di raccolta, ma questa guida ha la precedenza sulle linee guida più generali raccolte che seguono.|  
|`IEnumerable` <br /> `ICollection` <br /> `IList` <br /> `IEnumerable<T>` <br /> `ICollection<T>` <br /> `IList<T>`|**✓ DO** aggiungere il suffisso "Collection".|  
|`System.IO.Stream`|**✓ DO** aggiungere il suffisso "Stream".|  
|`CodeAccessPermission IPermission`|**✓ DO** aggiungere il suffisso "Autorizzazioni".|  
  
## <a name="naming-enumerations"></a>Enumerazioni di denominazione  
 I nomi dei tipi di enumerazione (detti anche enum) in generale devono rispettare le regole di denominazione dei tipi standard (sistema Pascal e così via). Tuttavia, esistono altre linee guida che si applicano in modo specifico alle enumerazioni.  
  
 **✓ DO** utilizzare un nome di tipo singolare per un'enumerazione, a meno che i relativi valori sono i campi di bit.  
  
 **✓ DO** utilizzi un nome di tipo plurale per un'enumerazione con i campi di bit come valori, collettivamente indicati come enumerazione di flag.  
  
 **X DO NOT** utilizzare un suffisso "Enum" nei nomi dei tipi enum.  
  
 **X DO NOT** utilizzare "Flag" o nomi di tipo suffissi "Flags" nell'enumerazione.  
  
 **X DO NOT** usare un prefisso ai nomi di valore di enumerazione (ad esempio, "ad" per le enumerazioni di ADO.), "rtf" per le enumerazioni RTF e così via.  
  
 *Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 @no__t 0Reprinted per autorizzazione di Pearson Education, Inc. dalle linee guida di progettazione di [Framework: Convenzioni, idiomi e modelli per le librerie .NET riutilizzabili, 2a edizione @ no__t-0 di Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo Microsoft Windows. *  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
- [Convenzioni di denominazione](../../../docs/standard/design-guidelines/naming-guidelines.md)
