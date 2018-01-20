---
title: "Procedura dettagliata: creazione di un controllo di Windows Form che usufruisca delle funzionalità offerte da Visual Studio in fase di progettazione"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms controls, creating
- design-time functionality [Windows Forms], Windows Forms
- DocumentDesigner class [Windows Forms]
- walkthroughs [Windows Forms], controls
ms.assetid: 6f487c59-cb38-4afa-ad2e-95edacb1d626
caps.latest.revision: "46"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a4e84c665897159d08cec36b0f35b4f5f2674445
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-creating-a-windows-forms-control-that-takes-advantage-of-visual-studio-design-time-features"></a>Procedura dettagliata: creazione di un controllo di Windows Form che usufruisca delle funzionalità offerte da Visual Studio in fase di progettazione
È possibile migliorare l'esperienza in fase di progettazione per un controllo personalizzato, è sufficiente creare una finestra di progettazione personalizzata associata.  
  
 Questa procedura dettagliata viene illustrato come creare una finestra di progettazione personalizzata per un controllo personalizzato. Verrà implementata una `MarqueeControl` tipo e una classe della finestra di progettazione associata, chiamato `MarqueeControlRootDesigner`.  
  
 Il `MarqueeControl` tipo implementa una visualizzazione simile a un teatro con luci animate e testo intermittente.  
  
 La finestra di progettazione per il controllo interagisce con l'ambiente di progettazione per fornire un'esperienza di progettazione personalizzata. Con la finestra di progettazione personalizzata, è possibile assemblare personalizzato `MarqueeControl` implementazione con luci animate e testo intermittente in varie combinazioni. È possibile utilizzare il controllo assemblato in un form come qualsiasi altro controllo Windows Form.  
  
 Le attività illustrate nella procedura dettagliata sono le seguenti:  
  
-   Creazione del progetto  
  
-   Creazione di un progetto libreria di controlli  
  
-   Riferimento al progetto di controllo personalizzato  
  
-   Definizione di un controllo personalizzato e la finestra di progettazione personalizzata  
  
-   Creazione di un'istanza del controllo personalizzato  
  
-   Impostazione del progetto per il debug in fase di progettazione  
  
-   Implementazione del controllo personalizzato  
  
-   Creazione di un controllo figlio per il controllo personalizzato  
  
-   Creare il controllo figlio MarqueeBorder  
  
-   Creazione di una finestra di progettazione personalizzata Shadow e le proprietà filtro  
  
-   Gestione delle modifiche di componente  
  
-   Aggiunta di verbi di progettazione per la finestra di progettazione personalizzata  
  
-   Creazione di un UITypeEditor personalizzato  
  
