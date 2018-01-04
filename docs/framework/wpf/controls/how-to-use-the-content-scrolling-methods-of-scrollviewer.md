---
title: 'Procedura: utilizzare i metodi di scorrimento del contenuto di ScrollViewer'
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
- IScrollInfo interface [WPF]
- scrolling methods [WPF]
- ScrollViewer control [WPF], scrolling methods
ms.assetid: 4708cc65-6510-45f8-82e6-30b0d3e30045
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5911d8e36b82aa44a1fdadfa60d422c894b4fc71
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-the-content-scrolling-methods-of-scrollviewer"></a><span data-ttu-id="34cbf-102">Procedura: utilizzare i metodi di scorrimento del contenuto di ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="34cbf-102">How to: Use the Content-Scrolling Methods of ScrollViewer</span></span>
<span data-ttu-id="34cbf-103">In questo esempio viene illustrato come utilizzare i metodi di scorrimento di <xref:System.Windows.Controls.ScrollViewer> elemento.</span><span class="sxs-lookup"><span data-stu-id="34cbf-103">This example shows how to use the scrolling methods of the <xref:System.Windows.Controls.ScrollViewer> element.</span></span> <span data-ttu-id="34cbf-104">Questi metodi consentono lo scorrimento incrementale del contenuto, tramite la riga o pagina, in un <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="34cbf-104">These methods provide incremental scrolling of content, either by line or by page, in a <xref:System.Windows.Controls.ScrollViewer>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34cbf-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="34cbf-105">Example</span></span>  
 <span data-ttu-id="34cbf-106">Nell'esempio seguente viene creato un <xref:System.Windows.Controls.ScrollViewer> denominato `sv1`, che ospita un elemento figlio <xref:System.Windows.Controls.TextBlock> elemento.</span><span class="sxs-lookup"><span data-stu-id="34cbf-106">The following example creates a <xref:System.Windows.Controls.ScrollViewer> named `sv1`, which hosts a child <xref:System.Windows.Controls.TextBlock> element.</span></span> <span data-ttu-id="34cbf-107">Poiché il <xref:System.Windows.Controls.TextBlock> è più grande del padre <xref:System.Windows.Controls.ScrollViewer>, vengono visualizzate le barre di scorrimento per consentire lo scorrimento.</span><span class="sxs-lookup"><span data-stu-id="34cbf-107">Because the <xref:System.Windows.Controls.TextBlock> is larger than the parent <xref:System.Windows.Controls.ScrollViewer>, scroll bars appear in order to enable scrolling.</span></span> <span data-ttu-id="34cbf-108"><xref:System.Windows.Controls.Button>gli elementi che rappresentano i vari metodi di scorrimento sono ancorati a sinistra in una funzione <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="34cbf-108"><xref:System.Windows.Controls.Button> elements that represent the various scrolling methods are docked on the left in a separate <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="34cbf-109">Ogni <xref:System.Windows.Controls.Button> nel [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file chiama un metodo personalizzato correlato che controlla il comportamento di scorrimento in <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="34cbf-109">Each <xref:System.Windows.Controls.Button> in the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file calls a related custom method that controls scrolling behavior in <xref:System.Windows.Controls.ScrollViewer>.</span></span>  
  
 [!code-xaml[ScrollViewerMethods#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewerMethods/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="34cbf-110">L'esempio seguente usa il <xref:System.Windows.Controls.ScrollViewer.LineUp%2A> e <xref:System.Windows.Controls.ScrollViewer.LineDown%2A> metodi.</span><span class="sxs-lookup"><span data-stu-id="34cbf-110">The following example uses the <xref:System.Windows.Controls.ScrollViewer.LineUp%2A> and <xref:System.Windows.Controls.ScrollViewer.LineDown%2A> methods.</span></span>  
  
 [!code-csharp[ScrollViewerMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewerMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ScrollViewerMethods#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewerMethods/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="34cbf-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34cbf-111">See Also</span></span>  
 <xref:System.Windows.Controls.ScrollViewer>  
 <xref:System.Windows.Controls.StackPanel>
