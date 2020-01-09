---
title: Nomi di membri dei tipi
ms.date: 10/22/2008
ms.technology: dotnet-standard
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
ms.openlocfilehash: a9cd531100057fbad4884a20e6e7db6ef94e7956
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709218"
---
# <a name="names-of-type-members"></a>Nomi di membri dei tipi
I tipi sono costituiti da membri: metodi, proprietà, eventi, costruttori e campi. Le sezioni seguenti illustrano le linee guida per assegnare nomi ai membri dei tipi.  
  
## <a name="names-of-methods"></a>Nomi dei metodi  
 I metodi sono il mezzo per l'esecuzione delle azioni. Pertanto le linee guida di progettazione richiedono che i nomi dei metodi siano verbi o frasi verbali. L'osservazione di questa linea guida è anche utile per distinguere i nomi dei metodi dai nomi delle proprietà e dei tipi, che sono frasi nominali o aggettivali.  
  
 **✓ DO** Assegnare ai metodi nomi corrispondenti a verbi o frasi verbali.  
  
```csharp  
public class String {  
    public int CompareTo(...);  
    public string[] Split(...);  
    public string Trim();  
}  
```  
  
## <a name="names-of-properties"></a>Nomi delle proprietà  
 A differenza degli altri membri, è necessario assegnare alle proprietà sintagmi nominali o nomi aggettivali. Il motivo è che una proprietà fa riferimento ai dati e il nome della proprietà deve riflettere questo fatto. Per i nomi delle proprietà viene sempre usata la notazione Pascal.  
  
 **✓ DO** Denominare le proprietà con un sostantivo, un sintagma nominale o un aggettivo.  
  
 **X DO NOT** Definire proprietà il cui nome corrisponde a quello dei metodi "Get", come nell'esempio seguente:  
  
 `public string TextWriter { get {...} set {...} }`  
 `public string GetTextWriter(int value) { ... }`  
  
 Questo criterio in genere indica che la proprietà dovrebbe di fatto essere un metodo.  
  
 **✓** Assegnare un nome alle proprietà della raccolta con una frase plurale che descrive gli elementi nella raccolta invece di usare una frase singolare seguita da "list" o "Collection".  
  
 **✓ DO** Assegnare alle proprietà booleane una frase affermativa (`CanSeek` invece di `CantSeek`). Facoltativamente, è anche possibile precedere le proprietà booleane con "is", "Can" o "has", ma solo dove viene aggiunto value.  
  
 **✓ CONSIDER** Assegnare a una proprietà lo stesso nome del tipo della proprietà.  
  
 Ad esempio, la proprietà seguente ottiene e imposta correttamente un valore di enumerazione denominato `Color`, pertanto è denominata `Color`:  
  
```csharp  
public enum Color {...}  
public class Control {  
    public Color Color { get {...} set {...} }  
}  
```  
  
## <a name="names-of-events"></a>Nomi degli eventi  
 Gli eventi fanno sempre riferimento a un'azione, che può essere in corso o già terminata. Pertanto, come nel caso dei metodi, i nomi degli eventi devono essere verbi e il tempo verbale indica il momento in cui viene generato l'evento.  
  
 **✓ DO** Assegnare agli eventi nomi corrispondenti a verbi o frasi verbali.  
  
 Alcuni esempi sono `Clicked`, `Painting` o `DroppedDown`.  
  
 **✓ DO** Assegnare agli eventi nomi che includano il concetto di prima e dopo, usando il presente e il passato.  
  
 Ad esempio, un evento di chiusura generato prima della chiusura di una finestra può essere chiamato `Closing`, mentre uno generato dopo la chiusura della finestra può essere chiamato `Closed`.  
  
 **X DO NOT** Usare prefissi o suffissi "Before" o "After" per indicare eventi precedenti o successivi ad altri elementi. Usare il presente e il passato come descritto in precedenza.  
  
 **✓ DO** Assegnare ai gestori dell'evento (delegati usati come tipi di eventi) il suffisso "EventHandler", come illustrato nell'esempio seguente:  
  
 `public delegate void ClickedEventHandler(object sender, ClickedEventArgs e);`  
  
 **✓ DO** Usare due parametri denominati `sender` e `e` nei gestori dell'evento.  
  
 Il parametro sender rappresenta l'oggetto che ha generato l'evento. Il parametro sender è in genere di tipo `object`, anche se è possibile usare un tipo più specifico.  
  
 **✓ DO** Denominare le classi di argomenti dell'evento con il suffisso "EventArgs".  
  
## <a name="names-of-fields"></a>Nomi dei campi  
 Le linee guida per i nomi dei campi si applicano ai campi statici pubblici e protetti. I campi interni e privati non sono descritti in queste linee guida, mentre i campi istanza pubblica o istanza protetta non sono consentiti dalle [linee guida di progettazione dei membri](../../../docs/standard/design-guidelines/member.md).  
  
 **✓ DO** Usare la notazione Pascal nei nomi dei campi.  
  
 **✓ DO** Denominare i campi con un sostantivo, un sintagma nominale o un aggettivo.  
  
 **X DO NOT** Usare un prefisso per i nomi dei campi.  
  
 Ad esempio evitare di usare "g_" o "s _" per indicare i campi statici.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
- [Convenzioni di denominazione](../../../docs/standard/design-guidelines/naming-guidelines.md)
