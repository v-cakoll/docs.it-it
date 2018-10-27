---
title: 'Procedura: creare un elemento Grid'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], creating [WPF], grid instance
ms.assetid: b2f07626-9df8-43b8-8d36-492f3cb42837
ms.openlocfilehash: b93bb859c4a0df50da2fa00587a28fda3776fd09
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50185784"
---
# <a name="how-to-create-a-grid-element"></a><span data-ttu-id="e2569-102">Procedura: creare un elemento Grid</span><span class="sxs-lookup"><span data-stu-id="e2569-102">How to: Create a Grid Element</span></span>
## <a name="example"></a><span data-ttu-id="e2569-103">Esempio</span><span class="sxs-lookup"><span data-stu-id="e2569-103">Example</span></span>  
 <span data-ttu-id="e2569-104">Nell'esempio seguente viene illustrato come creare e usare un'istanza di <xref:System.Windows.Controls.Grid> utilizzando [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] o code.</span><span class="sxs-lookup"><span data-stu-id="e2569-104">The following example shows how to create and use an instance of <xref:System.Windows.Controls.Grid> by using either [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] or code.</span></span> <span data-ttu-id="e2569-105">In questo esempio Usa tre <xref:System.Windows.Controls.ColumnDefinition> gli oggetti e tre <xref:System.Windows.Controls.RowDefinition> oggetti per creare una griglia che ha nove celle, ad esempio in un foglio di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e2569-105">This example uses three <xref:System.Windows.Controls.ColumnDefinition> objects and three <xref:System.Windows.Controls.RowDefinition> objects to create a grid that has nine cells, such as in a worksheet.</span></span> <span data-ttu-id="e2569-106">Ogni cella contiene un <xref:System.Windows.Controls.TextBlock> l'elemento che rappresenta i dati e la riga superiore contiene una <xref:System.Windows.Controls.TextBlock> con il <xref:System.Windows.Controls.Grid.ColumnSpan%2A> proprietà applicato.</span><span class="sxs-lookup"><span data-stu-id="e2569-106">Each cell contains a <xref:System.Windows.Controls.TextBlock> element that represents data, and the top row contains a <xref:System.Windows.Controls.TextBlock> with the <xref:System.Windows.Controls.Grid.ColumnSpan%2A> property applied.</span></span> <span data-ttu-id="e2569-107">Per visualizzare i limiti di ogni cella, il <xref:System.Windows.Controls.Grid.ShowGridLines%2A> proprietà è abilitata.</span><span class="sxs-lookup"><span data-stu-id="e2569-107">To show the boundaries of each cell, the <xref:System.Windows.Controls.Grid.ShowGridLines%2A> property is enabled.</span></span>  
  
 [!code-csharp[Grid#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Grid/CSharp/Grid_Code.cs#3)]
 [!code-vb[Grid#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Grid/VisualBasic/grid_vb.vb#3)]
 [!code-xaml[Grid#3](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Grid/XAML/default.xaml#3)]  
  
  <span data-ttu-id="e2569-108">Entrambi gli approcci genererà un'interfaccia utente che risulta molto lo stesso, come quello riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="e2569-108">Either approach will generate a user interface that looks much the same, like the one below.</span></span>

  ![una schermata illustra un'interfaccia utente WPF che contiene una griglia suddivisa in tre colonne.](./media/how-to-create-a-grid-element/how-to-create-a-grid-element.png)
## <a name="see-also"></a><span data-ttu-id="e2569-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2569-112">See Also</span></span>  
 <xref:System.Windows.Controls.Grid>  
 [<span data-ttu-id="e2569-113">Cenni preliminari sugli elementi Panel</span><span class="sxs-lookup"><span data-stu-id="e2569-113">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
