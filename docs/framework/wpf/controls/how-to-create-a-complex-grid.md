---
title: 'Procedura: creare una griglia complessa'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- calendar [WPF], creating
- monthly calendar [WPF], creating
- Grid control [WPF], creating [WPF], complex grid
ms.assetid: 4ce3040a-a156-4364-9596-98ca1eca5550
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2c0008a7379feefd9b3fe719f85b3205a72fb51d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-complex-grid"></a><span data-ttu-id="369d8-102">Procedura: creare una griglia complessa</span><span class="sxs-lookup"><span data-stu-id="369d8-102">How to: Create a Complex Grid</span></span>
<span data-ttu-id="369d8-103">In questo esempio viene illustrato come utilizzare un <xref:System.Windows.Controls.Grid> per creare layout simile a un calendario mensile.</span><span class="sxs-lookup"><span data-stu-id="369d8-103">This example shows how to use a <xref:System.Windows.Controls.Grid> to create layout that looks like a monthly calendar.</span></span>  
  
## <a name="example"></a><span data-ttu-id="369d8-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="369d8-104">Example</span></span>  
 <span data-ttu-id="369d8-105">Nell'esempio seguente definisce otto righe e otto colonne utilizzando la <xref:System.Windows.Controls.RowDefinition> e <xref:System.Windows.Controls.ColumnDefinition> classi.</span><span class="sxs-lookup"><span data-stu-id="369d8-105">The following example defines eight rows and eight columns by using the <xref:System.Windows.Controls.RowDefinition> and <xref:System.Windows.Controls.ColumnDefinition> classes.</span></span> <span data-ttu-id="369d8-106">Usa il <xref:System.Windows.Controls.Grid.ColumnSpan%2A?displayProperty=nameWithType> e <xref:System.Windows.Controls.Grid.RowSpan%2A?displayProperty=nameWithType> associate, insieme a <xref:System.Windows.Shapes.Rectangle> elementi che riempiono gli sfondi delle varie colonne e righe.</span><span class="sxs-lookup"><span data-stu-id="369d8-106">It uses the <xref:System.Windows.Controls.Grid.ColumnSpan%2A?displayProperty=nameWithType> and <xref:System.Windows.Controls.Grid.RowSpan%2A?displayProperty=nameWithType> attached properties, together with <xref:System.Windows.Shapes.Rectangle> elements, which fill the backgrounds of various columns and rows.</span></span> <span data-ttu-id="369d8-107">Questa progettazione è possibile perché può esistere più di un elemento in ogni cella in un <xref:System.Windows.Controls.Grid>, una differenza principio <xref:System.Windows.Controls.Grid> e <xref:System.Windows.Documents.Table>.</span><span class="sxs-lookup"><span data-stu-id="369d8-107">This design is possible because more than one element can exist in each cell in a <xref:System.Windows.Controls.Grid>, a principle difference between <xref:System.Windows.Controls.Grid> and <xref:System.Windows.Documents.Table>.</span></span>  
  
 <span data-ttu-id="369d8-108">L'esempio Usa sfumature verticali per <xref:System.Windows.Shapes.Shape.Fill%2A> le colonne e righe per migliorare la presentazione visiva e migliorare la leggibilità del calendario.</span><span class="sxs-lookup"><span data-stu-id="369d8-108">The example uses vertical gradients to <xref:System.Windows.Shapes.Shape.Fill%2A> the columns and rows in order to improve the visual presentation and readability of the calendar.</span></span> <span data-ttu-id="369d8-109">Stile <xref:System.Windows.Controls.TextBlock> elementi rappresentano le date e i giorni della settimana.</span><span class="sxs-lookup"><span data-stu-id="369d8-109">Styled <xref:System.Windows.Controls.TextBlock> elements represent the dates and days of the week.</span></span> <span data-ttu-id="369d8-110"><xref:System.Windows.Controls.TextBlock>gli elementi vengono posizionati all'interno delle celle utilizzando il <xref:System.Windows.FrameworkElement.Margin%2A> proprietà e le proprietà di allineamento che sono definite nello stile per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="369d8-110"><xref:System.Windows.Controls.TextBlock> elements are absolutely positioned within their cells by using the <xref:System.Windows.FrameworkElement.Margin%2A> property and alignment properties that are defined within the style for the application.</span></span>  
  
 [!code-xaml[GridComplex#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridComplex/CS/default.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="369d8-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="369d8-111">See Also</span></span>  
 <xref:System.Windows.Controls.Grid>  
 <xref:System.Windows.Documents.TableCell>  
 [<span data-ttu-id="369d8-112">Cenni sul disegno con colori a tinta unita e sfumature</span><span class="sxs-lookup"><span data-stu-id="369d8-112">Painting with Solid Colors and Gradients Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [<span data-ttu-id="369d8-113">Cenni preliminari sugli elementi Panel</span><span class="sxs-lookup"><span data-stu-id="369d8-113">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [<span data-ttu-id="369d8-114">Cenni preliminari sull'elemento Table</span><span class="sxs-lookup"><span data-stu-id="369d8-114">Table Overview</span></span>](../../../../docs/framework/wpf/advanced/table-overview.md)
