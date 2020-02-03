---
title: Panoramica
ms.date: 03/30/2017
helpviewer_keywords:
- smart clients
- Windows Forms, about Windows Forms
ms.assetid: 3a2b6284-c8d6-4e1c-8c69-0bed38f38cd4
ms.openlocfilehash: c3a8394086c9d744630179b089a1f986af12b339
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734546"
---
# <a name="windows-forms-overview"></a>Panoramica di Windows Forms

Nella panoramica seguente sono illustrati i vantaggi delle applicazioni client intelligenti, le principali funzionalità della programmazione di Windows Form e come è possibile usare Windows Form per compilare client intelligenti che rispondono alle esigenze delle aziende e degli utenti finali attuali.

## <a name="windows-forms-and-smart-client-apps"></a>App Windows Forms e smart client

 Con Windows Form è possibile sviluppare applicazioni Smart Client. Gli *smart client* sono applicazioni grafiche che possono essere distribuite e aggiornate facilmente, che possono funzionare anche quando non sono collegate a Internet e che consentono di accedere alle risorse sul computer locale in maniera molto più protetta rispetto alle tradizionali applicazioni Windows.

### <a name="build-rich-interactive-user-interfaces"></a>Crea interfacce utente avanzate e interattive

 Windows Forms è una tecnologia smart client per il .NET Framework, un set di librerie gestite che semplificano le attività comuni dell'applicazione, ad esempio la lettura e la scrittura nei file system. Quando si usa un ambiente di sviluppo come Visual Studio, è possibile creare Windows Forms applicazioni smart client che visualizzano informazioni, richiedono l'input dagli utenti e comunicano con computer remoti tramite una rete.

 In Windows Forms un *modulo* è una superficie visiva sulla quale è possibile visualizzare informazioni per l'utente. Per compilare applicazioni Windows Forms, in genere si aggiungono i controlli nei form e quindi si definiscono le risposte alle azioni degli utenti, ad esempio i clic con il mouse o le pressioni dei tasti. Un *controllo* è un elemento separato dell'interfaccia utente usato per visualizzare dati o accettare input di dati.

 Quando un utente esegue un'azione nel form o in uno dei controlli, viene generato un evento. L'applicazione reagisce a tali eventi usando il codice ed elabora gli eventi quando si verificano. Per altre informazioni, vedere [Creazione di gestori eventi in Windows Forms](creating-event-handlers-in-windows-forms.md).

 Windows Form contiene diversi controlli che possono essere inseriti nei form, ad esempio i controlli che visualizzano caselle di testo, pulsanti, caselle di riepilogo a discesa, pulsanti di opzione e persino pagine Web. Per un elenco di tutti i controlli utilizzabili in un modulo, vedere [Controlli da usare in Windows Forms](./controls/controls-to-use-on-windows-forms.md). Se un controllo esistente non dovesse soddisfare le proprie esigenze, Windows Form consente anche di creare controlli personalizzati usando la classe <xref:System.Windows.Forms.UserControl>.

 Windows Form dispone di controlli UI completi che simulano le funzionalità delle applicazioni di fascia alta quali Microsoft Office. Usando i controlli <xref:System.Windows.Forms.ToolStrip> e <xref:System.Windows.Forms.MenuStrip> è possibile creare barre degli strumenti e menu contenenti testo e immagini, visualizzare sottomenu nonché includere altri controlli, ad esempio caselle di testo e caselle combinate.

 Con il trascinamento della selezione **Progettazione Windows Form** in Visual Studio, è possibile creare facilmente Windows Forms applicazioni. È sufficiente selezionare i controlli con il cursore e aggiungerli nel punto desiderato del form. Per facilitare l'allineamento dei controlli, nella finestra di progettazione vengono forniti strumenti quali linee della griglia e guide di allineamento. Se si usa Visual Studio o si compila dalla riga di comando, è possibile usare i controlli <xref:System.Windows.Forms.FlowLayoutPanel>, <xref:System.Windows.Forms.TableLayoutPanel> e <xref:System.Windows.Forms.SplitContainer> per creare layout di form avanzati in meno tempo.

 Infine, se è necessario creare elementi dell'interfaccia utente personalizzati, lo spazio dei nomi <xref:System.Drawing> contiene diverse classi che consentono di creare linee, cerchi e altre forme direttamente in un form.

