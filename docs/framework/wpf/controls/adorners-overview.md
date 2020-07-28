---
title: Cenni preliminari sugli strumenti decorativi visuali
description: Informazioni sugli strumenti decorativi Windows Presentation Foundation, un tipo speciale di FrameworkElement che fornisce indicazioni a un utente, ad esempio handle funzionali per gli elementi.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], about adorners
ms.assetid: 33d4c5c2-2daf-4e45-ba9a-5b673e2b8280
ms.openlocfilehash: 43d4af9f86c6ae72a61f86d1ca19405c2dcc6cc8
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167734"
---
# <a name="adorners-overview"></a>Cenni preliminari sugli strumenti decorativi visuali

Gli strumenti decorativi sono un tipo speciale di <xref:System.Windows.FrameworkElement> , usato per fornire segnali visivi a un utente. Tra l'altro, è possibile usare gli strumenti decorativi per aggiungere handle funzionali agli elementi o fornire informazioni sullo stato relative a un controllo.

## <a name="about-adorners"></a>Informazioni sugli strumenti decorativi

Un oggetto <xref:System.Windows.Documents.Adorner> è un oggetto personalizzato <xref:System.Windows.FrameworkElement> associato a un oggetto <xref:System.Windows.UIElement> . Il rendering degli Adorner viene eseguito in un oggetto <xref:System.Windows.Documents.AdornerLayer> , ovvero una superficie di rendering che si trova sempre sopra l'elemento decorato o una raccolta di elementi decorati. Il rendering di uno strumento decorativo è indipendente dal rendering dell'oggetto <xref:System.Windows.UIElement> a cui è associato lo strumento decorativo visuale. Uno strumento decorativo visuale viene in genere posizionato in relazione all'elemento a cui è associato, utilizzando l'origine delle coordinate 2D standard posizionata in alto a sinistra dell'elemento decorato.

Applicazioni comuni per gli strumenti decorativi includono:

- Aggiunta di handle funzionali a un oggetto <xref:System.Windows.UIElement> che consente a un utente di modificare l'elemento in qualche modo, ovvero ridimensionare, ruotare, riposizionare e così via.
- Fornire indicazioni visive per identificare i vari stati, oppure in risposta a vari eventi.
- Sovrapposizione di decorazioni visive in un oggetto <xref:System.Windows.UIElement> .
- Mascherare visivamente o eseguire l'override di parte o di tutti i <xref:System.Windows.UIElement> .

[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] fornisce un framework di base per la decorazione di elementi visivi. La tabella seguente include i principali tipi usati per la decorazione di oggetti e il relativo scopo. Di seguito sono riportati alcuni esempi di utilizzo:

|||
|-|-|
|<xref:System.Windows.Documents.Adorner>|Classe di base astratta dalla quale ereditano tutte le implementazioni di strumenti decorativi concreti.|
|<xref:System.Windows.Documents.AdornerLayer>|Classe che rappresenta un livello di rendering per gli strumenti decorativi di uno o più elementi decorati.|
|<xref:System.Windows.Documents.AdornerDecorator>|Classe che consente di associare un livello dello strumento decorativo a una raccolta di elementi.|

## <a name="implementing-a-custom-adorner"></a>Implementazione di uno strumento decorativo personalizzato

Il framework di strumenti decorativi fornito da [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] è progettato principalmente per supportare la creazione di strumenti decorativi personalizzati. Uno strumento decorativo personalizzato viene creato implementando una classe che eredita dalla <xref:System.Windows.Documents.Adorner> classe astratta.

> [!NOTE]
> L'elemento padre di un oggetto <xref:System.Windows.Documents.Adorner> è <xref:System.Windows.Documents.AdornerLayer> che esegue il rendering dell'oggetto <xref:System.Windows.Documents.Adorner> , non dell'elemento decorato.

L'esempio seguente mostra una classe che implementa uno strumento decorativo semplice. Lo strumento decorativo di esempio semplicemente decora gli angoli di un oggetto <xref:System.Windows.UIElement> con i cerchi.

