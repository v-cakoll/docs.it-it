---
title: Ospitare un controllo Windows Forms in WPF
description: Informazioni su come ospitare Windows Forms controlli in Windows Presentation Foundation, che fornisce già molti controlli con un set di funzionalità avanzate.
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 9cb88415-39b0-4c46-80c4-ff325b674286
ms.openlocfilehash: ec67cf9fabaa5b7aadbb2a3c21ebf8dd828ee20f
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164982"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf"></a>Procedura dettagliata: Hosting di un controllo Windows Form in WPF

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] offre numerosi controlli con un insieme di funzionalità completo. Tuttavia, a volte può essere opportuno usare Windows Forms controlli sulle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pagine. Ad esempio, è possibile che si disponga di un investimento sostanziale nei controlli di Windows Forms esistenti o che si disponga di un controllo Windows Forms che fornisce funzionalità univoche.

In questa procedura dettagliata viene illustrato come ospitare un <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> controllo Windows Forms in una pagina utilizzando il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] codice.

Per un listato di codice completo delle attività illustrate in questa procedura dettagliata, vedere la pagina relativa all' [hosting di un controllo Windows Forms in WPF di esempio](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWPF).

## <a name="prerequisites"></a>Prerequisiti

Per completare la procedura dettagliata, è necessario Visual Studio.

## <a name="hosting-the-windows-forms-control"></a>Hosting del controllo Windows Forms

### <a name="to-host-the-maskedtextbox-control"></a>Per ospitare il controllo MaskedTextBox

1. Creare un progetto di applicazione WPF denominato `HostingWfInWpf` .

2. Aggiungere riferimenti agli assembly indicati di seguito.

    - WindowsFormsIntegration

    - System.Windows.Forms

3. Aprire MainWindow. XAML in WPF Designer.

4. Assegnare un nome all' <xref:System.Windows.Controls.Grid> elemento `grid1` .

     [!code-xaml[HostingWfInWPF#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml#1)]

5. Nella visualizzazione progettazione o nella visualizzazione XAML Selezionare l' <xref:System.Windows.Window> elemento.

6. Nella Finestra Proprietà fare clic sulla scheda **eventi** .

7. Fare doppio clic sull' <xref:System.Windows.FrameworkElement.Loaded> evento.

8. Inserire il codice seguente per gestire l' <xref:System.Windows.FrameworkElement.Loaded> evento.

     [!code-csharp[HostingWfInWPF#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#10)]
     [!code-vb[HostingWfInWPF#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#10)]

9. Nella parte superiore del file aggiungere la seguente `Imports` `using` istruzione o.

     [!code-csharp[HostingWfInWPF#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#11)]
     [!code-vb[HostingWfInWPF#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#11)]

10. Premere **F5** per compilare ed eseguire l'applicazione.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Progettare XAML in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [Procedura dettagliata: Hosting di un controllo Windows Form in WPF tramite XAML](walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml.md)
- [Procedura dettagliata: Hosting di un controllo composito Windows Form in WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Procedura dettagliata: Hosting di un controllo composito WPF in Windows Form](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Controlli Windows Form e controlli WPF equivalenti](windows-forms-controls-and-equivalent-wpf-controls.md)
- [Esempio di hosting di un controllo Windows Forms in WPF](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWPF)