> [!NOTE]
> I controlli Windows Form non sono progettati per il marshalling fra domini applicazioni. Per questo motivo, Microsoft non supporta il passaggio di un controllo Windows Form attraverso un limite di <xref:System.AppDomain>, anche se il tipo di base <xref:System.Windows.Controls.Control> di <xref:System.MarshalByRefObject> sembri indicare che ciò sia possibile. Le applicazioni Windows Forms che presentano più domini applicazioni sono supportate purché nessun controllo Windows Forms attraversi il limite di un dominio applicazione.

#### <a name="create-forms-and-controls"></a>Creazione di form e controlli

Per informazioni dettagliate sull'uso di queste funzionalità, vedere i seguenti argomenti della Guida.

|Descrizione|Argomento della Guida|
|-----------------|----------------|
|Uso dei controlli nei form|[Procedura: Aggiungere controlli a un Windows Forms](./controls/how-to-add-controls-to-windows-forms.md)|
|Uso del controllo <xref:System.Windows.Forms.ToolStrip>|[Procedura: creare un controllo ToolStrip di base con elementi standard utilizzando la finestra di progettazione](./controls/create-a-basic-wf-toolstrip-with-standard-items-using-the-designer.md)|
|Creazione di grafica con <xref:System.Drawing>|[Introduzione alla programmazione grafica](./advanced/getting-started-with-graphics-programming.md)|
|Creare controlli personalizzati|[Procedura: ereditare dalla classe UserControl](./controls/how-to-inherit-from-the-usercontrol-class.md)|

### <a name="display-and-manipulate-data"></a>Visualizzare e modificare i dati
 Molte applicazioni devono visualizzare i dati da un database, da un file XML, servizi Web XML o altre origini di dati. In Windows Form viene fornito un controllo denominato <xref:System.Windows.Forms.DataGridView> che consente di visualizzare dati tabulari in un formato tradizionale basato su righe e colonne, in modo che ciascun blocco di dati occupi una singola cella. Usando <xref:System.Windows.Forms.DataGridView> è possibile personalizzare l'aspetto delle singole celle, bloccare righe e colonne arbitrarie nonché visualizzare controlli complessi all'interno delle celle.

 Il collegamento alle origini dati tramite una rete è un'attività semplice con gli smart client Windows Form. Il componente <xref:System.Windows.Forms.BindingSource> rappresenta una connessione a un'origine dati ed espone metodi per l'associazione dei dati ai controlli, lo spostamento ai record precedenti e successivi, la modifica di record e il salvataggio delle modifiche nell'origine originale. Il controllo <xref:System.Windows.Forms.BindingNavigator> fornisce un'interfaccia semplice tramite il componente <xref:System.Windows.Forms.BindingSource> per gli utenti per spostarsi tra i record.

 È possibile creare facilmente controlli con associazione a dati usando la finestra Origini dati, in cui vengono visualizzate origini dati quali database, servizi Web e oggetti contenuti nel progetto. È possibile creare controlli associati a dati mediante il trascinamento di elementi da questa finestra nei form del progetto. È anche possibile connettere i controlli esistenti ai dati mediante il trascinamento di oggetti dalla finestra Origini dati nei controlli esistenti.

 Un altro tipo di data binding che è possibile gestire in Windows Forms sono le *impostazioni*. La maggioranza delle applicazioni client intelligenti devono conservare alcune informazioni relative al proprio stato in fase di esecuzione, ad esempio le ultime dimensioni note dei form, e conservare i dati relativi alle preferenze dell'utente, ad esempio le posizioni predefinite per i file salvati. La funzionalità Impostazioni applicazione risolve queste problematiche offrendo un modo semplice per archiviare entrambi i tipi di impostazioni sul computer client. Dopo aver definito queste impostazioni usando Visual Studio o un editor di codice, le impostazioni vengono rese permanente come XML e rilette automaticamente in memoria in fase di esecuzione.

#### <a name="display-and-manipulate-data"></a>Visualizzare e modificare i dati

Per informazioni dettagliate sull'uso di queste funzionalità, vedere i seguenti argomenti della Guida.

|Descrizione|Argomento della Guida|
|-----------------|----------------|
|Uso del componente <xref:System.Windows.Forms.BindingSource>|[Procedura: associare controlli Windows Forms al componente BindingSource usando la finestra di progettazione](./controls/bind-wf-controls-with-the-bindingsource.md)|
|Uso delle origini dati ADO.NET|[Procedura: ordinare e filtrare i dati ADO.NET con il componente BindingSource Windows Forms](./controls/sort-and-filter-ado-net-data-with-wf-bindingsource-component.md)|
|Uso della finestra Origini dati|[Associare controlli Windows Form ai dati in Visual Studio](/visualstudio/data-tools/bind-windows-forms-controls-to-data-in-visual-studio)|
|Uso delle impostazioni dell'applicazione|[Procedura: Creare le impostazioni applicazione](./advanced/how-to-create-application-settings.md)|

