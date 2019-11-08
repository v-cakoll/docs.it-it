---
title: 'Procedura: utilizzare il modello Master-Details con dati XML gerarchici'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: eb8dbdd8-5871-42bb-a16b-04e655fea677
ms.openlocfilehash: 0fe42d57fcaf4acee09340fdb3f5df73d7291566
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73733420"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-xml-data"></a><span data-ttu-id="17b60-102">Procedura: utilizzare il modello Master-Details con dati XML gerarchici</span><span class="sxs-lookup"><span data-stu-id="17b60-102">How to: Use the Master-Detail Pattern with Hierarchical XML Data</span></span>
<span data-ttu-id="17b60-103">In questo esempio viene illustrato come implementare lo scenario Master-Details con i dati XML.</span><span class="sxs-lookup"><span data-stu-id="17b60-103">This example shows how to implement the master-detail scenario with XML data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17b60-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="17b60-104">Example</span></span>  
 <span data-ttu-id="17b60-105">Questo esempio è la versione dei dati XML dell'esempio illustrato in [usare il modello Master-Details con dati gerarchici](how-to-use-the-master-detail-pattern-with-hierarchical-data.md).</span><span class="sxs-lookup"><span data-stu-id="17b60-105">This example is the XML data version of the example discussed in [Use the Master-Detail Pattern with Hierarchical Data](how-to-use-the-master-detail-pattern-with-hierarchical-data.md).</span></span> <span data-ttu-id="17b60-106">In questo esempio, i dati sono dal file `League.xml`.</span><span class="sxs-lookup"><span data-stu-id="17b60-106">In this example, the data is from the file `League.xml`.</span></span> <span data-ttu-id="17b60-107">Si noti come il terzo controllo <xref:System.Windows.Controls.ListBox> tiene traccia delle modifiche apportate alla selezione nel secondo <xref:System.Windows.Controls.ListBox> mediante l'associazione alla relativa proprietà <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="17b60-107">Note how the third <xref:System.Windows.Controls.ListBox> control tracks selection changes in the second <xref:System.Windows.Controls.ListBox> by binding to its <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> property.</span></span>  
  
 [!code-xaml[MasterDetailXml#HowTo1](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto1)]  
[!code-xaml[MasterDetailXml#HowTo2](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto2)]  
  
## <a name="see-also"></a><span data-ttu-id="17b60-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17b60-108">See also</span></span>

- <xref:System.Windows.HierarchicalDataTemplate>
- [<span data-ttu-id="17b60-109">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="17b60-109">How-to Topics</span></span>](data-binding-how-to-topics.md)
