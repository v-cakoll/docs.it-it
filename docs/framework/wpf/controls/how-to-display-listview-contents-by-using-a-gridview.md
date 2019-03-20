---
title: "Procedura: Visualizzare il contenuto dell'oggetto ListView tramite un oggetto GridView"
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], displaying contents with GridView
- GridView [WPF], displaying ListView contents
ms.assetid: 5bc1e767-ab46-4f14-bd41-3d5d39e1d000
ms.openlocfilehash: 1066869c80bf5bd87d656bcb4994c188ee0e8efc
ms.sourcegitcommit: 462dc41a13942e467984e48f4018d1f79ae67346
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2019
ms.locfileid: "58185610"
---
# <a name="how-to-display-listview-contents-by-using-a-gridview"></a><span data-ttu-id="9f30a-102">Procedura: Visualizzare il contenuto dell'oggetto ListView tramite un oggetto GridView</span><span class="sxs-lookup"><span data-stu-id="9f30a-102">How to: Display ListView Contents by Using a GridView</span></span>
<span data-ttu-id="9f30a-103">In questo esempio viene illustrato come definire un <xref:System.Windows.Controls.GridView> modalità di visualizzazione per un <xref:System.Windows.Controls.ListView> controllo.</span><span class="sxs-lookup"><span data-stu-id="9f30a-103">This example shows how to define a <xref:System.Windows.Controls.GridView> view mode for a <xref:System.Windows.Controls.ListView> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f30a-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="9f30a-104">Example</span></span>  
 <span data-ttu-id="9f30a-105">È possibile definire la modalità di visualizzazione di un <xref:System.Windows.Controls.GridView> specificando <xref:System.Windows.Controls.GridViewColumn> oggetti.</span><span class="sxs-lookup"><span data-stu-id="9f30a-105">You can define the view mode of a <xref:System.Windows.Controls.GridView> by specifying <xref:System.Windows.Controls.GridViewColumn> objects.</span></span> <span data-ttu-id="9f30a-106">Nell'esempio seguente viene illustrato come definire <xref:System.Windows.Controls.GridViewColumn> gli oggetti che associano il contenuto dei dati specificato per il <xref:System.Windows.Controls.ListView> controllo.</span><span class="sxs-lookup"><span data-stu-id="9f30a-106">The following example shows how to define <xref:System.Windows.Controls.GridViewColumn> objects that bind to the data content that is specified for the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="9f30a-107">Ciò <xref:System.Windows.Controls.GridView> esempio specifica tre <xref:System.Windows.Controls.GridViewColumn> negli oggetti mappati al `FirstName`, `LastName`, e `EmployeeNumber` campi del `EmployeeInfoDataSource` che viene impostato come il <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> del <xref:System.Windows.Controls.ListView> controllo.</span><span class="sxs-lookup"><span data-stu-id="9f30a-107">This <xref:System.Windows.Controls.GridView> example specifies three <xref:System.Windows.Controls.GridViewColumn> objects that map to the `FirstName`, `LastName`, and `EmployeeNumber` fields of the `EmployeeInfoDataSource` that is set as the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> of the <xref:System.Windows.Controls.ListView> control.</span></span>  
  
 [!code-xaml[ListViewCode#ListViewEmployee](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 <span data-ttu-id="9f30a-108">La figura seguente mostra come viene visualizzato in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="9f30a-108">The following illustration shows how this example appears.</span></span>  
  
 ![Screenshot che mostra un ListView con output GridView.](./media/gridview-overview/listview-gridview-output.jpg)  
  
## <a name="see-also"></a><span data-ttu-id="9f30a-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9f30a-110">See also</span></span>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="9f30a-111">Panoramica sul controllo ListView</span><span class="sxs-lookup"><span data-stu-id="9f30a-111">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="9f30a-112">Cenni preliminari su GridView</span><span class="sxs-lookup"><span data-stu-id="9f30a-112">GridView Overview</span></span>](gridview-overview.md)
- [<span data-ttu-id="9f30a-113">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="9f30a-113">How-to Topics</span></span>](listview-how-to-topics.md)
