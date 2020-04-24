---
title: Nozioni fondamentali relative alle applicazioni Windows Form
ms.date: 07/20/2015
helpviewer_keywords:
- Windows applications
- Windows Forms, Visual Basic
ms.assetid: 0b919d30-7fd6-42db-85c8-543d15312441
ms.openlocfilehash: 1aa1edf0130e388c6cc87662d83591f41a8e2325
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349155"
---
# <a name="windows-forms-application-basics-visual-basic"></a>Nozioni fondamentali relative alle applicazioni Windows Forms (Visual Basic)

Una parte importante del Visual Basic è la possibilità di creare Windows Forms applicazioni eseguite localmente sui computer degli utenti. È possibile usare Visual Studio per creare l'applicazione e l'interfaccia utente usando Windows Forms. Un Windows Forms Application viene compilato in base alle classi <xref:System.Windows.Forms> dello spazio dei nomi.

## <a name="designing-windows-forms-applications"></a>Progettazione di applicazioni Windows Forms

È possibile creare applicazioni di servizio Windows Forms e Windows con Visual Studio. Per altre informazioni, vedere gli argomenti seguenti:

- [Introduzione con Windows Forms](../../../framework/winforms/getting-started-with-windows-forms.md). Vengono fornite informazioni su come creare e programmare Windows Forms.

- [Controlli Windows Forms](../../../framework/winforms/controls/index.md). Raccolta di argomenti che illustrano in dettaglio l'uso dei controlli Windows Forms.

- [Applicazioni di servizio Windows](../../../framework/windows-services/index.md). Vengono elencati gli argomenti che illustrano come creare i servizi Windows.

## <a name="building-rich-interactive-user-interfaces"></a>Compilazione di interfacce utente complete e interattive

Windows Forms è il componente smart client della .NET Framework, un set di librerie gestite che consentono attività comuni dell'applicazione, ad esempio la lettura e la scrittura nei file system. Usando un ambiente di sviluppo come Visual Studio, è possibile creare Windows Forms applicazioni che visualizzano informazioni, richiedono l'input dagli utenti e comunicano con computer remoti tramite una rete.

In Windows Form un form è una superficie visiva sulla quale è possibile visualizzare informazioni per l'utente. In genere si compilano Windows Forms applicazioni posizionando i controlli sui moduli e sviluppando le risposte alle azioni dell'utente, ad esempio clic del mouse o pressione del tasto. Un *controllo* è un elemento separato dell'interfaccia utente usato per visualizzare dati o accettare input di dati.

### <a name="events"></a>Events

Quando un utente esegue un'operazione nel form o in uno dei relativi controlli, genera un evento. L'applicazione reagisce a tali eventi usando il codice ed elabora gli eventi quando si verificano. Per altre informazioni, vedere [Creazione di gestori eventi in Windows Forms](../../../framework/winforms/creating-event-handlers-in-windows-forms.md).

### <a name="controls"></a>Controlli

Windows Forms contiene un'ampia gamma di controlli che è possibile inserire nei form: controlli che visualizzano caselle di testo, pulsanti, caselle di riepilogo a discesa, pulsanti di opzione e persino pagine Web. Per un elenco di tutti i controlli utilizzabili in un modulo, vedere [Controlli da usare in Windows Forms](../../../framework/winforms/controls/controls-to-use-on-windows-forms.md). Se un controllo esistente non dovesse soddisfare le proprie esigenze, Windows Form consente anche di creare controlli personalizzati usando la classe <xref:System.Windows.Forms.UserControl>.

Windows Form dispone di controlli UI completi che simulano le funzionalità delle applicazioni di fascia alta quali Microsoft Office. Con il <xref:System.Windows.Forms.ToolStrip> controllo <xref:System.Windows.Forms.MenuStrip> e è possibile creare barre degli strumenti e menu contenenti testo e immagini, visualizzare sottomenu e ospitare altri controlli, ad esempio caselle di testo e caselle combinate.

