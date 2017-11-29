---
title: Utilizzo degli oggetti DrawingVisual
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
helpviewer_keywords:
- visual layer [WPF], DrawingVisual objects
- DrawingVisual objects in visual layer [WPF]
ms.assetid: 0b4e711d-e640-40cb-81c3-8f5c59909b7d
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ee46c41d6f0f42bbb9f50bd5862f6eb076b34bb1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="using-drawingvisual-objects"></a><span data-ttu-id="96b6f-102">Utilizzo degli oggetti DrawingVisual</span><span class="sxs-lookup"><span data-stu-id="96b6f-102">Using DrawingVisual Objects</span></span>
<span data-ttu-id="96b6f-103">In questo argomento viene fornita una panoramica dell'utilizzo di <xref:System.Windows.Media.DrawingVisual> gli oggetti di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] livello visivo.</span><span class="sxs-lookup"><span data-stu-id="96b6f-103">This topic provides an overview of how to use <xref:System.Windows.Media.DrawingVisual> objects in the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] visual layer.</span></span>  
  
<a name="drawingvisual_object"></a>   
## <a name="drawingvisual-object"></a><span data-ttu-id="96b6f-104">Oggetto DrawingVisual</span><span class="sxs-lookup"><span data-stu-id="96b6f-104">DrawingVisual Object</span></span>  
 <span data-ttu-id="96b6f-105">Il <xref:System.Windows.Media.DrawingVisual> è una classe utilizzata per eseguire il rendering di testo, immagini o forme di disegno semplificata.</span><span class="sxs-lookup"><span data-stu-id="96b6f-105">The <xref:System.Windows.Media.DrawingVisual> is a lightweight drawing class that is used to render shapes, images, or text.</span></span> <span data-ttu-id="96b6f-106">Questa classe è considerata semplice perché non offre la gestione di layout o eventi, con un conseguente aumento delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="96b6f-106">This class is considered lightweight because it does not provide layout or event handling, which improves its performance.</span></span> <span data-ttu-id="96b6f-107">Per questo motivo, i disegni sono ideali per sfondi e ClipArt.</span><span class="sxs-lookup"><span data-stu-id="96b6f-107">For this reason, drawings are ideal for backgrounds and clip art.</span></span>  
  
