---
title: Modelli di eventi deboli
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- weak event pattern implementation [WPF]
- event handlers [WPF], weak event pattern
- IWeakEventListener interface [WPF]
ms.assetid: e7c62920-4812-4811-94d8-050a65c856f6
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f96327f8eaad36f3faebf48db083125816589821
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="weak-event-patterns"></a>Modelli di eventi deboli
Nelle applicazioni, è possibile che i gestori associati alle origini eventi verranno eliminati, in coordinamento con l'oggetto listener che è associato il gestore per l'origine. Questa situazione può causare perdite di memoria. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] introduce un modello di progettazione che può essere utilizzato per risolvere questo problema, è necessario specificarne una classe di gestione dedicato per particolari eventi implementando un'interfaccia nei listener per quell'evento. Questo modello di progettazione è noto come il *modello di eventi deboli*.  
  
## <a name="why-implement-the-weak-event-pattern"></a>Per implementare il modello di eventi deboli?  
 Ascolto di eventi può causare perdite di memoria. La tecnica standard per l'ascolto di un evento consiste nell'utilizzare la sintassi specifica del linguaggio che associa un gestore a un evento su un'origine. In c#, ad esempio, la sintassi è: `source.SomeEvent += new SomeEventHandler(MyEventHandler)`.  
  
 Questa tecnica consente di creare un riferimento forte dall'origine evento per il listener di eventi. Associare un gestore eventi per un listener causa in genere, il listener per la durata che è influenzata dalla durata dell'oggetto di origine (a meno che il gestore dell'evento è stato rimosso in modo esplicito). Ma in determinate circostanze, è possibile la durata dell'oggetto del listener sia controllata da altri fattori, ad esempio, se attualmente a cui appartiene la struttura ad albero visuale dell'applicazione e non dalla durata dell'origine. Ogni volta che la durata dell'oggetto di origine si estende oltre la durata dell'oggetto del listener, lo schema di eventi normali comporta una perdita di memoria: il listener viene mantenuto attivo più a lungo del previsto.  
  
 Il modello di eventi deboli è progettato per risolvere questo problema di perdita di memoria. Ogni volta che un listener deve effettuare la registrazione per un evento, ma il listener non conosce in modo esplicito quando annullare la registrazione, è possibile utilizzare il modello di eventi deboli. Il modello di eventi deboli nonché ogni volta che la durata dell'oggetto di origine supera la durata utile del listener. (In questo caso, *utile* è determinato dall'utente.) Il modello di eventi deboli consente al listener di registrarsi e ricevere l'evento senza influire sulle caratteristiche di durata del listener in alcun modo. In effetti, il riferimento implicito dall'origine non determina se il listener è idoneo per l'operazione di garbage collection. Il riferimento è un riferimento debole, in questo modo la denominazione del modello di eventi deboli e correlata [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]. Il listener può essere l'operazione di garbage collection o altrimenti eliminato e l'origine può continuare senza mantenere riferimenti al gestore noncollectible a un oggetto ora eliminato.  
  
## <a name="who-should-implement-the-weak-event-pattern"></a>Che deve implementare il modello di eventi deboli?  
 Implementazione del modello di eventi deboli è interessante principalmente per gli autori di controlli. Come l'autore di un controllo, è responsabile in gran parte del comportamento e il contenuto del controllo e l'impatto che sul applicazioni in cui viene inserito. Ciò include il comportamento della durata degli oggetti controllo, in particolare la gestione del problema di perdita di memoria descritto.  
  
 Alcuni scenari si prestano implicitamente all'applicazione del modello di eventi deboli. Uno scenario di questo tipo è l'associazione dati. Data binding è comune per l'oggetto di origine sia completamente indipendente dell'oggetto listener, che è una destinazione di un'associazione. Molti aspetti di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] già un'associazione dati hanno lo schema di eventi deboli applicato in modalità di implementazione di eventi.  
  
## <a name="how-to-implement-the-weak-event-pattern"></a>Come implementare il modello di eventi deboli  
 Esistono tre modi per implementare il modello di eventi deboli. Nella tabella seguente sono elencati i tre approcci e fornite alcune indicazioni per quando è consigliabile utilizzarlo.  
  
