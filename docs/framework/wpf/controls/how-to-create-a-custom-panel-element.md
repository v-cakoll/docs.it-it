---
title: 'Procedura: creare un elemento Panel personalizzato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Panel control [WPF]
- custom Panel elements [WPF]
ms.assetid: e0df4f1e-8c07-4e86-89a3-e22acfffdc2a
ms.openlocfilehash: 31edc75114c5dad613e5b65e7d8b051e2c3713af
ms.sourcegitcommit: 9bd1c09128e012b6e34bdcbdf3576379f58f3137
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/23/2019
ms.locfileid: "72799140"
---
# <a name="how-to-create-a-custom-panel-element"></a><span data-ttu-id="370ad-102">Procedura: creare un elemento Panel personalizzato</span><span class="sxs-lookup"><span data-stu-id="370ad-102">How to: Create a Custom Panel Element</span></span>
## <a name="example"></a><span data-ttu-id="370ad-103">Esempio</span><span class="sxs-lookup"><span data-stu-id="370ad-103">Example</span></span>  
 <span data-ttu-id="370ad-104">Questo esempio illustra come eseguire l'override del comportamento di layout predefinito dell'elemento <xref:System.Windows.Controls.Panel> e creare elementi di layout personalizzati derivati da <xref:System.Windows.Controls.Panel>.</span><span class="sxs-lookup"><span data-stu-id="370ad-104">This example shows how to override the default layout behavior of the <xref:System.Windows.Controls.Panel> element and create custom layout elements that are derived from <xref:System.Windows.Controls.Panel>.</span></span>  
  
 <span data-ttu-id="370ad-105">Nell'esempio viene definito un semplice elemento <xref:System.Windows.Controls.Panel> personalizzato denominato `PlotPanel`, che posiziona gli elementi figlio in base a due coordinate x e y hardcoded.</span><span class="sxs-lookup"><span data-stu-id="370ad-105">The example defines a simple custom <xref:System.Windows.Controls.Panel> element called `PlotPanel`, which positions child elements according to two hard-coded x- and y-coordinates.</span></span> <span data-ttu-id="370ad-106">In questo esempio `x` e `y` sono entrambi impostati su `50`; Pertanto, tutti gli elementi figlio vengono posizionati in corrispondenza di tale posizione sugli assi x e y.</span><span class="sxs-lookup"><span data-stu-id="370ad-106">In this example, `x` and `y` are both set to `50`; therefore, all child elements are positioned at that location on the x and y axes.</span></span>  
  
 <span data-ttu-id="370ad-107">Per implementare comportamenti di <xref:System.Windows.Controls.Panel> personalizzati, nell'esempio vengono utilizzati i metodi <xref:System.Windows.FrameworkElement.MeasureOverride%2A> e <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>.</span><span class="sxs-lookup"><span data-stu-id="370ad-107">To implement custom <xref:System.Windows.Controls.Panel> behaviors, the example uses the <xref:System.Windows.FrameworkElement.MeasureOverride%2A> and <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> methods.</span></span> <span data-ttu-id="370ad-108">Ogni metodo restituisce i dati <xref:System.Windows.Size> necessari per posizionare ed eseguire il rendering degli elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="370ad-108">Each method returns the <xref:System.Windows.Size> data that is necessary to position and render child elements.</span></span>  
  
 [!code-cpp[PlotPanel#1](~/samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="370ad-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="370ad-109">See also</span></span>

- <xref:System.Windows.Controls.Panel>
- [<span data-ttu-id="370ad-110">Cenni preliminari sugli elementi Panel</span><span class="sxs-lookup"><span data-stu-id="370ad-110">Panels Overview</span></span>](panels-overview.md)
