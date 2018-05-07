---
title: 'Procedura dettagliata: debug di controlli di Windows Form personalizzati in fase di progettazione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- debugging [Visual Studio], walkthroughs
- custom controls [Windows Forms], walkthroughs
- visual editors
- debugging [Visual Studio], Windows Forms
- custom controls [Windows Forms], debugging
- designers
- controls [Windows Forms], debugging
- walkthroughs [Windows Forms], debugging
- design-time debugging
ms.assetid: 1fd83ccd-3798-42fc-85a3-6cba99467387
ms.openlocfilehash: b87c46b2182884f90b427498b9af696d14acac96
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-debugging-custom-windows-forms-controls-at-design-time"></a>Procedura dettagliata: debug di controlli di Windows Form personalizzati in fase di progettazione
Quando si crea un controllo personalizzato, si sarà spesso che sia necessario eseguire il debug il comportamento in fase di progettazione. Ciò vale soprattutto per la creazione di una finestra di progettazione personalizzata per il controllo personalizzato. Per informazioni dettagliate, vedere [procedura dettagliata: creazione di un Windows Form controllo che accetta vantaggio di Visual Studio in fase di progettazione funzionalità](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md).  
  
 È possibile eseguire il debug dei controlli personalizzati in Visual Studio, esattamente come si trattasse del debug di altre classi .NET Framework. La differenza è che si eseguirà il debug di un'istanza separata di Visual Studio che è in esecuzione il codice del controllo personalizzato  
  
 Le attività illustrate nella procedura dettagliata sono le seguenti:  
  
-   Creazione di un progetto Windows Form per ospitare il controllo personalizzato  
  
-   Creazione di un progetto libreria di controlli  
  
-   Aggiunta di una proprietà al controllo personalizzato  
  
-   Aggiunta del controllo personalizzato per il form host  
  
-   Impostazione del progetto per il debug in fase di progettazione  
  
-   Debug del controllo personalizzato in fase di progettazione  
  
 Al termine, si avrà una migliore comprensione delle attività necessarie per il debug del comportamento in fase di progettazione di un controllo personalizzato.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="creating-the-project"></a>Creazione del progetto  
 Il primo passaggio consiste nel creare il progetto di applicazione. Questo progetto verrà utilizzato per compilare l'applicazione che ospita il controllo personalizzato.  
  
#### <a name="to-create-the-project"></a>Per creare il progetto  
  
