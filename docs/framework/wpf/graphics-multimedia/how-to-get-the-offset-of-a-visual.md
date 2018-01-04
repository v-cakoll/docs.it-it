---
title: 'Procedura: ottenere l''offset di un oggetto Visual'
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
- getting offset values from visual objects [WPF]
- offset values [WPF], retrieving from visual objects [WPF]
- visual objects [WPF], retrieving offset values from
- retrieving offset values from visual objects [WPF]
ms.assetid: 889a1dd6-1b11-445a-b351-fbb04c53ee34
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ee18503bdd6100cbe7a62ac70d7ea0848fb124eb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-get-the-offset-of-a-visual"></a><span data-ttu-id="b2dbf-102">Procedura: ottenere l'offset di un oggetto Visual</span><span class="sxs-lookup"><span data-stu-id="b2dbf-102">How to: Get the Offset of a Visual</span></span>
<span data-ttu-id="b2dbf-103">Questi esempi mostrano come recuperare il valore di offset di un oggetto visivo è relativo padre, qualsiasi predecessore o discendente.</span><span class="sxs-lookup"><span data-stu-id="b2dbf-103">These examples show how to retrieve the offset value of a visual object that is relative to its parent, or any ancestor or descendant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2dbf-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="b2dbf-104">Example</span></span>  
 <span data-ttu-id="b2dbf-105">Il markup seguente viene mostrato un <xref:System.Windows.Controls.TextBlock> definito con <xref:System.Windows.FrameworkElement.Margin%2A> valore 4.</span><span class="sxs-lookup"><span data-stu-id="b2dbf-105">The following markup example shows a <xref:System.Windows.Controls.TextBlock> that is defined with <xref:System.Windows.FrameworkElement.Margin%2A> value of 4.</span></span>  
  
 [!code-xaml[VisualSnippets#VisualSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml#visualsnippet1)]  
  
 <span data-ttu-id="b2dbf-106">Esempio di codice seguente viene illustrato come utilizzare il <xref:System.Windows.Media.VisualTreeHelper.GetOffset%2A> metodo per recuperare l'offset del <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="b2dbf-106">The following code example shows how to use the <xref:System.Windows.Media.VisualTreeHelper.GetOffset%2A> method to retrieve the offset of the <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="b2dbf-107">Sono contenuti i valori di offset all'interno di restituito <xref:System.Windows.Vector> valore.</span><span class="sxs-lookup"><span data-stu-id="b2dbf-107">The offset values are contained within the returned <xref:System.Windows.Vector> value.</span></span>  
  
 [!code-csharp[VisualSnippets#VisualSnippet2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet2)]
 [!code-vb[VisualSnippets#VisualSnippet2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet2)]  
  
 <span data-ttu-id="b2dbf-108">L'offset prende in considerazione il <xref:System.Windows.FrameworkElement.Margin%2A> valore.</span><span class="sxs-lookup"><span data-stu-id="b2dbf-108">The offset takes into account the <xref:System.Windows.FrameworkElement.Margin%2A> value.</span></span> <span data-ttu-id="b2dbf-109">In questo caso, <xref:System.Windows.Vector.X%2A> è 4, e <xref:System.Windows.Vector.Y%2A> è 4.</span><span class="sxs-lookup"><span data-stu-id="b2dbf-109">In this case, <xref:System.Windows.Vector.X%2A> is 4, and <xref:System.Windows.Vector.Y%2A> is 4.</span></span>  
  
 <span data-ttu-id="b2dbf-110">Il valore di offset restituito è relativo elemento padre del <xref:System.Windows.Media.Visual>.</span><span class="sxs-lookup"><span data-stu-id="b2dbf-110">The returned offset value is relative to the parent of the <xref:System.Windows.Media.Visual>.</span></span> <span data-ttu-id="b2dbf-111">Se si desidera restituire un valore di offset non specificato fa riferimento l'elemento padre di un <xref:System.Windows.Media.Visual>, utilizzare il <xref:System.Windows.Media.Visual.TransformToAncestor%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="b2dbf-111">If you want to return an offset value that is not relative to the parent of a <xref:System.Windows.Media.Visual>, use the <xref:System.Windows.Media.Visual.TransformToAncestor%2A> method.</span></span>  
  
## <a name="getting-the-offset-relative-to-an-ancestor"></a><span data-ttu-id="b2dbf-112">Acquisizione dell'Offset relativo a un predecessore</span><span class="sxs-lookup"><span data-stu-id="b2dbf-112">Getting the Offset Relative to an Ancestor</span></span>  
 <span data-ttu-id="b2dbf-113">Il markup seguente viene mostrato un <xref:System.Windows.Controls.TextBlock> annidato all'interno di due <xref:System.Windows.Controls.StackPanel> oggetti.</span><span class="sxs-lookup"><span data-stu-id="b2dbf-113">The following markup example shows a <xref:System.Windows.Controls.TextBlock> that is nested within two <xref:System.Windows.Controls.StackPanel> objects.</span></span>  
  
 [!code-xaml[VisualSnippets#VisualSnippet7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window2.xaml#visualsnippet7)]  
  
 <span data-ttu-id="b2dbf-114">Nella figura seguente mostra i risultati del markup.</span><span class="sxs-lookup"><span data-stu-id="b2dbf-114">The following illustration shows the results of the markup.</span></span>  
  
 <span data-ttu-id="b2dbf-115">![Valori di offset degli oggetti](../../../../docs/framework/wpf/graphics-multimedia/media/visualoffset-01.png "VisualOffset_01")</span><span class="sxs-lookup"><span data-stu-id="b2dbf-115">![Offset values of objects](../../../../docs/framework/wpf/graphics-multimedia/media/visualoffset-01.png "VisualOffset_01")</span></span>  
<span data-ttu-id="b2dbf-116">TextBlock annidato all'interno di due StackPanel</span><span class="sxs-lookup"><span data-stu-id="b2dbf-116">TextBlock nested within two StackPanels</span></span>  
  
 <span data-ttu-id="b2dbf-117">Esempio di codice seguente viene illustrato come utilizzare il <xref:System.Windows.Media.Visual.TransformToAncestor%2A> metodo per recuperare l'offset del <xref:System.Windows.Controls.TextBlock> relativo contenitore <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="b2dbf-117">The following code example shows how to use the <xref:System.Windows.Media.Visual.TransformToAncestor%2A> method to retrieve the offset of the <xref:System.Windows.Controls.TextBlock> relative to the containing <xref:System.Windows.Window>.</span></span> <span data-ttu-id="b2dbf-118">Sono contenuti i valori di offset all'interno di restituito <xref:System.Windows.Media.GeneralTransform> valore.</span><span class="sxs-lookup"><span data-stu-id="b2dbf-118">The offset values are contained within the returned <xref:System.Windows.Media.GeneralTransform> value.</span></span>  
  
 [!code-csharp[VisualSnippets#VisualSnippet5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet5)]
 [!code-vb[VisualSnippets#VisualSnippet5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet5)]  
  
 <span data-ttu-id="b2dbf-119">L'offset prende in considerazione il <xref:System.Windows.FrameworkElement.Margin%2A> i valori per tutti gli oggetti nel contenitore <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="b2dbf-119">The offset takes into account the <xref:System.Windows.FrameworkElement.Margin%2A> values for all objects within the containing <xref:System.Windows.Window>.</span></span> <span data-ttu-id="b2dbf-120">In questo caso, <xref:System.Windows.Vector.X%2A> è 28 (16 + 8 + 4), e <xref:System.Windows.Vector.Y%2A> è 28.</span><span class="sxs-lookup"><span data-stu-id="b2dbf-120">In this case, <xref:System.Windows.Vector.X%2A> is 28 (16 + 8 + 4), and <xref:System.Windows.Vector.Y%2A> is 28.</span></span>  
  
 <span data-ttu-id="b2dbf-121">Il valore di offset restituito è relativo il predecessore di <xref:System.Windows.Media.Visual>.</span><span class="sxs-lookup"><span data-stu-id="b2dbf-121">The returned offset value is relative to the ancestor of the <xref:System.Windows.Media.Visual>.</span></span> <span data-ttu-id="b2dbf-122">Se si desidera restituire un valore di offset è relativo al discendente di un <xref:System.Windows.Media.Visual>, utilizzare il <xref:System.Windows.Media.Visual.TransformToDescendant%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="b2dbf-122">If you want to return an offset value that is relative to the descendant of a <xref:System.Windows.Media.Visual>, use the <xref:System.Windows.Media.Visual.TransformToDescendant%2A> method.</span></span>  
  
## <a name="getting-the-offset-relative-to-a-descendant"></a><span data-ttu-id="b2dbf-123">Acquisizione dell'Offset relativo a un discendente</span><span class="sxs-lookup"><span data-stu-id="b2dbf-123">Getting the Offset Relative to a Descendant</span></span>  
 <span data-ttu-id="b2dbf-124">Il markup seguente viene mostrato un <xref:System.Windows.Controls.TextBlock> contenuta all'interno di un <xref:System.Windows.Controls.StackPanel> oggetto.</span><span class="sxs-lookup"><span data-stu-id="b2dbf-124">The following markup example shows a <xref:System.Windows.Controls.TextBlock> that is contained within a <xref:System.Windows.Controls.StackPanel> object.</span></span>  
  
 [!code-xaml[VisualSnippets#VisualSnippet4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml#visualsnippet4)]  
  
 <span data-ttu-id="b2dbf-125">Esempio di codice seguente viene illustrato come utilizzare il <xref:System.Windows.Media.Visual.TransformToDescendant%2A> metodo per recuperare l'offset del <xref:System.Windows.Controls.StackPanel> rispetto al relativo elemento figlio <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="b2dbf-125">The following code example shows how to use the <xref:System.Windows.Media.Visual.TransformToDescendant%2A> method to retrieve the offset of the <xref:System.Windows.Controls.StackPanel> relative to its child <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="b2dbf-126">Sono contenuti i valori di offset all'interno di restituito <xref:System.Windows.Media.GeneralTransform> valore.</span><span class="sxs-lookup"><span data-stu-id="b2dbf-126">The offset values are contained within the returned <xref:System.Windows.Media.GeneralTransform> value.</span></span>  
  
 [!code-csharp[VisualSnippets#VisualSnippet9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet9)]
 [!code-vb[VisualSnippets#VisualSnippet9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet9)]  
  
 <span data-ttu-id="b2dbf-127">L'offset prende in considerazione il <xref:System.Windows.FrameworkElement.Margin%2A> i valori per tutti gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="b2dbf-127">The offset takes into account the <xref:System.Windows.FrameworkElement.Margin%2A> values for all objects.</span></span> <span data-ttu-id="b2dbf-128">In questo caso, <xref:System.Windows.Vector.X%2A> è -4 e <xref:System.Windows.Vector.Y%2A> è -4.</span><span class="sxs-lookup"><span data-stu-id="b2dbf-128">In this case, <xref:System.Windows.Vector.X%2A> is -4, and <xref:System.Windows.Vector.Y%2A> is -4.</span></span> <span data-ttu-id="b2dbf-129">I valori di offset sono valori negativi, poiché l'oggetto padre viene spostato negativamente rispetto all'oggetto figlio.</span><span class="sxs-lookup"><span data-stu-id="b2dbf-129">The offset values are negative values, since the parent object is negatively offset relative to its child object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2dbf-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2dbf-130">See Also</span></span>  
 <xref:System.Windows.Media.Visual>  
 <xref:System.Windows.Media.VisualTreeHelper>  
 [<span data-ttu-id="b2dbf-131">Cenni preliminari sul rendering della grafica WPF</span><span class="sxs-lookup"><span data-stu-id="b2dbf-131">WPF Graphics Rendering Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)
