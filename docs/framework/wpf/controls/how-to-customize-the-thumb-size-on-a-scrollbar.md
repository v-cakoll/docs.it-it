---
title: 'Procedura: personalizzare le dimensioni del cursore in una barra di scorrimento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ScrollBar control [WPF]
- customizing thumb size [WPF]
- thumb size [WPF]
ms.assetid: fa32b866-5ca1-4e73-85e7-2ac64b80d194
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c550aa425eedf4b434e061f05326bf6a6de91f9d
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-customize-the-thumb-size-on-a-scrollbar"></a><span data-ttu-id="4c329-102">Procedura: personalizzare le dimensioni del cursore in una barra di scorrimento</span><span class="sxs-lookup"><span data-stu-id="4c329-102">How to: Customize the Thumb Size on a ScrollBar</span></span>
<span data-ttu-id="4c329-103">In questo argomento viene illustrato come impostare il <xref:System.Windows.Controls.Primitives.Thumb> di un <xref:System.Windows.Controls.Primitives.ScrollBar> a una dimensione fissa e come specificare la dimensione minima per il <xref:System.Windows.Controls.Primitives.Thumb> di un <xref:System.Windows.Controls.Primitives.ScrollBar>.</span><span class="sxs-lookup"><span data-stu-id="4c329-103">This topic explains how to set the <xref:System.Windows.Controls.Primitives.Thumb> of a <xref:System.Windows.Controls.Primitives.ScrollBar> to a fixed size and how to specify a minimum size for the <xref:System.Windows.Controls.Primitives.Thumb> of a <xref:System.Windows.Controls.Primitives.ScrollBar>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c329-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="4c329-104">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="4c329-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4c329-105">Description</span></span>  
 <span data-ttu-id="4c329-106">Nell'esempio seguente viene creato un <xref:System.Windows.Controls.Primitives.ScrollBar> che ha un <xref:System.Windows.Controls.Primitives.Thumb> con dimensioni fisse.</span><span class="sxs-lookup"><span data-stu-id="4c329-106">The following example creates a <xref:System.Windows.Controls.Primitives.ScrollBar> that has a <xref:System.Windows.Controls.Primitives.Thumb> with a fixed size.</span></span> <span data-ttu-id="4c329-107">Nell'esempio viene impostata la <xref:System.Windows.Controls.Primitives.Track.ViewportSize%2A> proprietà del <xref:System.Windows.Controls.Primitives.Thumb> a <xref:System.Double.NaN> e imposta l'altezza del <xref:System.Windows.Controls.Primitives.Thumb>.</span><span class="sxs-lookup"><span data-stu-id="4c329-107">The example sets the <xref:System.Windows.Controls.Primitives.Track.ViewportSize%2A> property of the <xref:System.Windows.Controls.Primitives.Thumb> to <xref:System.Double.NaN> and sets the height of the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  <span data-ttu-id="4c329-108">Per creare un oggetto orizzontale <xref:System.Windows.Controls.Primitives.ScrollBar> con un <xref:System.Windows.Controls.Primitives.Thumb> che ha una larghezza fissa, impostare la larghezza del <xref:System.Windows.Controls.Primitives.Thumb>.</span><span class="sxs-lookup"><span data-stu-id="4c329-108">To create a horizontal <xref:System.Windows.Controls.Primitives.ScrollBar> with a <xref:System.Windows.Controls.Primitives.Thumb> that has a fixed width, set the width of the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
## <a name="code"></a><span data-ttu-id="4c329-109">Codice</span><span class="sxs-lookup"><span data-stu-id="4c329-109">Code</span></span>  
 [!code-xaml[ScrollBarCustomThumbSize#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#1)]  
  
## <a name="description"></a><span data-ttu-id="4c329-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4c329-110">Description</span></span>  
 <span data-ttu-id="4c329-111">Nell'esempio seguente viene creato un <xref:System.Windows.Controls.Primitives.ScrollBar> che ha un <xref:System.Windows.Controls.Primitives.Thumb> con una dimensione minima.</span><span class="sxs-lookup"><span data-stu-id="4c329-111">The following example creates a <xref:System.Windows.Controls.Primitives.ScrollBar> that has a <xref:System.Windows.Controls.Primitives.Thumb> with a minimum size.</span></span> <span data-ttu-id="4c329-112">Nell'esempio viene impostato il valore di <xref:System.Windows.SystemParameters.VerticalScrollBarButtonHeightKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="4c329-112">The example sets the value of <xref:System.Windows.SystemParameters.VerticalScrollBarButtonHeightKey%2A>.</span></span> <span data-ttu-id="4c329-113">Per creare un oggetto orizzontale <xref:System.Windows.Controls.Primitives.ScrollBar> con un <xref:System.Windows.Controls.Primitives.Thumb> con una larghezza minima, impostare il <xref:System.Windows.SystemParameters.HorizontalScrollBarButtonWidthKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="4c329-113">To create a horizontal <xref:System.Windows.Controls.Primitives.ScrollBar> with a <xref:System.Windows.Controls.Primitives.Thumb> that has a minimum width, set the <xref:System.Windows.SystemParameters.HorizontalScrollBarButtonWidthKey%2A>.</span></span>  
  
## <a name="code"></a><span data-ttu-id="4c329-114">Codice</span><span class="sxs-lookup"><span data-stu-id="4c329-114">Code</span></span>  
 [!code-xaml[ScrollBarCustomThumbSize#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#2)]  
  
## <a name="see-also"></a><span data-ttu-id="4c329-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c329-115">See Also</span></span>  
 [<span data-ttu-id="4c329-116">Stili e modelli di ScrollBar</span><span class="sxs-lookup"><span data-stu-id="4c329-116">ScrollBar Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/scrollbar-styles-and-templates.md)
