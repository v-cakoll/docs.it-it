---
title: Modelli di eventi deboli
description: Informazioni sul modello di evento Windows Presentation Foundation debole, che risolve il problema dei gestori che non vengono eliminati definitivamente, evitando perdite di memoria.
ms.date: 03/30/2017
helpviewer_keywords:
- weak event pattern implementation [WPF]
- event handlers [WPF], weak event pattern
- IWeakEventListener interface [WPF]
ms.assetid: e7c62920-4812-4811-94d8-050a65c856f6
ms.openlocfilehash: 75c6888c8ac20c41d13e3787005377c75248c5d9
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168272"
---
# <a name="weak-event-patterns"></a>Modelli di eventi deboli
Nelle applicazioni è possibile che i gestori collegati alle origini eventi non vengano eliminati in modo coordinato con l'oggetto listener che ha collegato il gestore all'origine. Questa situazione può causare perdite di memoria. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]introduce uno schema progettuale che può essere usato per risolvere questo problema, fornendo una classe Manager dedicata per determinati eventi e implementando un'interfaccia nei listener per tale evento. Questo schema progettuale è noto come *modello di eventi deboli*.  
  
## <a name="why-implement-the-weak-event-pattern"></a>Perché implementare il modello di eventi deboli?  
 L'ascolto degli eventi può causare perdite di memoria. La tecnica tipica per l'ascolto di un evento consiste nell'usare la sintassi specifica del linguaggio che connette un gestore a un evento in un'origine. In C#, ad esempio, la sintassi è: `source.SomeEvent += new SomeEventHandler(MyEventHandler)` .  
  
 Questa tecnica crea un riferimento sicuro dall'origine evento al listener di eventi. In genere, il fissaggio di un gestore eventi per un listener fa sì che il listener abbia una durata degli oggetti influenzato dalla durata dell'oggetto dell'origine (a meno che il gestore eventi non venga rimosso in modo esplicito). In alcuni casi, tuttavia, potrebbe essere necessario controllare la durata dell'oggetto del listener da altri fattori, ad esempio se appartiene attualmente alla struttura ad albero visuale dell'applicazione e non alla durata dell'origine. Ogni volta che la durata dell'oggetto di origine supera la durata dell'oggetto del listener, il modello di evento normale causa una perdita di memoria: il listener viene mantenuto attivo più a lungo del previsto.  
  
 Il modello di eventi vulnerabili è progettato per risolvere questo problema di perdita di memoria. Il modello di eventi vulnerabili può essere usato ogni volta che un listener deve registrarsi per un evento, ma il listener non sa in modo esplicito quando annullare la registrazione. Il modello di eventi vulnerabili può essere utilizzato anche ogni volta che la durata dell'oggetto dell'origine supera la durata utile dell'oggetto del listener. (In questo caso, l' *utilità* è determinata dall'utente). Il modello di eventi vulnerabili consente al listener di registrarsi e ricevere l'evento senza influire in alcun modo sulle caratteristiche di durata degli oggetti del listener. In effetti, il riferimento implicito dall'origine non determina se il listener è idoneo per Garbage Collection. Il riferimento è un riferimento debole, quindi la denominazione del modello di eventi deboli e le API correlate. Il listener può essere sottoposta a Garbage Collection o eliminato in altro modo e l'origine può continuare senza mantenere i riferimenti al gestore non ritirabili a un oggetto distrutto.  
  
## <a name="who-should-implement-the-weak-event-pattern"></a>Chi deve implementare il modello di eventi deboli?  
 L'implementazione del modello di eventi vulnerabili è particolarmente interessante per gli autori di controlli. In qualità di autore del controllo, l'utente è in gran parte responsabile del comportamento e del contenimento del controllo e dell'incidenza sulle applicazioni in cui viene inserito. Questo include il comportamento di controllo della durata degli oggetti, in particolare la gestione del problema di perdita di memoria descritto.  
  
 Determinati scenari si prestano intrinsecamente all'applicazione del modello di eventi deboli. Uno scenario di questo tipo è data binding. In data binding, è normale che l'oggetto di origine sia completamente indipendente dall'oggetto listener, che è la destinazione di un'associazione. Molti aspetti di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Data Binding hanno già il modello di eventi deboli applicato nella modalità di implementazione degli eventi.  
  
## <a name="how-to-implement-the-weak-event-pattern"></a>Come implementare il modello di eventi deboli  
 Esistono tre modi per implementare il modello di eventi deboli. Nella tabella seguente sono elencati i tre approcci e vengono fornite alcune indicazioni per l'utilizzo di ciascuno di essi.  
  
