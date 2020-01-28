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
ms.openlocfilehash: 81c837bd045992043208a59f6ee16803c1d6eb3c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744185"
---
# <a name="names-of-type-members"></a>Nomi di membri dei tipi
I tipi sono costituiti da membri: metodi, proprietà, eventi, costruttori e campi. Le sezioni seguenti illustrano le linee guida per assegnare nomi ai membri dei tipi.

## <a name="names-of-methods"></a>Nomi dei metodi
 I metodi sono il mezzo per l'esecuzione delle azioni. Pertanto le linee guida di progettazione richiedono che i nomi dei metodi siano verbi o frasi verbali. L'osservazione di questa linea guida è anche utile per distinguere i nomi dei metodi dai nomi delle proprietà e dei tipi, che sono frasi nominali o aggettivali.

 ✔️ assegnare i nomi dei metodi che sono verbi o frasi verbo.

```csharp
public class String {
    public int CompareTo(...);
    public string[] Split(...);
    public string Trim();
}
```

## <a name="names-of-properties"></a>Nomi delle proprietà
 A differenza degli altri membri, è necessario assegnare alle proprietà sintagmi nominali o nomi aggettivali. Il motivo è che una proprietà fa riferimento ai dati e il nome della proprietà deve riflettere questo fatto. Per i nomi delle proprietà viene sempre usata la notazione Pascal.

 ✔️ le proprietà del nome usando un sostantivo, una frase nominale o un aggettivo.

 ❌ non dispongono di proprietà corrispondenti al nome dei metodi "Get", come nell'esempio seguente:

 `public string TextWriter { get {...} set {...} }` `public string GetTextWriter(int value) { ... }`

 Questo criterio in genere indica che la proprietà dovrebbe di fatto essere un metodo.

 ✔️ ESEGUIRE le proprietà della raccolta dei nomi con una frase plurale che descrive gli elementi nella raccolta invece di usare una frase singolare seguita da "list" o "Collection".

 ✔️ denominare le proprietà booleane con una frase affermativa (`CanSeek` invece di `CantSeek`). Facoltativamente, è anche possibile precedere le proprietà booleane con "is", "Can" o "has", ma solo dove viene aggiunto value.

 ✔️ PROVARE a assegnare a una proprietà lo stesso nome del tipo.

 Ad esempio, la proprietà seguente ottiene e imposta correttamente un valore di enumerazione denominato `Color`, pertanto è denominata `Color`:

```csharp
public enum Color {...}
public class Control {
    public Color Color { get {...} set {...} }
}
```

## <a name="names-of-events"></a>Nomi degli eventi
 Gli eventi fanno sempre riferimento a un'azione, che può essere in corso o già terminata. Pertanto, come nel caso dei metodi, i nomi degli eventi devono essere verbi e il tempo verbale indica il momento in cui viene generato l'evento.

 ✔️ ESEGUIRE gli eventi di denominazione con un verbo o una frase verbo.

 Alcuni esempi sono `Clicked`, `Painting` o `DroppedDown`.

 ✔️ assegnare i nomi degli eventi con un concetto di prima e dopo, usando le decine attuali e precedenti.

 Ad esempio, un evento di chiusura generato prima della chiusura di una finestra può essere chiamato `Closing`, mentre uno generato dopo la chiusura della finestra può essere chiamato `Closed`.

 ❌ non usare prefissi o postcorrezioni "before" o "After" per indicare gli eventi pre-e post-post. Usare il presente e il passato come descritto in precedenza.

 ✔️ i gestori eventi dei nomi (delegati usati come tipi di eventi) con il suffisso "EventHandler", come illustrato nell'esempio seguente:

 `public delegate void ClickedEventHandler(object sender, ClickedEventArgs e);`

 ✔️ utilizzare due parametri denominati `sender` e `e` nei gestori di eventi.

 Il parametro sender rappresenta l'oggetto che ha generato l'evento. Il parametro sender è in genere di tipo `object`, anche se è possibile usare un tipo più specifico.

 ✔️ le classi di argomenti dell'evento Name con il suffisso "EventArgs".

## <a name="names-of-fields"></a>Nomi dei campi
 Le linee guida per i nomi dei campi si applicano ai campi statici pubblici e protetti. I campi interni e privati non sono descritti in queste linee guida, mentre i campi istanza pubblica o istanza protetta non sono consentiti dalle [linee guida di progettazione dei membri](../../../docs/standard/design-guidelines/member.md).

 ✔️ utilizzare sistema Pascal nei nomi dei campi.

 ✔️ i campi nome usando un sostantivo, una frase nominale o un aggettivo.

 ❌ non utilizzano un prefisso per i nomi dei campi.

 Ad esempio evitare di usare "g_" o "s _" per indicare i campi statici.

 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*

 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*

## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
- [Convenzioni di denominazione](../../../docs/standard/design-guidelines/naming-guidelines.md)
