---
title: Nozioni di base sull'input penna
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- procedural code in lieu of XAML [WPF]
- gradient brush [WPF], animating colors of
- XAML [WPF], procedural code in lieu of
- animation [WPF], gradient brush colors
- brushes [WPF], animating colors of
ms.assetid: 760332dd-594a-475d-865b-01659db8cab7
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 74227ebe815e971087569ff39ac0a3479c1b0d14
ms.sourcegitcommit: d3cfda0943364aaf6ccd574f55f584576c8a4fee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/08/2018
---
# <a name="getting-started-with-ink"></a>Nozioni di base sull'input penna
Inserimento di input penna nelle applicazioni è più semplice che mai. Input penna è stato migliorato da un corollario al metodo COM e Windows Form di programmazione per raggiungere la piena integrazione in corso il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Non è necessario installare gli SDK separati o le librerie di runtime.  
  
## <a name="prerequisites"></a>Prerequisiti  
 Per utilizzare gli esempi seguenti, è innanzitutto necessario installare Microsoft Visual Studio 2005 e [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)]. È anche necessario avere conoscenze su come scrivere applicazioni per [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Per ulteriori informazioni sui concetti introduttivi di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vedere [procedura dettagliata: applicazione desktop WPF prima](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).  
  
## <a name="quick-start"></a>Avvio rapido  
 In questa sezione consente di scrivere un semplice [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazione che raccoglie input penna.  
  
 Se non già stato fatto, installare Microsoft Visual Studio 2005 e [!INCLUDE[TLA#tla_winfxsdk](../../../../includes/tlasharptla-winfxsdk-md.md)]. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] le applicazioni in genere devono essere compilate prima possibile visualizzarli, anche se sono costituite interamente [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Tuttavia, il [!INCLUDE[TLA#tla_winfxsdk](../../../../includes/tlasharptla-winfxsdk-md.md)] include un'applicazione, XamlPad, progettata per velocizzare il processo di implementazione di un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-interfaccia utente basata su. Per visualizzare e globalmente con i primi esempi riportati in questo documento, è possibile utilizzare tale applicazione. Il processo di creazione di applicazioni compilate da [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] viene descritta più avanti in questo documento.  
  
 Per avviare XAMLPad, fare clic su di **avviare** dal menu **tutti i programmi**, scegliere **Microsoft Windows SDK**, scegliere **strumenti**, fare clic su **XAMLPad**. Nel riquadro di rendering XAMLPad esegue il rendering del codice XAML scritto nel riquadro del codice. È possibile modificare il codice XAML, e le modifiche vengano visualizzate immediatamente nel riquadro di rendering.  
  
#### <a name="got-ink"></a>Hai input penna?  
 Per avviare la prima [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazione che supporta l'input penna:  
  
1.  Open Microsoft Visual Studio 2005  
  
2.  Creare un nuovo **applicazione WPF (Windows)**  
  
3.  Tipo `<InkCanvas/>` tra il `<Grid>` tag  
  
4.  Premere **F5** per avviare l'applicazione nel debugger  
  
5.  Tramite uno stilo o un mouse, scrivere **HelloWorld** nella finestra  
  
 Si è scritto l'equivalente di input penna di un'applicazione "hello world" con sequenze di tasti solo 12.  
  
#### <a name="spice-up-your-application"></a>Personalizzare l'applicazione  
 Per sfruttare alcune funzionalità del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Sostituire tutto il contenuto tra l'apertura \<finestra > e di chiusura \</Window > tag con il markup seguente per ottenere uno sfondo con pennello sfumato sull'area di input penna.  
  
 [!code-xaml[DigitalInkTopics#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#1)]  
[!code-xaml[DigitalInkTopics#1a](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#1a)]  
  
#### <a name="using-animation"></a>Utilizzo dell'animazione  
 Per una divertente, animare i colori del pennello sfumato. Aggiungere il seguente [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dopo la chiusura `</InkCanvas>` tag ma prima della chiusura `</Page>` tag.  
  
 [!code-xaml[DigitalInkTopics#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#2)]  
  
#### <a name="adding-some-code-behind-the-xaml"></a>Aggiunta di codice sottostante a XAML  
 Mentre XAML è molto semplice progettare l'interfaccia utente, qualsiasi applicazione reale deve aggiungere il codice per gestire gli eventi. Di seguito è riportato un esempio semplice che consente di ingrandire l'input penna in risposta al pulsante destro del mouse:  
  
 Impostare il `MouseRightButtonUp` gestore il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]:  
  
 [!code-xaml[DigitalInkTopics#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#3)]  
  
 In Esplora soluzioni di Visual Studio, espandere Windows1. XAML e aprire il file code-behind, Window1.xaml.cs o Window1. XAML se si utilizza Visual Basic. Aggiungere il codice del gestore eventi seguente:  
  
 [!code-csharp[DigitalInkTopics#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml.cs#4)]
 [!code-vb[DigitalInkTopics#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window2.xaml.vb#4)]  
  
 A questo punto, eseguire l'applicazione. Aggiungere un input penna e quindi fare clic con il mouse o eseguire un equivalente premere e tenere con stilo.  
  
#### <a name="using-procedural-code-instead-of-xaml"></a>Usando codice procedurale anziché XAML  
 È possibile accedere a tutti [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] funzionalità dal codice procedurale. In questo caso è un'applicazione "Hello Ink World" per [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] che non utilizza [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] affatto. Incollare il codice seguente in un'applicazione Console vuota in Visual Studio. Aggiungere riferimenti agli assembly WindowsBase, PresentationCore e PresentationFramework e compilare l'applicazione premendo **F5**:  
  
 [!code-csharp[InkCanvasConsoleApp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasConsoleApp/CSharp/Program.cs#1)]
 [!code-vb[InkCanvasConsoleApp#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InkCanvasConsoleApp/VisualBasic/Module1.vb#1)]  
  
## <a name="see-also"></a>Vedere anche  
 [Input penna](../../../../docs/framework/wpf/advanced/digital-ink.md)  
 [Raccolta di input penna](../../../../docs/framework/wpf/advanced/collecting-ink.md)  
 [Riconoscimento della grafia](../../../../docs/framework/wpf/advanced/handwriting-recognition.md)  
 [Archiviazione dell'input penna](../../../../docs/framework/wpf/advanced/storing-ink.md)
