---
title: Cenni preliminari sugli strumenti decorativi visuali
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: adorners [WPF], about adorners
ms.assetid: 33d4c5c2-2daf-4e45-ba9a-5b673e2b8280
caps.latest.revision: "35"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 42e37a1a1c00ab1a2039eba5f310cadf9a2175c1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="adorners-overview"></a>Cenni preliminari sugli strumenti decorativi visuali
Gli strumenti decorativi sono un tipo speciale di <xref:System.Windows.FrameworkElement>, utilizzata per fornire indicazioni visive a un utente. Tra l'altro, è possibile usare gli strumenti decorativi per aggiungere handle funzionali agli elementi o fornire informazioni sullo stato relative a un controllo.  
  
  
  
<a name="about_Adorners"></a>   
## <a name="about-adorners"></a>Informazioni sugli strumenti decorativi  
 Un <xref:System.Windows.Documents.Adorner> è un oggetto personalizzato <xref:System.Windows.FrameworkElement> associato a un <xref:System.Windows.UIElement>. Gli strumenti decorativi vengono visualizzati in un <xref:System.Windows.Documents.AdornerLayer>, che è una superficie di rendering che si trova sempre nella parte superiore dell'elemento decorato o una raccolta di elementi decorati. Il rendering di uno strumento decorativo è indipendente dal rendering del <xref:System.Windows.UIElement> lo strumento decorativo a cui è associato. Uno strumento decorativo in genere è posizionato in relazione all'elemento a cui è associato, usando l'origine delle coordinate 2D standard che si trova in alto a sinistra dell'elemento decorato.  
  
 Applicazioni comuni per gli strumenti decorativi includono:  
  
-   Aggiunta di handle funzionali a un <xref:System.Windows.UIElement> che consentire agli utenti di modificare l'elemento in qualche modo (ridimensionare, ruotare, riposizionare e così via).  
  
-   Fornire indicazioni visive per identificare i vari stati, oppure in risposta a vari eventi.  
  
-   Sovrapporre decorazioni visuali su un <xref:System.Windows.UIElement>.  
  
-   Mascherare visivamente o eseguire l'override o parte di un <xref:System.Windows.UIElement>.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] fornisce un framework di base per la decorazione di elementi visivi. La tabella seguente include i principali tipi usati per la decorazione di oggetti e il relativo scopo. Di seguito sono riportati alcuni esempi di utilizzo.  
  
|||  
|-|-|  
|<xref:System.Windows.Documents.Adorner>|Classe di base astratta dalla quale ereditano tutte le implementazioni di strumenti decorativi concreti.|  
|<xref:System.Windows.Documents.AdornerLayer>|Classe che rappresenta un livello di rendering per gli strumenti decorativi di uno o più elementi decorati.|  
|<xref:System.Windows.Documents.AdornerDecorator>|Classe che consente di associare un livello dello strumento decorativo a una raccolta di elementi.|  
  
<a name="implement_custom_Adorner"></a>   
## <a name="implementing-a-custom-adorner"></a>Implementazione di uno strumento decorativo personalizzato  
 Il framework di strumenti decorativi fornito da [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] è progettato principalmente per supportare la creazione di strumenti decorativi personalizzati. Viene creato uno strumento decorativo personalizzato implementando una classe che eredita dalla classe astratta <xref:System.Windows.Documents.Adorner> classe.  
  
> [!NOTE]
>  L'elemento padre di un <xref:System.Windows.Documents.Adorner> è il <xref:System.Windows.Documents.AdornerLayer> che esegue il rendering di <xref:System.Windows.Documents.Adorner>, non l'elemento decorato.  
  
 L'esempio seguente mostra una classe che implementa uno strumento decorativo semplice. Lo strumento decorativo di esempio decora semplicemente gli angoli di un <xref:System.Windows.UIElement> con i cerchi.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
 [!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]  
  
 La figura seguente mostra il SimpleCircleAdorner a un <xref:System.Windows.Controls.TextBox>.  
  
 ![Esempio di strumento decorativo: elemento TextBox decorato](../../../../docs/framework/wpf/controls/media/adornedtextbox.png "AdornedTextBox")  
  