-   Creare un progetto di applicazione Windows denominato "DebuggingExample". Per informazioni dettagliate, vedere [Procedura: creare un progetto di applicazione Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
## <a name="creating-a-control-library-project"></a>Creazione di un progetto libreria di controlli  
 Il passaggio successivo consiste nel creare il progetto libreria di controlli e impostare il controllo personalizzato.  
  
#### <a name="to-create-the-control-library-project"></a>Per creare il progetto libreria di controlli  
  
1.  Aggiungere un **libreria di controlli Windows** progetto alla soluzione.  
  
2.  Aggiungere un nuovo **UserControl** elemento al progetto DebugControlLibrary. Per informazioni dettagliate, vedere [NIB: procedura: aggiungere nuovi elementi di progetto](http://msdn.microsoft.com/library/63d3e16b-de6e-4bb5-a0e3-ecec762201ce). Assegnare il nuovo file di origine di un nome di base di "DebugControl".  
  
3.  Utilizzando il **Esplora**, eliminare il controllo del progetto predefinita eliminando il file di codice con il nome di base "`UserControl1`". Per informazioni dettagliate, vedere [NIB: procedura: escludere elementi, eliminazione e Rimuovi](http://msdn.microsoft.com/library/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73).  
  
4.  Compilare la soluzione.  
  
## <a name="checkpoint"></a>Checkpoint  
 A questo punto, sarà in grado di visualizzare il controllo personalizzato nel **della casella degli strumenti**.  
  
#### <a name="to-check-your-progress"></a>Per controllare lo stato di avanzamento  
  
-   Individuare la nuova scheda **Componenti DebugControlLibrary** e fare clic per selezionarlo. Quando si apre, verrà visualizzato il controllo elencato come **DebugControl** con accanto l'icona predefinita.  
  
## <a name="adding-a-property-to-your-custom-control"></a>Aggiunta di una proprietà al controllo personalizzato  
 Per dimostrare che il codice del controllo personalizzato è in esecuzione in fase di progettazione, si verrà aggiunta una proprietà e impostare un punto di interruzione nel codice che implementa la proprietà.  
  
#### <a name="to-add-a-property-to-your-custom-control"></a>Per aggiungere una proprietà al controllo personalizzato  
  
1.  Aprire **DebugControl** nel **Editor di codice**. Aggiungere il codice seguente alla definizione di classe:  
  
    ```vb  
    Private demoStringValue As String = Nothing  
    <BrowsableAttribute(true)>  
    Public Property DemoString() As String  
  
        Get  
            Return Me.demoStringValue  
        End Get  
  
        Set(ByVal value As String)  
            Me.demoStringValue = value  
        End Set  
  
    End Property  
    ```  
  
    ```csharp  
    private string demoStringValue = null;  
    [Browsable(true)]  
    public string DemoString  
    {  
        get  
        {  
            return this.demoStringValue;  
        }  
        set  
        {  
            demoStringValue = value;  
        }  
    }  
    ```  
  
2.  Compilare la soluzione.  
  
## <a name="adding-your-custom-control-to-the-host-form"></a>Aggiunta del controllo personalizzato per il Form Host  
 Per eseguire il debug il comportamento in fase di progettazione del controllo personalizzato, si inserirà un'istanza della classe del controllo personalizzato in un form di host.  
  
#### <a name="to-add-your-custom-control-to-the-host-form"></a>Per aggiungere il controllo personalizzato per il form host  
  
1.  Nel progetto "DebuggingExample", aprire Form1 nel **Progettazione Windows Form**.  
  
2.  Nel **della casella degli strumenti**, aprire il **Componenti DebugControlLibrary** scheda e trascinare un **DebugControl** istanza nel form.  
  
3.  Trovare il `DemoString` proprietà personalizzata di **proprietà** finestra. Si noti che è possibile modificare il relativo valore come si farebbe con qualsiasi altra proprietà. Si noti inoltre che quando il `DemoString` proprietà è selezionata, la stringa di descrizione della proprietà viene visualizzata nella parte inferiore del **proprietà** finestra.  
  
## <a name="setting-up-the-project-for-design-time-debugging"></a>Impostazione del progetto per il debug in fase di progettazione  
 Per eseguire il debug di comportamento in fase di progettazione del controllo personalizzato, si eseguirà il debug di un'istanza separata di Visual Studio che è in esecuzione il codice del controllo personalizzato.  
  
#### <a name="to-set-up-the-project-for-design-time-debugging"></a>Per impostare il progetto per il debug in fase di progettazione  
  
1.  Fare clic su di **DebugControlLibrary** nel progetto di **Esplora** e selezionare **proprietà**.  
  
2.  Nel **DebugControlLibrary** finestra delle proprietà, seleziona il **Debug** scheda.  
  
     Nel **azione di avvio** selezionare **Avvia programma esterno**. Sarà il debug di un'istanza separata di Visual Studio, quindi fare clic sui puntini di sospensione (![schermata VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) per cercare l'IDE di Visual Studio. Il nome del file eseguibile è **devenv.exe**, e se è installato nel percorso predefinito, il relativo percorso %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe.  
  
3.  Fare clic su **OK** per chiudere la finestra di dialogo.  
  
4.  Fare doppio clic su di **DebugControlLibrary** del progetto e selezionare **imposta come progetto di avvio** per abilitare la configurazione di debug.  
  
## <a name="debugging-your-custom-control-at-design-time"></a>Debug del controllo personalizzato in fase di progettazione  
 A questo punto si è pronti per eseguire il debug del controllo personalizzato in fase di esecuzione in modalità progettazione. Quando si avvia la sessione di debug, verrà creata una nuova istanza di Visual Studio e si utilizzerà per caricare la soluzione "DebuggingExample". Quando si apre Form1 nel **progettazione form**, verrà creata e inizierà l'esecuzione di un'istanza del controllo personalizzato.  
  
#### <a name="to-debug-your-custom-control-at-design-time"></a>Per eseguire il debug del controllo personalizzato in fase di progettazione  
  
1.  Aprire il **DebugControl** file di origine il **Editor di codice** e inserire un punto di interruzione il `Set` funzione di accesso del `DemoString` proprietà.  
  
2.  Premere F5 per avviare la sessione di debug. Si noti che viene creata una nuova istanza di Visual Studio. È possibile distinguere tra le istanze in due modi:  
  
    -   Istanza di debug contiene la parola **esecuzione** nella barra del titolo  
  
    -   Istanza di debug contiene il **avviare** pulsante relativo **Debug** barra degli strumenti disabilitato  
  
     Il punto di interruzione è impostato nell'istanza di debug.  
  
3.  Nella nuova istanza di Visual Studio, aprire la soluzione "DebuggingExample". È possibile trovare facilmente la soluzione selezionando **progetti recenti** dal **File** menu. Il file della soluzione "DebuggingExample" verrà elencato come più file utilizzati di recente.  
  
4.  Aprire Form1 nella **progettazione form** e selezionare il **DebugControl** controllo.  
  
5.  Modificare il valore della `DemoString` proprietà. Si noti che quando si esegue il commit della modifica, l'istanza di debug di Visual Studio acquisisce lo stato attivo e l'esecuzione si ferma in corrispondenza del punto di interruzione. È possibile passo a passo la funzione di accesso della proprietà come il sarebbe qualsiasi altro codice.  
  
6.  Quando si è terminato la sessione di debug, è possibile uscire chiudendo l'istanza host di Visual Studio o facendo clic di **Termina debug** pulsante nell'istanza di debug.  
  
## <a name="next-steps"></a>Passaggi successivi  
 Ora che è possibile eseguire il debug dei controlli personalizzati in fase di progettazione, esistono diverse possibilità per espandere l'interazione del controllo con l'IDE di Visual Studio.  
  
-   È possibile utilizzare il <xref:System.ComponentModel.Component.DesignMode%2A> proprietà la <xref:System.ComponentModel.Component> classe per scrivere codice che verrà eseguito solo in fase di progettazione. Per informazioni dettagliate, vedere <xref:System.ComponentModel.Component.DesignMode%2A>.  
  
-   Esistono numerosi attributi è possibile applicare alle proprietà del controllo per modificare l'interazione del controllo personalizzato con la finestra di progettazione. È possibile trovare questi attributi di <xref:System.ComponentModel?displayProperty=nameWithType> dello spazio dei nomi.  
  
-   È possibile scrivere una finestra di progettazione personalizzata per il controllo personalizzato. In questo modo il controllo completo della fase di progettazione utilizzando l'infrastruttura della finestra di progettazione estendibile esposta da Visual Studio. Per informazioni dettagliate, vedere [procedura dettagliata: creazione di un Windows Form controllo che accetta vantaggio di Visual Studio in fase di progettazione funzionalità](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura dettagliata: Creazione di un controllo Windows Form che usufruisca delle funzionalità offerte da Visual Studio in fase di progettazione](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)  
 [Procedura: accedere ai servizi in fase di progettazione](http://msdn.microsoft.com/library/c186c4b6-076c-438d-9ed3-f13da29c8c1f)  
 [Procedura: Accedere al supporto in fase di progettazione in Windows Forms](http://msdn.microsoft.com/library/a84f8579-1f47-41b9-ba37-69030b0aff09)
