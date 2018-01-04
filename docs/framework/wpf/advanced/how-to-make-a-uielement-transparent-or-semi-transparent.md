---
title: 'Procedura: rendere trasparente o semitrasparente un oggetto UIElement'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UIElements [WPF], transparency
- opacity [WPF], of UIElements
- transparency of UIElements [WPF]
- UIElements [WPF], opacity
ms.assetid: a49fc8d6-7b32-4f28-9122-39b632a19b4b
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 25245319c02ae376410d71afb7a1e56eda259e99
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-make-a-uielement-transparent-or-semi-transparent"></a><span data-ttu-id="4869b-102">Procedura: rendere trasparente o semitrasparente un oggetto UIElement</span><span class="sxs-lookup"><span data-stu-id="4869b-102">How to: Make a UIElement Transparent or Semi-Transparent</span></span>
<span data-ttu-id="4869b-103">Questo esempio viene illustrato come rendere un <xref:System.Windows.UIElement> trasparente o semitrasparente.</span><span class="sxs-lookup"><span data-stu-id="4869b-103">This example shows how to make a <xref:System.Windows.UIElement> transparent or semi-transparent.</span></span> <span data-ttu-id="4869b-104">Per rendere un elemento trasparente o semitrasparente, impostare il relativo <xref:System.Windows.UIElement.Opacity%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="4869b-104">To make an element transparent or semi-transparent, you set its <xref:System.Windows.UIElement.Opacity%2A> property.</span></span> <span data-ttu-id="4869b-105">Il valore `0.0` l'elemento viene reso completamente trasparente, mentre un valore di `1.0` l'elemento viene reso completamente opaco.</span><span class="sxs-lookup"><span data-stu-id="4869b-105">A value of `0.0` makes the element completely transparent, while a value of `1.0` makes the element completely opaque.</span></span> <span data-ttu-id="4869b-106">Il valore `0.5` l'elemento viene reso 50% e così via.</span><span class="sxs-lookup"><span data-stu-id="4869b-106">A value of `0.5` makes the element 50% opaque, and so on.</span></span> <span data-ttu-id="4869b-107">Un elemento <xref:System.Windows.UIElement.Opacity%2A> è impostato su `1.0` per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="4869b-107">An element's <xref:System.Windows.UIElement.Opacity%2A> is set to `1.0` by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4869b-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="4869b-108">Example</span></span>  
 <span data-ttu-id="4869b-109">L'esempio seguente imposta il <xref:System.Windows.UIElement.Opacity%2A> di un pulsante per `0.25`, rendendo opaco l'oggetto e il relativo contenuto (in questo caso, il testo del pulsante) al 25%.</span><span class="sxs-lookup"><span data-stu-id="4869b-109">The following example sets the <xref:System.Windows.UIElement.Opacity%2A> of a button to `0.25`, making it and its contents (in this case, the button's text) 25% opaque.</span></span>  
  
 [!code-xaml[brushsamples_snip#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#2)]  
  
 [!code-csharp[brushsamples_procedural_snip#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#2)]  
  
 <span data-ttu-id="4869b-110">Se il contenuto di un elemento dispone delle proprie <xref:System.Windows.UIElement.Opacity%2A> impostazioni, tali valori vengono moltiplicate per gli elementi contenitori <xref:System.Windows.UIElement.Opacity%2A>.</span><span class="sxs-lookup"><span data-stu-id="4869b-110">If an element's contents have their own <xref:System.Windows.UIElement.Opacity%2A> settings, those values are multiplied against the containing elements <xref:System.Windows.UIElement.Opacity%2A>.</span></span>  
  
 <span data-ttu-id="4869b-111">Nell'esempio seguente imposta un pulsante <xref:System.Windows.UIElement.Opacity%2A> a `0.25`e <xref:System.Windows.UIElement.Opacity%2A> di un <xref:System.Windows.Controls.Image> controllo contenuto all'interno del pulsante su `0.5`.</span><span class="sxs-lookup"><span data-stu-id="4869b-111">The following example sets a button's <xref:System.Windows.UIElement.Opacity%2A> to `0.25`, and the <xref:System.Windows.UIElement.Opacity%2A> of an <xref:System.Windows.Controls.Image> control contained with in the button to `0.5`.</span></span> <span data-ttu-id="4869b-112">Di conseguenza, l'immagine viene visualizzata 12,5% opaco: 0,25 * 0,5 = 0,125.</span><span class="sxs-lookup"><span data-stu-id="4869b-112">As a result, the image appears 12.5% opaque: 0.25 * 0.5 = 0.125.</span></span>  
  
 [!code-xaml[brushsamples_snip#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#3)]  
  
 [!code-csharp[brushsamples_procedural_snip#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#3)]  
  
 <span data-ttu-id="4869b-113">Un altro modo per controllare l'opacità di un elemento consiste nell'impostare l'opacità del <xref:System.Windows.Media.Brush> che disegna l'elemento.</span><span class="sxs-lookup"><span data-stu-id="4869b-113">Another way to control the opacity of an element is to set the opacity of the <xref:System.Windows.Media.Brush> that paints the element.</span></span> <span data-ttu-id="4869b-114">Questo approccio consente di modificare in modo selettivo l'opacità di parti di un elemento e offre vantaggi nelle prestazioni rispetto all'uso dell'elemento <xref:System.Windows.UIElement.Opacity%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="4869b-114">This approach enables you to selectively alter the opacity of portions of an element, and provides performance benefits over using the element's <xref:System.Windows.UIElement.Opacity%2A> property.</span></span> <span data-ttu-id="4869b-115">L'esempio seguente imposta il <xref:System.Windows.Media.Brush.Opacity%2A> di un <xref:System.Windows.Media.SolidColorBrush> usato per disegnare il pulsante <xref:System.Windows.Controls.Control.Background%2A> è impostato su `0.25`.</span><span class="sxs-lookup"><span data-stu-id="4869b-115">The following example sets the <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.SolidColorBrush> used to paint the button's <xref:System.Windows.Controls.Control.Background%2A> is set to `0.25`.</span></span> <span data-ttu-id="4869b-116">Di conseguenza, lo sfondo del pennello è opaco al 25%, ma il relativo contenuto (testo del pulsante) rimane opaca al 100%.</span><span class="sxs-lookup"><span data-stu-id="4869b-116">As a result, the brush's background is 25% opaque, but its contents (the button's text) remain 100% opaque.</span></span>  
  
 [!code-xaml[brushsamples_snip#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#4)]  
  
 [!code-csharp[brushsamples_procedural_snip#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#4)]  
  
 <span data-ttu-id="4869b-117">È inoltre possibile controllare l'opacità di colori singoli all'interno di un pennello.</span><span class="sxs-lookup"><span data-stu-id="4869b-117">You may also control the opacity of individual colors within a brush.</span></span> <span data-ttu-id="4869b-118">Per ulteriori informazioni sui colori e pennelli, vedere [disegni con colori a tinta unita e sfumature Panoramica](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4869b-118">For more information about colors and brushes, see [Painting with Solid Colors and Gradients Overview](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).</span></span> <span data-ttu-id="4869b-119">Per un esempio che illustra come aggiungere un'animazione opacità di un elemento, vedere [animare l'opacità di un elemento o un pennello](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-the-opacity-of-an-element-or-brush.md).</span><span class="sxs-lookup"><span data-stu-id="4869b-119">For an example showing how to animate an element's opacity, see [Animate the Opacity of an Element or Brush](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-the-opacity-of-an-element-or-brush.md).</span></span>
