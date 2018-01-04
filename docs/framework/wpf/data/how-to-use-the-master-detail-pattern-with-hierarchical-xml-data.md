---
title: 'Procedura: utilizzare il modello Master-Details con dati XML gerarchici'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: eb8dbdd8-5871-42bb-a16b-04e655fea677
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f0ef460664b3701f4942b8c28b8e39f891d7c871
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-xml-data"></a><span data-ttu-id="ba85f-102">Procedura: utilizzare il modello Master-Details con dati XML gerarchici</span><span class="sxs-lookup"><span data-stu-id="ba85f-102">How to: Use the Master-Detail Pattern with Hierarchical XML Data</span></span>
<span data-ttu-id="ba85f-103">In questo esempio viene illustrato come implementare lo scenario master-Details con [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] dati.</span><span class="sxs-lookup"><span data-stu-id="ba85f-103">This example shows how to implement the master-detail scenario with [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba85f-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="ba85f-104">Example</span></span>  
 <span data-ttu-id="ba85f-105">Questo esempio si trova il [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] versione dei dati di esempio illustrato in [utilizzare il modello Master-Details con dati gerarchici](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md).</span><span class="sxs-lookup"><span data-stu-id="ba85f-105">This example is the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data version of the example discussed in [Use the Master-Detail Pattern with Hierarchical Data](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md).</span></span> <span data-ttu-id="ba85f-106">In questo esempio, i dati provengono da file `League.xml`.</span><span class="sxs-lookup"><span data-stu-id="ba85f-106">In this example, the data is from the file `League.xml`.</span></span> <span data-ttu-id="ba85f-107">Si noti come il terzo <xref:System.Windows.Controls.ListBox> controllo tiene traccia delle modifiche di selezione del secondo <xref:System.Windows.Controls.ListBox> tramite l'associazione alla relativa <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="ba85f-107">Note how the third <xref:System.Windows.Controls.ListBox> control tracks selection changes in the second <xref:System.Windows.Controls.ListBox> by binding to its <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> property.</span></span>  
  
 [!code-xaml[MasterDetailXml#HowTo1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto1)]  
[!code-xaml[MasterDetailXml#HowTo2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto2)]  
  
## <a name="see-also"></a><span data-ttu-id="ba85f-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ba85f-108">See Also</span></span>  
 <xref:System.Windows.HierarchicalDataTemplate>  
 [<span data-ttu-id="ba85f-109">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="ba85f-109">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
