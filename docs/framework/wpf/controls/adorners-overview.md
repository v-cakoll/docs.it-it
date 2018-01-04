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
ms.workload: dotnet
ms.openlocfilehash: 47b43b1b9848f91e77448d41609d8be5d60ecda5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="adorners-overview"></a><span data-ttu-id="a9d69-102">Cenni preliminari sugli strumenti decorativi visuali</span><span class="sxs-lookup"><span data-stu-id="a9d69-102">Adorners Overview</span></span>
<span data-ttu-id="a9d69-103">Gli strumenti decorativi sono un tipo speciale di <xref:System.Windows.FrameworkElement>, utilizzata per fornire indicazioni visive a un utente.</span><span class="sxs-lookup"><span data-stu-id="a9d69-103">Adorners are a special type of <xref:System.Windows.FrameworkElement>, used to provide visual cues to a user.</span></span> <span data-ttu-id="a9d69-104">Tra l'altro, è possibile usare gli strumenti decorativi per aggiungere handle funzionali agli elementi o fornire informazioni sullo stato relative a un controllo.</span><span class="sxs-lookup"><span data-stu-id="a9d69-104">Among other uses, Adorners can be used to add functional handles to elements or provide state information about a control.</span></span>  
  
  
  
<a name="about_Adorners"></a>   
## <a name="about-adorners"></a><span data-ttu-id="a9d69-105">Informazioni sugli strumenti decorativi</span><span class="sxs-lookup"><span data-stu-id="a9d69-105">About Adorners</span></span>  
 <span data-ttu-id="a9d69-106">Un <xref:System.Windows.Documents.Adorner> è un oggetto personalizzato <xref:System.Windows.FrameworkElement> associato a un <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="a9d69-106">An <xref:System.Windows.Documents.Adorner> is a custom <xref:System.Windows.FrameworkElement> that is bound to a <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="a9d69-107">Gli strumenti decorativi vengono visualizzati in un <xref:System.Windows.Documents.AdornerLayer>, che è una superficie di rendering che si trova sempre nella parte superiore dell'elemento decorato o una raccolta di elementi decorati.</span><span class="sxs-lookup"><span data-stu-id="a9d69-107">Adorners are rendered in an <xref:System.Windows.Documents.AdornerLayer>, which is a rendering surface that is always on top of the adorned element or a collection of adorned elements.</span></span> <span data-ttu-id="a9d69-108">Il rendering di uno strumento decorativo è indipendente dal rendering del <xref:System.Windows.UIElement> lo strumento decorativo a cui è associato.</span><span class="sxs-lookup"><span data-stu-id="a9d69-108">Rendering of an adorner is independent from rendering of the <xref:System.Windows.UIElement> that the adorner is bound to.</span></span> <span data-ttu-id="a9d69-109">Uno strumento decorativo in genere è posizionato in relazione all'elemento a cui è associato, usando l'origine delle coordinate 2D standard che si trova in alto a sinistra dell'elemento decorato.</span><span class="sxs-lookup"><span data-stu-id="a9d69-109">An adorner is typically positioned relative to the element to which it is bound, using the standard 2-D coordinate origin located at the upper-left of the adorned element.</span></span>  
  
 <span data-ttu-id="a9d69-110">Applicazioni comuni per gli strumenti decorativi includono:</span><span class="sxs-lookup"><span data-stu-id="a9d69-110">Common applications for adorners include:</span></span>  
  
-   <span data-ttu-id="a9d69-111">Aggiunta di handle funzionali a un <xref:System.Windows.UIElement> che consentire agli utenti di modificare l'elemento in qualche modo (ridimensionare, ruotare, riposizionare e così via).</span><span class="sxs-lookup"><span data-stu-id="a9d69-111">Adding functional handles to a <xref:System.Windows.UIElement> that enable a user to manipulate the element in some way (resize, rotate, reposition, etc.).</span></span>  
  
-   <span data-ttu-id="a9d69-112">Fornire indicazioni visive per identificare i vari stati, oppure in risposta a vari eventi.</span><span class="sxs-lookup"><span data-stu-id="a9d69-112">Provide visual feedback to indicate various states, or in response to various events.</span></span>  
  
-   <span data-ttu-id="a9d69-113">Sovrapporre decorazioni visuali su un <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="a9d69-113">Overlay visual decorations on a <xref:System.Windows.UIElement>.</span></span>  
  
