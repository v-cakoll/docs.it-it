---
title: "Procedura: eseguire l'associazione a un'enumerazione"
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], enumeration
- data binding [WPF], enumeration
- enumeration [WPF]
ms.assetid: b9091eba-1119-424e-868b-d1a4168b3732
ms.openlocfilehash: 921f15a32eeb5ccb20e879466fcfee3233bbd29e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33554947"
---
# <a name="how-to-bind-to-an-enumeration"></a><span data-ttu-id="bceb9-102">Procedura: eseguire l'associazione a un'enumerazione</span><span class="sxs-lookup"><span data-stu-id="bceb9-102">How to: Bind to an Enumeration</span></span>
<span data-ttu-id="bceb9-103">In questo esempio viene illustrato come associare a un'enumerazione tramite l'associazione al metodo GetValues dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bceb9-103">This example shows how to bind to an enumeration by binding to the enumeration's GetValues method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bceb9-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="bceb9-104">Example</span></span>  
 <span data-ttu-id="bceb9-105">Nell'esempio seguente, il <xref:System.Windows.Controls.ListBox> Visualizza un elenco di <xref:System.Windows.HorizontalAlignment> valori di enumerazione tramite l'associazione dati.</span><span class="sxs-lookup"><span data-stu-id="bceb9-105">In the following example, the <xref:System.Windows.Controls.ListBox> displays the list of <xref:System.Windows.HorizontalAlignment> enumeration values through data binding.</span></span> <span data-ttu-id="bceb9-106">Il <xref:System.Windows.Controls.ListBox> e <xref:System.Windows.Controls.Button> associati in modo che sia possibile modificare il <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> valore della proprietà il <xref:System.Windows.Controls.Button> selezionando un valore nel <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="bceb9-106">The <xref:System.Windows.Controls.ListBox> and the <xref:System.Windows.Controls.Button> are bound such that you can change the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property value of the <xref:System.Windows.Controls.Button> by selecting a value in the <xref:System.Windows.Controls.ListBox>.</span></span>  
  
 [!code-xaml[BindToEnum#BindToEnum](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToEnum/CS/Window1.xaml#bindtoenum)]  
  
## <a name="see-also"></a><span data-ttu-id="bceb9-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bceb9-107">See Also</span></span>  
 [<span data-ttu-id="bceb9-108">Eseguire l'associazione a un metodo</span><span class="sxs-lookup"><span data-stu-id="bceb9-108">Bind to a Method</span></span>](../../../../docs/framework/wpf/data/how-to-bind-to-a-method.md)  
 [<span data-ttu-id="bceb9-109">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="bceb9-109">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="bceb9-110">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="bceb9-110">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
