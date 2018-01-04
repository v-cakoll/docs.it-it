---
title: 'Procedura: eseguire l''associazione a un''enumerazione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- binding data [WPF], enumeration
- data binding [WPF], enumeration
- enumeration [WPF]
ms.assetid: b9091eba-1119-424e-868b-d1a4168b3732
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 72439cdc1c1017378a5b6b3f6b4bf41a9eee2537
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-to-an-enumeration"></a><span data-ttu-id="79a52-102">Procedura: eseguire l'associazione a un'enumerazione</span><span class="sxs-lookup"><span data-stu-id="79a52-102">How to: Bind to an Enumeration</span></span>
<span data-ttu-id="79a52-103">In questo esempio viene illustrato come associare a un'enumerazione tramite l'associazione al metodo GetValues dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="79a52-103">This example shows how to bind to an enumeration by binding to the enumeration's GetValues method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79a52-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="79a52-104">Example</span></span>  
 <span data-ttu-id="79a52-105">Nell'esempio seguente, il <xref:System.Windows.Controls.ListBox> Visualizza un elenco di <xref:System.Windows.HorizontalAlignment> valori di enumerazione tramite l'associazione dati.</span><span class="sxs-lookup"><span data-stu-id="79a52-105">In the following example, the <xref:System.Windows.Controls.ListBox> displays the list of <xref:System.Windows.HorizontalAlignment> enumeration values through data binding.</span></span> <span data-ttu-id="79a52-106">Il <xref:System.Windows.Controls.ListBox> e <xref:System.Windows.Controls.Button> associati in modo che sia possibile modificare il <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> valore della proprietà il <xref:System.Windows.Controls.Button> selezionando un valore nel <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="79a52-106">The <xref:System.Windows.Controls.ListBox> and the <xref:System.Windows.Controls.Button> are bound such that you can change the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property value of the <xref:System.Windows.Controls.Button> by selecting a value in the <xref:System.Windows.Controls.ListBox>.</span></span>  
  
 [!code-xaml[BindToEnum#BindToEnum](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToEnum/CS/Window1.xaml#bindtoenum)]  
  
## <a name="see-also"></a><span data-ttu-id="79a52-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79a52-107">See Also</span></span>  
 [<span data-ttu-id="79a52-108">Eseguire l'associazione a un metodo</span><span class="sxs-lookup"><span data-stu-id="79a52-108">Bind to a Method</span></span>](../../../../docs/framework/wpf/data/how-to-bind-to-a-method.md)  
 [<span data-ttu-id="79a52-109">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="79a52-109">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="79a52-110">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="79a52-110">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
