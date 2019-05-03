---
title: Modelli di eventi deboli
ms.date: 03/30/2017
helpviewer_keywords:
- weak event pattern implementation [WPF]
- event handlers [WPF], weak event pattern
- IWeakEventListener interface [WPF]
ms.assetid: e7c62920-4812-4811-94d8-050a65c856f6
ms.openlocfilehash: e0cd6837de626fa6bcd560811c6a70f7f6604daa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61669363"
---
# <a name="weak-event-patterns"></a>Modelli di eventi deboli
Nelle applicazioni, è possibile che i gestori associati alle origini evento non verranno distrutto in combinazione con l'oggetto listener che è associato il gestore per l'origine. Questa situazione può causare perdite di memoria. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] introduce un modello di progettazione che può essere utilizzato per risolvere questo problema, fornendo una classe di gestione dedicato per determinati eventi e implementando un'interfaccia nei listener per l'evento. Questo schema progettuale è noto come il *modello di eventi deboli*.  
  
## <a name="why-implement-the-weak-event-pattern"></a>Il motivo per cui implementare il modello di eventi deboli?  
 In ascolto degli eventi può causare perdite di memoria. La tecnica tipica per l'ascolto di un evento consiste nell'usare la sintassi specifica del linguaggio che associa un gestore a un evento su un'origine. Ad esempio, in C#, che la sintassi è: `source.SomeEvent += new SomeEventHandler(MyEventHandler)`.  
  
 Questa tecnica consente di creare un riferimento sicuro dall'origine evento per il listener di eventi. In genere, collegare un gestore eventi per un listener, fa sì che il listener avere una durata degli oggetti che è influenzata dalla durata dell'oggetto di origine (a meno che il gestore eventi viene rimosso in modo esplicito). Ma in alcune circostanze, potrebbe essere consigliabile la durata dell'oggetto del listener da parte di altri fattori, ad esempio se attualmente a cui appartiene la struttura ad albero visuale dell'applicazione e non dalla durata dell'origine. Ogni volta che la durata dell'oggetto di origine si estende oltre la durata dell'oggetto del listener, il modello di eventi normali comporta una perdita di memoria: il listener viene mantenuto attivo più a lungo del previsto.  
  
 Il modello di eventi deboli è progettato per risolvere questo problema di perdita di memoria. Il modello di eventi deboli può essere usato ogni volta che un listener deve effettuare la registrazione per un evento, ma il listener non sa in modo esplicito quando annullare la registrazione. Il modello di eventi deboli può essere usato anche ogni volta che la durata dell'oggetto di origine supera la durata utile del listener. (In questo caso *utile* è determinato dall'utente.) Il modello di eventi deboli consente il listener per registrarsi e ricevere l'evento senza influire sulle caratteristiche di durata del listener in alcun modo. In effetti, il riferimento implicito dall'origine non determina se il listener è idoneo per garbage collection. Il riferimento è un riferimento debole, in questo modo la denominazione del modello di eventi deboli e i relativi [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]. Il listener può essere garbage collection o altrimenti eliminato e l'origine può continuare senza mantenere riferimenti al gestore creare per un oggetto ora eliminato.  
  
## <a name="who-should-implement-the-weak-event-pattern"></a>Chi deve implementare il modello di eventi deboli?  
 Implementazione del pattern di eventi deboli è interessante principalmente per gli autori di controlli. Quando si crea un controllo, si è in gran parte responsabile per il comportamento e il contenimento del proprio controllo e l'impatto che ha su applicazioni in cui viene inserito. Ciò include il comportamento della durata degli oggetti controllo, in particolare la gestione del problema di perdita di memoria descritta.  
  
 Alcuni scenari intrinsecamente si prestano all'applicazione del modello di eventi deboli. Uno di questi scenari è l'associazione dati. Nel data binding, è comune per l'oggetto di origine sia completamente indipendente da dell'oggetto del listener, ovvero una destinazione di un'associazione. Molti aspetti di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] un data binding già sono il modello di eventi deboli applicato nel modo in cui vengono implementati gli eventi.  
  
## <a name="how-to-implement-the-weak-event-pattern"></a>Come implementare il modello di eventi deboli  
 Esistono tre modi per implementare il modello di eventi deboli. Nella tabella seguente sono elencati tre approcci e fornisce alcune linee guida per quando è consigliabile utilizzarlo.  
  
