---
title: Ospitare il controllo composito 3D WPF in Windows Forms
titleSuffix: ''
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting WPF content in Windows Forms [WPF]
- composite controls [WPF], hosting WPF in
ms.assetid: 486369a9-606a-4a3b-b086-a06f2119c7b0
ms.openlocfilehash: 07222809d62b207730ddad3c87b8fb60e1602bc3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744459"
---
# <a name="walkthrough-host-a-3d-wpf-composite-control-in-windows-forms"></a>Procedura dettagliata: ospitare un controllo composito 3D WPF in Windows Forms

In questa procedura dettagliata viene illustrato come creare un controllo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] composito e ospitarlo in controlli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] e form usando il controllo <xref:System.Windows.Forms.Integration.ElementHost>.

In questa procedura dettagliata verrà implementato un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> contenente due controlli figlio. Il <xref:System.Windows.Controls.UserControl> Visualizza un cono tridimensionale (3D). Il rendering degli oggetti 3D è molto più semplice con il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] rispetto a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]. È pertanto consigliabile ospitare una classe [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> per creare grafica 3D in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].

Le attività illustrate nella procedura dettagliata sono le seguenti:

- Creazione della <xref:System.Windows.Controls.UserControl>[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

- Creazione del progetto host Windows Forms.

- Hosting della <xref:System.Windows.Controls.UserControl>[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

## <a name="prerequisites"></a>Prerequisiti

Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:

- Visual Studio 2017

<a name="To_Create_the_UserControl"></a>
## <a name="create-the-usercontrol"></a>Creare UserControl

1. Creare un progetto **libreria di controlli utente WPF** denominato `HostingWpfUserControlInWf`.

2. Aprire UserControl1. XAML in WPF Designer.

3. Sostituire il codice generato con il codice seguente:

     [!code-xaml[HostingWpfUserControlInWf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]

     Questo codice definisce una <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> che contiene due controlli figlio. Il primo controllo figlio è un controllo <xref:System.Windows.Controls.Label?displayProperty=nameWithType>; il secondo è un controllo <xref:System.Windows.Controls.Viewport3D> che visualizza un cono 3D.

<a name="To_Create_the_Windows_Forms_Host_Project"></a>
## <a name="create-the-host-project"></a>Creare il progetto host

1. Aggiungere un progetto di **App Windows Forms (.NET Framework)** denominato `WpfUserControlHost` alla soluzione.

2. In **Esplora soluzioni**aggiungere un riferimento all'assembly WindowsFormsIntegration, denominato WindowsFormsIntegration. dll.

3. Aggiungere i riferimenti agli assembly [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] seguenti:

    - PresentationCore

    - PresentationFramework

    - WindowsBase

4. Aggiungere un riferimento al progetto `HostingWpfUserControlInWf`.

5. In Esplora soluzioni impostare il progetto `WpfUserControlHost` come progetto di avvio.

<a name="To_Host_the_Windows_Presentation_Foundation"></a>
## <a name="host-the-usercontrol"></a>Ospitare UserControl

1. Nella Progettazione Windows Form aprire Form1.

2. Nella Finestra Proprietà fare clic su **eventi**, quindi fare doppio clic sull'evento <xref:System.Windows.Forms.Form.Load> per creare un gestore eventi.

     Viene aperto l'editor di codice per il gestore dell'evento `Form1_Load` appena generato.

3. Sostituire il codice in Form1.cs con il codice seguente.

     Il gestore dell'evento `Form1_Load` crea un'istanza di `UserControl1` e aggiunge alla raccolta dei controlli figlio del controllo <xref:System.Windows.Forms.Integration.ElementHost>. Il controllo <xref:System.Windows.Forms.Integration.ElementHost> viene aggiunto alla raccolta di controlli figlio del form.

     [!code-csharp[HostingWpfUserControlInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/WpfUserControlHost/Form1.cs#10)]
     [!code-vb[HostingWpfUserControlInWf#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWpfUserControlInWf/VisualBasic/WpfUserControlHost/Form1.vb#10)]

4. Premere **F5** per compilare ed eseguire l'applicazione.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Progettare XAML in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [Procedura dettaglia: hosting di un controllo WPF composito in Windows Form](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Procedura dettagliata: Hosting di controlli Windows Form compositi in WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Hosting di un controllo composito WPF nell'esempio Windows Forms](https://go.microsoft.com/fwlink/?LinkID=160001)
