---
title: Nozioni fondamentali relative alle applicazioni Windows Forms (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Windows applications
- Windows Forms, Visual Basic
ms.assetid: 0b919d30-7fd6-42db-85c8-543d15312441
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: aaa7fbd679eceea53a673646173dc14dc4f209bc
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="windows-forms-application-basics-visual-basic"></a>Nozioni fondamentali relative alle applicazioni Windows Forms (Visual Basic)
Una parte importante di Visual Basic è la possibilità di creare applicazioni Windows Forms eseguite localmente nei computer degli utenti. È possibile utilizzare Visual Studio per creare l'applicazione e interfaccia utente tramite Windows Form. Un'applicazione Windows Forms è basata su classi di <xref:System.Windows.Forms> dello spazio dei nomi.  
  
## <a name="designing-windows-forms-applications"></a>Progettazione Windows Form di applicazioni  
 È possibile creare Windows Form e applicazioni di servizio Windows con [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]. Per altre informazioni, vedere i seguenti argomenti:  
  
-   [Introduzione a Windows Form](../../../framework/winforms/getting-started-with-windows-forms.md). Fornisce informazioni su come creare e programmare i Windows Form.  
   
-   [Controlli Windows Form](../../../framework/winforms/controls/index.md). Raccolta di argomenti che riporta in dettaglio l'uso di controlli Windows Form.  
  
-   [Applicazioni di servizio Windows](../../../framework/windows-services/index.md). Vengono elencati argomenti che illustrano come creare servizi Windows.  
  
## <a name="building-rich-interactive-user-interfaces"></a>Compilazione di interfacce utente complete e interattive  
 Windows Form è il componente smart client del [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], un set di librerie gestite che consentono l'esecuzione di attività comuni quali la lettura e scrittura nel file System. Uso di un ambiente di sviluppo come [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)], è possibile creare applicazioni Windows Form che visualizzano informazioni, richiedono l'input dagli utenti e comunicano con i computer remoti in rete.  
  
 In Windows Form, un modulo è una superficie visiva sulla quale è possibile visualizzare informazioni all'utente. Per compilare applicazioni Windows Form, inserire i controlli nel form e sviluppare le risposte alle azioni utente, ad esempio clic del mouse o le pressioni dei tasti. Un *controllo* è un elemento separato dell'interfaccia utente usato per visualizzare dati o accettare input di dati.  
  
### <a name="events"></a>Eventi  
 Quando un utente esegue un'operazione nel form o uno dei relativi controlli, viene generato un evento. L'applicazione reagisce a tali eventi usando il codice ed elabora gli eventi quando si verificano. Per altre informazioni, vedere [Creazione di gestori eventi in Windows Forms](../../../framework/winforms/creating-event-handlers-in-windows-forms.md).  
  
### <a name="controls"></a>Controlli  
 Windows Form contiene diversi controlli che è possibile inserire nei form: i controlli che visualizzano caselle di testo, pulsanti, caselle di riepilogo a discesa, pulsanti di opzione e persino pagine Web. Per un elenco di tutti i controlli utilizzabili in un modulo, vedere [Controlli da usare in Windows Forms](../../../framework/winforms/controls/controls-to-use-on-windows-forms.md). Se un controllo esistente non dovesse soddisfare le proprie esigenze, Windows Form consente anche di creare controlli personalizzati usando la classe <xref:System.Windows.Forms.UserControl>.  
  
 Windows Form dispone di controlli UI completi che simulano le funzionalità delle applicazioni di fascia alta quali Microsoft Office. Utilizzo di <xref:System.Windows.Forms.ToolStrip> e <xref:System.Windows.Forms.MenuStrip> (controllo), è possibile creare barre degli strumenti e menu contengono testo e immagini, visualizzare sottomenu nonché includere altri controlli, ad esempio caselle di testo e caselle combinate.  
  
 Con il [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] progettazione form di trascinamento e rilascio, è possibile creare facilmente applicazioni Windows Form: è sufficiente selezionare i controlli con il cursore e posizionarli in cui si desidera nel form. La finestra di progettazione vengono forniti strumenti quali linee della griglia e "snap" per facilitare l'allineamento di controlli. Sia che si usi [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] o di compilazione dalla riga di comando, è possibile utilizzare il <xref:System.Windows.Forms.FlowLayoutPanel>, <xref:System.Windows.Forms.TableLayoutPanel> e <xref:System.Windows.Forms.SplitContainer> controlli per creare avanzate di layout con meno tempo di form.  
  
### <a name="custom-ui-elements"></a>Elementi dell'interfaccia utente personalizzata  
 Infine, se è necessario creare elementi dell'interfaccia utente personalizzati, il <xref:System.Drawing> spazio dei nomi contiene tutte le classi che è necessario eseguire il rendering delle linee, cerchi e altre forme direttamente in un form.  
  
 Per informazioni dettagliate sull'utilizzo di queste funzionalità, vedere gli argomenti della Guida seguente.  
  
|A|Vedere|  
|--------|---------|  
|Creare una nuova applicazione Windows Form con [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]|[Procedura dettagliata: Creazione di un Windows Form semplice](http://msdn.microsoft.com/library/2d9daec0-0543-41d0-acb1-964f685bddbb)|  
|Utilizzare i controlli nel form|[Procedura: Aggiungere controlli a un Windows Forms](../../../framework/winforms/controls/how-to-add-controls-to-windows-forms.md)|   
|Creare la grafica con <xref:System.Drawing>|[Introduzione alla programmazione grafica](../../../framework/winforms/advanced/getting-started-with-graphics-programming.md)|  
|Creare controlli personalizzati|[Procedura: Ereditare dalla classe UserControl](../../../framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)|  
  
## <a name="displaying-and-manipulating-data"></a>Visualizzazione e modifica dei dati  
 Molte applicazioni devono visualizzare i dati da un database, da un file XML, servizi Web XML o altre origini di dati. Windows Form fornisce un controllo flessibile denominato il <xref:System.Windows.Forms.DataGridView> controllo per il rendering di dati tabulari in un formato di riga e colonna tradizionali, in modo che tutti i dati occupano una cella. Utilizzando <xref:System.Windows.Forms.DataGridView> è possibile personalizzare l'aspetto delle singole celle, bloccare righe e colonne presenti arbitrarie e visualizzare controlli complessi all'interno delle celle, tra le altre funzionalità.  
  
 Il collegamento alle origini dati tramite una rete è un'attività semplice con gli smart client Windows Form. Il componente <xref:System.Windows.Forms.BindingSource>, una novità di Windows Form in [!INCLUDE[vsprvslong](~/includes/vsprvslong-md.md)] e [!INCLUDE[dnprdnlong](~/includes/dnprdnlong-md.md)], rappresenta una connessione a un'origine dati ed espone metodi per l'associazione di dati a controlli, lo spostamento ai record precedenti e successivi, la modifica di record e il salvataggio delle modifiche fino all'origine iniziale. Il controllo <xref:System.Windows.Forms.BindingNavigator> fornisce un'interfaccia semplice tramite il componente <xref:System.Windows.Forms.BindingSource> per gli utenti per spostarsi tra i record.  
  
### <a name="data-bound-controls"></a>Controlli con associazione a dati  
 È possibile creare controlli associati a dati con facilità utilizzando la finestra Origini dati, che consente di visualizzare origini dati quali database, servizi Web e gli oggetti nel progetto. È possibile creare controlli associati a dati mediante il trascinamento di elementi da questa finestra nei form del progetto. È anche possibile connettere i controlli esistenti ai dati mediante il trascinamento di oggetti dalla finestra Origini dati nei controlli esistenti.  
  
### <a name="settings"></a>Impostazioni  
 Un altro tipo di associazione di dati che è possibile gestire in Windows Form sono le impostazioni. La maggior parte delle applicazioni smart client devono conservare alcune informazioni relative allo stato di runtime, ad esempio le ultime dimensioni note dei form e conservare i dati di preferenza dell'utente, ad esempio i percorsi predefiniti per i file salvati. La funzionalità Impostazioni applicazione risolve queste problematiche offrendo un modo semplice per archiviare entrambi i tipi di impostazioni del computer client. Una volta definite mediante [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] o un editor di codice, queste impostazioni vengono mantenute come XML e lette automaticamente in memoria in fase di esecuzione.  
  
 Per informazioni dettagliate sull'utilizzo di queste funzionalità, vedere gli argomenti della Guida seguente.  
  
|A|Vedere|  
|--------|---------|  
|Utilizzare il <xref:System.Windows.Forms.BindingSource> componente|[Procedura: associare controlli Windows Forms al componente BindingSource usando la finestra di progettazione](../../../framework/winforms/controls/bind-wf-controls-with-the-bindingsource.md)|  
|Lavorare con [!INCLUDE[vstecado](~/includes/vstecado-md.md)] origini dati|[Procedura: ordinare e filtrare i dati ADO.NET con il componente BindingSource Windows Forms](https://msdn.microsoft.com/library/ya3sah92.aspx)|  
|Utilizzare la finestra Origini dati|[Procedura dettagliata: visualizzazione di dati in un Windows Form](/visualstudio/data-tools/accessing-data-in-visual-studio)|  
  
## <a name="deploying-applications-to-client-computers"></a>Distribuzione delle applicazioni ai client  
 Dopo aver scritto l'applicazione, è necessario inviarlo agli utenti in modo che possano installarla ed eseguirla sui propri computer client. Utilizzo di [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] tecnologia, è possibile distribuire le applicazioni dall'interno [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] utilizzando solo pochi clic e fornire agli utenti con un URL che punta all'applicazione sul Web. [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] gestisce tutti gli elementi e le dipendenze dell'applicazione e garantisce che l'applicazione sia installato correttamente nel computer client.  
  
 Le applicazioni [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] possono essere configurate per essere eseguite solo quando l'utente è connesso alla rete oppure per essere eseguite sia online che offline. Quando si specifica che un'applicazione deve supportare l'operazione non in linea, [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] aggiunge un collegamento all'applicazione dell'utente **avviare** menu, in modo che l'utente possa aprirlo senza utilizzare l'URL.  
  
 Quando si aggiorna l'applicazione, vengono pubblicati un nuovo manifesto della distribuzione e una nuova copia dell'applicazione sul server Web. [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] rileva che è disponibile un aggiornamento e aggiorna l'installazione dell'utente; Nessuna programmazione personalizzata è necessario per aggiornare gli assembly precedenti.  
  
 Per un'introduzione completa a [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)], vedere [Sicurezza e distribuzione di ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment). Per informazioni dettagliate sull'utilizzo di queste funzionalità, vedere gli argomenti della Guida seguenti:  
  
|A|Vedere|  
|--------|---------|  
|Distribuire un'applicazione con [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)]|[Procedura: Pubblicare un'applicazione ClickOnce mediante la Pubblicazione guidata](/visualstudio/deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard)<br /><br /> [Procedura dettagliata: distribuzione manuale di un'applicazione ClickOnce](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application)|  
|Aggiorna un [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] distribuzione|[Procedura: Gestire gli aggiornamenti per un'applicazione ClickOnce](/visualstudio/deployment/how-to-manage-updates-for-a-clickonce-application)|  
|Gestire la sicurezza con [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)]|[Procedura: Abilitare le impostazioni di sicurezza ClickOnce](/visualstudio/deployment/how-to-enable-clickonce-security-settings)|  
  
## <a name="other-controls-and-features"></a>Altri controlli e funzionalità  
 Windows Form dispone di altre funzioni che rendono le comuni attività di implementazione estremamente semplici e rapide, quali il supporto per la creazione di caselle di dialogo, la stampa, l'aggiunta della Guida e la documentazione, la localizzazione dell'applicazione in diverse lingue. Inoltre, Windows Form si basa sull'infrastruttura di sicurezza del [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], che consente di rilasciare applicazioni più sicure ai clienti.  
  
 Per informazioni dettagliate sull'utilizzo di queste funzionalità, vedere gli argomenti della Guida seguenti:  
  
|A|Vedere|  
|--------|---------|  
|Stampare il contenuto di un form|[Procedura: stampare grafica in Windows Forms](../../../framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)<br /><br /> [Procedura: stampare un file di testo con più pagine in Windows Forms](../../../framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)|   
|Altre informazioni sulla sicurezza di Windows Form|[Panoramica della sicurezza in Windows Forms](../../../framework/winforms/security-in-windows-forms-overview.md)|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>  
 [Panoramica sui Windows Form](../../../framework/winforms/windows-forms-overview.md)  
 [Oggetto My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md)