Con la finestra di progettazione dei form di Visual Studio con trascinamento della selezione è possibile creare facilmente Windows Forms applicazioni: è sufficiente selezionare i controlli con il cursore e posizionarli nel punto desiderato del form. Nella finestra di progettazione vengono forniti strumenti quali linee della griglia e "linee di allineamento" che semplificano l'allineamento dei controlli. Se si usa Visual Studio o si compila dalla riga di comando, è possibile usare i <xref:System.Windows.Forms.FlowLayoutPanel>controlli <xref:System.Windows.Forms.TableLayoutPanel> , <xref:System.Windows.Forms.SplitContainer> e per creare layout di form avanzati con tempi e sforzi minimi.

### <a name="custom-ui-elements"></a>Elementi dell'interfaccia utente personalizzati

Infine, se è necessario creare elementi dell'interfaccia utente personalizzati, lo <xref:System.Drawing> spazio dei nomi contiene tutte le classi necessarie per eseguire il rendering di righe, cerchi e altre forme direttamente in un form.

Per informazioni dettagliate sull'uso di queste funzionalità, vedere gli argomenti della guida seguenti.

|A|Vedere|
|--------|---------|
|Creare una nuova Windows Forms Application con Visual Studio|[Esercitazione 1: creare un visualizzatore di immagini](/visualstudio/ide/tutorial-1-create-a-picture-viewer)|
|Usare i controlli nei moduli|[Procedura: aggiungere controlli a un Windows Form](../../../framework/winforms/controls/how-to-add-controls-to-windows-forms.md)|
|Crea grafica con<xref:System.Drawing>|[Introduzione alla programmazione grafica](../../../framework/winforms/advanced/getting-started-with-graphics-programming.md)|
|Creare controlli personalizzati|[Procedura: Ereditare dalla classe UserControl](../../../framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)|

## <a name="displaying-and-manipulating-data"></a>Visualizzazione e modifica dei dati

Molte applicazioni devono visualizzare i dati da un database, da un file XML, servizi Web XML o altre origini di dati. Windows Forms fornisce un controllo flessibile denominato controllo <xref:System.Windows.Forms.DataGridView> per il rendering di tali dati tabulari in un formato di riga e di colonna tradizionale, in modo che ogni porzione di dati occupi una propria cella. Utilizzando <xref:System.Windows.Forms.DataGridView> è possibile personalizzare l'aspetto delle singole celle, bloccare righe e colonne arbitrarie e visualizzare controlli complessi all'interno delle celle, tra le altre funzionalità.

Il collegamento alle origini dati tramite una rete è un'attività semplice con gli smart client Windows Form. Il <xref:System.Windows.Forms.BindingSource> componente, nuovo con Windows Forms in Visual Studio 2005 e .NET Framework 2,0, rappresenta una connessione a un'origine dati ed espone metodi per l'associazione di dati ai controlli, lo spostamento ai record precedenti e successivi, la modifica di record e il salvataggio delle modifiche nell'origine originale. Il controllo <xref:System.Windows.Forms.BindingNavigator> fornisce un'interfaccia semplice tramite il componente <xref:System.Windows.Forms.BindingSource> per gli utenti per spostarsi tra i record.

### <a name="data-bound-controls"></a>Controlli con associazione a dati

È possibile creare facilmente controlli con associazione a dati utilizzando la finestra Origini dati, in cui vengono visualizzate origini dati quali database, servizi Web e oggetti nel progetto. È possibile creare controlli associati a dati mediante il trascinamento di elementi da questa finestra nei form del progetto. È anche possibile connettere i controlli esistenti ai dati mediante il trascinamento di oggetti dalla finestra Origini dati nei controlli esistenti.

### <a name="settings"></a>Impostazioni

Un altro tipo di data binding che è possibile gestire in Windows Form sono le impostazioni. La maggior parte delle applicazioni smart client deve conservare alcune informazioni sullo stato della fase di esecuzione, ad esempio le ultime dimensioni note dei form, e conservare i dati relativi alle preferenze dell'utente, ad esempio i percorsi predefiniti per i file salvati. La funzionalità Impostazioni applicazione soddisfa questi requisiti, offrendo un modo semplice per archiviare entrambi i tipi di impostazioni nel computer client. Una volta definito utilizzando Visual Studio o un editor di codice, queste impostazioni vengono rese permanente come XML e rilette automaticamente in memoria in fase di esecuzione.

Per informazioni dettagliate sull'uso di queste funzionalità, vedere gli argomenti della guida seguenti.

