---
title: 'Procedura dettagliata: Creazione della prima applicazione Touch'
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
ms.openlocfilehash: 34a534653455449233c2908f4226cdb3a9bb9867
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54724239"
---
# <a name="walkthrough-creating-your-first-touch-application"></a>Procedura dettagliata: Creazione della prima applicazione Touch
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] consente alle applicazioni rispondere al tocco. Ad esempio, è possibile interagire con un'applicazione utilizzando uno o più dita su un dispositivo sensibile al tocco, ad esempio un touchscreen che questa procedura dettagliata viene creata un'applicazione che consente all'utente di spostare, ridimensionare o ruotare un oggetto tramite tocco.  
  
## <a name="prerequisites"></a>Prerequisiti  
 Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:  
  
-   Visual Studio.  
  
-   Un dispositivo che accetta un input tocco, ad esempio un touchscreen, che supporta Windows Touch.  
  
 Inoltre, si deve avere una conoscenza di base di come creare un'applicazione in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], in particolare la modalità sottoscrivere e gestire un evento. Per altre informazioni, vedere [Procedura dettagliata: Prima applicazione desktop WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).  
  
## <a name="creating-the-application"></a>Creare l'applicazione  
  
#### <a name="to-create-the-application"></a>Per creare l'applicazione  
  
1.  Creare un nuovo progetto di applicazione WPF in Visual Basic o Visual C# denominato `BasicManipulation`. Per altre informazioni, vedere [Procedura: Creare un nuovo progetto applicazione WPF](https://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).  
  
2.  Sostituire il contenuto del file MainWindow. XAML con il XAML seguente.  
  
     Questo codice crea un'applicazione semplice che contiene una linea rossa <xref:System.Windows.Shapes.Rectangle> su un <xref:System.Windows.Controls.Canvas>. Il <xref:System.Windows.UIElement.IsManipulationEnabled%2A> proprietà del <xref:System.Windows.Shapes.Rectangle> è impostato su true in modo che possa ricevere gli eventi di manipolazione. L'applicazione sottoscrive il <xref:System.Windows.UIElement.ManipulationStarting>, <xref:System.Windows.UIElement.ManipulationDelta>, e <xref:System.Windows.UIElement.ManipulationInertiaStarting> eventi. Questi eventi contengono la logica per spostare il <xref:System.Windows.Shapes.Rectangle> quando l'utente lo modifica.  
  
     [!code-xaml[BasicManipulation#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml#ui)]  
  
3.  Se si usa Visual Basic, nella prima riga del file MainWindow. XAML, sostituire `x:Class="BasicManipulation.MainWindow"` con `x:Class="MainWindow"`.  
  
4.  Nel `MainWindow` classe, aggiungere il codice seguente <xref:System.Windows.UIElement.ManipulationStarting> gestore dell'evento.  
  
     Il <xref:System.Windows.UIElement.ManipulationStarting> evento si verifica quando [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] rileva un tocco input inizia a modificare un oggetto. Il codice specifica che la posizione della manipolazione deve essere relativa ai <xref:System.Windows.Window> impostando la <xref:System.Windows.Input.ManipulationStartingEventArgs.ManipulationContainer%2A> proprietà.  
  
     [!code-csharp[BasicManipulation#ManipulationStarting](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationstarting)]
     [!code-vb[BasicManipulation#ManipulationStarting](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationstarting)]

5.  Nel `MainWindow` classe, aggiungere il codice seguente <xref:System.Windows.Input.ManipulationDelta> gestore dell'evento.

     Il <xref:System.Windows.Input.ManipulationDelta> evento si verifica quando il tocco modificata la posizione di input e può essere presente più volte durante una manipolazione. L'evento può verificarsi anche dopo la generazione di un dito. Ad esempio, se l'utente sposta un dito su una schermata, il <xref:System.Windows.Input.ManipulationDelta> evento si verifica più volte durante lo spostamento del dito. Quando l'utente solleva un dito dallo schermo, la <xref:System.Windows.Input.ManipulationDelta> eventi continua a verificarsi per simulare l'inerzia.

     Il codice si applica il <xref:System.Windows.Input.ManipulationDeltaEventArgs.DeltaManipulation%2A> per il <xref:System.Windows.UIElement.RenderTransform%2A> del <xref:System.Windows.Shapes.Rectangle> per spostarla quando l'utente sposta il tocco di input. Viene inoltre verificato se il <xref:System.Windows.Shapes.Rectangle> fuori dei limiti del <xref:System.Windows.Window> quando l'evento si verifica durante l'inerzia. Pertanto, l'applicazione chiama il <xref:System.Windows.Input.ManipulationDeltaEventArgs.Complete%2A?displayProperty=nameWithType> metodo per terminare la modifica.

     [!code-csharp[BasicManipulation#ManipulationDelta](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationdelta)]
     [!code-vb[BasicManipulation#ManipulationDelta](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationdelta)]

6.  Nel `MainWindow` classe, aggiungere il codice seguente <xref:System.Windows.UIElement.ManipulationInertiaStarting> gestore dell'evento.

     Il <xref:System.Windows.UIElement.ManipulationInertiaStarting> evento si verifica quando l'utente genera tutte le dita dallo schermo. Il codice imposta la velocità iniziale e la decelerazione per il movimento, espansione e rotazione del rettangolo.

     [!code-csharp[BasicManipulation#ManipulationInertiaStarting](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationinertiastarting)]
     [!code-vb[BasicManipulation#ManipulationInertiaStarting](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationinertiastarting)]

7.  Compilare ed eseguire il progetto.

     Nella finestra verrà visualizzato un quadrato rosso.

## <a name="testing-the-application"></a>Verifica dell'applicazione
 Per testare l'applicazione, provare le modifiche che seguono. Si noti che è possibile eseguire più di una delle seguenti operazioni nello stesso momento.

-   Per spostare il <xref:System.Windows.Shapes.Rectangle>, posizionare un dito sul <xref:System.Windows.Shapes.Rectangle> e muovere il dito sullo schermo.

-   Per ridimensionare il <xref:System.Windows.Shapes.Rectangle>, posizionare due dita sul <xref:System.Windows.Shapes.Rectangle> e sposta le dita o chiudere ogni.

-   Per ruotare il <xref:System.Windows.Shapes.Rectangle>, posizionare due dita sul <xref:System.Windows.Shapes.Rectangle> e ruotare le dita una attorno a altra.

 Affinché l'inerzia, generare rapidamente le dita dalla schermata quando si eseguono modifiche precedenti. Il <xref:System.Windows.Shapes.Rectangle> continueranno a spostare, ridimensionare o ruotare per alcuni secondi prima che venga interrotta.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.UIElement.ManipulationStarting?displayProperty=nameWithType>
- <xref:System.Windows.UIElement.ManipulationDelta?displayProperty=nameWithType>
- <xref:System.Windows.UIElement.ManipulationInertiaStarting?displayProperty=nameWithType>