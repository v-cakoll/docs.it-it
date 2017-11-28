---
title: Nomi di membri dei tipi
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- events [.NET Framework], names
- methods [.NET Framework], names
- type members
- properties [.NET Framework], names
- fields, names
- field names
- names [.NET Framework], type members
- members [.NET Framework], type
ms.assetid: af5a0903-36af-4c2a-b848-cf959affeaa5
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1a3460b734d5bab6f5362fa9d3631e06821f6d49
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="names-of-type-members"></a>Nomi di membri dei tipi
I tipi sono costituiti da membri: metodi, proprietà, eventi, costruttori e campi. Le sezioni seguenti descrivono le linee guida per la denominazione dei membri di tipo.  
  
## <a name="names-of-methods"></a>Nomi dei metodi  
 Poiché i metodi sono il mezzo di un'azione intrapresa, linee guida di progettazione richiedono che i nomi di metodo verbi o frasi di verbo. Di queste indicazioni inoltre viene usato per distinguere i nomi di metodo da nomi di proprietà e il tipo, ovvero sostantivo o aggettivo frasi.  
  
 **✓ SI** assegnare nomi di metodi che sono verbi o frasi di verbo.  
  
```  
public class String {  
    public int CompareTo(...);  
    public string[] Split(...);  
    public string Trim();  
}  
```  
  
## <a name="names-of-properties"></a>Nomi delle proprietà  
 A differenza di altri membri, è necessario assegnare proprietà sintagma nominale o nomi aggettivali. Ciò avviene perché una proprietà fa riferimento a dati e il nome della proprietà corrisponde a quello. Il sistema Pascal viene sempre utilizzato per i nomi delle proprietà.  
  
 **✓ SI** nome proprietà tramite un sostantivo, un sintagma nominale o un aggettivo.  
  
 **X non** dispongono di proprietà che corrispondono al nome dei metodi "Get" come nell'esempio seguente:  
  
 `public string TextWriter { get {...} set {...} }`  
 `public string GetTextWriter(int value) { ... }`  
  
 Questo modello è in genere indica che la proprietà deve essere effettivamente un metodo.  
  
 **✓ SI** nome di proprietà della raccolta con una plurale frase che descrive gli elementi della raccolta anziché una frase singolare, seguita da "List" o "Collection".  
  
 **✓ SI** proprietà booleane con una frase affermativa (`CanSeek` anziché `CantSeek`). Facoltativamente, è possibile anteporre anche le proprietà booleane con "Is", "può" o "Include" ma solo se aggiunge valore.  
  
 **Provare a ✓** assegnare lo stesso nome di tipo a una proprietà.  
  
 Ad esempio, la proprietà seguente correttamente viene impostato un valore di enumerazione denominato `Color`, pertanto la proprietà è denominata `Color`:  
  
```  
public enum Color {...}  
public class Control {  
    public Color Color { get {...} set {...} }  
}  
```  
  
## <a name="names-of-events"></a>Nomi degli eventi  
 Gli eventi si riferiscono sempre a un'azione, un problema o che si è verificato. Pertanto, come con i metodi, eventi sono denominati con i verbi e al tempo di verbi viene utilizzato per indicare l'ora quando viene generato l'evento.  
  
 **✓ SI** denominare eventi con un verbo o una frase del verbo.  
  
 Gli esempi includono `Clicked`, `Painting`, `DroppedDown`e così via.  
  
 **✓ SI** assegnare i nomi degli eventi con un concetto di prima e dopo, utilizzando il presente e passato tempi.  
  
 Ad esempio, un evento di chiusura che viene generato prima della chiusura di una finestra deve essere chiamato `Closing`, e uno che viene generato dopo la chiusura di finestra deve essere chiamato `Closed`.  
  
 **X non** utilizzare "Before" o "After" prefissi o suffissi per indicare pre- e post-eventi. Usare presente e passato tempi come descritto in precedenza.  
  
 **✓ SI** denominare i gestori eventi (delegati utilizzati come tipi di eventi) con il suffisso "EventHandler", come illustrato nell'esempio seguente:  
  
 `public delegate void ClickedEventHandler(object sender, ClickedEventArgs e);`  
  
 **✓ SI** utilizzare due parametri denominati `sender` e `e` nei gestori eventi.  
  
 Il parametro mittente rappresenta l'oggetto che ha generato l'evento. Il parametro mittente è in genere di tipo `object`, anche se è possibile utilizzare un tipo più specifico.  
  
 **✓ SI** nome evento classi di argomenti con il suffisso "EventArgs".  
  
## <a name="names-of-fields"></a>Nomi dei campi  
 Le convenzioni di denominazione per campo si applicano ai campi statici pubblici e protetti. I campi interni e privati non coperti dalle linee guida e i campi di istanza pubblici o protetti non sono consentiti dal [indicazioni per la progettazione di membro](../../../docs/standard/design-guidelines/member.md).  
  
 **✓ SI** utilizzare il sistema Pascal nei nomi di campo.  
  
 **✓ SI** nome campi utilizzando un sostantivo, un sintagma nominale o un aggettivo.  
  
 **X non** utilizzare un prefisso per i nomi dei campi.  
  
 Ad esempio, non utilizzare "g _" o "s _" per indicare i campi statici.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)  
 [Convenzioni di denominazione](../../../docs/standard/design-guidelines/naming-guidelines.md)
