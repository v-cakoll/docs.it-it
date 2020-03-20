---
title: Utilizzo degli oggetti DrawingVisual
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- visual layer [WPF], DrawingVisual objects
- DrawingVisual objects in visual layer [WPF]
ms.assetid: 0b4e711d-e640-40cb-81c3-8f5c59909b7d
ms.openlocfilehash: 9d67fbc0d9716c9df3935232c6c7e579b50d55bb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148322"
---
# <a name="using-drawingvisual-objects"></a>Utilizzo degli oggetti DrawingVisual
In questo argomento viene fornita <xref:System.Windows.Media.DrawingVisual> una [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] panoramica sull'utilizzo di oggetti nel livello visivo.  
  
<a name="drawingvisual_object"></a>
## <a name="drawingvisual-object"></a>Oggetto DrawingVisual  
 Si <xref:System.Windows.Media.DrawingVisual> tratta di una classe di disegno leggera utilizzata per eseguire il rendering di forme, immagini o testo. Questa classe è considerata semplice perché non offre la gestione di layout o eventi, con un conseguente aumento delle prestazioni. Per questo motivo, i disegni sono ideali per sfondi e ClipArt.  
  
<a name="drawingvisual_host_container"></a>
## <a name="drawingvisual-host-container"></a>Contenitore host di DrawingVisual  
 Per utilizzare <xref:System.Windows.Media.DrawingVisual> gli oggetti, è necessario creare un contenitore host per gli oggetti. L'oggetto contenitore host <xref:System.Windows.FrameworkElement> deve derivare dalla classe , <xref:System.Windows.Media.DrawingVisual> che fornisce il supporto per il layout e la gestione degli eventi che manca alla classe. Tramite l'oggetto contenitore host non vengono visualizzate proprietà visibili, poiché lo scopo principale di questo oggetto è quello di contenere oggetti figlio. Tuttavia, <xref:System.Windows.UIElement.Visibility%2A> la proprietà del contenitore <xref:System.Windows.Visibility.Visible>host deve essere impostata su ; in caso contrario, nessuno dei relativi elementi figlio sarà visibile.  
  
 Quando si crea un oggetto contenitore host per gli oggetti <xref:System.Windows.Media.VisualCollection>visivi, è necessario archiviare i riferimenti agli oggetti visivi in un oggetto . Utilizzare <xref:System.Windows.Media.VisualCollection.Add%2A> il metodo per aggiungere un oggetto visivo al contenitore host. Nell'esempio riportato di seguito viene creato un oggetto contenitore host e vengono aggiunti tre oggetti visivi al relativo <xref:System.Windows.Media.VisualCollection>oggetto .  
  
 [!code-csharp[DrawingVisualSample#100](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#100)]
 [!code-vb[DrawingVisualSample#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#100)]  
  
> [!NOTE]
> Per l'esempio di codice completo dal quale è stato estratto l'esempio di codice precedente, vedere [Hit Test Using DrawingVisuals Sample (Esempio di Hit Test mediante DrawingVisual)](https://github.com/Microsoft/WPF-Samples/tree/master/Visual%20Layer/DrawingVisual).  
  
<a name="creating_drawingvisual_objects"></a>
## <a name="creating-drawingvisual-objects"></a>Creazione di oggetti DrawingVisual  
 Quando si <xref:System.Windows.Media.DrawingVisual> crea un oggetto, non ha contenuto del disegno. È possibile aggiungere testo, grafica o contenuto dell'immagine recuperando l'oggetto <xref:System.Windows.Media.DrawingContext> e disegnandovi. Un <xref:System.Windows.Media.DrawingContext> oggetto viene restituito <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> chiamando <xref:System.Windows.Media.DrawingVisual> il metodo di un oggetto.  
  
 Per disegnare un <xref:System.Windows.Media.DrawingContext>rettangolo <xref:System.Windows.Media.DrawingContext.DrawRectangle%2A> in , <xref:System.Windows.Media.DrawingContext> utilizzare il metodo dell'oggetto . Sono disponibili metodi simili per disegnare altri tipi di contenuto. Al termine del disegno <xref:System.Windows.Media.DrawingContext>del contenuto <xref:System.Windows.Media.DrawingContext.Close%2A> in , <xref:System.Windows.Media.DrawingContext> chiamare il metodo per chiudere e rendere persistente il contenuto.  
  
 Nell'esempio seguente <xref:System.Windows.Media.DrawingVisual> viene creato un oggetto e viene <xref:System.Windows.Media.DrawingContext>disegnato un rettangolo nel relativo oggetto .  
  
 [!code-csharp[DrawingVisualSample#101](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#101)]
 [!code-vb[DrawingVisualSample#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#101)]  
  
<a name="creating_overrides"></a>
## <a name="creating-overrides-for-frameworkelement-members"></a>Creazione di override per i membri FrameworkElement  
 L'oggetto contenitore host è responsabile della gestione della raccolta di oggetti visivi. Ciò richiede che il contenitore host <xref:System.Windows.FrameworkElement> implementi gli override dei membri per la classe derivata.  
  
 L'elenco seguente descrive due membri per i quali è necessario eseguire l'override:  
  
- <xref:System.Windows.FrameworkElement.GetVisualChild%2A>: restituisce un elemento figlio in corrispondenza dell'indice specificato dalla raccolta di elementi figlio.  
  
- <xref:System.Windows.FrameworkElement.VisualChildrenCount%2A>: ottiene il numero di elementi figlio visivi all'interno di questo elemento.  
  
 Nell'esempio seguente vengono implementati <xref:System.Windows.FrameworkElement> gli override per i due membri.  
  
 [!code-csharp[DrawingVisualSample#102](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#102)]
 [!code-vb[DrawingVisualSample#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#102)]  
  
<a name="providing_hit_testing_support"></a>
## <a name="providing-hit-testing-support"></a>Supporto per l'hit testing  
 L'oggetto contenitore host può fornire la gestione degli eventi <xref:System.Windows.UIElement.Visibility%2A> anche se non <xref:System.Windows.Visibility.Visible>visualizza proprietà visibili, tuttavia la relativa proprietà deve essere impostata su . Ciò consente di creare una routine di gestione degli eventi per il contenitore host in grado di intercettare eventi del mouse, ad esempio il rilascio del pulsante sinistro del mouse. La routine di gestione degli eventi può <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> quindi implementare l'hit testing richiamando il metodo. Il parametro <xref:System.Windows.Media.HitTestResultCallback> del metodo fa riferimento a una routine definita dall'utente che è possibile utilizzare per determinare l'azione risultante di un hit test.  
  
 Nell'esempio seguente il supporto per l'hit testing viene implementato per l'oggetto contenitore host e i relativi elementi figlio.  
  
 [!code-csharp[DrawingVisualSample#103](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#103)]
 [!code-vb[DrawingVisualSample#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#103)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.DrawingVisual>
- <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>
- [Cenni preliminari sul rendering della grafica WPF](wpf-graphics-rendering-overview.md)
- [Hit testing a livello visivo](hit-testing-in-the-visual-layer.md)
