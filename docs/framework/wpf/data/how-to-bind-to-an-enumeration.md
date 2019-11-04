---
title: "Procedura: eseguire l'associazione a un'enumerazione"
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], enumeration
- data binding [WPF], enumeration
- enumeration [WPF]
ms.assetid: b9091eba-1119-424e-868b-d1a4168b3732
ms.openlocfilehash: 93f33e497fd7acb81c55f86bf38737d4e7d79bf2
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73454447"
---
# <a name="how-to-bind-to-an-enumeration"></a><span data-ttu-id="ee9c2-102">Procedura: eseguire l'associazione a un'enumerazione</span><span class="sxs-lookup"><span data-stu-id="ee9c2-102">How to: Bind to an Enumeration</span></span>
<span data-ttu-id="ee9c2-103">In questo esempio viene illustrato come eseguire l'associazione a un'enumerazione mediante l'associazione al metodo GetValues dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="ee9c2-103">This example shows how to bind to an enumeration by binding to the enumeration's GetValues method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee9c2-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="ee9c2-104">Example</span></span>  
 <span data-ttu-id="ee9c2-105">Nell'esempio seguente, il <xref:System.Windows.Controls.ListBox> Visualizza l'elenco dei valori di enumerazione <xref:System.Windows.HorizontalAlignment> tramite data binding.</span><span class="sxs-lookup"><span data-stu-id="ee9c2-105">In the following example, the <xref:System.Windows.Controls.ListBox> displays the list of <xref:System.Windows.HorizontalAlignment> enumeration values through data binding.</span></span> <span data-ttu-id="ee9c2-106">Il <xref:System.Windows.Controls.ListBox> e il <xref:System.Windows.Controls.Button> sono associati in modo che sia possibile modificare il valore della proprietà <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> della <xref:System.Windows.Controls.Button> selezionando un valore nella <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="ee9c2-106">The <xref:System.Windows.Controls.ListBox> and the <xref:System.Windows.Controls.Button> are bound such that you can change the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property value of the <xref:System.Windows.Controls.Button> by selecting a value in the <xref:System.Windows.Controls.ListBox>.</span></span>  
  
 [!code-xaml[BindToEnum#BindToEnum](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToEnum/CS/Window1.xaml#bindtoenum)]  
  
## <a name="see-also"></a><span data-ttu-id="ee9c2-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee9c2-107">See also</span></span>

- [<span data-ttu-id="ee9c2-108">Eseguire l'associazione a un metodo</span><span class="sxs-lookup"><span data-stu-id="ee9c2-108">Bind to a Method</span></span>](how-to-bind-to-a-method.md)
- [<span data-ttu-id="ee9c2-109">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="ee9c2-109">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="ee9c2-110">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="ee9c2-110">How-to Topics</span></span>](data-binding-how-to-topics.md)
