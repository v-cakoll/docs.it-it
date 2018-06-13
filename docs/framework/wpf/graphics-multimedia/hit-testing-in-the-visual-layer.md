---
title: Hit testing a livello visivo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit testing functionality [WPF]
- visual layer [WPF], hit testing functionality
ms.assetid: b1a64b61-14be-4d75-b89a-5c67bebb2c7b
ms.openlocfilehash: 60da11af51722e86a61c5e3298fafba2221f000b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33558109"
---
# <a name="hit-testing-in-the-visual-layer"></a>Hit testing a livello visivo
In questo argomento vengono forniti dei cenni preliminari sulle funzionalità di hit testing fornite dal livello visivo. Supporto per l'hit test consente di determinare se un valore di geometria o un punto rientra contenuto di cui viene eseguito il rendering di un <xref:System.Windows.Media.Visual>, che consente di implementare il comportamento dell'interfaccia utente, ad esempio un rettangolo di selezione per selezionare più oggetti.  
  
 
  
<a name="hit_testing_scenarios"></a>   
## <a name="hit-testing-scenarios"></a>Scenari di hit Testing  
 Il <xref:System.Windows.UIElement> classe fornisce il <xref:System.Windows.UIElement.InputHitTest%2A> metodo, che consente di eseguire l'hit test su un elemento utilizzando un determinato valore della coordinata. In molti casi, il <xref:System.Windows.UIElement.InputHitTest%2A> metodo fornisce la funzionalità desiderata per l'implementazione di hit testing di elementi. Esistono tuttavia diversi scenari nei quali potrebbe essere necessario implementare l'hit testing a livello visivo.  
  
-   Hit testing su non<xref:System.Windows.UIElement> oggetti: si applica se esegue l'hit test non<xref:System.Windows.UIElement> oggetti, ad esempio <xref:System.Windows.Media.DrawingVisual> o oggetti grafici.  
  
-   Hit testing tramite una geometria: applicabile se è necessario eseguire un hit test usando un oggetto geometry anziché il valore delle coordinate di un punto.  
  
-   Hit testing su più oggetti: applicabile quando è necessario eseguire un hit test su più oggetti, ad esempio oggetti sovrapposti. È possibile ottenere risultati per tutti gli elementi visivi che intersecano una geometria o un punto, non solo il primo.  
  
-   Ignorando <xref:System.Windows.UIElement> criteri di hit testing: si applica quando è necessario ignorare il <xref:System.Windows.UIElement> hit test dei criteri, che prendono in considerazione fattori quali l'eventuale disabilitazione di un elemento o invisibile.  
  
> [!NOTE]
>  Per un esempio di codice completo che illustra l'hit testing a livello visivo, vedere [Hit Test Using DrawingVisuals Sample (Esempio di Hit Test mediante DrawingVisual)](http://go.microsoft.com/fwlink/?LinkID=159994) e [Hit Test with Win32 Interoperation Sample (Esempio di hit test con interoperatività Win32)](http://go.microsoft.com/fwlink/?LinkID=159995).  
  