|Approccio|Quando implementare|  
|--------------|-----------------------|  
|Usare una classe di gestione di eventi deboli esistente|Se l'evento che si desidera eseguire la sottoscrizione ha un corrispondente <xref:System.Windows.WeakEventManager>, usare il gestore di eventi deboli esistente. Per un elenco di gestori di eventi deboli incluse in WPF, vedere la gerarchia di ereditarietà nel <xref:System.Windows.WeakEventManager> classe. Poiché i gestori di eventi deboli incluso sono limitati, probabilmente sarà necessario scegliere uno degli altri approcci.|  
|Usare una classe di gestione di eventi deboli generico|Usare un oggetto generico <xref:System.Windows.WeakEventManager%602> quando un oggetto esistente <xref:System.Windows.WeakEventManager> sono non disponibile, è necessario un modo semplice per implementare e non si è preoccupati dell'efficienza. Il tipo generico <xref:System.Windows.WeakEventManager%602> è meno efficiente rispetto a un gestore di eventi deboli esistenti o personalizzate. Ad esempio, la classe generica non più la reflection per individuare l'evento specificato il nome dell'evento. Inoltre, il codice per registrare l'evento utilizzando il tipo generico <xref:System.Windows.WeakEventManager%602> è più dettagliato rispetto all'uso di un oggetto esistente o personalizzato <xref:System.Windows.WeakEventManager>.|  
|Creare una classe di gestione di eventi deboli personalizzato|Creare una classe personalizzata <xref:System.Windows.WeakEventManager> quando un oggetto esistente <xref:System.Windows.WeakEventManager> non è disponibile e si desidera che un sistema più efficiente. Usando un oggetto personalizzato <xref:System.Windows.WeakEventManager> per sottoscrivere un evento sarà più efficiente, ma è necessario sostenere il costo di scrivere altro codice all'inizio.|  
|Usare un gestore di eventi deboli di terze parti|NuGet ha [alcuni gestori di eventi deboli](https://www.nuget.org/packages?q=weak+event+manager&prerel=false) e molti framework WPF supportano anche il modello (ad esempio, vedere [documentazione di Prism nella sottoscrizione di eventi loosely-coupled](https://github.com/PrismLibrary/Prism-Documentation/blob/master/docs/wpf/Communication.md#subscribing-to-events)).|

 Le sezioni seguenti descrivono come implementare il modello di eventi deboli.  Ai fini di questa discussione, l'evento da sottoscrivere presenta le caratteristiche seguenti.  
  
- Il nome dell'evento è `SomeEvent`.  
  
- L'evento viene generato dal `EventSource` classe.  
  
- Il gestore dell'evento è di tipo: `SomeEventEventHandler` (o `EventHandler<SomeEventEventArgs>`).  
  
- L'evento passato un parametro di tipo `SomeEventEventArgs` ai gestori eventi.  
  
### <a name="using-an-existing-weak-event-manager-class"></a>Usando una classe di gestore di eventi deboli esistente  
  
1. Trovare un evento debole esistente di gestione.  
  
     Per un elenco di gestori di eventi deboli incluse in WPF, vedere la gerarchia di ereditarietà nel <xref:System.Windows.WeakEventManager> classe.  
  
2. Utilizzare la gestione degli eventi debole anziché l'associazione dell'evento normale.  
  
     Ad esempio, se il codice Usa il modello seguente per sottoscrivere un evento:  
  
    ```  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     Sostituirlo con il modello seguente:  
  
    ```  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     Analogamente, se il codice Usa il modello seguente per annullare la sottoscrizione a un evento:  
  
    ```  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     Sostituirlo con il modello seguente:  
  
    ```  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
### <a name="using-the-generic-weak-event-manager-class"></a>Usando la classe generica di gestione degli eventi deboli  
  
1. Usare il tipo generico <xref:System.Windows.WeakEventManager%602> classe invece l'associazione dell'evento normale.  
  
     Quando si usa <xref:System.Windows.WeakEventManager%602> per registrare i listener di eventi, è specificare l'origine evento e <xref:System.EventArgs> tipo dei parametri di tipo di classe e chiamare <xref:System.Windows.WeakEventManager%602.AddHandler%2A> come illustrato nel codice seguente:  
  
    ```  
    WeakEventManager<EventSource, SomeEventEventArgs>.AddHandler(source, "SomeEvent", source_SomeEvent);  
    ```  
  
### <a name="creating-a-custom-weak-event-manager-class"></a>Creazione di una classe di gestione di eventi deboli personalizzato  
  
1. Copiare il modello di classe seguente al progetto.  
  
     Questa classe eredita dal <xref:System.Windows.WeakEventManager> classe.  
  
     [!code-csharp[WeakEvents#WeakEventManagerTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/WeakEvents/CSharp/WeakEventManagerTemplate.cs#weakeventmanagertemplate)]  
  
2. Sostituire il `SomeEventWeakEventManager` nome con il proprio nome.  
  
3. Sostituire i nomi di tre descritti in precedenza con i nomi corrispondenti per l'evento. (`SomeEvent`, `EventSource`, e `SomeEventEventArgs`)  
  
4. Impostare la visibilità (pubblica / interna / privata) della classe della gestione di eventi deboli per eventi che gestisce la stessa visibilità.  
  
5. Utilizzare la gestione degli eventi debole anziché l'associazione dell'evento normale.  
  
     Ad esempio, se il codice Usa il modello seguente per sottoscrivere un evento:  
  
    ```  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     Sostituirlo con il modello seguente:  
  
    ```  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     Analogamente, se il codice Usa il modello seguente per annullare la sottoscrizione a un evento:  
  
    ```  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     Sostituirlo con il modello seguente:  
  
    ```  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.WeakEventManager>
- <xref:System.Windows.IWeakEventListener>
- [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md)
- [Panoramica sul data binding](../data/data-binding-overview.md)
