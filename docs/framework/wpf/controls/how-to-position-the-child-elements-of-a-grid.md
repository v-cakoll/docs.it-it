---
title: 'Procedura: posizionare gli elementi figlio di una griglia'
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
helpviewer_keywords: Grid control [WPF], positioning child elements
ms.assetid: 27b3ba9b-ad32-44e2-bcab-a79d573a463c
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0ca385e1aee10fb10ac3e912999aec3a11d03ab4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-position-the-child-elements-of-a-grid"></a><span data-ttu-id="34115-102">Procedura: posizionare gli elementi figlio di una griglia</span><span class="sxs-lookup"><span data-stu-id="34115-102">How to: Position the Child Elements of a Grid</span></span>
<span data-ttu-id="34115-103">In questo esempio viene illustrato come utilizzare il metodo get e i metodi definiti nel set <xref:System.Windows.Controls.Grid> per posizionare gli elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="34115-103">This example shows how to use the get and set methods that are defined on <xref:System.Windows.Controls.Grid> to position child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34115-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="34115-104">Example</span></span>  
 <span data-ttu-id="34115-105">L'esempio seguente definisce un elemento padre <xref:System.Windows.Controls.Grid> elemento (`grid1`) che ha tre colonne e tre righe.</span><span class="sxs-lookup"><span data-stu-id="34115-105">The following example defines a parent <xref:System.Windows.Controls.Grid> element (`grid1`) that has three columns and three rows.</span></span> <span data-ttu-id="34115-106">Un elemento figlio <xref:System.Windows.Shapes.Rectangle> elemento (`rect1`) viene aggiunto al <xref:System.Windows.Controls.Grid> in zero posizione della colonna, riga posizione zero.</span><span class="sxs-lookup"><span data-stu-id="34115-106">A child <xref:System.Windows.Shapes.Rectangle> element (`rect1`) is added to the <xref:System.Windows.Controls.Grid> in column position zero, row position zero.</span></span> <span data-ttu-id="34115-107"><xref:System.Windows.Controls.Button>gli elementi rappresentano i metodi che possono essere chiamati per riposizionare il <xref:System.Windows.Shapes.Rectangle> elemento all'interno di <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="34115-107"><xref:System.Windows.Controls.Button> elements represent methods that can be called to reposition the <xref:System.Windows.Shapes.Rectangle> element within the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="34115-108">Quando un utente fa clic su un pulsante, il metodo correlato è attivato.</span><span class="sxs-lookup"><span data-stu-id="34115-108">When a user clicks a button, the related method is activated.</span></span>  
  
 [!code-xaml[gridGetSetMethods#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="34115-109">Nell'esempio di codice seguente gestisce i metodi che il pulsante <xref:System.Windows.Controls.Primitives.ButtonBase.Click> dagli eventi.</span><span class="sxs-lookup"><span data-stu-id="34115-109">The following code-behind example handles the methods that the button <xref:System.Windows.Controls.Primitives.ButtonBase.Click> events raise.</span></span> <span data-ttu-id="34115-110">L'esempio scrive chiamate ai metodi <xref:System.Windows.Controls.TextBlock> gli elementi correlati utilizzare metodi get per restituire i nuovi valori di proprietà come stringhe.</span><span class="sxs-lookup"><span data-stu-id="34115-110">The example writes these method calls to <xref:System.Windows.Controls.TextBlock> elements that use related get methods to output the new property values as strings.</span></span>  
  
 [!code-csharp[gridGetSetMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[gridGetSetMethods#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gridGetSetMethods/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="34115-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34115-111">See Also</span></span>  
 <xref:System.Windows.Controls.Grid>  
 [<span data-ttu-id="34115-112">Cenni preliminari sugli elementi Panel</span><span class="sxs-lookup"><span data-stu-id="34115-112">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