|Approccio|Quando implementare|  
|--------------|-----------------------|  
|Usa una classe di gestione degli eventi vulnerabili esistente|Se l'evento a cui si desidera eseguire la sottoscrizione ha un corrispondente <xref:System.Windows.WeakEventManager> , utilizzare il gestore eventi vulnerabile esistente. Per un elenco di gestori di eventi vulnerabili inclusi in WPF, vedere la gerarchia di ereditarietà nella <xref:System.Windows.WeakEventManager> classe. Poiché i gestori di eventi deboli inclusi sono limitati, probabilmente sarà necessario scegliere uno degli altri approcci.|  
|Usare una classe generica di gestione eventi debole|Usare un oggetto generico <xref:System.Windows.WeakEventManager%602> quando <xref:System.Windows.WeakEventManager> non è disponibile una esistente, si vuole un modo semplice per implementare e non si è interessati all'efficienza. Il generico <xref:System.Windows.WeakEventManager%602> è meno efficiente di un gestore di eventi vulnerabile esistente o personalizzato. La classe generica, ad esempio, esegue più reflection per individuare l'evento in base al nome dell'evento. Inoltre, il codice per registrare l'evento usando il generico <xref:System.Windows.WeakEventManager%602> è più dettagliato rispetto all'uso di un oggetto esistente o personalizzato <xref:System.Windows.WeakEventManager> .|  
|Creare una classe personalizzata di gestione eventi vulnerabili|Creare un'personalizzata <xref:System.Windows.WeakEventManager> quando <xref:System.Windows.WeakEventManager> non è disponibile una esistente e si desidera ottenere la migliore efficienza. L'uso di un oggetto personalizzato <xref:System.Windows.WeakEventManager> per sottoscrivere un evento è più efficiente, ma comporta il costo di scrivere altro codice all'inizio.|  
|Usare un gestore eventi vulnerabile di terze parti|NuGet dispone di [diversi gestori di eventi vulnerabili](https://www.nuget.org/packages?q=weak+event+manager&prerel=false) e molti framework WPF supportano anche il modello (ad esempio, vedere la [documentazione di Prisma sulla sottoscrizione di eventi a regime di controllo libero](https://github.com/PrismLibrary/Prism-Documentation/blob/master/docs/wpf/legacy/Communication.md#subscribing-to-events)).|

 Le sezioni seguenti descrivono come implementare il modello di eventi deboli.  Ai fini di questa discussione, l'evento da sottoscrivere presenta le caratteristiche seguenti.  
  
- Il nome dell'evento è `SomeEvent` .  
  
- L'evento viene generato dalla `EventSource` classe.  
  
- Il gestore eventi è di tipo: `SomeEventEventHandler` (o `EventHandler<SomeEventEventArgs>` ).  
  
- L'evento passa un parametro di tipo `SomeEventEventArgs` ai gestori eventi.  
  
### <a name="using-an-existing-weak-event-manager-class"></a>Utilizzo di una classe di gestione eventi debole esistente  
  
1. Trovare un gestore eventi vulnerabile esistente.  
  
     Per un elenco di gestori di eventi vulnerabili inclusi in WPF, vedere la gerarchia di ereditarietà nella <xref:System.Windows.WeakEventManager> classe.  
  
2. Utilizzare il nuovo gestore eventi debole anziché il normale collegamento evento.  
  
     Ad esempio, se il codice usa il modello seguente per sottoscrivere un evento:  
  
    ```csharp  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     Modificare il modello nel modo seguente:  
  
    ```csharp  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     Analogamente, se il codice usa il modello seguente per annullare la sottoscrizione di un evento:  
  
    ```csharp  
    source.SomeEvent -= new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     Modificare il modello nel modo seguente:  
  
    ```csharp  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
### <a name="using-the-generic-weak-event-manager-class"></a>Uso della classe generica di gestione eventi debole  
  
1. Usare la classe generica <xref:System.Windows.WeakEventManager%602> anziché il normale collegamento evento.  
  
     Quando si usa <xref:System.Windows.WeakEventManager%602> per registrare i listener di eventi, è necessario fornire l'origine e il tipo di evento <xref:System.EventArgs> come parametri di tipo alla classe e chiamare <xref:System.Windows.WeakEventManager%602.AddHandler%2A> come illustrato nel codice seguente:  
  
    ```csharp  
    WeakEventManager<EventSource, SomeEventEventArgs>.AddHandler(source, "SomeEvent", source_SomeEvent);  
    ```  
  
### <a name="creating-a-custom-weak-event-manager-class"></a>Creazione di una classe personalizzata di gestione eventi vulnerabili  
  
1. Copiare il modello di classe seguente nel progetto.  
  
     Questa classe eredita dalla <xref:System.Windows.WeakEventManager> classe.  
  
     [!code-csharp[WeakEvents#WeakEventManagerTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/WeakEvents/CSharp/WeakEventManagerTemplate.cs#weakeventmanagertemplate)]  
  
2. Sostituire il `SomeEventWeakEventManager` nome con il proprio nome.  
  
3. Sostituire i tre nomi descritti in precedenza con i nomi corrispondenti per l'evento. ( `SomeEvent` , `EventSource` e `SomeEventEventArgs` )  
  
4. Impostare la visibilità (pubblica/interna/privata) della classe del gestore eventi debole sulla stessa visibilità dell'evento gestito.  
  
5. Utilizzare il nuovo gestore eventi debole anziché il normale collegamento evento.  
  
     Ad esempio, se il codice usa il modello seguente per sottoscrivere un evento:  
  
    ```csharp  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     Modificare il modello nel modo seguente:  
  
    ```csharp  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     Analogamente, se il codice usa il modello seguente per annullare la sottoscrizione di un evento:  
  
    ```csharp  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     Modificare il modello nel modo seguente:  
  
    ```csharp  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.WeakEventManager>
- <xref:System.Windows.IWeakEventListener>
- [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md)
- [Panoramica sul data binding](../../../desktop-wpf/data/data-binding-overview.md)
