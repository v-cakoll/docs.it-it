---
title: Cenni preliminari sugli strumenti decorativi visuali
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], about adorners
ms.assetid: 33d4c5c2-2daf-4e45-ba9a-5b673e2b8280
ms.openlocfilehash: b41c1f10f7e1b7c1799fd27270a3eeb9899ceeb6
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111179"
---
# <a name="adorners-overview"></a>Cenni preliminari sugli strumenti decorativi visuali

Gli strumenti decorativi sono un tipo speciale di <xref:System.Windows.FrameworkElement>, utilizzato per fornire segnali visivi a un utente. Tra l'altro, è possibile usare gli strumenti decorativi per aggiungere handle funzionali agli elementi o fornire informazioni sullo stato relative a un controllo.

## <a name="about-adorners"></a>Informazioni sugli strumenti decorativi

Un <xref:System.Windows.Documents.Adorner> oggetto <xref:System.Windows.FrameworkElement> è una proprietà <xref:System.Windows.UIElement>associata a un oggetto . Gli strumenti decorativi visuali vengono sottoposti a rendering in un <xref:System.Windows.Documents.AdornerLayer>oggetto , che è una superficie di rendering che si trova sempre sopra l'elemento decorato o una raccolta di elementi decorati. Il rendering di uno strumento decorativo visuale è indipendente dal rendering dello <xref:System.Windows.UIElement> strumento decorativo visuale. Uno strumento decorativo visuale viene in genere posizionato rispetto all'elemento a cui è associato, utilizzando l'origine delle coordinate 2D standard situata nella parte superiore sinistra dell'elemento decorato.

Applicazioni comuni per gli strumenti decorativi includono:

- Aggiunta di maniglie funzionali a un <xref:System.Windows.UIElement> che consentono all'utente di modificare l'elemento in qualche modo (ridimensionare, ruotare, riposizionare e così via).
- Fornire indicazioni visive per identificare i vari stati, oppure in risposta a vari eventi.
- Sovrapposizione delle decorazioni visive su un <xref:System.Windows.UIElement>file .
- Mascherare o sostituire visivamente una <xref:System.Windows.UIElement>parte o tutto un file .

[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] fornisce un framework di base per la decorazione di elementi visivi. La tabella seguente include i principali tipi usati per la decorazione di oggetti e il relativo scopo. Di seguito sono riportati diversi esempi di utilizzo:

|||
|-|-|
|<xref:System.Windows.Documents.Adorner>|Classe di base astratta dalla quale ereditano tutte le implementazioni di strumenti decorativi concreti.|
|<xref:System.Windows.Documents.AdornerLayer>|Classe che rappresenta un livello di rendering per gli strumenti decorativi di uno o più elementi decorati.|
|<xref:System.Windows.Documents.AdornerDecorator>|Classe che consente di associare un livello dello strumento decorativo a una raccolta di elementi.|

## <a name="implementing-a-custom-adorner"></a>Implementazione di uno strumento decorativo personalizzato

Il framework di strumenti decorativi fornito da [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] è progettato principalmente per supportare la creazione di strumenti decorativi personalizzati. Uno strumento decorativo visuale personalizzato viene <xref:System.Windows.Documents.Adorner> creato implementando una classe che eredita dalla classe astratta.

> [!NOTE]
> L'elemento <xref:System.Windows.Documents.Adorner> padre <xref:System.Windows.Documents.AdornerLayer> di un <xref:System.Windows.Documents.Adorner>oggetto è che esegue il rendering di , non dell'elemento da orare.

L'esempio seguente mostra una classe che implementa uno strumento decorativo semplice. Lo strumento decorativo visuale <xref:System.Windows.UIElement> di esempio adorna semplicemente gli angoli di un con cerchi.

[!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
[!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]
  
L'immagine seguente mostra simpleCircleAdorner <xref:System.Windows.Controls.TextBox>applicato a un oggetto :

![Screenshot che mostra una casella di testo decorata.](./media/adorners-overview/simplecircleadorner-textbox.png)

## <a name="rendering-behavior-for-adorners"></a>Comportamento di rendering per gli strumenti decorativi

È importante notare che gli strumenti decorativi non includono alcun comportamento di rendering inerente, pertanto è responsabilità dell'implementatore garantire il rendering di uno strumento decorativo visuale. Un modo comune di implementare <xref:System.Windows.UIElement.OnRender%2A> il comportamento di <xref:System.Windows.Media.DrawingContext> rendering consiste nell'eseguire l'override del metodo e usare uno o più oggetti per eseguire il rendering degli oggetti visivi dello strumento decorativo visuale in base alle esigenze (come illustrato nell'esempio precedente).

