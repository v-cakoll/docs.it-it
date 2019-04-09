---
title: 'Procedura: Accedere a raccolte con chiavi in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keyed collections [Windows Forms]
- collections [Windows Forms], accessing with keys
ms.assetid: b9b79b8b-d9bf-4f8c-b9d6-9578bc3219d3
ms.openlocfilehash: fdd3a56ab9a267990bb0e832c0d4cc2af9334034
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59214040"
---
# <a name="how-to-access-keyed-collections-in-windows-forms"></a><span data-ttu-id="84193-102">Procedura: Accedere a raccolte con chiavi in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="84193-102">How to: Access Keyed Collections in Windows Forms</span></span>
-   <span data-ttu-id="84193-103">È possibile accedere a singoli elementi della raccolta dalla chiave.</span><span class="sxs-lookup"><span data-stu-id="84193-103">You can access individual collection items by key.</span></span> <span data-ttu-id="84193-104">Questa funzionalità è stata aggiunta a molte classi di raccolta che in genere vengono usate dalle applicazioni di Windows Form.</span><span class="sxs-lookup"><span data-stu-id="84193-104">This functionality has been added to many collection classes that are typically used by Windows Forms applications.</span></span> <span data-ttu-id="84193-105">L'elenco seguente mostra alcune delle classi di raccolta che dispone di raccolte con chiave accessibile:</span><span class="sxs-lookup"><span data-stu-id="84193-105">The following list shows some of the collection classes that have accessible keyed collections:</span></span>  
  
-   <xref:System.Windows.Forms.ListView.ListViewItemCollection>  
  
-   <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection>  
  
-   <xref:System.Windows.Forms.Control.ControlCollection>  
  
-   <xref:System.Windows.Forms.TabControl.TabPageCollection>  
  
-   <xref:System.Windows.Forms.TreeNodeCollection>  
  
 <span data-ttu-id="84193-106">La chiave associata a un elemento in una raccolta è in genere il nome dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="84193-106">The key associated with an item in a collection is typically the name of the item.</span></span> <span data-ttu-id="84193-107">Le procedure seguenti illustrano come usare le classi di raccolta per eseguire attività comuni.</span><span class="sxs-lookup"><span data-stu-id="84193-107">The following procedures show you how to use collection classes to perform common tasks.</span></span>  
  
### <a name="to-find-and-give-focus-to-a-nested-control-in-a-control-collection"></a><span data-ttu-id="84193-108">Per trovare e attivare un controllo annidato in una raccolta di controllo</span><span class="sxs-lookup"><span data-stu-id="84193-108">To find and give focus to a nested control in a control collection</span></span>  
  
-   <span data-ttu-id="84193-109">Usare la <xref:System.Windows.Forms.Control.ControlCollection.Find%2A> e <xref:System.Windows.Forms.Control.Focus%2A> metodi per specificare il nome del controllo da trovare e attivare controllo.</span><span class="sxs-lookup"><span data-stu-id="84193-109">Use the <xref:System.Windows.Forms.Control.ControlCollection.Find%2A> and <xref:System.Windows.Forms.Control.Focus%2A> methods to specify the name of the control to find and give focus to.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#1)]  
  
### <a name="to-access-an-image-in-an-image-collection"></a><span data-ttu-id="84193-110">Per accedere a un'immagine in una raccolta di immagini</span><span class="sxs-lookup"><span data-stu-id="84193-110">To access an image in an image collection</span></span>  
  
-   <span data-ttu-id="84193-111">Usare il <xref:System.Windows.Forms.ImageList.ImageCollection.Item%2A> proprietà per specificare il nome dell'immagine di cui si desidera accedere.</span><span class="sxs-lookup"><span data-stu-id="84193-111">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Item%2A> property to specify the name of the image you want to access.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#2)]  
  
### <a name="to-set-a-tab-page-as-the-selected-tab"></a><span data-ttu-id="84193-112">Per impostare una pagina della scheda selezionata</span><span class="sxs-lookup"><span data-stu-id="84193-112">To set a tab page as the selected tab</span></span>  
  
-   <span data-ttu-id="84193-113">Usare la <xref:System.Windows.Forms.TabControl.SelectedTab%2A> proprietà con il <xref:System.Windows.Forms.TabControl.TabPageCollection.Item%2A> proprietà per specificare il nome della scheda per impostare come scheda selezionata.</span><span class="sxs-lookup"><span data-stu-id="84193-113">Use the <xref:System.Windows.Forms.TabControl.SelectedTab%2A> property together with the <xref:System.Windows.Forms.TabControl.TabPageCollection.Item%2A> property to specify the name of the tab page to set as the selected tab.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="84193-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84193-114">See also</span></span>

- [<span data-ttu-id="84193-115">Guida introduttiva a Windows Form</span><span class="sxs-lookup"><span data-stu-id="84193-115">Getting Started with Windows Forms</span></span>](getting-started-with-windows-forms.md)
- [<span data-ttu-id="84193-116">Procedura: Aggiungere o rimuovere immagini con il componente ImageList di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="84193-116">How to: Add or Remove Images with the Windows Forms ImageList Component</span></span>](./controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)
