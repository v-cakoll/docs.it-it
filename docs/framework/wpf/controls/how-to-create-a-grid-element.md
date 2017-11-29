---
title: 'Procedura: creare un elemento Grid'
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
helpviewer_keywords: Grid control [WPF], creating [WPF], grid instance
ms.assetid: b2f07626-9df8-43b8-8d36-492f3cb42837
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bd9614aee6e2bf7085b2fbee77993217439320a5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-grid-element"></a><span data-ttu-id="70f84-102">Procedura: creare un elemento Grid</span><span class="sxs-lookup"><span data-stu-id="70f84-102">How to: Create a Grid Element</span></span>
## <a name="example"></a><span data-ttu-id="70f84-103">Esempio</span><span class="sxs-lookup"><span data-stu-id="70f84-103">Example</span></span>  
 <span data-ttu-id="70f84-104">Nell'esempio seguente viene illustrato come creare e utilizzare un'istanza di <xref:System.Windows.Controls.Grid> utilizzando [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] o codice.</span><span class="sxs-lookup"><span data-stu-id="70f84-104">The following example shows how to create and use an instance of <xref:System.Windows.Controls.Grid> by using either [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] or code.</span></span> <span data-ttu-id="70f84-105">In questo esempio vengono utilizzati tre <xref:System.Windows.Controls.ColumnDefinition> oggetti e tre <xref:System.Windows.Controls.RowDefinition> oggetti per creare una griglia che ha nove celle, ad esempio in un foglio di lavoro.</span><span class="sxs-lookup"><span data-stu-id="70f84-105">This example uses three <xref:System.Windows.Controls.ColumnDefinition> objects and three <xref:System.Windows.Controls.RowDefinition> objects to create a grid that has nine cells, such as in a worksheet.</span></span> <span data-ttu-id="70f84-106">Ogni cella contiene un <xref:System.Windows.Controls.TextBlock> elemento che rappresenta i dati e la riga superiore contiene una <xref:System.Windows.Controls.TextBlock> con il <xref:System.Windows.Controls.Grid.ColumnSpan%2A> proprietà applicato.</span><span class="sxs-lookup"><span data-stu-id="70f84-106">Each cell contains a <xref:System.Windows.Controls.TextBlock> element that represents data, and the top row contains a <xref:System.Windows.Controls.TextBlock> with the <xref:System.Windows.Controls.Grid.ColumnSpan%2A> property applied.</span></span> <span data-ttu-id="70f84-107">Per visualizzare i limiti di ogni cella, il <xref:System.Windows.Controls.Grid.ShowGridLines%2A> proprietà è abilitata.</span><span class="sxs-lookup"><span data-stu-id="70f84-107">To show the boundaries of each cell, the <xref:System.Windows.Controls.Grid.ShowGridLines%2A> property is enabled.</span></span>  
  
 [!code-csharp[Grid#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Grid/CSharp/Grid_Code.cs#3)]
 [!code-vb[Grid#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Grid/VisualBasic/grid_vb.vb#3)]
 [!code-xaml[Grid#3](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Grid/XAML/default.xaml#3)]  
  
## <a name="see-also"></a><span data-ttu-id="70f84-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="70f84-108">See Also</span></span>  
 <xref:System.Windows.Controls.Grid>  
 [<span data-ttu-id="70f84-109">Cenni preliminari sugli elementi Panel</span><span class="sxs-lookup"><span data-stu-id="70f84-109">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
