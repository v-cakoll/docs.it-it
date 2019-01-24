---
title: 'Procedura: Creare un elemento Panel personalizzato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Panel control [WPF]
- custom Panel elements [WPF]
ms.assetid: e0df4f1e-8c07-4e86-89a3-e22acfffdc2a
ms.openlocfilehash: 93d9ebacda8c753ab5a4446999e1aa86828a2b9e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54621932"
---
# <a name="how-to-create-a-custom-panel-element"></a><span data-ttu-id="7bf97-102">Procedura: Creare un elemento Panel personalizzato</span><span class="sxs-lookup"><span data-stu-id="7bf97-102">How to: Create a Custom Panel Element</span></span>
## <a name="example"></a><span data-ttu-id="7bf97-103">Esempio</span><span class="sxs-lookup"><span data-stu-id="7bf97-103">Example</span></span>  
 <span data-ttu-id="7bf97-104">Questo esempio illustra come eseguire l'override del comportamento di layout predefinito del <xref:System.Windows.Controls.Panel> elemento e creare elementi di layout personalizzati che derivano dalla <xref:System.Windows.Controls.Panel>.</span><span class="sxs-lookup"><span data-stu-id="7bf97-104">This example shows how to override the default layout behavior of the <xref:System.Windows.Controls.Panel> element and create custom layout elements that are derived from <xref:System.Windows.Controls.Panel>.</span></span>  
  
 <span data-ttu-id="7bf97-105">L'esempio definisce un oggetto personalizzato semplice <xref:System.Windows.Controls.Panel> elemento denominato `PlotPanel`, che posiziona gli elementi figlio in base a due hardcoded coordinate x e y-.</span><span class="sxs-lookup"><span data-stu-id="7bf97-105">The example defines a simple custom <xref:System.Windows.Controls.Panel> element called `PlotPanel`, which positions child elements according to two hard-coded x- and y-coordinates.</span></span> <span data-ttu-id="7bf97-106">In questo esempio `x` e `y` sono entrambe impostate su `50`; pertanto, tutti gli elementi figlio vengono posizionati nel percorso specificato su x e y assi.</span><span class="sxs-lookup"><span data-stu-id="7bf97-106">In this example, `x` and `y` are both set to `50`; therefore, all child elements are positioned at that location on the x and y axes.</span></span>  
  
 <span data-ttu-id="7bf97-107">Per implementare custom <xref:System.Windows.Controls.Panel> comportamenti predefiniti, nell'esempio viene usato il <xref:System.Windows.FrameworkElement.MeasureOverride%2A> e <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> metodi.</span><span class="sxs-lookup"><span data-stu-id="7bf97-107">To implement custom <xref:System.Windows.Controls.Panel> behaviors, the example uses the <xref:System.Windows.FrameworkElement.MeasureOverride%2A> and <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> methods.</span></span> <span data-ttu-id="7bf97-108">Ogni metodo restituisce il <xref:System.Windows.Size> i dati necessari per posizionare e il rendering degli elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="7bf97-108">Each method returns the <xref:System.Windows.Size> data that is necessary to position and render child elements.</span></span>  
  
 [!code-cpp[PlotPanel#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="7bf97-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7bf97-109">See also</span></span>
- <xref:System.Windows.Controls.Panel>
- [<span data-ttu-id="7bf97-110">Cenni preliminari sugli elementi Panel</span><span class="sxs-lookup"><span data-stu-id="7bf97-110">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
- [<span data-ttu-id="7bf97-111">Creare un contenuto-Wrapping Panel Sample personalizzato</span><span class="sxs-lookup"><span data-stu-id="7bf97-111">Create a Custom Content-Wrapping Panel Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159979)
