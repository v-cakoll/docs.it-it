---
title: 'Procedura: allineare orizzontalmente o verticalmente il contenuto in un elemento StackPanel'
description: Informazioni su come modificare l'orientamento del contenuto in un Windows Presentation Foundation StackPanel e in HorizontalAlignment e VerticalAlignment del contenuto figlio.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- StackPanel control [WPF], content alignment [WPF]
- content alignment [WPF]
- aligning [WPF], content
ms.assetid: c1e8f962-72c8-4e7a-8670-7a2d7e021791
ms.openlocfilehash: d3c7215d8193d1d8a72597c44cf265f5bd400ea1
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167633"
---
# <a name="how-to-horizontally-or-vertically-align-content-in-a-stackpanel"></a><span data-ttu-id="985aa-103">Procedura: allineare orizzontalmente o verticalmente il contenuto in un elemento StackPanel</span><span class="sxs-lookup"><span data-stu-id="985aa-103">How to: Horizontally or Vertically Align Content in a StackPanel</span></span>
<span data-ttu-id="985aa-104">In questo esempio viene illustrato come modificare il <xref:System.Windows.Controls.StackPanel.Orientation%2A> contenuto di un <xref:System.Windows.Controls.StackPanel> elemento e come modificare l'oggetto e il <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> contenuto figlio.</span><span class="sxs-lookup"><span data-stu-id="985aa-104">This example shows how to adjust the <xref:System.Windows.Controls.StackPanel.Orientation%2A> of content within a <xref:System.Windows.Controls.StackPanel> element, and also how to adjust the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> and <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> of child content.</span></span>  
  
## <a name="example"></a><span data-ttu-id="985aa-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="985aa-105">Example</span></span>  
 <span data-ttu-id="985aa-106">Nell'esempio seguente vengono creati tre <xref:System.Windows.Controls.ListBox> elementi in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="985aa-106">The following example creates three <xref:System.Windows.Controls.ListBox> elements in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="985aa-107">Ogni <xref:System.Windows.Controls.ListBox> rappresenta i valori possibili delle <xref:System.Windows.Controls.StackPanel.Orientation%2A> proprietà, <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> e <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> di un oggetto <xref:System.Windows.Controls.StackPanel> .</span><span class="sxs-lookup"><span data-stu-id="985aa-107">Each <xref:System.Windows.Controls.ListBox> represents the possible values of the <xref:System.Windows.Controls.StackPanel.Orientation%2A>, <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, and <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> properties of a <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="985aa-108">Quando un utente seleziona un valore in uno degli <xref:System.Windows.Controls.ListBox> elementi, la proprietà associata di e i <xref:System.Windows.Controls.StackPanel> relativi elementi figlio <xref:System.Windows.Controls.Button> cambiano.</span><span class="sxs-lookup"><span data-stu-id="985aa-108">When a user selects a value in any of the <xref:System.Windows.Controls.ListBox> elements, the associated property of the <xref:System.Windows.Controls.StackPanel> and its child <xref:System.Windows.Controls.Button> elements change.</span></span>  
  
 [!code-xaml[StackPanelIntroSamp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="985aa-109">Il file code-behind seguente definisce le modifiche apportate agli eventi associati alle <xref:System.Windows.Controls.ListBox> modifiche della selezione.</span><span class="sxs-lookup"><span data-stu-id="985aa-109">The following code-behind file defines the changes to the events that are associated with the <xref:System.Windows.Controls.ListBox> selection changes.</span></span> <span data-ttu-id="985aa-110"><xref:System.Windows.Controls.StackPanel>è identificato da <xref:System.Windows.FrameworkElement.Name%2A> `sp1` .</span><span class="sxs-lookup"><span data-stu-id="985aa-110"><xref:System.Windows.Controls.StackPanel> is identified by the <xref:System.Windows.FrameworkElement.Name%2A> `sp1`.</span></span>  
  
 [!code-csharp[StackPanelIntroSamp#2](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml.cs#2)]
 [!code-vb[StackPanelIntroSamp#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelIntroSamp/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="985aa-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="985aa-111">See also</span></span>

- <xref:System.Windows.Controls.StackPanel>
- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>
- <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>
- [<span data-ttu-id="985aa-112">Cenni preliminari sugli elementi Panel</span><span class="sxs-lookup"><span data-stu-id="985aa-112">Panels Overview</span></span>](panels-overview.md)
