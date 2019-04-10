---
title: 'Procedura dettagliata: Hosting di un controllo composito WPF 3D in Windows Form'
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting WPF content in Windows Forms [WPF]
- composite controls [WPF], hosting WPF in
ms.assetid: 486369a9-606a-4a3b-b086-a06f2119c7b0
ms.openlocfilehash: e5b98a33f29759a81ba1cbc1fefbd45c0e5bf736
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59330168"
---
# <a name="walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms"></a>Procedura dettagliata: Hosting di un controllo composito WPF 3D in Windows Form

Questa procedura dettagliata illustra come creare un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] composito controllano e ospitarlo in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] form e controlli tramite il <xref:System.Windows.Forms.Integration.ElementHost> controllo.

In questa procedura dettagliata verrà implementata una [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> che contiene due controlli figlio. Il <xref:System.Windows.Controls.UserControl> Visualizza un cono tridimensionale (3D). Il rendering di oggetti 3D è molto più semplice con il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] rispetto a con [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]. Pertanto, è logico all'host un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> classe per creare grafica 3D nel [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].

Le attività illustrate nella procedura dettagliata sono le seguenti:

-   Creazione di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.

-   Creazione del progetto host Windows Form.

-   Hosting di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.

## <a name="prerequisites"></a>Prerequisiti

Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:

-   Visual Studio 2017

<a name="To_Create_the_UserControl"></a>
## <a name="create-the-usercontrol"></a>Creare la classe UserControl

1. Creare un **libreria di controlli utente WPF** progetto denominato `HostingWpfUserControlInWf`.

2. Aprire UserControl1.xaml nel [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].

3. Sostituire il codice generato con il codice seguente:

     [!code-xaml[HostingWpfUserControlInWf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]

     Questo codice definisce un <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> che contiene due controlli figlio. Il primo controllo figlio è un <xref:System.Windows.Controls.Label?displayProperty=nameWithType> controllo; il secondo è un <xref:System.Windows.Controls.Viewport3D> controllo che visualizza un cono 3D.

<a name="To_Create_the_Windows_Forms_Host_Project"></a>
## <a name="create-the-host-project"></a>Creare il progetto host

1. Aggiungere un **App WPF (.NET Framework)** progetto denominato `WpfUserControlHost` alla soluzione. Per altre informazioni, vedere [Procedura dettagliata: Prima applicazione desktop WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md).

2. Nelle **Esplora soluzioni**, aggiungere un riferimento all'assembly WindowsFormsIntegration, denominato WindowsFormsIntegration. dll.

3. Aggiungere i riferimenti ai seguenti [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assembly:

    -   PresentationCore

    -   PresentationFramework

    -   WindowsBase

4. Aggiungere un riferimento al progetto `HostingWpfUserControlInWf`.

5. In Esplora soluzioni, impostare il `WpfUserControlHost` progetto come progetto di avvio.

<a name="To_Host_the_Windows_Presentation_Foundation"></a>
## <a name="host-the-usercontrol"></a>Ospitare il controllo UserControl

1. Aprire Form1 in Progettazione Windows Form.

2. Nella finestra Proprietà, fare clic su **eventi**e quindi fare doppio clic il <xref:System.Windows.Forms.Form.Load> eventi per creare un gestore eventi.

     Si apre l'Editor di codice appena generato `Form1_Load` gestore dell'evento.

3. Sostituire il codice in Form1.cs con il codice seguente.

     Il `Form1_Load` gestore eventi crea un'istanza di `UserControl1` e aggiunge ripristinare il <xref:System.Windows.Forms.Integration.ElementHost> insieme di controlli figlio del controllo. Il <xref:System.Windows.Forms.Integration.ElementHost> controllo viene aggiunto alla raccolta del modulo dei controlli figlio.

     [!code-csharp[HostingWpfUserControlInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/WpfUserControlHost/Form1.cs#10)]
     [!code-vb[HostingWpfUserControlInWf#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWpfUserControlInWf/VisualBasic/WpfUserControlHost/Form1.vb#10)]

4. Premere **F5** per compilare ed eseguire l'applicazione.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Progettare XAML in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
- [Procedura dettagliata: Hosting di un controllo composito WPF in Windows Form](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Procedura dettagliata: Hosting di un controllo composito Windows Form in WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Hosting di un controllo WPF composito in Windows Form](https://go.microsoft.com/fwlink/?LinkID=160001)