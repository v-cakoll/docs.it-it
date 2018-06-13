---
title: 'Procedura: visualizzare il contenuto di ListView utilizzando un oggetto GridView'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], displaying contents with GridView
- GridView [WPF], displaying ListView contents
ms.assetid: 5bc1e767-ab46-4f14-bd41-3d5d39e1d000
ms.openlocfilehash: 103a439b9cee959d0077e5a759364eb9b943905d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33554051"
---
# <a name="how-to-display-listview-contents-by-using-a-gridview"></a><span data-ttu-id="80613-102">Procedura: visualizzare il contenuto di ListView utilizzando un oggetto GridView</span><span class="sxs-lookup"><span data-stu-id="80613-102">How to: Display ListView Contents by Using a GridView</span></span>
<span data-ttu-id="80613-103">In questo esempio viene illustrato come definire un <xref:System.Windows.Controls.GridView> modalità di visualizzazione per un <xref:System.Windows.Controls.ListView> controllo.</span><span class="sxs-lookup"><span data-stu-id="80613-103">This example shows how to define a <xref:System.Windows.Controls.GridView> view mode for a <xref:System.Windows.Controls.ListView> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="80613-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="80613-104">Example</span></span>  
 <span data-ttu-id="80613-105">È possibile definire la modalità di visualizzazione di un <xref:System.Windows.Controls.GridView> specificando <xref:System.Windows.Controls.GridViewColumn> oggetti.</span><span class="sxs-lookup"><span data-stu-id="80613-105">You can define the view mode of a <xref:System.Windows.Controls.GridView> by specifying <xref:System.Windows.Controls.GridViewColumn> objects.</span></span> <span data-ttu-id="80613-106">Nell'esempio seguente viene illustrato come definire <xref:System.Windows.Controls.GridViewColumn> gli oggetti associati per il contenuto dei dati specificato per il <xref:System.Windows.Controls.ListView> controllo.</span><span class="sxs-lookup"><span data-stu-id="80613-106">The following example shows how to define <xref:System.Windows.Controls.GridViewColumn> objects that bind to the data content that is specified for the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="80613-107">Questo <xref:System.Windows.Controls.GridView> esempio specifica tre <xref:System.Windows.Controls.GridViewColumn> gli oggetti che eseguono il mapping per il `FirstName`, `LastName`, e `EmployeeNumber` campi del `EmployeeInfoDataSource` che viene impostato come il <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> del <xref:System.Windows.Controls.ListView> controllo.</span><span class="sxs-lookup"><span data-stu-id="80613-107">This <xref:System.Windows.Controls.GridView> example specifies three <xref:System.Windows.Controls.GridViewColumn> objects that map to the `FirstName`, `LastName`, and `EmployeeNumber` fields of the `EmployeeInfoDataSource` that is set as the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> of the <xref:System.Windows.Controls.ListView> control.</span></span>  
  
 [!code-xaml[ListViewCode#ListViewEmployee](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 <span data-ttu-id="80613-108">Nella figura seguente mostra come viene visualizzata in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="80613-108">The following illustration shows how this example appears.</span></span>  
  
 <span data-ttu-id="80613-109">![ListView con output GridView ](../../../../docs/framework/wpf/controls/media/listviewgridview.JPG "ListViewGridView")</span><span class="sxs-lookup"><span data-stu-id="80613-109">![ListView with GridView output](../../../../docs/framework/wpf/controls/media/listviewgridview.JPG "ListViewGridView")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80613-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80613-110">See Also</span></span>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [<span data-ttu-id="80613-111">Panoramica sul controllo ListView</span><span class="sxs-lookup"><span data-stu-id="80613-111">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [<span data-ttu-id="80613-112">Cenni preliminari su GridView</span><span class="sxs-lookup"><span data-stu-id="80613-112">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)  
 [<span data-ttu-id="80613-113">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="80613-113">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)
