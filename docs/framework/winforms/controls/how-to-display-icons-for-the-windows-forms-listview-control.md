---
title: 'Procedura: visualizzare icone per il controllo ListView Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], displaying icons
- icons [Windows Forms], displaying for ListView controls
- lists [Windows Forms], displaying icons
- ImageList component [Windows Forms], with ListView control
- list views [Windows Forms], displaying icons
ms.assetid: 9d577542-8595-429b-99e5-078770ec9d35
ms.openlocfilehash: 0e597ed182739947014b4f405ee2dc3149b62849
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33533604"
---
# <a name="how-to-display-icons-for-the-windows-forms-listview-control"></a><span data-ttu-id="1637d-102">Procedura: visualizzare icone per il controllo ListView Windows Form</span><span class="sxs-lookup"><span data-stu-id="1637d-102">How to: Display Icons for the Windows Forms ListView Control</span></span>
<span data-ttu-id="1637d-103">Windows Form <xref:System.Windows.Forms.ListView> controllo può visualizzare le icone da tre elenchi di immagini.</span><span class="sxs-lookup"><span data-stu-id="1637d-103">The Windows Forms <xref:System.Windows.Forms.ListView> control can display icons from three image lists.</span></span> <span data-ttu-id="1637d-104">Le visualizzazioni elenco e dettagli SmallIcon visualizzano immagini dall'elenco di immagini specificato nella <xref:System.Windows.Forms.ListView.SmallImageList%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="1637d-104">The List, Details, and SmallIcon views display images from the image list specified in the <xref:System.Windows.Forms.ListView.SmallImageList%2A> property.</span></span> <span data-ttu-id="1637d-105">La visualizzazione LargeIcon visualizza immagini dall'elenco di immagini specificato nella <xref:System.Windows.Forms.ListView.LargeImageList%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="1637d-105">The LargeIcon view displays images from the image list specified in the <xref:System.Windows.Forms.ListView.LargeImageList%2A> property.</span></span> <span data-ttu-id="1637d-106">Una visualizzazione elenco può anche visualizzare un altro set di icone, impostato nella <xref:System.Windows.Forms.ListView.StateImageList%2A> proprietà, accanto alle icone grandi o piccole.</span><span class="sxs-lookup"><span data-stu-id="1637d-106">A list view can also display an additional set of icons, set in the <xref:System.Windows.Forms.ListView.StateImageList%2A> property, next to the large or small icons.</span></span> <span data-ttu-id="1637d-107">Per ulteriori informazioni sugli elenchi di immagini, vedere [componente ImageList](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) e [procedura: aggiungere o rimuovere immagini con il componente ImageList di Windows Form](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span><span class="sxs-lookup"><span data-stu-id="1637d-107">For more information about image lists, see [ImageList Component](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) and [How to: Add or Remove Images with the Windows Forms ImageList Component](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span>  
  
### <a name="to-display-images-in-a-list-view"></a><span data-ttu-id="1637d-108">Per visualizzare le immagini in una visualizzazione elenco</span><span class="sxs-lookup"><span data-stu-id="1637d-108">To display images in a list view</span></span>  
  
1.  <span data-ttu-id="1637d-109">Impostare la proprietà appropriata, ovvero<xref:System.Windows.Forms.ListView.SmallImageList%2A>, <xref:System.Windows.Forms.ListView.LargeImageList%2A>, o <xref:System.Windows.Forms.ListView.StateImageList%2A>: esistente <xref:System.Windows.Forms.ImageList> componente che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="1637d-109">Set the appropriate property—<xref:System.Windows.Forms.ListView.SmallImageList%2A>, <xref:System.Windows.Forms.ListView.LargeImageList%2A>, or <xref:System.Windows.Forms.ListView.StateImageList%2A>—to the existing <xref:System.Windows.Forms.ImageList> component you wish to use.</span></span>  
  
     <span data-ttu-id="1637d-110">Queste proprietà possono essere impostate nella finestra di progettazione con la finestra proprietà o nel codice.</span><span class="sxs-lookup"><span data-stu-id="1637d-110">These properties can be set in the designer with the Properties window, or in code.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#41)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#41)]  
  
2.  <span data-ttu-id="1637d-111">Impostare il <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> o <xref:System.Windows.Forms.ListViewItem.StateImageIndex%2A> proprietà per ogni elemento di elenco che è associata un'icona.</span><span class="sxs-lookup"><span data-stu-id="1637d-111">Set the <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> or <xref:System.Windows.Forms.ListViewItem.StateImageIndex%2A> property for each list item that has an associated icon.</span></span>  
  
     <span data-ttu-id="1637d-112">Queste proprietà possono essere impostate nel codice o all'interno di **Editor della raccolta ListViewItem**.</span><span class="sxs-lookup"><span data-stu-id="1637d-112">These properties can be set in code, or within the **ListViewItem Collection Editor**.</span></span> <span data-ttu-id="1637d-113">Per aprire la **Editor della raccolta ListViewItem**, fare clic sul pulsante con i puntini di sospensione (![schermata VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) accanto il <xref:System.Windows.Forms.ListView.Items%2A>proprietà il **proprietà** finestra.</span><span class="sxs-lookup"><span data-stu-id="1637d-113">To open the **ListViewItem Collection Editor**, click the ellipsis button (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.ListView.Items%2A> property on the **Properties** window.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#42)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#42)]  
  
## <a name="see-also"></a><span data-ttu-id="1637d-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1637d-114">See Also</span></span>  
 [<span data-ttu-id="1637d-115">Panoramica del controllo ListView</span><span class="sxs-lookup"><span data-stu-id="1637d-115">ListView Control Overview</span></span>](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [<span data-ttu-id="1637d-116">Procedura: Aggiungere e rimuovere elementi con il controllo ListView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="1637d-116">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)  
 [<span data-ttu-id="1637d-117">Procedura: Aggiungere colonne al controllo ListView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="1637d-117">How to: Add Columns to the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)  
 [<span data-ttu-id="1637d-118">Procedura: Aggiungere informazioni personalizzate a un controllo TreeView o ListView (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="1637d-118">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)  
 [<span data-ttu-id="1637d-119">Componente ImageList</span><span class="sxs-lookup"><span data-stu-id="1637d-119">ImageList Component</span></span>](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)
