---
title: 'Procedura dettagliata: creazione della prima applicazione a tocco'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating a touch-sensitive application [WPF]
- touchscreen applications [WPF], creating
- touch-sensitive applications [WPF], creating
- creating a touchscreen application [WPF]
ms.assetid: d69e602e-9a25-4e24-950b-e89eaa2a906b
ms.openlocfilehash: 94a97c30179f7a8231426e31b8cacc364629ffc3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-creating-your-first-touch-application"></a>Procedura dettagliata: creazione della prima applicazione a tocco
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] consente alle applicazioni di rispondere al tocco. Ad esempio, è possibile interagire con un'applicazione utilizzando uno o più dita su un dispositivo di tocco sensibili, ad esempio un touchscreen, che questa procedura dettagliata viene creata un'applicazione che consente all'utente di spostare, ridimensionare o ruotare un oggetto tramite tocco.  
  
## <a name="prerequisites"></a>Prerequisiti  
 Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:  
  
-   [!INCLUDE[vs_dev10_ext](../../../../includes/vs-dev10-ext-md.md)].  
  
-   Windows 7.  
  
-   Un dispositivo che accetta l'input, ad esempio un touchscreen, che supporta Windows Touch tocco.  
  
 Inoltre, occorre una conoscenza di come creare un'applicazione in base [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], in particolare come sottoscrivere e gestire un evento. Per ulteriori informazioni, vedere [procedura dettagliata: applicazione desktop WPF prima](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).  
  
## <a name="creating-the-application"></a>Creare l'applicazione  
  
#### <a name="to-create-the-application"></a>Per creare l'applicazione  
  
1.  Creare un nuovo progetto di applicazione WPF in Visual Basic o Visual C# denominato `BasicManipulation`. Per altre informazioni, vedere [Procedura: Creare un nuovo progetto di applicazione WPF](http://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).  
  
2.  Sostituire il contenuto di MainWindow. XAML con il seguente codice XAML.  
  
     Questo codice crea un'applicazione semplice che contiene un rosso <xref:System.Windows.Shapes.Rectangle> su un <xref:System.Windows.Controls.Canvas>. Il <xref:System.Windows.UIElement.IsManipulationEnabled%2A> proprietà del <xref:System.Windows.Shapes.Rectangle> è impostata su true in modo che possa ricevere eventi di modifica. L'applicazione sottoscrive il <xref:System.Windows.UIElement.ManipulationStarting>, <xref:System.Windows.UIElement.ManipulationDelta>, e <xref:System.Windows.UIElement.ManipulationInertiaStarting> eventi. Questi eventi contengono la logica per spostare il <xref:System.Windows.Shapes.Rectangle> quando l'utente lo modifica.  
  
     [!code-xaml[BasicManipulation#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml#ui)]  
  
3.  Se si utilizza Visual Basic, nella prima riga di MainWindow. XAML, sostituire `x:Class="BasicManipulation.MainWindow"` con `x:Class="MainWindow"`.  
  
4.  Nel `MainWindow` classe, aggiungere le seguenti <xref:System.Windows.UIElement.ManipulationStarting> gestore dell'evento.  
  
     Il <xref:System.Windows.UIElement.ManipulationStarting> evento si verifica quando [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] rileva un tocco input inizia a modificare un oggetto. Il codice specifica che la posizione della modifica deve essere relativo al <xref:System.Windows.Window> impostando il <xref:System.Windows.Input.ManipulationStartingEventArgs.ManipulationContainer%2A> proprietà.  
  
     [!code-csharp[BasicManipulation#ManipulationStarting](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationstarting)]
     [!code-vb[BasicManipulation#ManipulationStarting](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationstarting)]  
  
5.  Nel `MainWindow` classe, aggiungere le seguenti <xref:System.Windows.Input.ManipulationDelta> gestore dell'evento.  
  
     Il <xref:System.Windows.Input.ManipulationDelta> evento si verifica quando il tocco cambia la posizione di input e può ricorrere più volte durante una manipolazione. L'evento può verificarsi anche dopo la generazione di un dito. Se l'utente trascina un dito su uno schermo, ad esempio il <xref:System.Windows.Input.ManipulationDelta> evento si verifica più volte durante lo spostamento di un dito. Quando l'utente solleva un dito dallo schermo, il <xref:System.Windows.Input.ManipulationDelta> evento continua a verificarsi per simulare l'inerzia.  
  
     Il codice si applica il <xref:System.Windows.Input.ManipulationDeltaEventArgs.DeltaManipulation%2A> per il <xref:System.Windows.UIElement.RenderTransform%2A> del <xref:System.Windows.Shapes.Rectangle> per spostarlo quando l'utente sposta il tocco di input. Controlla inoltre se il <xref:System.Windows.Shapes.Rectangle> è esterno ai limiti del <xref:System.Windows.Window> quando l'evento si verifica durante l'inerzia. In tal caso, l'applicazione chiama il <xref:System.Windows.Input.ManipulationDeltaEventArgs.Complete%2A?displayProperty=nameWithType> metodo per terminare la modifica.  
  
     [!code-csharp[BasicManipulation#ManipulationDelta](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationdelta)]
     [!code-vb[BasicManipulation#ManipulationDelta](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationdelta)]  
  
6.  Nel `MainWindow` classe, aggiungere le seguenti <xref:System.Windows.UIElement.ManipulationInertiaStarting> gestore dell'evento.  
  
     Il <xref:System.Windows.UIElement.ManipulationInertiaStarting> evento si verifica quando l'utente solleva tutte le dita dallo schermo. Il codice imposta la velocità iniziale e decelerazione per lo spostamento, espansione e la rotazione del rettangolo.  
  
     [!code-csharp[BasicManipulation#ManipulationInertiaStarting](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationinertiastarting)]
     [!code-vb[BasicManipulation#ManipulationInertiaStarting](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationinertiastarting)]  
  
7.  Compilare ed eseguire il progetto.  
  
     Verrà visualizzato un quadrato rosso vengono visualizzati nella finestra.  
  
## <a name="testing-the-application"></a>Verifica dell'applicazione  
 Per testare l'applicazione, provare le seguenti modifiche. Si noti che è possibile eseguire più di una delle seguenti operazioni nello stesso momento.  
  
-   Per spostare il <xref:System.Windows.Shapes.Rectangle>, inserire un dito sul <xref:System.Windows.Shapes.Rectangle> e spostare il dito sullo schermo.  
  
-   Per ridimensionare il <xref:System.Windows.Shapes.Rectangle>, posizionare due dita sul <xref:System.Windows.Shapes.Rectangle> e aprire o chiudere ogni dita.  
  
-   Per ruotare il <xref:System.Windows.Shapes.Rectangle>, posizionare due dita sul <xref:System.Windows.Shapes.Rectangle> e ruotare un dito intorno a altro.  
  
 Per fare in modo inerzia, sollevare velocemente le dita dallo schermo quando si eseguono modifiche precedenti. Il <xref:System.Windows.Shapes.Rectangle> continuerà a spostare, ridimensionare o ruotare per alcuni secondi prima di interrompere.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.UIElement.ManipulationStarting?displayProperty=nameWithType>  
 <xref:System.Windows.UIElement.ManipulationDelta?displayProperty=nameWithType>  
 <xref:System.Windows.UIElement.ManipulationInertiaStarting?displayProperty=nameWithType>
