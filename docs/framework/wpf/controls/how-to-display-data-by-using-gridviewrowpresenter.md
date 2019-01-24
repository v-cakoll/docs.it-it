---
title: 'Procedura: Visualizzare i dati utilizzando GridViewRowPresenter'
ms.date: 03/30/2017
helpviewer_keywords:
- displaying data with GridViewRowPresenter [WPF]
- GridViewRowPresenter [WPF]
ms.assetid: bdb785a5-a262-44d5-a517-ea14383e5f70
ms.openlocfilehash: b60fe0e78883b166688377c42113a093c78d7751
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54607959"
---
# <a name="how-to-display-data-by-using-gridviewrowpresenter"></a>Procedura: Visualizzare i dati utilizzando GridViewRowPresenter
Questo esempio illustra come usare il <xref:System.Windows.Controls.GridViewRowPresenter> e <xref:System.Windows.Controls.GridViewHeaderRowPresenter> oggetti per visualizzare i dati nelle colonne.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come specificare una <xref:System.Windows.Controls.GridViewColumnCollection> che consente di visualizzare il <xref:System.DateTime.DayOfWeek%2A> e <xref:System.DateTime.Year%2A> di un <xref:System.DateTime> utilizzando <xref:System.Windows.Controls.GridViewRowPresenter> e <xref:System.Windows.Controls.GridViewHeaderRowPresenter> oggetti. L'esempio definisce anche un <xref:System.Windows.Style> per il <xref:System.Windows.Controls.GridViewColumn.Header%2A> di un <xref:System.Windows.Controls.GridViewColumn>.  
  
 [!code-xaml[GridViewRowPresenterSample#GridViewRowPresenter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewRowPresenterSample/CS/Window1.xaml#gridviewrowpresenter)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>
- <xref:System.Windows.Controls.GridViewRowPresenter>
- <xref:System.Windows.Controls.GridViewColumnCollection>
- [Cenni preliminari su GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)
