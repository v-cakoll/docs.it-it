---
title: Ospitare un controllo ActiveX in WPF
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ActiveX controls [WPF interoperability]
- hosting ActiveX controls [WPF]
ms.assetid: 1931d292-0dd1-434f-963c-dcda7638d75a
ms.openlocfilehash: f2d9345eaaba7b85a217e6b230ae202f27ad3af8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742615"
---
# <a name="walkthrough-hosting-an-activex-control-in-wpf"></a>Procedura dettagliata: hosting di un controllo ActiveX in WPF
Per consentire una migliore interazione con i browser, è possibile utilizzare i controlli Microsoft ActiveX nell'applicazione basata su [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. In questa procedura dettagliata viene illustrato come è possibile ospitare Microsoft Windows Media Player come controllo in una pagina di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

 Le attività illustrate nella procedura dettagliata sono le seguenti:

- Creazione del progetto.

- Creazione del controllo ActiveX.

- Hosting del controllo ActiveX in una pagina WPF.

 Al termine di questa procedura dettagliata, si apprenderà come usare i controlli Microsoft ActiveX nell'applicazione basata su [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

## <a name="prerequisites"></a>Prerequisiti
 Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:

- Microsoft Windows Media Player installato nel computer in cui è installato Visual Studio.

- Visual Studio 2010.

## <a name="creating-the-project"></a>Creazione del progetto

### <a name="to-create-and-set-up-the-project"></a>Per creare e impostare il progetto

1. Creare un progetto di applicazione WPF denominato `HostingAxInWpf`.

2. Aggiungere un progetto libreria di controlli Windows Forms alla soluzione e denominare il progetto `WmpAxLib`.

3. Nel progetto WmpAxLib aggiungere un riferimento all'assembly di Windows Media Player, denominato wmp. dll.

4. Aprire la **casella degli strumenti**.

5. Fare clic con il pulsante destro del mouse nella **casella degli strumenti**, quindi **scegliere Scegli elementi**.

6. Fare clic sulla scheda **componenti com** , selezionare il controllo **Media Player Windows** , quindi fare clic su **OK**.

     Il controllo Media Player Windows viene aggiunto alla **casella degli strumenti**.

7. In Esplora soluzioni fare clic con il pulsante destro del mouse sul file **UserControl1** e quindi scegliere **Rinomina**.

8. Modificare il nome in `WmpAxControl.vb` o `WmpAxControl.cs`, a seconda del linguaggio.

9. Se viene richiesto di rinominare tutti i riferimenti, fare clic su **Sì**.

## <a name="creating-the-activex-control"></a>Creazione del controllo ActiveX
Visual Studio genera automaticamente una classe wrapper <xref:System.Windows.Forms.AxHost> per un controllo Microsoft ActiveX quando il controllo viene aggiunto a un'area di progettazione. La procedura seguente consente di creare un assembly gestito denominato AxInterop. WMPLib. dll.

### <a name="to-create-the-activex-control"></a>Per creare il controllo ActiveX

1. Aprire WmpAxControl. vb o WmpAxControl.cs nel Progettazione Windows Form.

2. Dalla **casella degli strumenti**aggiungere il controllo Windows Media Player nell'area di progettazione.

3. Nella Finestra Proprietà impostare il valore della proprietà <xref:System.Windows.Forms.Control.Dock%2A> del controllo Media Player di Windows su <xref:System.Windows.Forms.DockStyle.Fill>.

4. Compilare il progetto libreria di controlli WmpAxLib.

## <a name="hosting-the-activex-control-on-a-wpf-page"></a>Hosting del controllo ActiveX in una pagina WPF

### <a name="to-host-the-activex-control"></a>Per ospitare il controllo ActiveX

1. Nel progetto HostingAxInWpf aggiungere un riferimento all'assembly di interoperabilità ActiveX generato.

     Questo assembly è denominato AxInterop. WMPLib. dll ed è stato aggiunto alla cartella debug del progetto WmpAxLib quando è stato importato il controllo Media Player di Windows.

2. Aggiungere un riferimento all'assembly WindowsFormsIntegration, denominato WindowsFormsIntegration. dll.

3. Aggiungere un riferimento all'assembly [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], denominato System. Windows. Forms. dll.

4. Aprire MainWindow. XAML in WPF Designer.

5. Denominare l'elemento <xref:System.Windows.Controls.Grid> `grid1`.

     [!code-xaml[HostingAxInWpf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml#1)]

6. Nella visualizzazione progettazione o nella visualizzazione XAML Selezionare l'elemento <xref:System.Windows.Window>.

7. Nella Finestra Proprietà fare clic sulla scheda **eventi** .

8. Fare doppio clic sull'evento <xref:System.Windows.FrameworkElement.Loaded>.

9. Inserire il codice seguente per gestire l'evento <xref:System.Windows.FrameworkElement.Loaded>.

     Questo codice crea un'istanza del controllo <xref:System.Windows.Forms.Integration.WindowsFormsHost> e aggiunge un'istanza del controllo `AxWindowsMediaPlayer` come figlio.

     [!code-csharp[HostingAxInWpf#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml.cs#11)]
     [!code-vb[HostingAxInWpf#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingAxInWpf/VisualBasic/HostingAxInWpf/window1.xaml.vb#11)]  
  
10. Premere F5 per compilare ed eseguire l'applicazione.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Progettare XAML in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [Procedura dettagliata: Hosting di controlli Windows Form compositi in WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Procedura dettaglia: hosting di un controllo WPF composito in Windows Form](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
