---
title: Nozioni fondamentali relative alle applicazioni Windows Forms (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Windows applications
- Windows Forms, Visual Basic
ms.assetid: 0b919d30-7fd6-42db-85c8-543d15312441
ms.openlocfilehash: dd3385d6459199d56f74abfb1b8e0e218a2adf78
ms.sourcegitcommit: 2d42b7ae4252cfe1232777f501ea9ac97df31b63
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2019
ms.locfileid: "67487795"
---
# <a name="windows-forms-application-basics-visual-basic"></a>Nozioni fondamentali relative alle applicazioni Windows Forms (Visual Basic)
Una parte importante di Visual Basic è la possibilità di creare applicazioni Windows Forms che vengono eseguite localmente sui computer degli utenti. È possibile usare Visual Studio per creare l'applicazione e interfaccia utente mediante Windows Forms. Un'applicazione Windows Forms è basata sulle classi dal <xref:System.Windows.Forms> dello spazio dei nomi.  
  
## <a name="designing-windows-forms-applications"></a>Progettazione di Windows Forms Application  
 È possibile creare applicazioni di servizio di Windows e Windows Forms con Visual Studio. Per altre informazioni, vedere i seguenti argomenti:  
  
- [Introduzione a Windows Form](../../../framework/winforms/getting-started-with-windows-forms.md). Fornisce informazioni su come creare e programmare i Windows Form.  
   
- [Controlli di Windows Form](../../../framework/winforms/controls/index.md). Raccolta di argomenti che riporta in dettaglio l'uso di controlli Windows Form.  
  
- [Le applicazioni di servizio Windows](../../../framework/windows-services/index.md). Elenca argomenti che illustrano come creare servizi Windows.  
  
## <a name="building-rich-interactive-user-interfaces"></a>Compilazione di interfacce utente complete e interattive  
 Windows Forms è il componente smart client di .NET Framework, un set di librerie gestite che semplificano attività comuni dell'applicazione, ad esempio la lettura e scrittura nel file System. Usa un ambiente di sviluppo come Visual Studio, è possibile creare applicazioni Windows Forms che visualizzano informazioni, richiedono l'input dagli utenti e comunicano con i computer remoti tramite una rete.  
  
 In Windows Form, un modulo è una superficie visiva sulla quale è possibile visualizzare le informazioni all'utente. Per compilare applicazioni Windows Forms, inserire i controlli nei form e sviluppare le risposte alle azioni dell'utente, ad esempio clic del mouse o pressioni di tasti. Un *controllo* è un elemento separato dell'interfaccia utente usato per visualizzare dati o accettare input di dati.  
  
### <a name="events"></a>Eventi  
 Quando un utente esegue un'azione nel form o uno dei relativi controlli, viene generato un evento. L'applicazione reagisce a tali eventi usando il codice ed elabora gli eventi quando si verificano. Per altre informazioni, vedere [Creazione di gestori eventi in Windows Forms](../../../framework/winforms/creating-event-handlers-in-windows-forms.md).  
  
### <a name="controls"></a>Controlli  
 Windows Form contiene diversi controlli che è possibile inserire nei form: i controlli che visualizzano caselle di testo, pulsanti, caselle di riepilogo a discesa, pulsanti di opzione e persino pagine Web. Per un elenco di tutti i controlli utilizzabili in un modulo, vedere [Controlli da usare in Windows Forms](../../../framework/winforms/controls/controls-to-use-on-windows-forms.md). Se un controllo esistente non dovesse soddisfare le proprie esigenze, Windows Form consente anche di creare controlli personalizzati usando la classe <xref:System.Windows.Forms.UserControl>.  
  
 Windows Form dispone di controlli UI completi che simulano le funzionalità delle applicazioni di fascia alta quali Microsoft Office. Usando il <xref:System.Windows.Forms.ToolStrip> e <xref:System.Windows.Forms.MenuStrip> (controllo), è possibile creare barre degli strumenti e menu contengono testo e immagini, visualizzare sottomenu nonché includere altri controlli, ad esempio caselle di testo e caselle combinate.  
  
 Con Progettazione form di trascinamento e rilascio di Visual Studio, è possibile creare facilmente applicazioni Windows Forms: è sufficiente selezionare i controlli con il cursore e inserirli in cui si desidera nel form. La finestra di progettazione vengono forniti strumenti quali linee della griglia e "guide di allineamento" per facilitare l'allineamento dei controlli. E se si usa Visual Studio o la compilazione dalla riga di comando, è possibile usare la <xref:System.Windows.Forms.FlowLayoutPanel>, <xref:System.Windows.Forms.TableLayoutPanel> e <xref:System.Windows.Forms.SplitContainer> layout poco tempo e fatica di form controlli per creare avanzate.  
  
### <a name="custom-ui-elements"></a>Elementi dell'interfaccia utente personalizzata  
 Infine, se è necessario creare elementi dell'interfaccia utente personalizzati, il <xref:System.Drawing> dello spazio dei nomi contiene tutte le classi necessarie per eseguire il rendering di linee, cerchi e altre forme direttamente in un form.  
  
 Per informazioni dettagliate sull'uso di queste funzionalità, vedere gli argomenti della Guida seguente.  
  
|A|Vedere|  
|--------|---------|  
|Creare una nuova applicazione Windows Forms con Visual Studio|[Esercitazione 1: Creare un Visualizzatore immagini](/visualstudio/ide/tutorial-1-create-a-picture-viewer)|  
|Usare i controlli nei form|[Procedura: Aggiungere controlli a un Windows Form](../../../framework/winforms/controls/how-to-add-controls-to-windows-forms.md)|   
|Creare grafici con <xref:System.Drawing>|[Introduzione alla programmazione grafica](../../../framework/winforms/advanced/getting-started-with-graphics-programming.md)|  
|Creare controlli personalizzati|[Procedura: Ereditare dalla classe UserControl](../../../framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)|  
  
## <a name="displaying-and-manipulating-data"></a>Visualizzazione e modifica dei dati  
 Molte applicazioni devono visualizzare i dati da un database, da un file XML, servizi Web XML o altre origini di dati. Windows Forms viene fornito un controllo chiamato il <xref:System.Windows.Forms.DataGridView> controllo per il rendering dei dati tabulari in un formato tradizionale di righe e colonne, in modo che ogni blocco di dati occupi una singola cella. Usando <xref:System.Windows.Forms.DataGridView> è possibile personalizzare l'aspetto delle singole celle, bloccare righe e colonne posto arbitrarie e visualizzare controlli complessi all'interno delle celle, tra le altre funzionalità.  
  
 Il collegamento alle origini dati tramite una rete è un'attività semplice con gli smart client Windows Form. Il <xref:System.Windows.Forms.BindingSource> novità di Windows Forms in Visual Studio 2005 e .NET Framework 2.0, rappresenta una connessione a un'origine dati ed espone metodi per l'associazione dati a controlli, lo spostamento ai record precedenti e successivi, la modifica di record, e salvataggio delle modifiche nell'origine originale. Il controllo <xref:System.Windows.Forms.BindingNavigator> fornisce un'interfaccia semplice tramite il componente <xref:System.Windows.Forms.BindingSource> per gli utenti per spostarsi tra i record.  
  
### <a name="data-bound-controls"></a>Controlli con associazione a dati  
 È possibile creare controlli associati a dati con facilità tramite la finestra Origini dati, che consente di visualizzare origini dati quali database, servizi Web e gli oggetti nel progetto. È possibile creare controlli associati a dati mediante il trascinamento di elementi da questa finestra nei form del progetto. È anche possibile connettere i controlli esistenti ai dati mediante il trascinamento di oggetti dalla finestra Origini dati nei controlli esistenti.  
  
### <a name="settings"></a>Impostazioni  
 Un altro tipo di data binding, che è possibile gestire in Windows Form sono le impostazioni. La maggior parte delle applicazioni smart client devono conservare alcune informazioni relative al proprio stato di runtime, ad esempio le ultime dimensioni note dei form e conservare i dati alle preferenze dell'utente, ad esempio i percorsi predefiniti per i file salvati. La funzionalità Impostazioni applicazione risolve queste problematiche offrendo un modo semplice per archiviare entrambi i tipi di impostazioni nel computer client. Una volta definite mediante Visual Studio o un editor di codice, queste impostazioni vengono mantenute come XML e lette automaticamente in memoria in fase di esecuzione.  
  
 Per informazioni dettagliate sull'uso di queste funzionalità, vedere gli argomenti della Guida seguente.  
  
|A|Vedere|  
|--------|---------|  
|Usare il <xref:System.Windows.Forms.BindingSource> componente|[Procedura: Associare controlli Windows Form al componente BindingSource usando la finestra di progettazione](../../../framework/winforms/controls/bind-wf-controls-with-the-bindingsource.md)|  
|Usare le origini dati ADO.NET|[Procedura: Ordinare e filtrare i dati ADO.NET con il Windows Form componente BindingSource](../../../framework/winforms/controls/sort-and-filter-ado-net-data-with-wf-bindingsource-component.md)|
|Utilizzare la finestra Origini dati|[Procedura dettagliata: Visualizzazione dei dati in un Windows Form](/visualstudio/data-tools/accessing-data-in-visual-studio)|  
  
## <a name="deploying-applications-to-client-computers"></a>Distribuzione delle applicazioni ai client  
 Una volta scritta, l'applicazione, è necessario inviarlo agli utenti in modo che possano installarla ed eseguirla sui propri computer client. Tramite la tecnologia ClickOnce, è possibile distribuire le applicazioni dall'interno di Visual Studio con pochi clic e fornire agli utenti con un URL che punta all'applicazione sul Web. ClickOnce consente di gestire tutti gli elementi e le dipendenze dell'applicazione e garantisce che l'applicazione sia installata correttamente nel computer client.  
  
 Applicazioni ClickOnce possono essere configurato per eseguire solo quando l'utente è connesso alla rete, o per essere eseguite sia online e offline. Quando si specifica che un'applicazione deve supportare l'operazione non in linea, ClickOnce aggiunge un collegamento all'applicazione dell'utente **avviare** menu, in modo che l'utente possa aprirlo senza usare l'URL.  
  
 Quando si aggiorna l'applicazione, vengono pubblicati un nuovo manifesto della distribuzione e una nuova copia dell'applicazione sul server Web. ClickOnce rileva che è disponibile un aggiornamento e aggiorna l'installazione dell'utente; Nessuna programmazione personalizzata è necessario per aggiornare gli assembly precedenti.  
  
 Per un'introduzione completa a ClickOnce, vedere [ClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment). Per informazioni dettagliate sull'uso di queste funzionalità, vedere gli argomenti della Guida seguenti:  
  
|A|Vedere|  
|--------|---------|  
|Distribuire un'applicazione con ClickOnce|[Procedura: Pubblicare un'applicazione ClickOnce mediante la Pubblicazione guidata](/visualstudio/deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard)<br /><br /> [Procedura dettagliata: Distribuzione manuale di un'applicazione ClickOnce](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application)|  
|Aggiornare una distribuzione di ClickOnce|[Procedura: Gestire gli aggiornamenti per un'applicazione ClickOnce](/visualstudio/deployment/how-to-manage-updates-for-a-clickonce-application)|  
|Gestire la sicurezza con ClickOnce|[Procedura: Abilitare le impostazioni di sicurezza ClickOnce](/visualstudio/deployment/how-to-enable-clickonce-security-settings)|  
  
## <a name="other-controls-and-features"></a>Altri controlli e funzionalità  
 Windows Form dispone di altre funzioni che rendono le comuni attività di implementazione estremamente semplici e rapide, quali il supporto per la creazione di caselle di dialogo, la stampa, l'aggiunta della Guida e la documentazione, la localizzazione dell'applicazione in diverse lingue. Inoltre, Windows Form si basa sul potente sistema di sicurezza di .NET Framework, consentendo di affidabilità delle applicazioni distribuite ai clienti.  
  
 Per informazioni dettagliate sull'uso di queste funzionalità, vedere gli argomenti della Guida seguenti:  
  
|A|Vedere|  
|--------|---------|  
|Stampare il contenuto di un form|[Procedura: Stampare grafica in Windows Form](../../../framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)<br /><br /> [Procedura: Stampare un File di testo con più pagine in Windows Form](../../../framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)|   
|Altre informazioni sulla sicurezza di Windows Form|[Panoramica della sicurezza in Windows Forms](../../../framework/winforms/security-in-windows-forms-overview.md)|  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- [Panoramica sui Windows Form](../../../framework/winforms/windows-forms-overview.md)
- [Oggetto My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md)