<a name="hit_testing_support"></a>   
## <a name="hit-testing-support"></a>Supporto per Hit Testing  
 Lo scopo del <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> metodi di <xref:System.Windows.Media.VisualTreeHelper> classe consiste nel determinare se un valore della coordinata geometria o un punto è all'interno del contenuto viene eseguito il rendering di un oggetto specifico, ad esempio un controllo o un elemento grafico. Ad esempio, è possibile usare l'hit testing per determinare se un clic del mouse all'interno del rettangolo di delimitazione di un oggetto avviene all'interno della geometria di un cerchio. È inoltre possibile scegliere di eseguire l'override dell'implementazione predefinita dell'hit testing per eseguire calcoli di hit testing personalizzati.  
  
 La figura seguente mostra la relazione tra l'area dell'oggetto non rettangolare e il rettangolo di delimitazione.  
  
 ![Diagramma dell'area di hit test validi](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-mmgraphics-visuals-hittest-1.png "wcpsdk_mmgraphics_visuals_hittest_1")  
Diagramma dell'area di hit testing valida  
  
<a name="hit_testing_and_z-order"></a>   
## <a name="hit-testing-and-z-order"></a>Hit Testing e ordine Z  
 Il livello visivo di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] supporta l'hit testing su tutti gli oggetti in un punto o in una geometria, non solo sull'oggetto di primo livello. I risultati vengono restituiti nell'ordine Z. Tuttavia, l'oggetto visivo che viene passato come parametro per il <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> metodo determina la parte dell'albero visuale che verrà raggiunto test. È possibile sottoporre a hit testing l'intera struttura ad albero visuale o parte di essa.  
  
 Nella figura seguente, l'oggetto cerchio è sovrapposto sia al quadrato che al triangolo. Se si è solo interessati all'hit test l'oggetto visivo il cui valore di ordine z è superiore, è possibile impostare l'enumerazione di hit test visiva da restituire <xref:System.Windows.Media.HitTestResultBehavior.Stop> dal <xref:System.Windows.Media.HitTestResultCallback> per interrompere lo scorrimento dell'hit test dopo il primo elemento.  
  
 ![Diagramma di z&#45;dell'ordine di un struttura ad albero visuale](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-mmgraphics-visuals-hittest-2.png "wcpsdk_mmgraphics_visuals_hittest_2")  
Diagramma dell'ordine Z di una struttura ad albero visuale  
  
 Se si desidera enumerare tutti gli oggetti visivi in un momento specifico o di geometria, restituire <xref:System.Windows.Media.HitTestResultBehavior.Continue> dal <xref:System.Windows.Media.HitTestResultCallback>. Ciò significa che è possibile eseguire l'hit test per gli oggetti visivi che sono al di sotto di altri oggetti, anche se sono completamente nascosti. Per altre informazioni, vedere il codice di esempio nella sezione "Utilizzo del callback dei risultati di un hit test".  
  
> [!NOTE]
>  Anche un oggetto visivo trasparente può essere sottoposto a hit test.  
  
<a name="using_default_hit_testing"></a>   
## <a name="using-default-hit-testing"></a>Uso dell'hit testing predefinito  
 È possibile individuare se un punto è all'interno della geometria di un oggetto visivo, utilizzando il <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> per specificare un oggetto visivo e un punto di coordinare valore da testare. Il parametro dell'oggetto visivo identifica il punto di avvio nella struttura ad albero visuale della ricerca dell'hit test. Se un oggetto visivo viene trovato la struttura ad albero visuale la cui geometria contiene la coordinata, cui è impostato il <xref:System.Windows.Media.HitTestResult.VisualHit%2A> proprietà di un <xref:System.Windows.Media.HitTestResult> oggetto. Il <xref:System.Windows.Media.HitTestResult> viene quindi restituito dal <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> metodo. Se il punto non è incluso con la sottostruttura ad albero visuale sottoposta a hit test, <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> restituisce `null`.  
  
> [!NOTE]
>  L'hit testing predefinito restituisce sempre l'oggetto di livello superiore nell'ordine Z. Per identificare tutti gli oggetti visivi, compresi quelli che potrebbero essere parzialmente o completamente nascosti, usare un callback dei risultati dell'hit test.  
  
 Il valore della coordinata viene passato come parametro per il punto di <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> metodo deve essere relativo al sistema di coordinate dell'oggetto visivo hit testing. Ad esempio, se sono presenti oggetti visivi annidati nelle coordinate (100, 100) nello spazio delle coordinate dell'elemento padre, l'hit testing su un oggetto visivo figlio con coordinate (0, 0) è equivalente all'hit testing con coordinate (100, 100) nello spazio delle coordinate dell'elemento padre.  
  
 Il codice seguente viene illustrato come impostare i gestori di eventi del mouse per un <xref:System.Windows.UIElement> oggetto che viene utilizzata per acquisire gli eventi utilizzati per l'hit test.  
  
 [!code-csharp[HitTestingOverview#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#100)]
 [!code-vb[HitTestingOverview#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#100)]  
  
### <a name="how-the-visual-tree-affects-hit-testing"></a>Effetti della struttura ad albero visuale sull'hit testing  
 Il punto iniziale nella struttura ad albero visuale determina quali oggetti vengono restituiti durante l'enumerazione di hit test degli oggetti. Se si dispone di più oggetti da sottoporre a hit test, l'oggetto visivo usato come punto di inizio nella struttura ad albero visuale deve essere il predecessore comune di tutti gli oggetti interessati. Se si desidera ad esempio sottoporre a hit test sia l'elemento pulsante che l'elemento visivo di disegno nel diagramma seguente, è necessario impostare il punto di inizio nella struttura ad albero visuale sul predecessore comune a entrambi. In questo caso, l'elemento canvas è il predecessore comune di sia dell'elemento pulsante che dell'elemento visivo di disegno.  
  
 ![Diagramma di una gerarchia struttura ad albero visuale](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-mmgraphics-visuals-overview-01.gif "wcpsdk_mmgraphics_visuals_overview_01")  
Diagramma della gerarchia di una struttura ad albero visuale  
  
> [!NOTE]
>  Il <xref:System.Windows.UIElement.IsHitTestVisible%2A> proprietà ottiene o imposta un valore che dichiara se un <xref:System.Windows.UIElement>-oggetto derivato può essere restituito come risultato dell'hit test da una parte del relativo contenuto sottoposto a rendering. In questo modo è possibile modificare selettivamente la struttura ad albero visuale per determinare quali oggetti visivi sono coinvolti in un hit test.  
  
<a name="using_a_hit_test_result_callback"></a>   
## <a name="using-a-hit-test-result-callback"></a>Uso del callback dei risultati di un hit test  
 È possibile enumerare tutti gli oggetti visivi in una struttura ad albero visuale la cui geometria contiene un valore di coordinate specificato. Ciò consente di identificare tutti gli oggetti visivi, inclusi quelli che potrebbero essere parzialmente o completamente nascosti da altri oggetti visivi. Per enumerare gli oggetti visivi in uso una struttura ad albero visuale di <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> metodo con una funzione di callback dell'hit test. La funzione di callback dell'hit test viene chiamata dal sistema quando il valore delle coordinate specificato è contenuto in un oggetto visivo.  
  
 Durante l'enumerazione dei risultati dell'hit test, evitare di eseguire operazioni che modifichino la struttura ad albero visuale. L'aggiunta o la rimozione di un oggetto dalla struttura ad albero visuale mentre viene attraversata può produrre un comportamento imprevedibile. È possibile modificare la struttura ad albero visuale dopo il <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> metodo restituisce. Si consiglia di fornire una struttura di dati, ad esempio un <xref:System.Collections.ArrayList>, per archiviare i valori durante l'enumerazione dei risultati dell'hit test.  
  
 [!code-csharp[HitTestingOverview#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#101)]
 [!code-vb[HitTestingOverview#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#101)]  
  
 Il metodo di callback dell'hit test definisce le azioni eseguite quando viene identificato un hit test su un determinato oggetto visivo nella struttura ad albero visuale. Dopo aver eseguito le azioni, restituire un <xref:System.Windows.Media.HitTestResultBehavior> valore che determina se continuare l'enumerazione di altri oggetti visivi o meno.  
  
 [!code-csharp[HitTestingOverview#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#102)]
 [!code-vb[HitTestingOverview#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#102)]  
  
> [!NOTE]
>  L'ordine di enumerazione di oggetti visivi di hit testing è l'ordine Z. L'oggetto visivo di livello superiore nell'ordine Z viene enumerato per primo. Gli altri oggetti visivi vengono enumerati a livelli decrescenti nell'ordine Z. Questo ordine di enumerazione corrisponde all'ordine di rendering degli oggetti visivi.  
  
 È possibile interrompere l'enumerazione di oggetti visivi in qualsiasi momento nella funzione di callback dell'hit test restituendo <xref:System.Windows.Media.HitTestResultBehavior.Stop>.  
  
 [!code-csharp[HitTestingOverview#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#103)]
 [!code-vb[HitTestingOverview#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#103)]  
  
<a name="using_a_hit_test_filter_callback"></a>   
## <a name="using-a-hit-test-filter-callback"></a>Uso del callback di un filtro dell'hit test  
 È possibile usare un filtro dell'hit test facoltativo per limitare gli oggetti inviati ai risultati dell'hit test. Ciò consente di ignorare parti della struttura ad albero visuale che non si desidera elaborare nei risultati dell'hit test. Per implementare un filtro hit test, definire una funzione di callback del filtro dell'hit test e passarlo come valore di parametro, quando si chiama il <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> metodo.  
  
 [!code-csharp[HitTestingOverview#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#104)]
 [!code-vb[HitTestingOverview#104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#104)]  
  
 Se non si desidera fornire la funzione di callback del filtro dell'hit test facoltativo, passare un `null` valore come parametro per il <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> metodo.  
  
 [!code-csharp[HitTestingOverview#105](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#105)]
 [!code-vb[HitTestingOverview#105](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#105)]  
  
 ![Eliminazione di un struttura ad albero visuale con un filtro hit test](../../../../docs/framework/wpf/graphics-multimedia/media/filteredvisualtree-01.png "FilteredVisualTree_01")  
Eliminazione di una struttura ad albero visuale  
  
 La funzione di callback del filtro dell'hit test consente di enumerare tutti gli oggetti visivi il cui contenuto di rendering include le coordinate specificate. È possibile tuttavia decidere di ignorare determinate parti della struttura ad albero visuale che non si desidera elaborare nella funzione di callback dei risultati dell'hit test. Il valore restituito dalla funzione di callback del filtro dell'hit test determina il tipo di azione che deve essere eseguita dall'enumerazione degli oggetti visivi. Se viene restituito il valore, ad esempio <xref:System.Windows.Media.HitTestFilterBehavior.ContinueSkipSelfAndChildren>, è possibile rimuovere l'oggetto visivo corrente e i relativi elementi figlio dall'enumerazione dei risultati dell'hit test. Ciò significa che la funzione di callback dei risultati di hit test non visualizzerà questi oggetti nell'enumerazione. L'eliminazione di oggetti dalla struttura ad albero visuale consente di ridurre la quantità di elaborazione durante la fase di enumerazione dei risultati dell'hit test. Nell'esempio di codice seguente il filtro ignora le etichette e i relativi discendenti e sottopone a hit test tutti gli altri elementi.  
  
 [!code-csharp[HitTestingOverview#106](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#106)]
 [!code-vb[HitTestingOverview#106](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#106)]  
  
> [!NOTE]
>  Verrà talvolta chiamato il callback del filtro dell'hit test nei casi in cui non viene chiamato il callback di risultati dell'hit test.  
  
<a name="overriding_default_hit_testing"></a>   
## <a name="overriding-default-hit-testing"></a>Override dell'hit testing predefinito  
 È possibile eseguire l'override di supporto predefinito hit un oggetto visivo test eseguendo l'override di <xref:System.Windows.Media.Visual.HitTestCore%2A> metodo. Ciò significa che quando si richiama il <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> (metodo), l'implementazione sottoposta a override di <xref:System.Windows.Media.Visual.HitTestCore%2A> viene chiamato. Il metodo sottoposto a override viene chiamato quando un hit test viene eseguito all'interno del rettangolo delimitatore dell'oggetto visivo, anche se le coordinate non rientrano nel contenuto sottoposto a rendering dell'oggetto visivo.  
  
 [!code-csharp[HitTestingOverview#107](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#107)]
 [!code-vb[HitTestingOverview#107](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#107)]  
  
 È possibile che si desideri eseguire un hit test sia sul rettangolo di delimitazione, sia sul contenuto di rendering di un oggetto visivo. Tramite il `PointHitTestParameters` valore del parametro in sottoposto a override <xref:System.Windows.Media.Visual.HitTestCore%2A> metodo come parametro al metodo di base <xref:System.Windows.Media.Visual.HitTestCore%2A>, è possibile eseguire azioni basate su un'occorrenza del rettangolo di delimitazione di un oggetto visivo e quindi eseguire un hit test secondo il il rendering del contenuto dell'oggetto visivo.  
  
 [!code-csharp[HitTestingOverview#108](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#108)]
 [!code-vb[HitTestingOverview#108](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#108)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>  
 <xref:System.Windows.Media.HitTestResult>  
 <xref:System.Windows.Media.HitTestResultCallback>  
 <xref:System.Windows.Media.HitTestFilterCallback>  
 <xref:System.Windows.UIElement.IsHitTestVisible%2A>  
 [Hit Test mediante DrawingVisuals Sample](http://go.microsoft.com/fwlink/?LinkID=159994)  
 [Hit Test con esempio di interoperatività Win32](http://go.microsoft.com/fwlink/?LinkID=159995)  
 [Eseguire un hit test della geometria in un oggetto Visual](../../../../docs/framework/wpf/graphics-multimedia/how-to-hit-test-geometry-in-a-visual.md)  
 [Eseguire un hit test utilizzando un contenitore di host Win32](../../../../docs/framework/wpf/graphics-multimedia/how-to-hit-test-using-a-win32-host-container.md)
