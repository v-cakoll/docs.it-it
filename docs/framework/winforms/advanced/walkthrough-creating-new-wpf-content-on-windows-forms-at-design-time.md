---
title: 'Procedura dettagliata: creazione di nuovo contenuto WPF in Windows Form in fase di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [Windows Forms], WPF and Windows Forms
- WPF content [Windows Forms], hosting in Windows Forms
- hosting WPF content in Windows Forms
- ElementHost control
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: 2e92d8e8-f0e4-4df7-9f07-2acf35cd798c
ms.openlocfilehash: 1ea0160530fea0f35c6d4746dc4bbca9439bc462
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529009"
---
# <a name="walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time"></a>Procedura dettagliata: creazione di nuovo contenuto WPF in Windows Form in fase di progettazione
Questo argomento descrive come creare un controllo Windows Presentation Foundation (WPF) da usare nelle applicazioni basate su Windows Form.  
  
 Questa procedura dettagliata prevede l'esecuzione delle attività seguenti:  
  
-   Creare il progetto.  
  
-   Creare un nuovo controllo WPF.  
  
-   Aggiungere il nuovo controllo WPF a un Windows Form. Il controllo WPF è ospitato in un controllo <xref:System.Windows.Forms.Integration.ElementHost>.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="prerequisites"></a>Prerequisiti  
 Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].  
  
## <a name="creating-the-project"></a>Creazione del progetto  
 Il primo passaggio consiste nella creazione del progetto Windows Form.  
  
> [!NOTE]
>  Con il contenuto WPF sono supportati solo progetti C# e Visual Basic.  
  
#### <a name="to-create-the-project"></a>Per creare il progetto  
  
-   Creare un nuovo progetto applicazione Windows Forms in Visual Basic o Visual c# denominato `HostingWpf`.  
  
## <a name="creating-a-new-wpf-control"></a>Creazione di un nuovo controllo WPF  
 Creare un nuovo controllo WPF e aggiungerlo al progetto è facile come aggiungere qualsiasi altro elemento. Progettazione Windows Form funziona con un particolare tipo di controllo denominato *controllo composito*, o *controllo utente*. Per altre informazioni sui controlli utente WPF, vedere <xref:System.Windows.Controls.UserControl>.  
  
> [!NOTE]
>  Il tipo <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> per WPF è distinto dal tipo di controllo utente fornito da Windows Form, denominato anch'esso <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>.  
  
#### <a name="to-create-a-new-wpf-control"></a>Per creare un nuovo controllo WPF.  
  
1.  In **Esplora**, aggiungere un nuovo **libreria di controlli utente WPF** progetto alla soluzione. Usare il nome predefinito per la libreria di controlli, `WpfControlLibrary1`. Il nome predefinito del controllo è `UserControl1.xaml`.  
  
     L'aggiunta del nuovo controllo ha gli effetti seguenti:  
  
    -   Viene aggiunto il file UserControl1.xaml.  
  
    -   Viene aggiunto il file UserControl1.xaml.cs o UserControl1.xaml.vb. Questo file contiene il code-behind per i gestori eventi e l'altra implementazione.  
  
    -   Vengono aggiunti riferimenti agli assembly WPF.  
  
    -   Il file UserControl1.xaml viene aperto in [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)].  
  
2.  In visualizzazione Progettazione verificare che `UserControl1` sia selezionato. Per ulteriori informazioni, vedere [procedura: selezionare e spostare elementi nella finestra di progettazione](http://msdn.microsoft.com/library/54cb70b6-b35b-46e4-a0cc-65189399c474).  
  
3.  Nel **proprietà** finestra, impostare il valore della <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> proprietà `200`.  
  
4.  Dal **della casella degli strumenti**, trascinare un <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> controllo sull'area di progettazione.  
  
5.  Nel **proprietà** finestra, impostare il valore della <xref:System.Windows.Controls.TextBox.Text%2A> proprietà **contenuto ospitato**.  
  
    > [!NOTE]
    >  In generale, è opportuno ospitare contenuto WPF più sofisticato. Il controllo <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> è qui usato a solo a titolo esemplificativo.  
  
6.  Compilare il progetto.  
  
## <a name="adding-a-wpf-control-to-a-windows-form"></a>Aggiunta di un controllo WPF a un Windows Form  
 Il nuovo controllo WPF è pronto per l'uso sul form. Windows Forms usa il controllo <xref:System.Windows.Forms.Integration.ElementHost> per ospitare contenuto WPF  
  
#### <a name="to-add-a-wpf-control-to-a-windows-form"></a>Per aggiungere un controllo WPF a un Windows Form  
  
1.  Aprire `Form1` in Progettazione Windows Form.  
  
2.  Nel **della casella degli strumenti**, individuare la scheda **controlli utente WPF WPFUserControlLibrary**.  
  
3.  Trascinare un'istanza di `UserControl1` sul form.  
  
    -   Un controllo <xref:System.Windows.Forms.Integration.ElementHost> verrà creato automaticamente sul form per ospitare il controllo WPF.  
  
    -   Il <xref:System.Windows.Forms.Integration.ElementHost> controllo è denominato `elementHost1` e nel **proprietà** , è possibile visualizzare il relativo <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> è impostata su **UserControl1**.  
  
    -   I riferimenti agli assembly WPF vengono aggiunti al progetto.  
  
    -   Il controllo `elementHost1` include un pannello smart tag che mostra le opzioni di hosting disponibili.  
  
4.  Nel **ElementHost Tasks** pannello smart tag, seleziona **ancora nel contenitore padre**.  
  
5.  Premere F5 per compilare ed eseguire l'applicazione.  
  
## <a name="next-steps"></a>Passaggi successivi  
 Windows Form e WPF sono tecnologie diverse progettate per interagire strettamente. Per migliorare l'aspetto e il comportamento nelle applicazioni, provare le operazioni seguenti.  
  
-   Ospitare un controllo Windows Form in una pagina WPF. Per ulteriori informazioni, vedere [procedura dettagliata: Hosting di un controllo Windows Form in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).  
  
-   Applicare stili di visualizzazione Windows Form al contenuto WPF. Per altre informazioni, vedere [Procedura: Abilitare stili di visualizzazione in un'applicazione ibrida](../../../../docs/framework/wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md).  
  
-   Modificare lo stile del contenuto WPF. Per ulteriori informazioni, vedere [procedura dettagliata: applicazione di stili del contenuto WPF](../../../../docs/framework/winforms/advanced/walkthrough-styling-wpf-content.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Migrazione e interoperabilità](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [Uso di controlli WPF](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [WPF Designer](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)
