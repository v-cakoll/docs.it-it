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
ms.openlocfilehash: e76ac22d4b8205576c8ed9ab67482c143a52fbd8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33565314"
---
# <a name="using-drawingvisual-objects"></a>Utilizzo degli oggetti DrawingVisual
In questo argomento viene fornita una panoramica dell'utilizzo di <xref:System.Windows.Media.DrawingVisual> gli oggetti di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] livello visivo.  
  
<a name="drawingvisual_object"></a>   
## <a name="drawingvisual-object"></a>Oggetto DrawingVisual  
 Il <xref:System.Windows.Media.DrawingVisual> è una classe utilizzata per eseguire il rendering di testo, immagini o forme di disegno semplificata. Questa classe è considerata semplice perché non offre la gestione di layout o eventi, con un conseguente aumento delle prestazioni. Per questo motivo, i disegni sono ideali per sfondi e ClipArt.  
  
<a name="drawingvisual_host_container"></a>   
## <a name="drawingvisual-host-container"></a>Contenitore host di DrawingVisual  
 Per utilizzare <xref:System.Windows.Media.DrawingVisual> oggetti, è necessario creare un contenitore host per gli oggetti. L'oggetto contenitore host deve derivare dal <xref:System.Windows.FrameworkElement> (classe), che fornisce il layout e la gestione degli eventi che supportano il <xref:System.Windows.Media.DrawingVisual> mancano alla classe. Tramite l'oggetto contenitore host non vengono visualizzate proprietà visibili, poiché lo scopo principale di questo oggetto è quello di contenere oggetti figlio. Tuttavia, il <xref:System.Windows.UIElement.Visibility%2A> proprietà del contenitore host deve essere impostata su <xref:System.Windows.Visibility.Visible>; in caso contrario, i relativi elementi figlio non saranno visibili.  
  
 Quando si crea un oggetto contenitore host per gli oggetti visivi, è necessario archiviare i riferimenti agli oggetti visivi in un <xref:System.Windows.Media.VisualCollection>. Utilizzare il <xref:System.Windows.Media.VisualCollection.Add%2A> metodo per aggiungere un oggetto visivo per il contenitore dell'host. Nell'esempio seguente viene creato un oggetto contenitore host e vengono aggiunti tre oggetti visivi relativo <xref:System.Windows.Media.VisualCollection>.  
  
 [!code-csharp[DrawingVisualSample#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#100)]
 [!code-vb[DrawingVisualSample#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#100)]  
  
> [!NOTE]
>  Per l'esempio di codice completo dal quale è stato estratto l'esempio di codice precedente, vedere [Hit Test Using DrawingVisuals Sample (Esempio di Hit Test mediante DrawingVisual)](http://go.microsoft.com/fwlink/?LinkID=159994).  
  
<a name="creating_drawingvisual_objects"></a>   
## <a name="creating-drawingvisual-objects"></a>Creazione di oggetti DrawingVisual  
 Quando si crea un <xref:System.Windows.Media.DrawingVisual> dell'oggetto, non ha contenuto di disegno. È possibile aggiungere testo, immagini o contenuto dell'immagine per il recupero dell'oggetto <xref:System.Windows.Media.DrawingContext> e di disegno al suo interno. Oggetto <xref:System.Windows.Media.DrawingContext> restituito chiamando il <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> metodo di un <xref:System.Windows.Media.DrawingVisual> oggetto.  
  
 Per disegnare un rettangolo nel <xref:System.Windows.Media.DrawingContext>, utilizzare il <xref:System.Windows.Media.DrawingContext.DrawRectangle%2A> metodo il <xref:System.Windows.Media.DrawingContext> oggetto. Sono disponibili metodi simili per disegnare altri tipi di contenuto. Al termine il contenuto del disegno nel <xref:System.Windows.Media.DrawingContext>, chiamare il <xref:System.Windows.Media.DrawingContext.Close%2A> metodo per chiudere la <xref:System.Windows.Media.DrawingContext> e mantenere il contenuto.  
  
 Nell'esempio seguente, un <xref:System.Windows.Media.DrawingVisual> oggetto viene creato e viene disegnato un rettangolo nel relativo <xref:System.Windows.Media.DrawingContext>.  
  
 [!code-csharp[DrawingVisualSample#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#101)]
 [!code-vb[DrawingVisualSample#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#101)]  
  
<a name="creating_overrides"></a>   
## <a name="creating-overrides-for-frameworkelement-members"></a>Creazione di override per i membri FrameworkElement  
 L'oggetto contenitore host è responsabile della gestione della raccolta di oggetti visivi. Ciò richiede che il contenitore host implementi l'override di membri per derivata <xref:System.Windows.FrameworkElement> classe.  
  
 L'elenco seguente descrive due membri per i quali è necessario eseguire l'override:  
  
-   <xref:System.Windows.FrameworkElement.GetVisualChild%2A>: Restituisce un elemento figlio in corrispondenza dell'indice specificato dalla raccolta di elementi figlio.  
  
-   <xref:System.Windows.FrameworkElement.VisualChildrenCount%2A>: Ottiene il numero di elementi figlio visivi in questo elemento.  
  
 Nell'esempio seguente, le sostituzioni per i due <xref:System.Windows.FrameworkElement> vengono implementati i membri.  
  
 [!code-csharp[DrawingVisualSample#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#102)]
 [!code-vb[DrawingVisualSample#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#102)]  
  
<a name="providing_hit_testing_support"></a>   
## <a name="providing-hit-testing-support"></a>Supporto per l'hit testing  
 L'oggetto contenitore host può fornire la gestione degli eventi, anche se non viene visualizzata alcuna proprietà visibile, tuttavia, il relativo <xref:System.Windows.UIElement.Visibility%2A> proprietà deve essere impostata su <xref:System.Windows.Visibility.Visible>. Ciò consente di creare una routine di gestione degli eventi per il contenitore host in grado di intercettare eventi del mouse, ad esempio il rilascio del pulsante sinistro del mouse. Routine di gestione degli eventi possono quindi implementare l'hit testing richiamando il <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> metodo. Il metodo <xref:System.Windows.Media.HitTestResultCallback> parametro fa riferimento a una routine definita dall'utente che è possibile utilizzare per determinare l'azione risulta dell'hit test.  
  
 Nell'esempio seguente il supporto per l'hit testing viene implementato per l'oggetto contenitore host e i relativi elementi figlio.  
  
 [!code-csharp[DrawingVisualSample#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#103)]
 [!code-vb[DrawingVisualSample#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#103)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.DrawingVisual>  
 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>  
 [Cenni preliminari sul rendering della grafica WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)  
 [Hit testing a livello visivo](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)
