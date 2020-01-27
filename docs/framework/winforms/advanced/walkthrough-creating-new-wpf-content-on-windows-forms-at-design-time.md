---
title: Crea nuovo contenuto WPF in Windows Forms
titleSuffix: ''
ms.date: 08/18/2018
helpviewer_keywords:
- interoperability [Windows Forms], WPF and Windows Forms
- WPF content [Windows Forms], hosting in Windows Forms
- hosting WPF content in Windows Forms
- ElementHost control
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: 2e92d8e8-f0e4-4df7-9f07-2acf35cd798c
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 69a0598b05d1b2bff84b203317d6d5a166ce109d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746394"
---
# <a name="walkthrough-create-new-wpf-content-on-windows-forms-at-design-time"></a>Procedura dettagliata: creare nuovi contenuti WPF in Windows Forms in fase di progettazione

Questo articolo illustra come creare un controllo Windows Presentation Foundation (WPF) da usare nelle applicazioni basate su Windows Forms.

## <a name="prerequisites"></a>Prerequisiti

Per completare la procedura dettagliata, è necessario Visual Studio.

## <a name="create-the-project"></a>Creare il progetto

Aprire Visual Studio e creare un nuovo progetto di **App Windows Forms (.NET Framework)** in Visual Basic o C# in un oggetto visivo denominato `HostingWpf`.

> [!NOTE]
> Con il contenuto WPF sono supportati solo progetti C# e Visual Basic.

## <a name="create-a-new-wpf-control"></a>Creare un nuovo controllo WPF

Creare un nuovo controllo WPF e aggiungerlo al progetto è facile come aggiungere qualsiasi altro elemento. Il Progettazione Windows Form funziona con un particolare tipo di controllo denominato *controllo composito*o *controllo utente*. Per altre informazioni sui controlli utente WPF, vedere <xref:System.Windows.Controls.UserControl>.

> [!NOTE]
> Il tipo <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> per WPF è distinto dal tipo di controllo utente fornito da Windows Form, denominato anch'esso <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>.

Per creare un nuovo controllo WPF:

1. In **Esplora soluzioni**aggiungere un nuovo progetto di **libreria di controlli utente (.NET Framework) WPF** alla soluzione. Usare il nome predefinito per la libreria di controlli, `WpfControlLibrary1`. Il nome predefinito del controllo è `UserControl1.xaml`.

   L'aggiunta del nuovo controllo ha gli effetti seguenti:

   - Viene aggiunto il file UserControl1.xaml.

   - Viene aggiunto il file UserControl1.xaml.cs (o UserControl1. XAML. vb). Questo file contiene il code-behind per i gestori eventi e l'altra implementazione.

   - Vengono aggiunti riferimenti agli assembly WPF.

   - Il file UserControl1. XAML viene aperto in WPF Designer per Visual Studio.

2. In visualizzazione Progettazione verificare che `UserControl1` sia selezionato.

3. Nella finestra **Proprietà** impostare il valore delle proprietà <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> su **200**.

4. Dalla **casella degli strumenti**trascinare un controllo <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> nell'area di progettazione.

5. Nella finestra **Proprietà** impostare il valore della proprietà <xref:System.Windows.Controls.TextBox.Text%2A> su **contenuto ospitato**.

   > [!NOTE]
   > In generale, è opportuno ospitare contenuto WPF più sofisticato. Il controllo <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> è qui usato a solo a titolo esemplificativo.

6. Compilazione del progetto.

## <a name="add-a-wpf-control-to-a-windows-form"></a>Aggiungere un controllo WPF a un Windows Form

Il nuovo controllo WPF è pronto per l'uso sul form. Windows Forms utilizza il controllo <xref:System.Windows.Forms.Integration.ElementHost> per ospitare contenuto WPF.

Per aggiungere un controllo WPF a un Windows Form:

1. Aprire `Form1` in Progettazione Windows Form.

2. Nella **casella degli strumenti**trovare la scheda con etichetta **WPFUserControlLibrary WPF User Controls**.

3. Trascinare un'istanza di `UserControl1` sul form.

    - Un controllo <xref:System.Windows.Forms.Integration.ElementHost> verrà creato automaticamente sul form per ospitare il controllo WPF.

    - Il controllo <xref:System.Windows.Forms.Integration.ElementHost> è denominato `elementHost1` e nella finestra **Proprietà** è possibile visualizzare la relativa proprietà <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> è impostata su **UserControl1**.

    - I riferimenti agli assembly WPF vengono aggiunti al progetto.

    - Il controllo `elementHost1` include un pannello smart tag che mostra le opzioni di hosting disponibili.

4. Nel pannello smart tag **attività ElementHost** selezionare **ancora nel contenitore padre**.

5. Premere **F5** per compilare ed eseguire l'applicazione.

## <a name="next-steps"></a>Passaggi successivi

Windows Form e WPF sono tecnologie diverse progettate per interagire strettamente. Per fornire un aspetto e un comportamento più completi nelle applicazioni, provare a eseguire le operazioni seguenti:

- Ospitare un controllo Windows Form in una pagina WPF. Per ulteriori informazioni, vedere [procedura dettagliata: hosting di un controllo Windows Forms in WPF](../../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).

- Applicare stili di visualizzazione Windows Form al contenuto WPF. Per altre informazioni, vedere [Procedura: Abilitare stili di visualizzazione in un'applicazione ibrida](../../wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md).

- Modificare lo stile del contenuto WPF. Per ulteriori informazioni, vedere [procedura dettagliata: applicazione di stili al contenuto WPF](walkthrough-styling-wpf-content.md).

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Migrazione e interoperabilità](../../wpf/advanced/migration-and-interoperability.md)
- [Uso di controlli WPF](using-wpf-controls.md)
- [Progettare XAML in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