-   Test del controllo personalizzato nella finestra di progettazione  
  
 Al termine, il controllo personalizzato avrà un aspetto simile al seguente:  
  
 ![Possibile disposizione di MarqueeControl](../../../../docs/framework/winforms/controls/media/demomarqueecontrol.gif "DemoMarqueeControl")  
  
 Per il listato di codice completo, vedere [procedura: creare Windows Form controllo che accetta vantaggio della fase di progettazione funzionalità](http://msdn.microsoft.com/library/8e0bad0e-56f3-43d2-bf63-a945c654d97c).  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="prerequisites"></a>Prerequisiti  
 Per completare questa procedura dettagliata, è necessario:  
  
-   Disporre di autorizzazioni sufficienti creare ed eseguire progetti di applicazione Windows Form nel computer in cui è installato Visual Studio.  
  
## <a name="creating-the-project"></a>Creazione del progetto  
 Il primo passaggio consiste nel creare il progetto di applicazione. Questo progetto verrà utilizzato per compilare l'applicazione che ospita il controllo personalizzato.  
  
#### <a name="to-create-the-project"></a>Per creare il progetto  
  
-   Creare un progetto di applicazione Windows Form denominato "MarqueeControlTest". Per altre informazioni, vedere [Procedura: Creare un nuovo progetto di applicazione Windows Form](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
## <a name="creating-a-control-library-project"></a>Creazione di un progetto libreria di controlli  
 Il passaggio successivo consiste nel creare il progetto libreria di controlli. Si creerà un nuovo controllo personalizzato e la finestra di progettazione personalizzata corrispondente.  
  
#### <a name="to-create-the-control-library-project"></a>Per creare il progetto libreria di controlli  
  
1.  Aggiungere un progetto libreria di controlli Windows Form alla soluzione. Denominare il progetto "MarqueeControlLibrary".  
  
2.  Utilizzando **Esplora**, eliminare il controllo del progetto predefinita eliminando il file di origine denominato "UserControl1. cs" o "UserControl1. vb", a seconda del linguaggio scelto. Per ulteriori informazioni, vedere [NIB: procedura: escludere elementi, eliminazione e Rimuovi](http://msdn.microsoft.com/library/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73).  
  
3.  Aggiungere un nuovo <xref:System.Windows.Forms.UserControl> elemento il `MarqueeControlLibrary` progetto. Assegnare il nuovo file di origine di un nome di base di "MarqueeControl".  
  
4.  Utilizzando **Esplora**, creare una nuova cartella nel `MarqueeControlLibrary` progetto. Per ulteriori informazioni, vedere [NIB: procedura: aggiungere nuovi elementi di progetto](http://msdn.microsoft.com/library/63d3e16b-de6e-4bb5-a0e3-ecec762201ce). Denominare la nuova cartella "Progettazione".  
  
5.  Fare doppio clic su di **progettazione** cartella e aggiungere una nuova classe. Assegnare al file di origine di un nome di base di "MarqueeControlRootDesigner".  
  
6.  È necessario utilizzare i tipi dall'assembly System. Design e quindi aggiungere il riferimento per il `MarqueeControlLibrary` progetto.  
  
    > [!NOTE]
    >  Per utilizzare all'assembly, il progetto deve utilizzare la versione completa di .NET Framework, non .NET Framework Client Profile. Per modificare il framework di destinazione, vedere [procedura: destinare una versione di .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).  
  
## <a name="referencing-the-custom-control-project"></a>Riferimento al progetto di controllo personalizzato  
 Si utilizzerà il `MarqueeControlTest` progetto per testare il controllo personalizzato. Il progetto di test di riconoscerà il controllo personalizzato quando si aggiunge un riferimento al progetto il `MarqueeControlLibrary` assembly.  
  
#### <a name="to-reference-the-custom-control-project"></a>Per fare riferimento al progetto di controllo personalizzato  
  
-   Nel `MarqueeControlTest` del progetto, aggiungere un riferimento al progetto il `MarqueeControlLibrary` assembly. Assicurarsi di utilizzare il **progetti** nella scheda il **Aggiungi riferimento** la finestra di dialogo anziché di riferimento di `MarqueeControlLibrary` direttamente l'assembly.  
  
## <a name="defining-a-custom-control-and-its-custom-designer"></a>Definizione di un controllo personalizzato e la finestra di progettazione personalizzata  
 Il controllo personalizzato verrà derivare il <xref:System.Windows.Forms.UserControl> classe. In questo modo il controllo includere altri controlli e ottenere il controllo sono disponibili numerose funzionalità predefinite.  
  
 Il controllo personalizzato avrà una finestra di progettazione personalizzata associata. In questo modo è possibile creare un proprio ambiente di progettazione personalizzata specificamente per il controllo personalizzato.  
  
 Associare il controllo con la finestra di progettazione utilizzando la <xref:System.ComponentModel.DesignerAttribute> classe. Poiché si sta sviluppando l'intero comportamento in fase di progettazione del controllo personalizzato, la finestra di progettazione personalizzata implementerà il <xref:System.ComponentModel.Design.IRootDesigner> interfaccia.  
  
#### <a name="to-define-a-custom-control-and-its-custom-designer"></a>Per definire un controllo personalizzato e la finestra di progettazione personalizzata  
  
1.  Aprire il `MarqueeControl` file di origine di **Editor di codice**. Nella parte superiore del file, importare gli spazi dei nomi seguenti:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#220](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#220)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#220](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#220)]  
  
2.  Aggiungere il <xref:System.ComponentModel.DesignerAttribute> per il `MarqueeControl` dichiarazione di classe. Consente di associare il controllo personalizzato con la finestra di progettazione.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#240](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#240)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#240](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#240)]  
  
3.  Aprire il `MarqueeControlRootDesigner` file di origine di **Editor di codice**. Nella parte superiore del file, importare gli spazi dei nomi seguenti:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#520](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#520)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#520](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#520)]  
  
4.  Modificare la dichiarazione di `MarqueeControlRootDesigner` da cui ereditare la <xref:System.Windows.Forms.Design.DocumentDesigner> classe. Applicare il <xref:System.ComponentModel.ToolboxItemFilterAttribute> per specificare l'interazione della finestra di progettazione con il **della casella degli strumenti**.  
  
     **Nota** la definizione per il `MarqueeControlRootDesigner` classe è stata inclusa in uno spazio dei nomi "MarqueeControlLibrary". Questa dichiarazione posiziona la finestra di progettazione in uno speciale spazio dei nomi riservato per i tipi correlati alla progettazione.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#530](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#530)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#530](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#530)]  
  
5.  Definire il costruttore per la `MarqueeControlRootDesigner` classe. Inserire un <xref:System.Diagnostics.Trace.WriteLine%2A> istruzione nel corpo del costruttore. Ciò è utile a scopo di debug.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#540](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#540)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#540](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#540)]  
  
## <a name="creating-an-instance-of-your-custom-control"></a>Creazione di un'istanza del controllo personalizzato  
 Per osservare il comportamento personalizzato in fase di progettazione del controllo, si inserirà un'istanza del controllo nel form in `MarqueeControlTest` progetto.  
  
#### <a name="to-create-an-instance-of-your-custom-control"></a>Per creare un'istanza del controllo personalizzato  
  
1.  Aggiungere un nuovo <xref:System.Windows.Forms.UserControl> elemento il `MarqueeControlTest` progetto. Assegnare il nuovo file di origine di un nome di base di "DemoMarqueeControl".  
  
2.  Aprire il `DemoMarqueeControl` file nel **Editor di codice**. Nella parte superiore del file, importare il `MarqueeControlLibrary` dello spazio dei nomi:  
  
```vb  
Imports MarqueeControlLibrary  
```  
  
```csharp  
using MarqueeControlLibrary;  
```  
  
1.  Modificare la dichiarazione di `DemoMarqueeControl` da cui ereditare la `MarqueeControl` classe.  
  
2.  Compilare il progetto.  
  
3.  Aprire `Form1` in Progettazione Windows Form.  
  
4.  Trovare il **Componenti MarqueeControlTest** nella scheda il **della casella degli strumenti** e aprirlo. Trascinare un `DemoMarqueeControl` dal **della casella degli strumenti** nel form.  
  
5.  Compilare il progetto.  
  
## <a name="setting-up-the-project-for-design-time-debugging"></a>Impostazione del progetto per il debug in fase di progettazione  
 Quando si sviluppa una soluzione personalizzata in fase di progettazione, sarà necessario eseguire il debug di controlli e componenti. È un modo semplice per configurare il progetto per consentire il debug in fase di progettazione. Per ulteriori informazioni, vedere [procedura dettagliata: debug di controlli Windows personalizzata form in fase di progettazione](../../../../docs/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time.md).  
  
#### <a name="to-set-up-the-project-for-design-time-debugging"></a>Per impostare il progetto per il debug in fase di progettazione  
  
1.  Fare doppio clic su di `MarqueeControlLibrary` del progetto e selezionare **proprietà**.  
  
2.  Nella finestra di dialogo "Pagine delle proprietà MarqueeControlLibrary", selezionare il **Debug** pagina.  
  
3.  Nel **azione di avvio** selezionare **Avvia programma esterno**. Sarà il debug di un'istanza separata di Visual Studio, quindi fare clic sui puntini di sospensione (![schermata VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) per cercare l'IDE di Visual Studio. Il nome del file eseguibile è devenv.exe e, se è installato nel percorso predefinito, il relativo percorso %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe  
  
4.  Fare clic su OK per chiudere la finestra di dialogo.  
  
5.  Fare doppio clic su di `MarqueeControlLibrary` del progetto e scegliere "Imposta come progetto di avvio" per abilitare la configurazione di debug.  
  
## <a name="checkpoint"></a>Checkpoint  
 A questo punto si è pronti per il debug del comportamento in fase di progettazione del controllo personalizzato. Dopo aver determinato che l'ambiente di debug sia configurato correttamente, si testerà l'associazione tra il controllo personalizzato e la finestra di progettazione personalizzata.  
  
#### <a name="to-test-the-debugging-environment-and-the-designer-association"></a>Per testare l'ambiente di debug e l'associazione della finestra di progettazione  
  
1.  Aprire il `MarqueeControlRootDesigner` file di origine il **Editor di codice** e inserire un punto di interruzione il <xref:System.Diagnostics.Trace.WriteLine%2A> istruzione.  
  
2.  Premere F5 per avviare la sessione di debug. Si noti che viene creata una nuova istanza di Visual Studio.  
  
3.  Nella nuova istanza di Visual Studio, aprire la soluzione "MarqueeControlTest". È possibile trovare facilmente la soluzione selezionando **progetti recenti** dal **File** menu. Il file della soluzione "MarqueeControlTest" verrà elencato come più file utilizzati di recente.  
  
4.  Aprire il `DemoMarqueeControl` nella finestra di progettazione. Si noti che l'istanza di debug di Visual Studio acquisisce lo stato attivo e l'esecuzione si ferma in corrispondenza del punto di interruzione. Premere F5 per continuare la sessione di debug.  
  
 A questo punto, tutto ciò che è presente per poter sviluppare ed eseguire il debug del controllo personalizzato e la finestra di progettazione personalizzata associata. Il resto di questa procedura dettagliata si concentrerà sui dettagli di implementazione delle funzionalità del controllo e la finestra di progettazione.  
  
## <a name="implementing-your-custom-control"></a>Implementazione del controllo personalizzato  
 Il `MarqueeControl` è un <xref:System.Windows.Forms.UserControl> con un minimo di personalizzazione. Che espone due metodi: `Start`, che avvia l'animazione, e `Stop`, che blocca l'animazione. Poiché il `MarqueeControl` contiene i controlli figlio che implementano il `IMarqueeWidget` interfaccia, `Start` e `Stop` enumerare ogni controllo figlio e chiamare il `StartMarquee` e `StopMarquee` metodi, rispettivamente, per ogni controllo figlio che implementa `IMarqueeWidget`.  
  
 L'aspetto del `MarqueeBorder` e `MarqueeText` controlli dipende il layout, in modo `MarqueeControl` esegue l'override di <xref:System.Windows.Forms.Control.OnLayout%2A> metodo e chiama <xref:System.Windows.Forms.Control.PerformLayout%2A> i controlli figlio di questo tipo.  
  
 Questo è l'estensione del `MarqueeControl` personalizzazioni. Le funzioni di runtime vengono implementate dal `MarqueeBorder` e `MarqueeText` controlli e le funzionalità in fase di progettazione vengono implementati dal `MarqueeBorderDesigner` e `MarqueeControlRootDesigner` classi.  
  
#### <a name="to-implement-your-custom-control"></a>Per implementare il controllo personalizzato  
  
1.  Aprire il `MarqueeControl` file di origine di **Editor di codice**. Implementare il `Start` e `Stop` metodi.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#260](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#260)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#260](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#260)]  
  
2.  Eseguire l'override del metodo <xref:System.Windows.Forms.Control.OnLayout%2A>.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#270](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#270)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#270](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#270)]  
  
## <a name="creating-a-child-control-for-your-custom-control"></a>Creazione di un controllo figlio per il controllo personalizzato  
 Il `MarqueeControl` ospiterà i due tipi di controlli figlio: il `MarqueeBorder` controllo e `MarqueeText` controllo.  
  
-   `MarqueeBorder`: Questo controllo disegna un bordo di "luci" lungo i bordi. Che lampeggiano in sequenza, pertanto verranno visualizzati in intorno al bordo. La velocità di intermittenza è controllata da una proprietà denominata `UpdatePeriod`. Molte altre proprietà personalizzate determinare altri aspetti dell'aspetto del controllo. I due metodi `StartMarquee` e `StopMarquee`, controllare se l'animazione avvia e arresta.  
  
-   `MarqueeText`: Il controllo disegna una stringa lampeggiante. Ad esempio il `MarqueeBorder` controllo intermittenza in corrispondenza del quale il testo è determinata dal `UpdatePeriod` proprietà. Il `MarqueeText` controllo dispone anche di `StartMarquee` e `StopMarquee` metodi in comune con il `MarqueeBorder` controllo.  
  
 In fase di progettazione di `MarqueeControlRootDesigner` consente di questi due tipi di controllo da aggiungere a un `MarqueeControl` in qualsiasi combinazione.  
  
 Funzionalità comuni per i due controlli vengono inserite in un'interfaccia denominata `IMarqueeWidget`. In questo modo il `MarqueeControl` per individuare eventuali controlli figlio correlati alla selezione e comportarsi di conseguenza.  
  
 Per implementare la funzionalità di animazione periodica, si utilizzerà <xref:System.ComponentModel.BackgroundWorker> oggetti dal <xref:System.ComponentModel?displayProperty=nameWithType> dello spazio dei nomi. È possibile utilizzare <xref:System.Windows.Forms.Timer> oggetti, ma quando molti `IMarqueeWidget` gli oggetti sono presenti, il singolo thread dell'interfaccia utente potrebbe non essere possibile gestire l'animazione.  
  
#### <a name="to-create-a-child-control-for-your-custom-control"></a>Per creare un controllo figlio per il controllo personalizzato  
  
1.  Aggiungere un nuovo elemento di classe per il `MarqueeControlLibrary` progetto. Assegnare il nuovo file di origine di un nome di base di "IMarqueeWidget".  
  
2.  Aprire il `IMarqueeWidget` file di origine di **Editor di codice** e modificare la dichiarazione da `class` per `interface`:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#2)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#2)]  
  
3.  Aggiungere il codice seguente per il `IMarqueeWidget` interfaccia per esporre una proprietà che gestiscono l'animazione e due metodi:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#3)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#3)]  
  
4.  Aggiungere un nuovo **controllo personalizzato** elemento il `MarqueeControlLibrary` progetto. Assegnare il nuovo file di origine di un nome di base di "MarqueeText".  
  
5.  Trascinare un <xref:System.ComponentModel.BackgroundWorker> componente dal **della casella degli strumenti** sul `MarqueeText` controllo. Tale componente consentirà di `MarqueeText` controllo di aggiornamento in modo asincrono.  
  
6.  Nella finestra Proprietà impostare il <xref:System.ComponentModel.BackgroundWorker> del componente `WorkerReportsProgess` e <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> proprietà `true`. Queste impostazioni consentono di <xref:System.ComponentModel.BackgroundWorker> componente di generare periodicamente il <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> eventi e annullare gli aggiornamenti asincroni. Per ulteriori informazioni, vedere [componente BackgroundWorker](../../../../docs/framework/winforms/controls/backgroundworker-component.md).  
  
7.  Aprire il `MarqueeText` file di origine di **Editor di codice**. Nella parte superiore del file, importare gli spazi dei nomi seguenti:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#120)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#120)]  
  
8.  Modificare la dichiarazione di `MarqueeText` da cui ereditare <xref:System.Windows.Forms.Label> e implementare il `IMarqueeWidget` interfaccia:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#130](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#130)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#130](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#130)]  
  
9. Dichiarare le variabili di istanza che corrispondono alle proprietà esposte e inizializzarle nel costruttore. Il `isLit` campo determina se il testo da disegnare il colore di base di `LightColor` proprietà.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#140](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#140)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#140](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#140)]  
  
10. Implementare l'interfaccia `IMarqueeWidget`.  
  
     Il `StartMarquee` e `StopMarquee` metodi richiamano il <xref:System.ComponentModel.BackgroundWorker> del componente <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> e <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> metodi per avviare e arrestare l'animazione.  
  
     Il <xref:System.ComponentModel.CategoryAttribute.Category%2A> e <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> gli attributi vengono applicati per la `UpdatePeriod` proprietà viene visualizzato in una sezione personalizzata della finestra proprietà denominata "Marquee".  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#150](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#150)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#150](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#150)]  
  
11. Implementare funzioni di accesso della proprietà. È necessario esporre ai client le due proprietà: `LightColor` e `DarkColor`. Il <xref:System.ComponentModel.CategoryAttribute.Category%2A> e <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> vengono applicati a queste proprietà, le proprietà verranno visualizzate in una sezione personalizzata della finestra proprietà denominata "Marquee".  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#160](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#160)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#160](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#160)]  
  
12. Implementare i gestori per il <xref:System.ComponentModel.BackgroundWorker> del componente <xref:System.ComponentModel.BackgroundWorker.DoWork> e <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> eventi.  
  
     Il <xref:System.ComponentModel.BackgroundWorker.DoWork> gestore rimane inattivo per il numero di millisecondi specificato da `UpdatePeriod` genera quindi il <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> evento, fino a quando non interrompe il codice chiamando <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>.  
  
     Il <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> gestore dell'evento attiva o disattiva il testo compreso tra lo stato chiaro e scuro per dare l'impressione di lampeggiante.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#180](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#180)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#180](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#180)]  
  
13. Eseguire l'override di <xref:System.Windows.Forms.Control.OnPaint%2A> metodo per abilitare l'animazione.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#170](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#170)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#170](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#170)]  
  
14. Premere F6 per compilare la soluzione.  
  
## <a name="create-the-marqueeborder-child-control"></a>Creare il controllo figlio MarqueeBorder  
 Il `MarqueeBorder` è leggermente più complesso di controllo di `MarqueeText` controllo. Dispone di più proprietà e l'animazione nel <xref:System.Windows.Forms.Control.OnPaint%2A> metodo è più complesso. In generale, è abbastanza simile a quella di `MarqueeText` controllo.  
  
 Poiché il `MarqueeBorder` controllo può contenere controlli figlio, è necessario essere a conoscenza di <xref:System.Windows.Forms.Control.Layout> eventi.  
  
#### <a name="to-create-the-marqueeborder-control"></a>Per creare il controllo MarqueeBorder  
  
1.  Aggiungere un nuovo **controllo personalizzato** elemento il `MarqueeControlLibrary` progetto. Assegnare il nuovo file di origine di un nome di base di "MarqueeBorder".  
  
2.  Trascinare un <xref:System.ComponentModel.BackgroundWorker> componente dal **della casella degli strumenti** sul `MarqueeBorder` controllo. Tale componente consentirà di `MarqueeBorder` controllo di aggiornamento in modo asincrono.  
  
3.  Nella finestra Proprietà impostare il <xref:System.ComponentModel.BackgroundWorker> del componente `WorkerReportsProgess` e <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> proprietà `true`. Queste impostazioni consentono di <xref:System.ComponentModel.BackgroundWorker> componente di generare periodicamente il <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> eventi e annullare gli aggiornamenti asincroni. Per ulteriori informazioni, vedere [componente BackgroundWorker](../../../../docs/framework/winforms/controls/backgroundworker-component.md).  
  
4.  Nella finestra Proprietà fare clic sul pulsante eventi. Gestori per il <xref:System.ComponentModel.BackgroundWorker.DoWork> e <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> eventi.  
  
5.  Aprire il `MarqueeBorder` file di origine di **Editor di codice**. Nella parte superiore del file, importare gli spazi dei nomi seguenti:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#20)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#20)]  
  
6.  Modificare la dichiarazione di `MarqueeBorder` da cui ereditare <xref:System.Windows.Forms.Panel> e implementare il `IMarqueeWidget` interfaccia.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#30)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#30)]  
  
7.  Dichiarare le due enumerazioni per la gestione di `MarqueeBorder` stato del controllo: `MarqueeSpinDirection`, che determina la direzione in cui le luci "" intorno al bordo, e `MarqueeLightShape`, che determina la forma di luci (quadrata o circolare). Inserire queste dichiarazioni prima il `MarqueeBorder` dichiarazione di classe.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#97](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#97)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#97](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#97)]  
  
8.  Dichiarare le variabili di istanza che corrispondono alle proprietà esposte e inizializzarle nel costruttore.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#40](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#40)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#40](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#40)]  
  
9. Implementare l'interfaccia `IMarqueeWidget`.  
  
     Il `StartMarquee` e `StopMarquee` metodi richiamano il <xref:System.ComponentModel.BackgroundWorker> del componente <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> e <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> metodi per avviare e arrestare l'animazione.  
  
     Poiché il `MarqueeBorder` controllo può contenere controlli figlio, il `StartMarquee` metodo enumera tutti i controlli figlio e chiama `StartMarquee` per quelli che implementano `IMarqueeWidget`. Il `StopMarquee` metodo ha un'implementazione simile.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#50](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#50)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#50](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#50)]  
  
10. Implementare funzioni di accesso della proprietà. Il `MarqueeBorder` controllo include diverse proprietà per controllare l'aspetto.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#60](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#60)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#60](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#60)]  
  
11. Implementare i gestori per il <xref:System.ComponentModel.BackgroundWorker> del componente <xref:System.ComponentModel.BackgroundWorker.DoWork> e <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> eventi.  
  
     Il <xref:System.ComponentModel.BackgroundWorker.DoWork> gestore rimane inattivo per il numero di millisecondi specificato da `UpdatePeriod` genera quindi il <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> evento, fino a quando non interrompe il codice chiamando <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>.  
  
     Il <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> gestore dell'evento incrementa la posizione della luce "base", da cui lo stato chiaro o scuro delle altre luci è determinato, e chiamate di <xref:System.Windows.Forms.Control.Refresh%2A> metodo in modo che il controllo verrà ridisegnato.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#90](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#90)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#90](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#90)]  
  
12. Implementare i metodi di supporto `IsLit` e `DrawLight`.  
  
     Il `IsLit` metodo determina il colore di una luce in una determinata posizione. Luci che sono "accende" vengono disegnate nel colore specificato per il `LightColor` proprietà e quelli che sono "scuro" vengono disegnati nel colore specificato dal `DarkColor` proprietà.  
  
     Il `DrawLight` metodo disegna una luce utilizzando il colore appropriato, una forma e la posizione.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#80](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#80)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#80](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#80)]  
  
13. Eseguire l'override di <xref:System.Windows.Forms.Control.OnLayout%2A> e <xref:System.Windows.Forms.Control.OnPaint%2A> metodi.  
  
     Il <xref:System.Windows.Forms.Control.OnPaint%2A> metodo disegna le luci lungo i bordi del `MarqueeBorder` controllo.  
  
     Poiché il <xref:System.Windows.Forms.Control.OnPaint%2A> metodo dipende dalle dimensioni del `MarqueeBorder` controllo, è necessario chiamarlo ogni volta che viene modificato il layout. A tale scopo, eseguire l'override <xref:System.Windows.Forms.Control.OnLayout%2A> e chiamare <xref:System.Windows.Forms.Control.Refresh%2A>.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#70](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#70)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#70](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#70)]  
  
## <a name="creating-a-custom-designer-to-shadow-and-filter-properties"></a>Creazione di una finestra di progettazione personalizzata Shadow e le proprietà filtro  
 La `MarqueeControlRootDesigner` classe fornisce l'implementazione per la finestra di progettazione radice. Oltre a questa finestra di progettazione, che opera sul `MarqueeControl`, è necessario che una finestra di progettazione associata in modo specifico il `MarqueeBorder` controllo. Questa finestra di progettazione fornisce un comportamento personalizzato appropriato nel contesto della finestra di progettazione radice personalizzata.  
  
 In particolare, il `MarqueeBorderDesigner` sarà "nascondere" e filtrare alcune proprietà di `MarqueeBorder` controllo, alterando l'interazione con l'ambiente di progettazione.  
  
 Intercettazione di chiamate alla funzione di accesso di un componente proprietà è nota come "shadowing". Consente di tenere traccia del valore impostato dall'utente, una finestra di progettazione e, facoltativamente, passare il valore per il componente in fase di progettazione.  
  
 Per questo esempio, il <xref:System.Windows.Forms.Control.Visible%2A> e <xref:System.Windows.Forms.Control.Enabled%2A> proprietà verranno eseguite mediante il `MarqueeBorderDesigner`, che impedisce all'utente di rendere il `MarqueeBorder` controllo invisibile o disattivato in fase di progettazione.  
  
 Finestre di progettazione può anche aggiungere e rimuovere le proprietà. Per questo esempio, il <xref:System.Windows.Forms.Control.Padding%2A> proprietà verrà rimosso in fase di progettazione, poiché il `MarqueeBorder` controllo a livello di codice imposta la spaziatura interna in base alla dimensione delle luci specificata per il `LightSize` proprietà.  
  
 La classe base per `MarqueeBorderDesigner` è <xref:System.ComponentModel.Design.ComponentDesigner>, che dispone di metodi che è possono modificare le proprietà, attributi e gli eventi esposti da un controllo in fase di progettazione:  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterProperties%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterAttributes%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterAttributes%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterEvents%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterEvents%2A>  
  
 Quando si modifica l'interfaccia pubblica di un componente usando questi metodi, è necessario seguire queste regole:  
  
-   Aggiungere o rimuovere gli elementi di `PreFilter` solo metodi  
  
-   Modificare gli elementi esistenti nel `PostFilter` solo metodi  
  
-   Chiamare sempre per prima l'implementazione di base `PreFilter` metodi  
  
-   Chiamare sempre l'implementazione di base ultima `PostFilter` metodi  
  
 Rispettare queste regole assicura che tutte le finestre di progettazione nell'ambiente di progettazione di una vista coerente di tutti i componenti in fase di progettazione.  
  
 La <xref:System.ComponentModel.Design.ComponentDesigner> classe fornisce un dizionario per la gestione dei valori di proprietà nascosti, che elimina la necessità di creare variabili di istanza specifico.  
  
#### <a name="to-create-a-custom-designer-to-shadow-and-filter-properties"></a>Per creare una finestra di progettazione personalizzata per le proprietà di ombreggiatura e filtro  
  
1.  Fare doppio clic su di **progettazione** cartella e aggiungere una nuova classe. Assegnare al file di origine di un nome di base di "MarqueeBorderDesigner".  
  
2.  Aprire il `MarqueeBorderDesigner` file di origine di **Editor di codice**. Nella parte superiore del file, importare gli spazi dei nomi seguenti:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#420](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#420)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#420](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#420)]  
  
3.  Modificare la dichiarazione di `MarqueeBorderDesigner` da cui ereditare <xref:System.Windows.Forms.Design.ParentControlDesigner>.  
  
     Poiché il `MarqueeBorder` controllo può contenere controlli figlio, `MarqueeBorderDesigner` eredita da <xref:System.Windows.Forms.Design.ParentControlDesigner>, che gestisce l'interazione padre-figlio.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#430](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#430)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#430](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#430)]  
  
4.  Eseguire l'override dell'implementazione di base di <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#450](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#450)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#450](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#450)]  
  
5.  Implementare le proprietà <xref:System.Windows.Forms.Control.Enabled%2A> e <xref:System.Windows.Forms.Control.Visible%2A>. Queste implementazioni nascondere le proprietà del controllo.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#440](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#440)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#440](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#440)]  
  
## <a name="handling-component-changes"></a>Gestione delle modifiche di componente  
 Il `MarqueeControlRootDesigner` classe fornisce l'esperienza in fase di progettazione personalizzata per il `MarqueeControl` istanze. La maggior parte delle funzionalità della fase di progettazione viene ereditata dalla <xref:System.Windows.Forms.Design.DocumentDesigner> classe; sarà codice implementare due personalizzazioni specifiche: la gestione delle modifiche di componente e l'aggiunta di verbi di progettazione.  
  
 Quando gli utenti progettano le `MarqueeControl` istanze, la finestra di progettazione radice verrà tenere traccia delle modifiche per il `MarqueeControl` e i relativi controlli figlio. L'ambiente in fase di progettazione offre un servizio utile, <xref:System.ComponentModel.Design.IComponentChangeService>, per il rilevamento modifiche allo stato dei componenti.  
  
 Acquisizione di un riferimento al servizio eseguendo una query con l'ambiente di <xref:System.ComponentModel.Design.ComponentDesigner.GetService%2A> metodo. Se la query ha esito positivo, la finestra di progettazione è possibile collegare un gestore per il <xref:System.ComponentModel.Design.IComponentChangeService.ComponentChanged> eventi ed eseguire qualsiasi attività necessarie per mantenere uno stato coerente in fase di progettazione.  
  
 In caso del `MarqueeControlRootDesigner` (classe), verrà chiamato il <xref:System.Windows.Forms.Control.Refresh%2A> metodo su ogni `IMarqueeWidget` oggetto incluso il `MarqueeControl`. In questo modo il `IMarqueeWidget` oggetto verrà ridisegnato correttamente quando le proprietà del controllo padre <xref:System.Windows.Forms.Control.Size%2A> vengono modificati.  
  
#### <a name="to-handle-component-changes"></a>Per gestire le modifiche di componente  
  
1.  Aprire il `MarqueeControlRootDesigner` file di origine il **Editor di codice** ed eseguire l'override di <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> (metodo). Chiamare l'implementazione di base di <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> ed eseguire query per il <xref:System.ComponentModel.Design.IComponentChangeService>.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#580](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#580)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#580](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#580)]  
  
2.  Implementare il <xref:System.ComponentModel.Design.IComponentChangeService.OnComponentChanged%2A> gestore dell'evento. Tipo del componente di invio, test e se è un `IMarqueeWidget`, chiamare il relativo <xref:System.Windows.Forms.Control.Refresh%2A> (metodo).  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#560](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#560)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#560](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#560)]  
  
## <a name="adding-designer-verbs-to-your-custom-designer"></a>Aggiunta di verbi di progettazione per la finestra di progettazione personalizzata  
 Un verbo di progettazione è un comando di menu collegato a un gestore eventi. I verbi di progettazione vengono aggiunti al menu di scelta rapida di un componente in fase di progettazione. Per altre informazioni, vedere <xref:System.ComponentModel.Design.DesignerVerb>.  
  
 Si aggiungeranno due verbi di progettazione per le finestre di progettazione: **Esegui Test** e **Interrompi Test**. Consentono di visualizzare il comportamento in fase di esecuzione di tali verbi di `MarqueeControl` in fase di progettazione. Verranno aggiunto a questi verbi di `MarqueeControlRootDesigner`.  
  
 Quando **Esegui Test** viene richiamato, il gestore dell'evento verbo chiamerà il `StartMarquee` metodo il `MarqueeControl`. Quando **Interrompi Test** viene richiamato, il gestore dell'evento verbo chiamerà il `StopMarquee` metodo il `MarqueeControl`. L'implementazione del `StartMarquee` e `StopMarquee` metodi chiamano questi metodi nei controlli contenuti che implementano `IMarqueeWidget`, pertanto qualsiasi contenuto `IMarqueeWidget` controlli parteciperà anche il test.  
  
#### <a name="to-add-designer-verbs-to-your-custom-designers"></a>Per aggiungere verbi di progettazione di finestre di progettazione personalizzate  
  
1.  Nel `MarqueeControlRootDesigner` classe, aggiungere i gestori eventi denominata `OnVerbRunTest` e `OnVerbStopTest`.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#570](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#570)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#570](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#570)]  
  
2.  Connettersi a questi gestori eventi ai verbi di progettazione corrispondente. `MarqueeControlRootDesigner`eredita un <xref:System.ComponentModel.Design.DesignerVerbCollection> dalla relativa classe base. Verranno creati due nuovi <xref:System.ComponentModel.Design.DesignerVerb> degli oggetti e aggiungerli a questo insieme di <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> metodo.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#590](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#590)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#590](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#590)]  
  
## <a name="creating-a-custom-uitypeeditor"></a>Creazione di un UITypeEditor personalizzato  
 Quando si crea una fase di progettazione personalizzata per gli utenti, è spesso utile per creare un'interazione con la finestra proprietà personalizzata. È possibile ottenere questo risultato creando un <xref:System.Drawing.Design.UITypeEditor>. Per ulteriori informazioni, vedere [procedura: creare un Editor di tipo dell'interfaccia utente](http://msdn.microsoft.com/library/292c6e33-8d85-4012-9b51-05835a6f6dfd).  
  
 Il `MarqueeBorder` controllo espone diverse proprietà nella finestra Proprietà. Due di queste proprietà, `MarqueeSpinDirection` e `MarqueeLightShape` sono rappresentate da enumerazioni. Per illustrare l'utilizzo di un editor di tipo dell'interfaccia utente, il `MarqueeLightShape` della proprietà è associato un <xref:System.Drawing.Design.UITypeEditor> classe.  
  
#### <a name="to-create-a-custom-ui-type-editor"></a>Per creare un tipo di interfaccia utente personalizzato editor  
  
1.  Aprire il `MarqueeBorder` file di origine di **Editor di codice**.  
  
2.  Nella definizione di `MarqueeBorder` classe, dichiarare una classe denominata `LightShapeEditor` che deriva da <xref:System.Drawing.Design.UITypeEditor>.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#96](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#96)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#96](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#96)]  
  
3.  Dichiarare un <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> variabile dell'istanza denominata `editorService`.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#92](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#92)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#92](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#92)]  
  
4.  Eseguire l'override del metodo <xref:System.Drawing.Design.UITypeEditor.GetEditStyle%2A>. Questa implementazione restituisce <xref:System.Drawing.Design.UITypeEditorEditStyle.DropDown>, che indica come visualizzare l'ambiente di progettazione di `LightShapeEditor`.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#93](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#93)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#93](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#93)]  
  
5.  Eseguire l'override del metodo <xref:System.Drawing.Design.UITypeEditor.EditValue%2A>. Questa implementazione esegue una query all'ambiente di progettazione un <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> oggetto. Se ha esito positivo, viene creato un `LightShapeSelectionControl`. Il <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.DropDownControl%2A> metodo viene chiamato per avviare il `LightShapeEditor`. Il valore restituito da questa chiamata viene restituito all'ambiente di progettazione.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#94](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#94)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#94](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#94)]  
  
## <a name="creating-a-view-control-for-your-custom-uitypeeditor"></a>Creazione di un controllo di visualizzazione per il UITypeEditor personalizzato  
  
1.  Il `MarqueeLightShape` proprietà supporta due tipi di forme chiare: `Square` e `Circle`. Si creerà un controllo personalizzato utilizzato esclusivamente allo scopo di visualizzare graficamente i valori nella finestra Proprietà. Questo controllo personalizzato da utilizzare per il <xref:System.Drawing.Design.UITypeEditor> per interagire con la finestra Proprietà.  
  
#### <a name="to-create-a-view-control-for-your-custom-ui-type-editor"></a>Per creare un controllo di visualizzazione per l'interfaccia utente personalizzata dell'editor di tipo  
  
1.  Aggiungere un nuovo <xref:System.Windows.Forms.UserControl> elemento il `MarqueeControlLibrary` progetto. Assegnare il nuovo file di origine di un nome di base di "LightShapeSelectionControl".  
  
2.  Trascinare due <xref:System.Windows.Forms.Panel> dei controlli di **della casella degli strumenti** sul `LightShapeSelectionControl`. Denominarle `squarePanel` e `circlePanel`. Disporli affiancati. Impostare il <xref:System.Windows.Forms.Control.Size%2A> proprietà sia <xref:System.Windows.Forms.Panel> i controlli a (60, 60). Impostare il <xref:System.Windows.Forms.Control.Location%2A> proprietà del `squarePanel` controllo (8, 10). Impostare il <xref:System.Windows.Forms.Control.Location%2A> proprietà del `circlePanel` controllo (80, 10). Infine, impostare il <xref:System.Windows.Forms.Control.Size%2A> proprietà del `LightShapeSelectionControl` per (150, 80).  
  
3.  Aprire il `LightShapeSelectionControl` file di origine di **Editor di codice**. Nella parte superiore del file, importare il <xref:System.Windows.Forms.Design?displayProperty=nameWithType> dello spazio dei nomi:  
  
```vb  
Imports System.Windows.Forms.Design  
```  
  
```csharp  
using System.Windows.Forms.Design;  
```  
  
1.  Implementare <xref:System.Windows.Forms.Control.Click> gestori eventi per il `squarePanel` e `circlePanel` controlli. Tali metodi richiamano <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.CloseDropDown%2A> alla fine personalizzata <xref:System.Drawing.Design.UITypeEditor> sessione di modifica.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#390](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#390)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#390](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#390)]  
  
2.  Dichiarare un <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> variabile dell'istanza denominata `editorService`.  
  
```vb  
Private editorService As IWindowsFormsEditorService  
```  
  
```csharp  
private IWindowsFormsEditorService editorService;  
```  
  
1.  Dichiarare un `MarqueeLightShape` variabile dell'istanza denominata `lightShapeValue`.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#330](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#330)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#330](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#330)]  
  
2.  Nel `LightShapeSelectionControl` costruttore, collegare il <xref:System.Windows.Forms.Control.Click> gestori eventi per il `squarePanel` e `circlePanel` dei controlli <xref:System.Windows.Forms.Control.Click> eventi. Inoltre, definire un overload del costruttore che assegna il `MarqueeLightShape` valore dall'ambiente di progettazione per il `lightShapeValue` campo.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#340](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#340)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#340](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#340)]  
  
3.  Nel <xref:System.ComponentModel.Component.Dispose%2A> metodo, scollegare il <xref:System.Windows.Forms.Control.Click> gestori eventi.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#350](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#350)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#350](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#350)]  
  
4.  In **Esplora soluzioni** fare clic sul pulsante **Mostra tutti i file**. Aprire il file LightShapeSelectionControl.Designer.cs o LightShapeSelectionControl.Designer.vb e rimuovere la definizione predefinita del <xref:System.ComponentModel.Component.Dispose%2A> metodo.  
  
5.  Implementare la proprietà `LightShape`.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#360](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#360)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#360](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#360)]  
  
6.  Eseguire l'override del metodo <xref:System.Windows.Forms.Control.OnPaint%2A>. Questa implementazione verrà disegnato un quadrato pieno e un cerchio. Evidenzia il valore selezionato disegnando un bordo intorno a una forma o l'altro.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#380](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#380)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#380](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#380)]  
  
## <a name="testing-your-custom-control-in-the-designer"></a>Test del controllo personalizzato nella finestra di progettazione  
 A questo punto, è possibile compilare il `MarqueeControlLibrary` progetto. Creazione di un controllo che eredita da testare l'implementazione di `MarqueeControl` classe e l'uso in un form.  
  
#### <a name="to-create-a-custom-marqueecontrol-implementation"></a>Per creare un'implementazione personalizzata di MarqueeControl  
  
1.  Aprire `DemoMarqueeControl` in Progettazione Windows Form. Crea un'istanza del `DemoMarqueeControl` tipo e lo visualizza in un'istanza del `MarqueeControlRootDesigner` tipo.  
  
2.  Nel **della casella degli strumenti**, aprire il **componenti MarqueeControlLibrary** scheda. Verrà visualizzato il `MarqueeBorder` e `MarqueeText` disponibili per la selezione di controlli.  
  
3.  Trascinare un'istanza di `MarqueeBorder` sul controllo di `DemoMarqueeControl` area di progettazione. Ancorare il `MarqueeBorder` nel controllo padre.  
  
4.  Trascinare un'istanza di `MarqueeText` sul controllo di `DemoMarqueeControl` area di progettazione.  
  
5.  Compilare la soluzione.  
  
6.  Fare doppio clic su di `DemoMarqueeControl` e dal menu di scelta rapida selezionare il **Esegui Test** per avviare l'animazione. Fare clic su **Interrompi Test** per arrestare l'animazione.  
  
7.  Aprire **Form1** nella visualizzazione progettazione.  
  
8.  Inserire due <xref:System.Windows.Forms.Button> controlli nel form. Denominarle `startButton` e `stopButton`e modificare il <xref:System.Windows.Forms.Control.Text%2A> valori della proprietà da **avviare** e **arrestare**, rispettivamente.  
  
9. Implementare <xref:System.Windows.Forms.Control.Click> gestori eventi per entrambi <xref:System.Windows.Forms.Button> controlli.  
  
10. Nel **della casella degli strumenti**, aprire il **Componenti MarqueeControlTest** scheda. Verrà visualizzato il `DemoMarqueeControl` disponibili per la selezione.  
  
11. Trascinare un'istanza di `DemoMarqueeControl` sul **Form1** area di progettazione.  
  
12. Nel <xref:System.Windows.Forms.Control.Click> richiamare i gestori eventi, il `Start` e `Stop` metodi di `DemoMarqueeControl`.  
  
```vb  
Private Sub startButton_Click(sender As Object, e As System.EventArgs)  
    Me.demoMarqueeControl1.Start()  
End Sub 'startButton_Click  
  
Private Sub stopButton_Click(sender As Object, e As System.EventArgs)  
Me.demoMarqueeControl1.Stop()  
End Sub 'stopButton_Click  
```  
  
```csharp  
private void startButton_Click(object sender, System.EventArgs e)  
{  
    this.demoMarqueeControl1.Start();  
}  
  
private void stopButton_Click(object sender, System.EventArgs e)  
{  
    this.demoMarqueeControl1.Stop();  
}  
```  
  
1.  Impostare il `MarqueeControlTest` il progetto come progetto di avvio ed eseguirlo. Verrà visualizzato il modulo contenente il `DemoMarqueeControl`. Fare clic su di **avviare** per iniziare l'animazione. Dovrebbe essere la luce lo spostamento del bordo e il testo lampeggiante.  
  
## <a name="next-steps"></a>Passaggi successivi  
 Il `MarqueeControlLibrary` illustra una semplice implementazione di controlli personalizzati e finestre di progettazione associate. È possibile rendere più sofisticate in questo esempio in diversi modi:  
  
-   Modificare i valori di proprietà per il `DemoMarqueeControl` nella finestra di progettazione. Aggiungere più `MarqueBorder` controlla e ancorarli nelle relative istanze padre per creare un effetto annidato. Provare varie combinazioni di impostazioni diverse per il `UpdatePeriod` e le proprietà correlate alla luce.  
  
-   Creare altre implementazioni di `IMarqueeWidget`. È possibile, ad esempio, può creare un "neon segno" lampeggiante o un'animazione con più immagini.  
  
-   Consente di personalizzare ulteriormente l'esperienza in fase di progettazione. È possibile eseguire lo shadowing di più proprietà di <xref:System.Windows.Forms.Control.Enabled%2A> e <xref:System.Windows.Forms.Control.Visible%2A>, ed è possibile aggiungere nuove proprietà. Aggiungere nuovi verbi di progettazione per semplificare le attività comuni come ancorare i controlli figlio.  
  
-   Licenza di `MarqueeControl`. Per ulteriori informazioni, vedere [come: licenza componenti e controlli](http://msdn.microsoft.com/library/8e66c1ed-a445-4b26-8185-990b6e2bbd57).  
  
-   Controllare il modo in cui vengono serializzati i controlli e la modalità di generazione di codice per loro. Per ulteriori informazioni, vedere [compilazione e generazione di codice sorgente dinamico](../../../../docs/framework/reflection-and-codedom/dynamic-source-code-generation-and-compilation.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.UserControl>  
 <xref:System.Windows.Forms.Design.ParentControlDesigner>  
 <xref:System.Windows.Forms.Design.DocumentDesigner>  
 <xref:System.ComponentModel.Design.IRootDesigner>  
 <xref:System.ComponentModel.Design.DesignerVerb>  
 <xref:System.Drawing.Design.UITypeEditor>  
 <xref:System.ComponentModel.BackgroundWorker>  
 [Procedura: Creare un controllo Windows Form che utilizza le funzionalità di progettazione](http://msdn.microsoft.com/library/8e0bad0e-56f3-43d2-bf63-a945c654d97c)  
 [Estensione del supporto in fase di progettazione](http://msdn.microsoft.com/library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2)  
 [Finestre di progettazione personalizzate](http://msdn.microsoft.com/library/ca11988e-d38e-44d8-a05d-71362ae7844d)  
 [Libreria di forme .NET: Progettazione di esempio](http://windowsforms.net/articles/shapedesigner.aspx)
