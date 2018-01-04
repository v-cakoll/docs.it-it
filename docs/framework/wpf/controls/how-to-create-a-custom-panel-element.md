---
title: 'Procedura: creare un elemento Panel personalizzato'
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
- cpp
helpviewer_keywords:
- Panel control [WPF]
- custom Panel elements [WPF]
ms.assetid: e0df4f1e-8c07-4e86-89a3-e22acfffdc2a
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5eacc5435e259c20c25b64d6e82c33d07338602a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-custom-panel-element"></a><span data-ttu-id="4b55d-102">Procedura: creare un elemento Panel personalizzato</span><span class="sxs-lookup"><span data-stu-id="4b55d-102">How to: Create a Custom Panel Element</span></span>
## <a name="example"></a><span data-ttu-id="4b55d-103">Esempio</span><span class="sxs-lookup"><span data-stu-id="4b55d-103">Example</span></span>  
 <span data-ttu-id="4b55d-104">Questo esempio viene illustrato come eseguire l'override di comportamento di layout predefinito di <xref:System.Windows.Controls.Panel> elemento e creare elementi di layout personalizzati che derivano da <xref:System.Windows.Controls.Panel>.</span><span class="sxs-lookup"><span data-stu-id="4b55d-104">This example shows how to override the default layout behavior of the <xref:System.Windows.Controls.Panel> element and create custom layout elements that are derived from <xref:System.Windows.Controls.Panel>.</span></span>  
  
 <span data-ttu-id="4b55d-105">L'esempio definisce un oggetto personalizzato semplice <xref:System.Windows.Controls.Panel> elemento denominato `PlotPanel`, che gli elementi figlio posizionati in base alle due hardcoded coordinate x e y-.</span><span class="sxs-lookup"><span data-stu-id="4b55d-105">The example defines a simple custom <xref:System.Windows.Controls.Panel> element called `PlotPanel`, which positions child elements according to two hard-coded x- and y-coordinates.</span></span> <span data-ttu-id="4b55d-106">In questo esempio, `x` e `y` sono impostati entrambi su `50`; pertanto, tutti gli elementi figlio sono posizionati in tale posizione su x e y assi.</span><span class="sxs-lookup"><span data-stu-id="4b55d-106">In this example, `x` and `y` are both set to `50`; therefore, all child elements are positioned at that location on the x and y axes.</span></span>  
  
 <span data-ttu-id="4b55d-107">Per implementare personalizzato <xref:System.Windows.Controls.Panel> comportamenti, nell'esempio viene utilizzato il <xref:System.Windows.FrameworkElement.MeasureOverride%2A> e <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> metodi.</span><span class="sxs-lookup"><span data-stu-id="4b55d-107">To implement custom <xref:System.Windows.Controls.Panel> behaviors, the example uses the <xref:System.Windows.FrameworkElement.MeasureOverride%2A> and <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> methods.</span></span> <span data-ttu-id="4b55d-108">Ogni metodo restituisce il <xref:System.Windows.Size> dati necessari per il posizionamento e il rendering degli elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="4b55d-108">Each method returns the <xref:System.Windows.Size> data that is necessary to position and render child elements.</span></span>  
  
 [!code-cpp[PlotPanel#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="4b55d-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4b55d-109">See Also</span></span>  
 <xref:System.Windows.Controls.Panel>  
 [<span data-ttu-id="4b55d-110">Cenni preliminari sugli elementi Panel</span><span class="sxs-lookup"><span data-stu-id="4b55d-110">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [<span data-ttu-id="4b55d-111">Creare un esempio di pannello personalizzato di disposizione del contenuto</span><span class="sxs-lookup"><span data-stu-id="4b55d-111">Create a Custom Content-Wrapping Panel Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=159979)
