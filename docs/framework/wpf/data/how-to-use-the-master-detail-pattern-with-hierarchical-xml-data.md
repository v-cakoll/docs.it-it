---
title: 'Procedura: Utilizzare il modello Master-Details con dati XML gerarchici'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: eb8dbdd8-5871-42bb-a16b-04e655fea677
ms.openlocfilehash: 2b1ed34fe363f44a3a9eb80dc56d721868329717
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57378106"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-xml-data"></a><span data-ttu-id="9d8ac-102">Procedura: Utilizzare il modello Master-Details con dati XML gerarchici</span><span class="sxs-lookup"><span data-stu-id="9d8ac-102">How to: Use the Master-Detail Pattern with Hierarchical XML Data</span></span>
<span data-ttu-id="9d8ac-103">In questo esempio viene illustrato come implementare lo scenario master-Details con [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] dei dati.</span><span class="sxs-lookup"><span data-stu-id="9d8ac-103">This example shows how to implement the master-detail scenario with [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d8ac-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="9d8ac-104">Example</span></span>  
 <span data-ttu-id="9d8ac-105">Questo esempio è il [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] versione di dati di esempio illustrato in [usare il modello Master-Details con dati gerarchici](how-to-use-the-master-detail-pattern-with-hierarchical-data.md).</span><span class="sxs-lookup"><span data-stu-id="9d8ac-105">This example is the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data version of the example discussed in [Use the Master-Detail Pattern with Hierarchical Data](how-to-use-the-master-detail-pattern-with-hierarchical-data.md).</span></span> <span data-ttu-id="9d8ac-106">In questo esempio, i dati sono nel file `League.xml`.</span><span class="sxs-lookup"><span data-stu-id="9d8ac-106">In this example, the data is from the file `League.xml`.</span></span> <span data-ttu-id="9d8ac-107">Si noti come la terza <xref:System.Windows.Controls.ListBox> controllo tiene traccia delle modifiche di selezione nella seconda <xref:System.Windows.Controls.ListBox> tramite l'associazione alla relativo <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="9d8ac-107">Note how the third <xref:System.Windows.Controls.ListBox> control tracks selection changes in the second <xref:System.Windows.Controls.ListBox> by binding to its <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> property.</span></span>  
  
 [!code-xaml[MasterDetailXml#HowTo1](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto1)]  
[!code-xaml[MasterDetailXml#HowTo2](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto2)]  
  
## <a name="see-also"></a><span data-ttu-id="9d8ac-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d8ac-108">See also</span></span>
- <xref:System.Windows.HierarchicalDataTemplate>
- [<span data-ttu-id="9d8ac-109">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="9d8ac-109">How-to Topics</span></span>](data-binding-how-to-topics.md)
