---
title: Gestione e generazione di eventi
description: Informazioni su come gestire e generare eventi .NET basati sul modello delegato. Questo modello consente ai sottoscrittori di eseguire la registrazione o ricevere notifiche dai provider.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- delegate model for events
- application development [.NET], events
- application development [.NET Framework], events
- application development [.NET Core], events
- events [.NET]
- events [.NET Core]
- events [.NET Framework]
ms.assetid: b6f65241-e0ad-4590-a99f-200ce741bb1f
ms.openlocfilehash: 8cf0ff323e9bf7305e3d9cbb6dabd8f685059e97
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2020
ms.locfileid: "84447108"
---
# <a name="handling-and-raising-events"></a>Gestione e generazione di eventi

Gli eventi in .NET si basano sul modello di delegato. Il modello di delegato segue lo [schema progettuale osservatore](observer-design-pattern.md), che consente a un sottoscrittore di effettuare la registrazione con e ricevere notifiche da un provider. Un mittente dell'evento esegue il push di una notifica di evento, mentre un ricevitore di eventi riceve la notifica e definisce una risposta. In questo articolo viene descritto come implementare gli eventi nel codice, come usare gli eventi nelle applicazioni e i componenti principali del modello di delegato.  
  
 Per informazioni sulla gestione di eventi nelle applicazioni Windows 8.x Store, vedere la pagina relativa alla [Panoramica degli eventi e degli eventi indirizzati](https://docs.microsoft.com/previous-versions/windows/apps/hh758286(v=win.10)).  
  
## <a name="events"></a>Eventi

Un evento è un messaggio inviato da un oggetto per segnalare l'occorrenza di un'azione. L'azione può essere causata dall'interazione dell'utente, ad esempio il clic su un pulsante, oppure essere il risultato di altre logiche di programma, ad esempio la modifica di un valore della proprietà. L'oggetto che genera l'evento viene chiamato *mittente dell'evento*. Il mente dell'evento non sa quale oggetto o metodo riceverà (handle) gli eventi che egli genera. L'evento è in genere un membro del mittente dell'evento. Ad esempio, l'evento <xref:System.Web.UI.WebControls.Button.Click> è un membro della classe <xref:System.Web.UI.WebControls.Button> e l'evento <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> è un membro della classe che implementa l'interfaccia <xref:System.ComponentModel.INotifyPropertyChanged>.  
  
Per definire un evento, usare la [`event`](../../csharp/language-reference/keywords/event.md) parola chiave C# o Visual Basic [`Event`](../../visual-basic/language-reference/statements/event-statement.md) nella firma della classe di evento e specificare il tipo di delegato per l'evento. I delegati vengono descritti nella sezione successiva.  
  
In genere, per generare un evento, aggiungere un metodo contrassegnato come `protected` e `virtual` (in C#) o `Protected` e `Overridable` (in Visual Basic). Denominare il metodo `On`*NomeEvento*; ad esempio, `OnDataReceived`. Il metodo deve accettare un parametro che specifica un oggetto dati dell'evento, ovvero un oggetto di tipo <xref:System.EventArgs> o un tipo derivato. Fornire questo metodo per consentire alle classi derivate di sostituire la logica per la generazione dell'evento. Affinché l'evento sia ricevuto da delegati registrati, occorre che tramite una classe derivata venga sempre chiamato il metodo `On`*NomeEvento* della classe di base.  

Nell'esempio riportato di seguito viene illustrato come dichiarare un evento denominato `ThresholdReached`. L'evento è associato al delegato<xref:System.EventHandler> e generato in un metodo denominato `OnThresholdReached`.  
  
 [!code-csharp[EventsOverview#1](~/samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programtruncated.cs#1)]
 [!code-vb[EventsOverview#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1truncated.vb#1)]  
  
## <a name="delegates"></a>Delegati

Un delegato è un tipo che contiene un riferimento a un metodo. Un delegato è dichiarato con una firma che mostra il tipo restituito e i parametri per i metodi a cui fa riferimento e può contenere riferimenti solo ai metodi che corrispondono alla firma. Un delegato è pertanto equivalente a un puntatore a funzione indipendente dai tipi o un callback. Una dichiarazione di delegato è sufficiente per definire una classe delegata.  
  
Sono molti gli usi dei delegati in .NET. Nel contesto degli eventi, un delegato è un intermediario (o meccanismo di tipo puntatore) tra l'origine evento e il codice che gestisce l'evento. Associare un delegato a un evento, incluso il tipo di delegato nella dichiarazione di evento, come illustrato nell'esempio nella sezione precedente. Per altre informazioni sui delegati, vedere la classe <xref:System.Delegate>.  
  
.NET fornisce i delegati <xref:System.EventHandler> e <xref:System.EventHandler%601> per supportare la maggior parte degli scenari per gli eventi. Usare il delegato <xref:System.EventHandler> per tutti gli eventi che non includono dati dell'evento. Usare il delegato <xref:System.EventHandler%601> per eventi che includono dati sull'evento. Questi delegati non hanno alcun valore di tipo restituito e accettano due parametri (un oggetto per l'origine dell'evento e un oggetto per i dati dell'evento).  
  
I delegati sono [multicast](xref:System.MulticastDelegate), il che significa che possono mantenere riferimenti a più di un metodo di gestione degli eventi. Per informazioni dettagliate, vedere la pagina di riferimento per <xref:System.Delegate>. I delegati offrono flessibilità e controlli specifici nella gestione degli eventi. Un delegato agisce come un dispatcher di eventi per la classe che genera l'evento compilando un elenco di gestori eventi registrati per l'evento.  
  
Per gli scenari in cui i delegati <xref:System.EventHandler> e <xref:System.EventHandler%601> non sono appropriati, è possibile definire un delegato. Gli scenari che richiedono di definire un delegato sono molto rari, ad esempio quando è necessario lavorare con un codice che non riconosce i generics. Si contrassegna un delegato con la [`delegate`](../../csharp/language-reference/builtin-types/reference-types.md#the-delegate-type) parola chiave C# e Visual Basic [`Delegate`](../../visual-basic/language-reference/statements/delegate-statement.md) nella dichiarazione. Nell'esempio riportato di seguito viene illustrato come dichiarare un delegato denominato `ThresholdReachedEventHandler`.  
  
[!code-csharp[EventsOverview#4](~/samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programtruncated.cs#4)]
[!code-vb[EventsOverview#4](~/samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1truncated.vb#4)]  
  
## <a name="event-data"></a>Dati dell'evento

I dati associati a un evento possono essere forniti tramite una classe di dati eventi. .NET fornisce molte classi di dati eventi che possono essere usate nelle applicazioni. Ad esempio, la classe <xref:System.IO.Ports.SerialDataReceivedEventArgs> è la classe di dati eventi per l'evento <xref:System.IO.Ports.SerialPort.DataReceived?displayProperty=nameWithType>. .NET segue un modello di denominazione che prevede di terminare tutte le classi di dati eventi con `EventArgs`. È possibile determinare quale classe di dati eventi è associata a un evento esaminando il delegato per tale evento. Ad esempio, il delegato <xref:System.IO.Ports.SerialDataReceivedEventHandler> include la classe <xref:System.IO.Ports.SerialDataReceivedEventArgs> come uno dei relativi parametri.  
  
La classe <xref:System.EventArgs> è il tipo base per tutte le classi di dati eventi. <xref:System.EventArgs> è anche la classe usata quando a un evento non sono stati associati dati. Quando si crea un evento il cui solo scopo è quello di segnalare ad altre classi che si è verificato qualcosa e non è necessario passare i dati, includere la classe <xref:System.EventArgs> come secondo parametro nel delegato. È possibile passare il valore <xref:System.EventArgs.Empty?displayProperty=nameWithType> quando non viene fornito alcun dato. Il delegato <xref:System.EventHandler> include la classe <xref:System.EventArgs> come parametro.  
  
Quando si vuole creare una classe di dati eventi personalizzata, creare una classe che deriva da <xref:System.EventArgs> e quindi specificare i membri necessari per passare i dati correlati all'evento. In genere, è necessario usare lo stesso modello di denominazione di .NET e terminare il nome della classe di dati eventi con `EventArgs`.  
  
Nell'esempio seguente viene illustrata una classe di dati eventi denominata `ThresholdReachedEventArgs`. Contiene le proprietà specifiche per l'evento generato.  
  
[!code-csharp[EventsOverview#3](~/samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programtruncated.cs#3)]
[!code-vb[EventsOverview#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1truncated.vb#3)]  
  
## <a name="event-handlers"></a>Gestori eventi

Per rispondere a un evento, definire un metodo del gestore eventi nel ricevitore di eventi. Questo metodo deve corrispondere alla firma del delegato per l'evento gestito. Nel gestore eventi eseguire le azioni necessarie quando viene generato l'evento, ad esempio la raccolta dell'input quando un utente fa clic su un pulsante. Per ricevere notifiche quando si verifica l'evento, il metodo del gestore eventi deve sottoscrivere l'evento.  
  
Nell'esempio seguente viene illustrato un metodo del gestore eventi denominato `c_ThresholdReached` che corrisponde alla firma per il delegato <xref:System.EventHandler>. Il metodo sottoscrive l'evento `ThresholdReached`.  
  
[!code-csharp[EventsOverview#2](~/samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programtruncated.cs#2)]
[!code-vb[EventsOverview#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1truncated.vb#2)]  
  
## <a name="static-and-dynamic-event-handlers"></a>Gestori eventi statici e dinamici  

.NET consente ai sottoscrittori di registrarsi per le notifiche degli eventi in modo statico o dinamico. I gestori eventi statici sono attivi per l'intera durata della classe di cui gestiscono gli eventi. I gestori eventi dinamici sono attivati e disattivati in modo esplicito durante l'esecuzione del programma, in genere in risposta a una logica di programma condizionale. Ad esempio, possono essere usati se le notifiche degli eventi sono necessarie solo in determinate condizioni oppure se un'applicazione fornisce più gestori eventi e le condizioni di runtime definiscono quello appropriato da usare. Nell'esempio della sezione precedente viene illustrato come aggiungere un gestore eventi in modo dinamico. Per altre informazioni, vedere [Eventi (Visual Basic)](../../visual-basic/programming-guide/language-features/events/index.md) e [Eventi (Guida per programmatori C#)](../../csharp/programming-guide/events/index.md).  
  
## <a name="raising-multiple-events"></a>Generazione di più eventi  
 Se la propria classe genera più eventi, il compilatore genera un campo per ogni istanza del delegato di evento. Se il numero di eventi è elevato, il costo di archiviazione di un campo per ciascun delegato non è sostenibile. Per questi casi, .NET fornisce le proprietà evento che è possibile usare con un'altra struttura di dati di propria scelta per archiviare i delegati degli eventi.  
  
 Le proprietà dell'evento sono costituite da dichiarazioni di eventi accompagnate dalle funzioni di accesso agli eventi. Queste funzioni sono metodi che consentono di aggiungere o rimuovere istanze del delegato di evento dalla struttura di dati di archiviazione. Si noti che le proprietà evento sono più lente rispetto ai campi evento, perché ogni delegato dell'evento deve essere recuperato prima di poter essere richiamato. Il compromesso è tra memoria e velocità. Se la classe definisce molti eventi che vengono generati di rado, sarà necessario implementare le proprietà degli eventi. Per altre informazioni, vedere [Procedura: gestire più eventi mediante le relative proprietà](how-to-handle-multiple-events-using-event-properties.md).  
  
## <a name="related-topics"></a>Argomenti correlati  
  
|Titolo|Descrizione|  
|-----------|-----------------|  
|[Procedura: generare e utilizzare eventi](how-to-raise-and-consume-events.md)|Contiene esempi di generazione e uso di eventi.|  
|[Procedura: gestire più eventi mediante le relative proprietà](how-to-handle-multiple-events-using-event-properties.md)|Viene illustrato come usare le proprietà degli eventi per gestire più eventi.|  
|[Modello di progettazione Observer](observer-design-pattern.md)|Viene descritto lo schema progettuale che consente a un sottoscrittore di effettuare la registrazione con e ricevere notifiche da un provider.|  
|[Procedura: Usare eventi in un'applicazione Web Form](how-to-consume-events-in-a-web-forms-application.md)|Viene illustrato come gestire un evento generato da un controllo Web Form.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.EventHandler>
- <xref:System.EventHandler%601>
- <xref:System.EventArgs>
- <xref:System.Delegate>
- [Eventi (Visual Basic)](../../visual-basic/programming-guide/language-features/events/index.md)
- [Eventi (Guida per programmatori C#)](../../csharp/programming-guide/events/index.md)
- [Panoramica degli eventi e degli eventi indirizzati (app UWP)](/windows/uwp/xaml-platform/events-and-routed-events-overview)