### <a name="deploy-apps-to-client-computers"></a>Distribuire le app nei computer client

Una volta scritta, l'applicazione deve essere inviata agli utenti in modo che possano installarla ed eseguirla sui propri client. Quando si usa la tecnologia ClickOnce, è possibile distribuire le applicazioni dall'interno di Visual Studio con pochi clic e fornire agli utenti un URL che punta all'applicazione sul Web. ClickOnce gestisce tutti gli elementi e le dipendenze dell'applicazione e garantisce che l'applicazione sia installata correttamente nel computer client.

Le applicazioni ClickOnce possono essere configurate per essere eseguite solo quando l'utente è connesso alla rete oppure per l'esecuzione sia online che offline. Quando si specifica che un'applicazione deve supportare l'operazione offline, ClickOnce aggiunge un collegamento all'applicazione nel menu **Start** dell'utente. In questo modo, l'utente può aprire l'applicazione senza usare l'URL.

Quando si aggiorna l'applicazione, vengono pubblicati un nuovo manifesto della distribuzione e una nuova copia dell'applicazione sul server Web. ClickOnce rileverà che è disponibile un aggiornamento e aggiornerà l'installazione dell'utente. non è necessaria alcuna programmazione personalizzata per aggiornare gli assembly precedenti.

#### <a name="deploy-clickonce-apps"></a>Distribuire app ClickOnce

Per un'introduzione completa a ClickOnce, vedere [sicurezza e distribuzione di ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment). Per informazioni dettagliate sull'uso di queste funzionalità, vedere i seguenti argomenti della Guida.

|Descrizione|Argomento della Guida|
|-----------------|----------------|
|Distribuzione di un'applicazione tramite ClickOnce|[Procedura: Pubblicare un'applicazione ClickOnce mediante la Pubblicazione guidata](/visualstudio/deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard)<br /><br /> [Procedura dettagliata: distribuzione manuale di un'applicazione ClickOnce](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application)|
|Aggiornamento di una distribuzione ClickOnce|[Procedura: Gestire gli aggiornamenti per un'applicazione ClickOnce](/visualstudio/deployment/how-to-manage-updates-for-a-clickonce-application)|
|Gestione della sicurezza con ClickOnce|[Procedura: Abilitare le impostazioni di sicurezza ClickOnce](/visualstudio/deployment/how-to-enable-clickonce-security-settings)|

### <a name="other-controls-and-features"></a>Altri controlli e funzionalità

Windows Form dispone di altre funzioni che rendono le comuni attività di implementazione estremamente semplici e rapide, quali il supporto per la creazione di caselle di dialogo, la stampa, l'aggiunta della Guida e la documentazione, la localizzazione dell'applicazione in diverse lingue. Inoltre, Windows Forms si basa sul sistema di sicurezza affidabile del .NET Framework. Questo assicura la massima affidabilità delle applicazioni distribuite ai clienti.

#### <a name="implement-other-controls-and-features"></a>Implementare altri controlli e funzionalità

Per informazioni dettagliate sull'uso di queste funzionalità, vedere i seguenti argomenti della Guida.

|Descrizione|Argomento della Guida|
|-----------------|----------------|
|Stampa del contenuto di un form|[Procedura: stampare grafica in Windows Forms](./advanced/how-to-print-graphics-in-windows-forms.md)<br /><br /> [Procedura: stampare un file di testo con più pagine in Windows Forms](./advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)|
|Altre informazioni sulla sicurezza di Windows Form|[Panoramica della sicurezza in Windows Forms](security-in-windows-forms-overview.md)|

## <a name="see-also"></a>Vedere anche

- [Guida introduttiva a Windows Form](getting-started-with-windows-forms.md)
- [Creazione di un nuovo Windows Form](creating-a-new-windows-form.md)
- [Panoramica sul controllo ToolStrip](./controls/toolstrip-control-overview-windows-forms.md)
- [Panoramica sul controllo DataGridView](./controls/datagridview-control-overview-windows-forms.md)
- [Cenni preliminari sul componente BindingSource](./controls/bindingsource-component-overview.md)
- [Cenni preliminari sulle impostazioni delle applicazioni](./advanced/application-settings-overview.md)
- [Sicurezza e distribuzione di ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment)
