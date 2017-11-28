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
ms.openlocfilehash: 31fb9adbda47514e5405d465c0b5e2493b966d8c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-to-an-enumeration"></a><span data-ttu-id="cc6b6-102">Procedura: eseguire l'associazione a un'enumerazione</span><span class="sxs-lookup"><span data-stu-id="cc6b6-102">How to: Bind to an Enumeration</span></span>
<span data-ttu-id="cc6b6-103">In questo esempio viene illustrato come associare a un'enumerazione tramite l'associazione al metodo GetValues dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="cc6b6-103">This example shows how to bind to an enumeration by binding to the enumeration's GetValues method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc6b6-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="cc6b6-104">Example</span></span>  
 <span data-ttu-id="cc6b6-105">Nell'esempio seguente, il <xref:System.Windows.Controls.ListBox> Visualizza un elenco di <xref:System.Windows.HorizontalAlignment> valori di enumerazione tramite l'associazione dati.</span><span class="sxs-lookup"><span data-stu-id="cc6b6-105">In the following example, the <xref:System.Windows.Controls.ListBox> displays the list of <xref:System.Windows.HorizontalAlignment> enumeration values through data binding.</span></span> <span data-ttu-id="cc6b6-106">Il <xref:System.Windows.Controls.ListBox> e <xref:System.Windows.Controls.Button> associati in modo che sia possibile modificare il <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> valore della proprietà il <xref:System.Windows.Controls.Button> selezionando un valore nel <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="cc6b6-106">The <xref:System.Windows.Controls.ListBox> and the <xref:System.Windows.Controls.Button> are bound such that you can change the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property value of the <xref:System.Windows.Controls.Button> by selecting a value in the <xref:System.Windows.Controls.ListBox>.</span></span>  
  
 [!code-xaml[BindToEnum#BindToEnum](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToEnum/CS/Window1.xaml#bindtoenum)]  
  
## <a name="see-also"></a><span data-ttu-id="cc6b6-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc6b6-107">See Also</span></span>  
 [<span data-ttu-id="cc6b6-108">Eseguire l'associazione a un metodo</span><span class="sxs-lookup"><span data-stu-id="cc6b6-108">Bind to a Method</span></span>](../../../../docs/framework/wpf/data/how-to-bind-to-a-method.md)  
 [<span data-ttu-id="cc6b6-109">Cenni preliminari sull'associazione dati</span><span class="sxs-lookup"><span data-stu-id="cc6b6-109">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="cc6b6-110">Procedure relative</span><span class="sxs-lookup"><span data-stu-id="cc6b6-110">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