|Approccio|Quando implementare|  
|--------------|-----------------------|  
|Utilizzare una classe di gestione di eventi deboli esistente|Se l'evento che si desidera eseguire la sottoscrizione ha un corrispondente <xref:System.Windows.WeakEventManager>, utilizzare la gestione di eventi deboli esistente. Per un elenco di gestori di eventi deboli incluse in WPF, vedere la gerarchia di ereditarietà nel <xref:System.Windows.WeakEventManager> classe. Si noti, tuttavia, che sono presenti relativamente pochi gestori di eventi deboli che sono inclusi in WPF, pertanto sarà probabilmente necessario scegliere uno degli approcci.|  
|Utilizzare una classe di gestione di eventi deboli generico|Utilizzare un oggetto generico <xref:System.Windows.WeakEventManager%602> quando un oggetto esistente <xref:System.Windows.WeakEventManager> non disponibile, si desidera un modo semplice per implementare e non si intende l'efficienza. Il tipo generico <xref:System.Windows.WeakEventManager%602> è meno efficace rispetto a un gestore di eventi deboli esistenti o personalizzate. Ad esempio, la classe generica non più la reflection per individuare l'evento specificato il nome dell'evento. Inoltre, il codice per registrare l'evento utilizzando il tipo generico <xref:System.Windows.WeakEventManager%602> è più dettagliato rispetto all'utilizzo di un oggetto esistente o personalizzato <xref:System.Windows.WeakEventManager>.|  
|Creare una classe di gestione di eventi deboli personalizzato|Creare una classe personalizzata <xref:System.Windows.WeakEventManager> quando un oggetto esistente <xref:System.Windows.WeakEventManager> non è disponibile e si desidera ottenere migliori prestazioni. Utilizzo di un <xref:System.Windows.WeakEventManager> per sottoscrivere un evento sarà più efficiente, ma si comportano il costo della scrittura del codice più all'inizio.|  
  
 Nelle sezioni seguenti viene descritto come implementare il modello di eventi deboli.  Ai fini di questa discussione, sottoscrivere l'evento ha le caratteristiche seguenti.  
  
-   Il nome dell'evento è `SomeEvent`.  
  
-   L'evento viene generato per la `EventSource` classe.  
  
-   Il gestore dell'evento è di tipo: `SomeEventEventHandler` (o `EventHandler<SomeEventEventArgs>`).  
  
-   L'evento passa un parametro di tipo `SomeEventEventArgs` ai gestori di eventi.  
  
### <a name="using-an-existing-weak-event-manager-class"></a>Utilizzando una classe di gestione degli eventi deboli esistente  
  
1.  Trovare un evento debole esistente di gestione.  
  
     Per un elenco di gestori di eventi deboli incluse in WPF, vedere la gerarchia di ereditarietà nel <xref:System.Windows.WeakEventManager> classe.  
  
2.  Utilizzare la gestione degli eventi debole anziché il collegamento di un evento normale.  
  
     Ad esempio, se il codice utilizza il modello seguente per sottoscrivere un evento:  
  
    ```  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     Selezionare il modello seguente:  
  
    ```  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     Analogamente, se il codice utilizza il modello seguente per annullare la sottoscrizione a un evento:  
  
    ```  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     Selezionare il modello seguente:  
  
    ```  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
### <a name="using-the-generic-weak-event-manager-class"></a>Utilizzando la classe generica di gestione degli eventi deboli  
  
1.  Utilizzare il metodo generico <xref:System.Windows.WeakEventManager%602> classe anziché il collegamento di un evento normale.  
  
     Quando si utilizza <xref:System.Windows.WeakEventManager%602> per registrare i listener di eventi, si fornisce l'origine evento e <xref:System.EventArgs> tipo dei parametri di tipo di classe e chiamare <xref:System.Windows.WeakEventManager%602.AddHandler%2A> come illustrato nel codice seguente:  
  
    ```  
    WeakEventManager<EventSource, SomeEventEventArgs>.AddHandler(source, "SomeEvent", source_SomeEvent);  
    ```  
  
### <a name="creating-a-custom-weak-event-manager-class"></a>Creazione di una classe di gestione degli eventi deboli personalizzato  
  
1.  Copiare il modello di classe seguente al progetto.  
  
     Questa classe eredita la <xref:System.Windows.WeakEventManager> classe.  
  
     [!code-csharp[WeakEvents#WeakEventManagerTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WeakEvents/CSharp/WeakEventManagerTemplate.cs#weakeventmanagertemplate)]  
  
2.  Sostituire il `SomeEventWeakEventManager` nome con il nome desiderato.  
  
3.  Sostituire i nomi di tre descritti in precedenza con i nomi corrispondenti per l'evento. (`SomeEvent`, `EventSource`, e `SomeEventEventArgs`)  
  
4.  Impostare la visibilità della classe di gestione di eventi deboli (pubblica / interna / privata) per la stessa visibilità gestisce l'evento.  
  
5.  Utilizzare la gestione degli eventi debole anziché il collegamento di un evento normale.  
  
     Ad esempio, se il codice utilizza il modello seguente per sottoscrivere un evento:  
  
    ```  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     Selezionare il modello seguente:  
  
    ```  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     Analogamente, se il codice utilizza il modello seguente per annullare la sottoscrizione a un evento:  
  
    ```  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     Selezionare il modello seguente:  
  
    ```  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.WeakEventManager>  
 <xref:System.Windows.IWeakEventListener>  
 [Cenni preliminari sugli eventi indirizzati](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [Panoramica sul data binding](../../../../docs/framework/wpf/data/data-binding-overview.md)