[!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
[!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]
  
La figura seguente mostra la SimpleCircleAdorner applicata a <xref:System.Windows.Controls.TextBox> :

![Screenshot che mostra una casella di testo decorata.](./media/adorners-overview/simplecircleadorner-textbox.png)

## <a name="rendering-behavior-for-adorners"></a>Comportamento di rendering per gli strumenti decorativi

È importante notare che gli strumenti decorativi non includono alcun comportamento di rendering inerente, pertanto è responsabilità dell'implementatore garantire il rendering di uno strumento decorativo visuale. Un modo comune per implementare il comportamento di rendering consiste nell'eseguire l'override del <xref:System.Windows.UIElement.OnRender%2A> metodo e usare uno o più <xref:System.Windows.Media.DrawingContext> oggetti per eseguire il rendering degli oggetti visivi dello strumento decorativo in base alle esigenze, come illustrato nell'esempio precedente.

> [!NOTE]
> Il rendering di qualsiasi elemento posizionato nel livello degli strumenti decorativi viene eseguito al di sopra degli altri stili impostati. In altre parole, gli strumenti decorativi vengono sempre visualizzati al di sopra degli altri elementi e non possono essere sottoposti a override tramite l'ordine z.

## <a name="events-and-hit-testing"></a>Eventi e hit test

Gli strumenti decorativi ricevono gli eventi di input esattamente come tutti gli altri <xref:System.Windows.FrameworkElement> .  Poiché uno strumento decorativo ha sempre un ordine z più elevato rispetto all'elemento che adorna, lo strumento decorativo riceve gli eventi di input (ad esempio <xref:System.Windows.UIElement.Drop> o <xref:System.Windows.UIElement.MouseMove> ) che possono essere destinati all'elemento decorato sottostante.  Uno strumento decorativo può ascoltare determinati eventi di input e passare tali valori all'elemento decorato sottostante generando nuovamente l'evento.

Per abilitare l'hit test pass-through di elementi in uno strumento decorativo visuale, impostare la proprietà hit test <xref:System.Windows.UIElement.IsHitTestVisible%2A> su **false** nello strumento decorativo visuale.  Per ulteriori informazioni sugli hit testing, vedere [hit testing a livello visivo](../graphics-multimedia/hit-testing-in-the-visual-layer.md).

## <a name="adorning-a-single-uielement"></a>Decorazione di un singolo UIElement

Per associare uno strumento decorativo a un particolare <xref:System.Windows.UIElement> , attenersi alla seguente procedura:

1. Chiamare il metodo statico <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> per ottenere un <xref:System.Windows.Documents.AdornerLayer> oggetto per l'oggetto <xref:System.Windows.UIElement> da decorare. <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>esamina la struttura ad albero visuale, iniziando dall'oggetto specificato <xref:System.Windows.UIElement> e restituisce il primo livello dello strumento decorativo rilevato. (se non viene trovato alcun livello dello strumento decorativo, il metodo restituisce null).

2. Chiamare il <xref:System.Windows.Documents.AdornerLayer.Add%2A> metodo per associare lo strumento decorativo visuale alla destinazione <xref:System.Windows.UIElement> .

 Nell'esempio seguente viene associato un SimpleCircleAdorner (illustrato in precedenza) a <xref:System.Windows.Controls.TextBox> un *oggetto denominato TextBox*:

 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]

> [!NOTE]
> Non è attualmente possibile usare [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] per associare uno strumento decorativo a un altro elemento.

## <a name="adorning-the-children-of-a-panel"></a>Decorazione degli elementi figlio di un elemento Panel

Per associare uno strumento decorativo agli elementi figlio di un <xref:System.Windows.Controls.Panel> , attenersi alla procedura seguente:

1. Chiamare il `static` metodo <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> per trovare un livello dello strumento decorativo per l'elemento i cui elementi figlio devono essere decorati.

2. Enumerare gli elementi figlio dell'elemento padre e chiamare il <xref:System.Windows.Documents.AdornerLayer.Add%2A> metodo per associare uno strumento decorativo a ogni elemento figlio.

Nell'esempio seguente viene associato un SimpleCircleAdorner (illustrato in precedenza) agli elementi figlio di un oggetto <xref:System.Windows.Controls.StackPanel> denominato *StackPanel*:

[!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
[!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.AdornerHitTestResult>
- [Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF](../graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
- [Disegnare con oggetti Image, Drawing e Visual](../graphics-multimedia/painting-with-images-drawings-and-visuals.md)
- [Cenni preliminari sugli oggetti Drawing](../graphics-multimedia/drawing-objects-overview.md)
- [Procedure relative](adorners-how-to-topics.md)