<a name="rendering_behavior_for_Adorners"></a>   
## <a name="rendering-behavior-for-adorners"></a>Comportamento di rendering per gli strumenti decorativi  
 È importante notare che gli strumenti decorativi non includono alcun comportamento di rendering inerente, pertanto è responsabilità dell'implementatore garantire il rendering di uno strumento decorativo visuale.   È un modo comune di implementare il comportamento di rendering per eseguire l'override di <xref:System.Windows.UIElement.OnRender%2A> metodo e utilizzare uno o più <xref:System.Windows.Media.DrawingContext> oggetti per eseguire il rendering degli elementi visivi dello strumento decorativo in base alle esigenze (come illustrato nell'esempio precedente).  
  
> [!NOTE]
>  Il rendering di qualsiasi elemento posizionato nel livello degli strumenti decorativi viene eseguito al di sopra degli altri stili impostati. In altre parole, gli strumenti decorativi vengono sempre visualizzati al di sopra degli altri elementi e non possono essere sottoposti a override tramite l'ordine z.  
  
<a name="adorner_events_hittest"></a>   
## <a name="events-and-hit-testing"></a>Eventi e hit test  
 Gli strumenti decorativi riceveranno eventi di input come qualsiasi altro <xref:System.Windows.FrameworkElement>.  Poiché uno strumento decorativo ha sempre un ordine z più elevato rispetto all'elemento che decora, lo strumento decorativo visuale riceve eventi di input (ad esempio <xref:System.Windows.UIElement.Drop> o <xref:System.Windows.UIElement.MouseMove>) che possono essere destinati all'elemento decorato sottostante.  Uno strumento decorativo può ascoltare determinati eventi di input e passare tali valori all'elemento decorato sottostante generando nuovamente l'evento.  
  
 Per abilitare l'hit testing pass-through di elementi in uno strumento decorativo visuale, impostare l'hit test <xref:System.Windows.UIElement.IsHitTestVisible%2A> proprietà **false** sullo strumento decorativo.  Per altre informazioni sull'hit test, vedere  
  
 [Hit testing a livello visivo](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md).  
  
<a name="adorn_single_element"></a>   
## <a name="adorning-a-single-uielement"></a>Decorazione di un singolo UIElement  
 Per associare un adorner a un particolare <xref:System.Windows.UIElement>, seguire questi passaggi:  
  
1.  Chiamare il metodo statico <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> per ottenere un <xref:System.Windows.Documents.AdornerLayer> dell'oggetto per il <xref:System.Windows.UIElement> da decorare. <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>descrive la struttura ad albero visuale, inizia in corrispondenza <xref:System.Windows.UIElement>e restituisce il primo livello dello strumento decorativo visuale trovato. (se non viene trovato alcun livello dello strumento decorativo, il metodo restituisce null).  
  
2.  Chiamare il <xref:System.Windows.Documents.AdornerLayer.Add%2A> metodo per associare lo strumento decorativo di destinazione <xref:System.Windows.UIElement>.  
  
 Nell'esempio seguente viene associato un SimpleCircleAdorner (illustrato in precedenza) a un <xref:System.Windows.Controls.TextBox> denominato *myTextBox*.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]  
  
> [!NOTE]
>  Non è attualmente possibile usare [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] per associare uno strumento decorativo a un altro elemento.  
  
<a name="adorn_children_panel"></a>   
## <a name="adorning-the-children-of-a-panel"></a>Decorazione degli elementi figlio di un elemento Panel  
 Per associare uno strumento decorativo visuale agli elementi figlio di un <xref:System.Windows.Controls.Panel>, seguire questi passaggi:  
  
1.  Chiamare il `static` metodo <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> per trovare un livello dello strumento decorativo per l'elemento per decorare i cui elementi figlio.  
  
2.  Enumerare gli elementi figlio dell'elemento padre e chiamata di <xref:System.Windows.Documents.AdornerLayer.Add%2A> metodo per associare un adorner a ogni elemento figlio.  
  
 Nell'esempio seguente viene associato un SimpleCircleAdorner (illustrato in precedenza) per gli elementi figlio di un <xref:System.Windows.Controls.StackPanel> denominato *myStackPanel*.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.AdornerHitTestResult>  
 [Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)  
 [Disegnare con oggetti Image, Drawing e Visual](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)  
 [Cenni preliminari sugli oggetti Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [Procedure relative](../../../../docs/framework/wpf/controls/adorners-how-to-topics.md)