> [!NOTE]
> Il rendering di qualsiasi elemento posizionato nel livello degli strumenti decorativi viene eseguito al di sopra degli altri stili impostati. In altre parole, gli strumenti decorativi vengono sempre visualizzati al di sopra degli altri elementi e non possono essere sottoposti a override tramite l'ordine z.

## <a name="events-and-hit-testing"></a>Eventi e hit test

Gli strumenti decorativi <xref:System.Windows.FrameworkElement>ricevono eventi di input come qualsiasi altro file .  Poiché uno strumento decorativo visuale ha sempre un ordine z superiore rispetto <xref:System.Windows.UIElement.Drop> <xref:System.Windows.UIElement.MouseMove>all'elemento che adorna, lo strumento decorativo visuale riceve gli eventi di input (ad esempio o ) che possono essere destinati all'elemento decorato sottostante.  Uno strumento decorativo può ascoltare determinati eventi di input e passare tali valori all'elemento decorato sottostante generando nuovamente l'evento.

Per abilitare l'hit testing pass-through degli elementi <xref:System.Windows.UIElement.IsHitTestVisible%2A> in uno strumento decorativo visuale, impostare la proprietà di hit test su **false** nello strumento decorativo visuale.  Per ulteriori informazioni [sull'hit](../graphics-multimedia/hit-testing-in-the-visual-layer.md)testing, vedere Hit Testing nel livello visivo .

## <a name="adorning-a-single-uielement"></a>Decorazione di un singolo UIElement

Per associare uno strumento <xref:System.Windows.UIElement>decorativo visuale a un particolare , attenersi alla seguente procedura:

1. Chiamare il <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> metodo statico <xref:System.Windows.Documents.AdornerLayer> per <xref:System.Windows.UIElement> ottenere un oggetto per l'oggetto da orare. <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>consente di salire nella struttura <xref:System.Windows.UIElement>ad albero visuale, a partire dal , e restituisce il primo livello dello strumento decorativo visuale trovato. (se non viene trovato alcun livello dello strumento decorativo, il metodo restituisce null).

2. Chiamare <xref:System.Windows.Documents.AdornerLayer.Add%2A> il metodo per associare <xref:System.Windows.UIElement>lo strumento decorativo visuale alla destinazione.

 L'esempio seguente associa un SimpleCircleAdorner (illustrato in precedenza) a un <xref:System.Windows.Controls.TextBox> oggetto denominato *myTextBox*:

 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]

> [!NOTE]
> Non è attualmente possibile usare [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] per associare uno strumento decorativo a un altro elemento.

## <a name="adorning-the-children-of-a-panel"></a>Decorazione degli elementi figlio di un elemento Panel

Per associare uno strumento decorativo visuale agli elementi figlio di un <xref:System.Windows.Controls.Panel>oggetto , attenersi alla seguente procedura:

1. Chiamare `static` il <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> metodo per trovare un livello dello strumento decorativo visuale per l'elemento i cui elementi figlio devono essere decorati.

2. Enumerare gli elementi figlio dell'elemento padre e chiamare il <xref:System.Windows.Documents.AdornerLayer.Add%2A> metodo per associare uno strumento decorativo visuale a ogni elemento figlio.

L'esempio seguente associa un SimpleCircleAdorner (illustrato in <xref:System.Windows.Controls.StackPanel> precedenza) agli elementi figlio di un oggetto denominato *myStackPanel*:

[!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
[!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.AdornerHitTestResult>
- [Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF](../graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
- [Disegnare con oggetti Image, Drawing e Visual](../graphics-multimedia/painting-with-images-drawings-and-visuals.md)
- [Cenni preliminari sugli oggetti Drawing](../graphics-multimedia/drawing-objects-overview.md)
- [Procedure relative](adorners-how-to-topics.md)