-   <span data-ttu-id="a9d69-114">Mascherare visivamente o eseguire l'override o parte di un <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="a9d69-114">Visually mask or override part or all of a <xref:System.Windows.UIElement>.</span></span>  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="a9d69-115"> fornisce un framework di base per la decorazione di elementi visivi.</span><span class="sxs-lookup"><span data-stu-id="a9d69-115"> provides a basic framework for adorning visual elements.</span></span> <span data-ttu-id="a9d69-116">La tabella seguente include i principali tipi usati per la decorazione di oggetti e il relativo scopo.</span><span class="sxs-lookup"><span data-stu-id="a9d69-116">The following table lists the primary types used when adorning objects, and their purpose.</span></span> <span data-ttu-id="a9d69-117">Di seguito sono riportati alcuni esempi di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="a9d69-117">Several usage examples follow.</span></span>  
  
|||  
|-|-|  
|<xref:System.Windows.Documents.Adorner>|<span data-ttu-id="a9d69-118">Classe di base astratta dalla quale ereditano tutte le implementazioni di strumenti decorativi concreti.</span><span class="sxs-lookup"><span data-stu-id="a9d69-118">An abstract base class from which all concrete adorner implementations inherit.</span></span>|  
|<xref:System.Windows.Documents.AdornerLayer>|<span data-ttu-id="a9d69-119">Classe che rappresenta un livello di rendering per gli strumenti decorativi di uno o più elementi decorati.</span><span class="sxs-lookup"><span data-stu-id="a9d69-119">A class representing a rendering layer for the adorner(s) of one or more adorned elements.</span></span>|  
|<xref:System.Windows.Documents.AdornerDecorator>|<span data-ttu-id="a9d69-120">Classe che consente di associare un livello dello strumento decorativo a una raccolta di elementi.</span><span class="sxs-lookup"><span data-stu-id="a9d69-120">A class that enables an adorner layer to be associated with a collection of elements.</span></span>|  
  
<a name="implement_custom_Adorner"></a>   
## <a name="implementing-a-custom-adorner"></a><span data-ttu-id="a9d69-121">Implementazione di uno strumento decorativo personalizzato</span><span class="sxs-lookup"><span data-stu-id="a9d69-121">Implementing a Custom Adorner</span></span>  
 <span data-ttu-id="a9d69-122">Il framework di strumenti decorativi fornito da [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] è progettato principalmente per supportare la creazione di strumenti decorativi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="a9d69-122">The adorners framework provided by [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] is intended primarily to support the creation of custom adorners.</span></span> <span data-ttu-id="a9d69-123">Viene creato uno strumento decorativo personalizzato implementando una classe che eredita dalla classe astratta <xref:System.Windows.Documents.Adorner> classe.</span><span class="sxs-lookup"><span data-stu-id="a9d69-123">A custom adorner is created by implementing a class that inherits from the abstract <xref:System.Windows.Documents.Adorner> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a9d69-124">L'elemento padre di un <xref:System.Windows.Documents.Adorner> è il <xref:System.Windows.Documents.AdornerLayer> che esegue il rendering di <xref:System.Windows.Documents.Adorner>, non l'elemento decorato.</span><span class="sxs-lookup"><span data-stu-id="a9d69-124">The parent of an <xref:System.Windows.Documents.Adorner> is the <xref:System.Windows.Documents.AdornerLayer> that renders the <xref:System.Windows.Documents.Adorner>, not the element being adorned.</span></span>  
  
 <span data-ttu-id="a9d69-125">L'esempio seguente mostra una classe che implementa uno strumento decorativo semplice.</span><span class="sxs-lookup"><span data-stu-id="a9d69-125">The following example shows a class that implements a simple adorner.</span></span> <span data-ttu-id="a9d69-126">Lo strumento decorativo di esempio decora semplicemente gli angoli di un <xref:System.Windows.UIElement> con i cerchi.</span><span class="sxs-lookup"><span data-stu-id="a9d69-126">The example adorner simply adorns the corners of a <xref:System.Windows.UIElement> with circles.</span></span>  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
 [!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]  
  
 <span data-ttu-id="a9d69-127">La figura seguente mostra il SimpleCircleAdorner a un <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="a9d69-127">The following image shows the SimpleCircleAdorner applied to a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
 <span data-ttu-id="a9d69-128">![Esempio di strumento decorativo: elemento TextBox decorato](../../../../docs/framework/wpf/controls/media/adornedtextbox.png "AdornedTextBox")</span><span class="sxs-lookup"><span data-stu-id="a9d69-128">![Adorners Example: An adorned TextBox](../../../../docs/framework/wpf/controls/media/adornedtextbox.png "AdornedTextBox")</span></span>  
  