|A|Vedere|
|--------|---------|
|Usa il <xref:System.Windows.Forms.BindingSource> componente|[Procedura: associare controlli Windows Form al componente BindingSource utilizzando la finestra di progettazione](../../../framework/winforms/controls/bind-wf-controls-with-the-bindingsource.md)|
|Usare le origini dati di ADO.NET|[Procedura: ordinare e filtrare i dati ADO.NET con il componente BindingSource Windows Form](../../../framework/winforms/controls/sort-and-filter-ado-net-data-with-wf-bindingsource-component.md)|
|Utilizzare la finestra Origini dati|[Procedura dettagliata: visualizzazione di dati in un Windows Form](/visualstudio/data-tools/accessing-data-in-visual-studio)|

## <a name="deploying-applications-to-client-computers"></a>Distribuzione delle applicazioni ai client

Una volta scritta, l'applicazione deve essere inviata agli utenti in modo che possano installarla ed eseguirla sui propri computer client. Utilizzando la tecnologia ClickOnce, è possibile distribuire le applicazioni dall'interno di Visual Studio utilizzando solo pochi clic e fornire agli utenti un URL che punta all'applicazione sul Web. ClickOnce gestisce tutti gli elementi e le dipendenze dell'applicazione e garantisce che l'applicazione sia installata correttamente nel computer client.

Le applicazioni ClickOnce possono essere configurate per essere eseguite solo quando l'utente è connesso alla rete oppure per l'esecuzione sia online che offline. Quando si specifica che un'applicazione deve supportare l'operazione offline, ClickOnce aggiunge un collegamento all'applicazione nel menu **Start** dell'utente, in modo che l'utente possa aprirlo senza usare l'URL.

Quando si aggiorna l'applicazione, vengono pubblicati un nuovo manifesto della distribuzione e una nuova copia dell'applicazione sul server Web. ClickOnce rileva che è disponibile un aggiornamento e aggiorna l'installazione dell'utente; non è necessaria alcuna programmazione personalizzata per aggiornare gli assembly precedenti.

Per un'introduzione completa a ClickOnce, vedere [sicurezza e distribuzione di ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment). Per informazioni dettagliate sull'uso di queste funzionalità, vedere gli argomenti della guida seguenti:

|A|Vedere|
|--------|---------|
|Distribuire un'applicazione con ClickOnce|[Procedura: Pubblicare un'applicazione ClickOnce mediante la Pubblicazione guidata](/visualstudio/deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard)<br /><br /> [Procedura dettagliata: distribuzione manuale di un'applicazione ClickOnce](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application)|
|Aggiornare una distribuzione ClickOnce|[Procedura: gestire gli aggiornamenti per un'applicazione ClickOnce](/visualstudio/deployment/how-to-manage-updates-for-a-clickonce-application)|
|Gestione della sicurezza con ClickOnce|[Procedura: abilitare le impostazioni di sicurezza ClickOnce](/visualstudio/deployment/how-to-enable-clickonce-security-settings)|

## <a name="other-controls-and-features"></a>Altri controlli e funzionalità

Windows Form dispone di altre funzioni che rendono le comuni attività di implementazione estremamente semplici e rapide, quali il supporto per la creazione di caselle di dialogo, la stampa, l'aggiunta della Guida e la documentazione, la localizzazione dell'applicazione in diverse lingue. Inoltre, Windows Forms si basa sul sistema di sicurezza affidabile del .NET Framework, consentendo di rilasciare applicazioni più sicure per i clienti.

Per informazioni dettagliate sull'uso di queste funzionalità, vedere gli argomenti della guida seguenti:

|A|Vedere|
|--------|---------|
|Stampa il contenuto di un form|[Procedura: stampare grafica in Windows Forms](../../../framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)<br /><br /> [Procedura: stampare un file di testo con più pagine in Windows Form](../../../framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)|
|Altre informazioni sulla sicurezza di Windows Form|[Cenni preliminari sulla sicurezza in Windows Form](../../../framework/winforms/security-in-windows-forms-overview.md)|

## <a name="see-also"></a>Vedi anche

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- [Panoramica sui Windows Form](../../../framework/winforms/windows-forms-overview.md)
- [Oggetto My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md)
