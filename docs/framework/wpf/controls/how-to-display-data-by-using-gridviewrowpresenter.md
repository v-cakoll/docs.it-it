---
title: 'Procedura: Visualizzare i dati usando GridViewRowPresenter'
ms.date: 03/30/2017
helpviewer_keywords:
- displaying data with GridViewRowPresenter [WPF]
- GridViewRowPresenter [WPF]
ms.assetid: bdb785a5-a262-44d5-a517-ea14383e5f70
ms.openlocfilehash: 0e471df3ab6fd10417fc58ece4cdb8ff1c457c95
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59149149"
---
# <a name="how-to-display-data-by-using-gridviewrowpresenter"></a><span data-ttu-id="a6f3e-102">Procedura: Visualizzare i dati usando GridViewRowPresenter</span><span class="sxs-lookup"><span data-stu-id="a6f3e-102">How to: Display Data by Using GridViewRowPresenter</span></span>
<span data-ttu-id="a6f3e-103">Questo esempio illustra come usare il <xref:System.Windows.Controls.GridViewRowPresenter> e <xref:System.Windows.Controls.GridViewHeaderRowPresenter> oggetti per visualizzare i dati nelle colonne.</span><span class="sxs-lookup"><span data-stu-id="a6f3e-103">This example shows how to use the <xref:System.Windows.Controls.GridViewRowPresenter> and <xref:System.Windows.Controls.GridViewHeaderRowPresenter> objects to display data in columns.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6f3e-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="a6f3e-104">Example</span></span>  
 <span data-ttu-id="a6f3e-105">Nell'esempio seguente viene illustrato come specificare una <xref:System.Windows.Controls.GridViewColumnCollection> che consente di visualizzare il <xref:System.DateTime.DayOfWeek%2A> e <xref:System.DateTime.Year%2A> di un <xref:System.DateTime> utilizzando <xref:System.Windows.Controls.GridViewRowPresenter> e <xref:System.Windows.Controls.GridViewHeaderRowPresenter> oggetti.</span><span class="sxs-lookup"><span data-stu-id="a6f3e-105">The following example shows how to specify a <xref:System.Windows.Controls.GridViewColumnCollection> that displays the <xref:System.DateTime.DayOfWeek%2A> and <xref:System.DateTime.Year%2A> of a <xref:System.DateTime> object by using <xref:System.Windows.Controls.GridViewRowPresenter> and <xref:System.Windows.Controls.GridViewHeaderRowPresenter> objects.</span></span> <span data-ttu-id="a6f3e-106">L'esempio definisce anche un <xref:System.Windows.Style> per il <xref:System.Windows.Controls.GridViewColumn.Header%2A> di un <xref:System.Windows.Controls.GridViewColumn>.</span><span class="sxs-lookup"><span data-stu-id="a6f3e-106">The example also defines a <xref:System.Windows.Style> for the <xref:System.Windows.Controls.GridViewColumn.Header%2A> of a <xref:System.Windows.Controls.GridViewColumn>.</span></span>  
  
 [!code-xaml[GridViewRowPresenterSample#GridViewRowPresenter](~/samples/snippets/csharp/VS_Snippets_Wpf/GridViewRowPresenterSample/CS/Window1.xaml#gridviewrowpresenter)]  
  
## <a name="see-also"></a><span data-ttu-id="a6f3e-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6f3e-107">See also</span></span>

- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>
- <xref:System.Windows.Controls.GridViewRowPresenter>
- <xref:System.Windows.Controls.GridViewColumnCollection>
- [<span data-ttu-id="a6f3e-108">Cenni preliminari su GridView</span><span class="sxs-lookup"><span data-stu-id="a6f3e-108">GridView Overview</span></span>](gridview-overview.md)