<a name="drawingvisual_host_container"></a>   
## <a name="drawingvisual-host-container"></a><span data-ttu-id="96b6f-108">Contenitore host di DrawingVisual</span><span class="sxs-lookup"><span data-stu-id="96b6f-108">DrawingVisual Host Container</span></span>  
 <span data-ttu-id="96b6f-109">Per utilizzare <xref:System.Windows.Media.DrawingVisual> oggetti, è necessario creare un contenitore host per gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="96b6f-109">In order to use <xref:System.Windows.Media.DrawingVisual> objects, you need to create a host container for the objects.</span></span> <span data-ttu-id="96b6f-110">L'oggetto contenitore host deve derivare dal <xref:System.Windows.FrameworkElement> (classe), che fornisce il layout e la gestione degli eventi che supportano il <xref:System.Windows.Media.DrawingVisual> mancano alla classe.</span><span class="sxs-lookup"><span data-stu-id="96b6f-110">The host container object must derive from the <xref:System.Windows.FrameworkElement> class, which provides the layout and event handling support that the <xref:System.Windows.Media.DrawingVisual> class lacks.</span></span> <span data-ttu-id="96b6f-111">Tramite l'oggetto contenitore host non vengono visualizzate proprietà visibili, poiché lo scopo principale di questo oggetto è quello di contenere oggetti figlio.</span><span class="sxs-lookup"><span data-stu-id="96b6f-111">The host container object does not display any visible properties, since its main purpose is to contain child objects.</span></span> <span data-ttu-id="96b6f-112">Tuttavia, il <xref:System.Windows.UIElement.Visibility%2A> proprietà del contenitore host deve essere impostata su <xref:System.Windows.Visibility.Visible>; in caso contrario, i relativi elementi figlio non saranno visibili.</span><span class="sxs-lookup"><span data-stu-id="96b6f-112">However, the <xref:System.Windows.UIElement.Visibility%2A> property of the host container must be set to <xref:System.Windows.Visibility.Visible>; otherwise, none of its child elements will be visible.</span></span>  
  
 <span data-ttu-id="96b6f-113">Quando si crea un oggetto contenitore host per gli oggetti visivi, è necessario archiviare i riferimenti agli oggetti visivi in un <xref:System.Windows.Media.VisualCollection>.</span><span class="sxs-lookup"><span data-stu-id="96b6f-113">When you create a host container object for visual objects, you need to store the visual object references in a <xref:System.Windows.Media.VisualCollection>.</span></span> <span data-ttu-id="96b6f-114">Utilizzare il <xref:System.Windows.Media.VisualCollection.Add%2A> metodo per aggiungere un oggetto visivo per il contenitore dell'host.</span><span class="sxs-lookup"><span data-stu-id="96b6f-114">Use the <xref:System.Windows.Media.VisualCollection.Add%2A> method to add a visual object to the host container.</span></span> <span data-ttu-id="96b6f-115">Nell'esempio seguente viene creato un oggetto contenitore host e vengono aggiunti tre oggetti visivi relativo <xref:System.Windows.Media.VisualCollection>.</span><span class="sxs-lookup"><span data-stu-id="96b6f-115">In the following example, a host container object is created, and three visual objects are added to its <xref:System.Windows.Media.VisualCollection>.</span></span>  
  
 [!code-csharp[DrawingVisualSample#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#100)]
 [!code-vb[DrawingVisualSample#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#100)]  
  
> [!NOTE]
>  <span data-ttu-id="96b6f-116">Per l'esempio di codice completo dal quale è stato estratto l'esempio di codice precedente, vedere [Hit Test Using DrawingVisuals Sample (Esempio di Hit Test mediante DrawingVisual)](http://go.microsoft.com/fwlink/?LinkID=159994).</span><span class="sxs-lookup"><span data-stu-id="96b6f-116">For the complete code sample from which the preceding code example was extracted, see [Hit Test Using DrawingVisuals Sample](http://go.microsoft.com/fwlink/?LinkID=159994).</span></span>  
  
<a name="creating_drawingvisual_objects"></a>   
## <a name="creating-drawingvisual-objects"></a><span data-ttu-id="96b6f-117">Creazione di oggetti DrawingVisual</span><span class="sxs-lookup"><span data-stu-id="96b6f-117">Creating DrawingVisual Objects</span></span>  
 <span data-ttu-id="96b6f-118">Quando si crea un <xref:System.Windows.Media.DrawingVisual> dell'oggetto, non ha contenuto di disegno.</span><span class="sxs-lookup"><span data-stu-id="96b6f-118">When you create a <xref:System.Windows.Media.DrawingVisual> object, it has no drawing content.</span></span> <span data-ttu-id="96b6f-119">È possibile aggiungere testo, immagini o contenuto dell'immagine per il recupero dell'oggetto <xref:System.Windows.Media.DrawingContext> e di disegno al suo interno.</span><span class="sxs-lookup"><span data-stu-id="96b6f-119">You can add text, graphics, or image content by retrieving the object's <xref:System.Windows.Media.DrawingContext> and drawing into it.</span></span> <span data-ttu-id="96b6f-120">Oggetto <xref:System.Windows.Media.DrawingContext> restituito chiamando il <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> metodo di un <xref:System.Windows.Media.DrawingVisual> oggetto.</span><span class="sxs-lookup"><span data-stu-id="96b6f-120">A <xref:System.Windows.Media.DrawingContext> is returned by calling the <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> method of a <xref:System.Windows.Media.DrawingVisual> object.</span></span>  
  
 <span data-ttu-id="96b6f-121">Per disegnare un rettangolo nel <xref:System.Windows.Media.DrawingContext>, utilizzare il <xref:System.Windows.Media.DrawingContext.DrawRectangle%2A> metodo il <xref:System.Windows.Media.DrawingContext> oggetto.</span><span class="sxs-lookup"><span data-stu-id="96b6f-121">To draw a rectangle into the <xref:System.Windows.Media.DrawingContext>, use the <xref:System.Windows.Media.DrawingContext.DrawRectangle%2A> method of the <xref:System.Windows.Media.DrawingContext> object.</span></span> <span data-ttu-id="96b6f-122">Sono disponibili metodi simili per disegnare altri tipi di contenuto.</span><span class="sxs-lookup"><span data-stu-id="96b6f-122">Similar methods exist for drawing other types of content.</span></span> <span data-ttu-id="96b6f-123">Al termine il contenuto del disegno nel <xref:System.Windows.Media.DrawingContext>, chiamare il <xref:System.Windows.Media.DrawingContext.Close%2A> metodo per chiudere la <xref:System.Windows.Media.DrawingContext> e mantenere il contenuto.</span><span class="sxs-lookup"><span data-stu-id="96b6f-123">When you are finished drawing content into the <xref:System.Windows.Media.DrawingContext>, call the <xref:System.Windows.Media.DrawingContext.Close%2A> method to close the <xref:System.Windows.Media.DrawingContext> and persist the content.</span></span>  
  
 <span data-ttu-id="96b6f-124">Nell'esempio seguente, un <xref:System.Windows.Media.DrawingVisual> oggetto viene creato e viene disegnato un rettangolo nel relativo <xref:System.Windows.Media.DrawingContext>.</span><span class="sxs-lookup"><span data-stu-id="96b6f-124">In the following example, a <xref:System.Windows.Media.DrawingVisual> object is created, and a rectangle is drawn into its <xref:System.Windows.Media.DrawingContext>.</span></span>  
  
 [!code-csharp[DrawingVisualSample#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#101)]
 [!code-vb[DrawingVisualSample#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#101)]  
  
<a name="creating_overrides"></a>   
## <a name="creating-overrides-for-frameworkelement-members"></a><span data-ttu-id="96b6f-125">Creazione di override per i membri FrameworkElement</span><span class="sxs-lookup"><span data-stu-id="96b6f-125">Creating Overrides for FrameworkElement Members</span></span>  
 <span data-ttu-id="96b6f-126">L'oggetto contenitore host è responsabile della gestione della raccolta di oggetti visivi.</span><span class="sxs-lookup"><span data-stu-id="96b6f-126">The host container object is responsible for managing its collection of visual objects.</span></span> <span data-ttu-id="96b6f-127">Ciò richiede che il contenitore host implementi l'override di membri per derivata <xref:System.Windows.FrameworkElement> classe.</span><span class="sxs-lookup"><span data-stu-id="96b6f-127">This requires that the host container implement member overrides for the derived <xref:System.Windows.FrameworkElement> class.</span></span>  
  
 <span data-ttu-id="96b6f-128">L'elenco seguente descrive due membri per i quali è necessario eseguire l'override:</span><span class="sxs-lookup"><span data-stu-id="96b6f-128">The following list describes the two members you must override:</span></span>  
  
-   <span data-ttu-id="96b6f-129"><xref:System.Windows.FrameworkElement.GetVisualChild%2A>: Restituisce un elemento figlio in corrispondenza dell'indice specificato dalla raccolta di elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="96b6f-129"><xref:System.Windows.FrameworkElement.GetVisualChild%2A>: Returns a child at the specified index from the collection of child elements.</span></span>  
  
-   <span data-ttu-id="96b6f-130"><xref:System.Windows.FrameworkElement.VisualChildrenCount%2A>: Ottiene il numero di elementi figlio visivi all'interno di questo elemento.</span><span class="sxs-lookup"><span data-stu-id="96b6f-130"><xref:System.Windows.FrameworkElement.VisualChildrenCount%2A>: Gets the number of visual child elements within this element.</span></span>  
  
 <span data-ttu-id="96b6f-131">Nell'esempio seguente, le sostituzioni per i due <xref:System.Windows.FrameworkElement> vengono implementati i membri.</span><span class="sxs-lookup"><span data-stu-id="96b6f-131">In the following example, overrides for the two <xref:System.Windows.FrameworkElement> members are implemented.</span></span>  
  
 [!code-csharp[DrawingVisualSample#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#102)]
 [!code-vb[DrawingVisualSample#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#102)]  
  
<a name="providing_hit_testing_support"></a>   
## <a name="providing-hit-testing-support"></a><span data-ttu-id="96b6f-132">Supporto per l'hit testing</span><span class="sxs-lookup"><span data-stu-id="96b6f-132">Providing Hit Testing Support</span></span>  
 <span data-ttu-id="96b6f-133">L'oggetto contenitore host può fornire la gestione degli eventi, anche se non viene visualizzata alcuna proprietà visibile, tuttavia, il relativo <xref:System.Windows.UIElement.Visibility%2A> proprietà deve essere impostata su <xref:System.Windows.Visibility.Visible>.</span><span class="sxs-lookup"><span data-stu-id="96b6f-133">The host container object can provide event handling even if it does not display any visible properties—however, its <xref:System.Windows.UIElement.Visibility%2A> property must be set to <xref:System.Windows.Visibility.Visible>.</span></span> <span data-ttu-id="96b6f-134">Ciò consente di creare una routine di gestione degli eventi per il contenitore host in grado di intercettare eventi del mouse, ad esempio il rilascio del pulsante sinistro del mouse.</span><span class="sxs-lookup"><span data-stu-id="96b6f-134">This allows you to create an event handling routine for the host container that can trap mouse events, such as the release of the left mouse button.</span></span> <span data-ttu-id="96b6f-135">Routine di gestione degli eventi possono quindi implementare l'hit testing richiamando il <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="96b6f-135">The event handling routine can then implement hit testing by invoking the <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> method.</span></span> <span data-ttu-id="96b6f-136">Il metodo <xref:System.Windows.Media.HitTestResultCallback> parametro fa riferimento a una routine definita dall'utente che è possibile utilizzare per determinare l'azione risulta dell'hit test.</span><span class="sxs-lookup"><span data-stu-id="96b6f-136">The method's <xref:System.Windows.Media.HitTestResultCallback> parameter refers to a user-defined procedure that you can use to determine the resulting action of a hit test.</span></span>  
  
 <span data-ttu-id="96b6f-137">Nell'esempio seguente il supporto per l'hit testing viene implementato per l'oggetto contenitore host e i relativi elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="96b6f-137">In the following example, hit testing support is implemented for the host container object and its children.</span></span>  
  
 [!code-csharp[DrawingVisualSample#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#103)]
 [!code-vb[DrawingVisualSample#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#103)]  
  
## <a name="see-also"></a><span data-ttu-id="96b6f-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="96b6f-138">See Also</span></span>  
 <xref:System.Windows.Media.DrawingVisual>  
 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>  
 [<span data-ttu-id="96b6f-139">Cenni preliminari sul rendering della grafica WPF</span><span class="sxs-lookup"><span data-stu-id="96b6f-139">WPF Graphics Rendering Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)  
 [<span data-ttu-id="96b6f-140">Hit testing a livello visivo</span><span class="sxs-lookup"><span data-stu-id="96b6f-140">Hit Testing in the Visual Layer</span></span>](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)
