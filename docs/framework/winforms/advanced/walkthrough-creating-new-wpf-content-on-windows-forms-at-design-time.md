---
title: 'Procedura dettagliata: Creazione di nuovo contenuto WPF in Windows Form in fase di progettazione'
ms.date: 08/18/2018
helpviewer_keywords:
- interoperability [Windows Forms], WPF and Windows Forms
- WPF content [Windows Forms], hosting in Windows Forms
- hosting WPF content in Windows Forms
- ElementHost control
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: 2e92d8e8-f0e4-4df7-9f07-2acf35cd798c
ms.openlocfilehash: ed48db399ba47f0e6be96f7bca33d3892b19e433
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61747681"
---
# <a name="walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time"></a>Procedura dettagliata: Creazione di nuovo contenuto WPF in Windows Form in fase di progettazione

Questo argomento descrive come creare un controllo Windows Presentation Foundation (WPF) da usare nelle applicazioni basate su Windows Form.

Questa procedura dettagliata prevede l'esecuzione delle attività seguenti:

- Creare il progetto.

- Creare un nuovo controllo WPF.

- Aggiungere il nuovo controllo WPF a un Windows Form. Il controllo WPF è ospitato in un controllo <xref:System.Windows.Forms.Integration.ElementHost>.

## <a name="prerequisites"></a>Prerequisiti

Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:

- Visual Studio 2017

## <a name="creating-the-project"></a>Creazione del progetto

Il primo passaggio consiste nella creazione del progetto Windows Form. Aprire Visual Studio e creare una nuova **Windows Forms App (.NET Framework)** progetto in Visual Basic o Visual c# denominato `HostingWpf`.

> [!NOTE]
> Con il contenuto WPF sono supportati solo progetti C# e Visual Basic.

## <a name="creating-a-new-wpf-control"></a>Creazione di un nuovo controllo WPF

Creare un nuovo controllo WPF e aggiungerlo al progetto è facile come aggiungere qualsiasi altro elemento. Finestra di progettazione Windows Form funziona con un particolare tipo di controllo denominato *controllo composito*, o *controllo utente*. Per altre informazioni sui controlli utente WPF, vedere <xref:System.Windows.Controls.UserControl>.

> [!NOTE]
> Il tipo <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> per WPF è distinto dal tipo di controllo utente fornito da Windows Form, denominato anch'esso <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>.

### <a name="to-create-a-new-wpf-control"></a>Per creare un nuovo controllo WPF.

1. Nelle **Esplora soluzioni**, aggiungere un nuovo **libreria di controlli utente WPF (.NET Framework)** progetto alla soluzione. Usare il nome predefinito per la libreria di controlli, `WpfControlLibrary1`. Il nome predefinito del controllo è `UserControl1.xaml`.

     Aggiunta del nuovo controllo ha gli effetti seguenti:

    - Viene aggiunto il file UserControl1.xaml.

    - Viene aggiunto il file UserControl1.xaml.cs o UserControl1.xaml.vb. Questo file contiene il code-behind per i gestori eventi e l'altra implementazione.

    - Vengono aggiunti riferimenti agli assembly WPF.

    - Il file UserControl1.xaml viene aperto in [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)].

2. In visualizzazione Progettazione verificare che `UserControl1` sia selezionato. Per altre informazioni, vedere [Procedura: Selezionare e spostare gli elementi nell'area di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).

3. Nel **le proprietà** finestra, impostare il valore della <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> le proprietà da **200**.

4. Dal **casella degli strumenti**, trascinare un <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> controllo nell'area di progettazione.

5. Nel **delle proprietà** finestra, impostare il valore della <xref:System.Windows.Controls.TextBox.Text%2A> proprietà **contenuto ospitato**.

    > [!NOTE]
    > In generale, è opportuno ospitare contenuto WPF più sofisticato. Il controllo <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> è qui usato a solo a titolo esemplificativo.

6. Compilare il progetto.

## <a name="adding-a-wpf-control-to-a-windows-form"></a>Aggiunta di un controllo WPF a un Windows Form

Il nuovo controllo WPF è pronto per l'uso sul form. Windows Form usa il <xref:System.Windows.Forms.Integration.ElementHost> controllo per ospitare contenuto WPF.

### <a name="to-add-a-wpf-control-to-a-windows-form"></a>Per aggiungere un controllo WPF a un Windows Form

1. Aprire `Form1` in Progettazione Windows Form.

2. Nel **casella degli strumenti**, trovare la scheda con etichettata **controlli utente WPF WPFUserControlLibrary**.

3. Trascinare un'istanza di `UserControl1` sul form.

    - Un controllo <xref:System.Windows.Forms.Integration.ElementHost> verrà creato automaticamente sul form per ospitare il controllo WPF.

    - Il <xref:System.Windows.Forms.Integration.ElementHost> controllo è denominato `elementHost1` e nel **delle proprietà** finestra, è possibile visualizzare relativo <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> è impostata su **UserControl1**.

    - I riferimenti agli assembly WPF vengono aggiunti al progetto.

    - Il controllo `elementHost1` include un pannello smart tag che mostra le opzioni di hosting disponibili.

4. Nel **ElementHost Tasks** pannello smart tag, seleziona **ancora nel contenitore padre**.

5. Premere **F5** per compilare ed eseguire l'applicazione.

## <a name="next-steps"></a>Passaggi successivi

Windows Form e WPF sono tecnologie diverse progettate per interagire strettamente. Per migliorare l'aspetto e comportamento nelle applicazioni, procedere come segue:

- Ospitare un controllo Windows Form in una pagina WPF. Per altre informazioni, vedere [Procedura dettagliata: Controllo che ospita un Windows Form in WPF](../../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).

- Applicare stili di visualizzazione Windows Form al contenuto WPF. Per altre informazioni, vedere [Procedura: Abilitare gli stili di visualizzazione in un'applicazione ibrida](../../wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md).

- Modificare lo stile del contenuto WPF. Per altre informazioni, vedere [Procedura dettagliata: Applicazione degli stili WPF contenuto](walkthrough-styling-wpf-content.md).

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Migrazione e interoperabilità](../../wpf/advanced/migration-and-interoperability.md)
- [Uso di controlli WPF](using-wpf-controls.md)
- [Progettare XAML in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