<a name="rendering_behavior_for_Adorners"></a>   
## <a name="rendering-behavior-for-adorners"></a><span data-ttu-id="a9d69-129">Comportamento di rendering per gli strumenti decorativi</span><span class="sxs-lookup"><span data-stu-id="a9d69-129">Rendering Behavior for Adorners</span></span>  
 <span data-ttu-id="a9d69-130">È importante notare che gli strumenti decorativi non includono alcun comportamento di rendering inerente, pertanto è responsabilità dell'implementatore garantire il rendering di uno strumento decorativo visuale.</span><span class="sxs-lookup"><span data-stu-id="a9d69-130">It is important to note that adorners do not include any inherent rendering behavior; ensuring that an adorner renders is the responsibility of the adorner implementer.</span></span>   <span data-ttu-id="a9d69-131">È un modo comune di implementare il comportamento di rendering per eseguire l'override di <xref:System.Windows.UIElement.OnRender%2A> metodo e utilizzare uno o più <xref:System.Windows.Media.DrawingContext> oggetti per eseguire il rendering degli elementi visivi dello strumento decorativo in base alle esigenze (come illustrato nell'esempio precedente).</span><span class="sxs-lookup"><span data-stu-id="a9d69-131">A common way of implementing rendering behavior is to override the <xref:System.Windows.UIElement.OnRender%2A> method and use one or more <xref:System.Windows.Media.DrawingContext> objects to render the adorner's visuals as needed (as shown in the example above).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a9d69-132">Il rendering di qualsiasi elemento posizionato nel livello degli strumenti decorativi viene eseguito al di sopra degli altri stili impostati.</span><span class="sxs-lookup"><span data-stu-id="a9d69-132">Anything placed in the adorner layer is rendered on top of the rest of any styles you have set.</span></span> <span data-ttu-id="a9d69-133">In altre parole, gli strumenti decorativi vengono sempre visualizzati al di sopra degli altri elementi e non possono essere sottoposti a override tramite l'ordine z.</span><span class="sxs-lookup"><span data-stu-id="a9d69-133">In other words, adorners are always visually on top and cannot be overridden using z-order.</span></span>  
  
<a name="adorner_events_hittest"></a>   
## <a name="events-and-hit-testing"></a><span data-ttu-id="a9d69-134">Eventi e hit test</span><span class="sxs-lookup"><span data-stu-id="a9d69-134">Events and Hit Testing</span></span>  
 <span data-ttu-id="a9d69-135">Gli strumenti decorativi riceveranno eventi di input come qualsiasi altro <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="a9d69-135">Adorners receive input events just like any other <xref:System.Windows.FrameworkElement>.</span></span>  <span data-ttu-id="a9d69-136">Poiché uno strumento decorativo ha sempre un ordine z più elevato rispetto all'elemento che decora, lo strumento decorativo visuale riceve eventi di input (ad esempio <xref:System.Windows.UIElement.Drop> o <xref:System.Windows.UIElement.MouseMove>) che possono essere destinati all'elemento decorato sottostante.</span><span class="sxs-lookup"><span data-stu-id="a9d69-136">Because an adorner always has a higher z-order than the element it adorns, the adorner receives input events (such as <xref:System.Windows.UIElement.Drop> or <xref:System.Windows.UIElement.MouseMove>) that may be intended for the underlying adorned element.</span></span>  <span data-ttu-id="a9d69-137">Uno strumento decorativo può ascoltare determinati eventi di input e passare tali valori all'elemento decorato sottostante generando nuovamente l'evento.</span><span class="sxs-lookup"><span data-stu-id="a9d69-137">An adorner can listen for certain input events and pass these on to the underlying adorned element by re-raising the event.</span></span>  
  
 <span data-ttu-id="a9d69-138">Per abilitare l'hit testing pass-through di elementi in uno strumento decorativo visuale, impostare l'hit test <xref:System.Windows.UIElement.IsHitTestVisible%2A> proprietà **false** sullo strumento decorativo.</span><span class="sxs-lookup"><span data-stu-id="a9d69-138">To enable pass-through hit testing of elements under an adorner, set the hit test <xref:System.Windows.UIElement.IsHitTestVisible%2A> property to **false** on the adorner.</span></span>  <span data-ttu-id="a9d69-139">Per altre informazioni sull'hit test, vedere</span><span class="sxs-lookup"><span data-stu-id="a9d69-139">For more information about hit testing, see</span></span>  
  
 <span data-ttu-id="a9d69-140">[Hit testing a livello visivo](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md).</span><span class="sxs-lookup"><span data-stu-id="a9d69-140">[Hit Testing in the Visual Layer](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md).</span></span>  
  
<a name="adorn_single_element"></a>   
## <a name="adorning-a-single-uielement"></a><span data-ttu-id="a9d69-141">Decorazione di un singolo UIElement</span><span class="sxs-lookup"><span data-stu-id="a9d69-141">Adorning a Single UIElement</span></span>  
 <span data-ttu-id="a9d69-142">Per associare un adorner a un particolare <xref:System.Windows.UIElement>, seguire questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="a9d69-142">To bind an adorner to a particular <xref:System.Windows.UIElement>, follow these steps:</span></span>  
  
1.  <span data-ttu-id="a9d69-143">Chiamare il metodo statico <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> per ottenere un <xref:System.Windows.Documents.AdornerLayer> dell'oggetto per il <xref:System.Windows.UIElement> da decorare.</span><span class="sxs-lookup"><span data-stu-id="a9d69-143">Call the static method <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> to get an <xref:System.Windows.Documents.AdornerLayer> object for the <xref:System.Windows.UIElement> to be adorned.</span></span> <span data-ttu-id="a9d69-144"><xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>descrive la struttura ad albero visuale, inizia in corrispondenza <xref:System.Windows.UIElement>e restituisce il primo livello dello strumento decorativo visuale trovato.</span><span class="sxs-lookup"><span data-stu-id="a9d69-144"><xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> walks up the visual tree, starting at the specified <xref:System.Windows.UIElement>, and returns the first adorner layer it finds.</span></span> <span data-ttu-id="a9d69-145">(se non viene trovato alcun livello dello strumento decorativo, il metodo restituisce null).</span><span class="sxs-lookup"><span data-stu-id="a9d69-145">(If no adorner layers are found, the method returns null.)</span></span>  
  
2.  <span data-ttu-id="a9d69-146">Chiamare il <xref:System.Windows.Documents.AdornerLayer.Add%2A> metodo per associare lo strumento decorativo di destinazione <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="a9d69-146">Call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind the adorner to the target <xref:System.Windows.UIElement>.</span></span>  
  
 <span data-ttu-id="a9d69-147">Nell'esempio seguente viene associato un SimpleCircleAdorner (illustrato in precedenza) a un <xref:System.Windows.Controls.TextBox> denominato *myTextBox*.</span><span class="sxs-lookup"><span data-stu-id="a9d69-147">The following example binds a SimpleCircleAdorner (shown above) to a <xref:System.Windows.Controls.TextBox> named *myTextBox*.</span></span>  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]  
  
> [!NOTE]
>  <span data-ttu-id="a9d69-148">Non è attualmente possibile usare [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] per associare uno strumento decorativo a un altro elemento.</span><span class="sxs-lookup"><span data-stu-id="a9d69-148">Using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to bind an adorner to another element is currently not supported.</span></span>  
  
<a name="adorn_children_panel"></a>   
## <a name="adorning-the-children-of-a-panel"></a><span data-ttu-id="a9d69-149">Decorazione degli elementi figlio di un elemento Panel</span><span class="sxs-lookup"><span data-stu-id="a9d69-149">Adorning the Children of a Panel</span></span>  
 <span data-ttu-id="a9d69-150">Per associare uno strumento decorativo visuale agli elementi figlio di un <xref:System.Windows.Controls.Panel>, seguire questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="a9d69-150">To bind an adorner to the children of a <xref:System.Windows.Controls.Panel>, follow these steps:</span></span>  
  
1.  <span data-ttu-id="a9d69-151">Chiamare il `static` metodo <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> per trovare un livello dello strumento decorativo per l'elemento per decorare i cui elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="a9d69-151">Call the `static` method <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> to find an adorner layer for the element whose children are to be adorned.</span></span>  
  
2.  <span data-ttu-id="a9d69-152">Enumerare gli elementi figlio dell'elemento padre e chiamata di <xref:System.Windows.Documents.AdornerLayer.Add%2A> metodo per associare un adorner a ogni elemento figlio.</span><span class="sxs-lookup"><span data-stu-id="a9d69-152">Enumerate through the children of the parent element and call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind an adorner to each child element.</span></span>  
  
 <span data-ttu-id="a9d69-153">Nell'esempio seguente viene associato un SimpleCircleAdorner (illustrato in precedenza) per gli elementi figlio di un <xref:System.Windows.Controls.StackPanel> denominato *myStackPanel*.</span><span class="sxs-lookup"><span data-stu-id="a9d69-153">The following example binds a SimpleCircleAdorner (shown above) to the children of a <xref:System.Windows.Controls.StackPanel> named *myStackPanel*.</span></span>  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]  
  
## <a name="see-also"></a><span data-ttu-id="a9d69-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a9d69-154">See Also</span></span>  
 <xref:System.Windows.Media.AdornerHitTestResult>  
 [<span data-ttu-id="a9d69-155">Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF</span><span class="sxs-lookup"><span data-stu-id="a9d69-155">Shapes and Basic Drawing in WPF Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)  
 [<span data-ttu-id="a9d69-156">Disegnare con oggetti Image, Drawing e Visual</span><span class="sxs-lookup"><span data-stu-id="a9d69-156">Painting with Images, Drawings, and Visuals</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)  
 [<span data-ttu-id="a9d69-157">Cenni preliminari sugli oggetti Drawing</span><span class="sxs-lookup"><span data-stu-id="a9d69-157">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [<span data-ttu-id="a9d69-158">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="a9d69-158">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/adorners-how-to-topics.md)
