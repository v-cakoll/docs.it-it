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
ms.openlocfilehash: a88e4766a1e774582bcd0356c9b6e77bc31f1960
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928531"
---
# <a name="how-to-access-keyed-collections-in-windows-forms"></a><span data-ttu-id="c6423-102">Procedura: Accedere a raccolte con chiavi in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c6423-102">How to: Access Keyed Collections in Windows Forms</span></span>

- <span data-ttu-id="c6423-103">È possibile accedere a singoli elementi della raccolta in base alla chiave.</span><span class="sxs-lookup"><span data-stu-id="c6423-103">You can access individual collection items by key.</span></span> <span data-ttu-id="c6423-104">Questa funzionalità è stata aggiunta a numerose classi di raccolta che in genere vengono utilizzate dalle applicazioni Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c6423-104">This functionality has been added to many collection classes that are typically used by Windows Forms applications.</span></span> <span data-ttu-id="c6423-105">Nell'elenco seguente vengono illustrate alcune delle classi di raccolta con le raccolte con chiave accessibili:</span><span class="sxs-lookup"><span data-stu-id="c6423-105">The following list shows some of the collection classes that have accessible keyed collections:</span></span>  
  
- <xref:System.Windows.Forms.ListView.ListViewItemCollection>  
  
- <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection>  
  
- <xref:System.Windows.Forms.Control.ControlCollection>  
  
- <xref:System.Windows.Forms.TabControl.TabPageCollection>  
  
- <xref:System.Windows.Forms.TreeNodeCollection>  
  
 <span data-ttu-id="c6423-106">La chiave associata a un elemento in una raccolta è in genere il nome dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="c6423-106">The key associated with an item in a collection is typically the name of the item.</span></span> <span data-ttu-id="c6423-107">Nelle procedure riportate di seguito viene illustrato come utilizzare le classi di raccolta per eseguire attività comuni.</span><span class="sxs-lookup"><span data-stu-id="c6423-107">The following procedures show you how to use collection classes to perform common tasks.</span></span>  
  
### <a name="to-find-and-give-focus-to-a-nested-control-in-a-control-collection"></a><span data-ttu-id="c6423-108">Per individuare e assegnare lo stato attivo a un controllo annidato in una raccolta di controlli</span><span class="sxs-lookup"><span data-stu-id="c6423-108">To find and give focus to a nested control in a control collection</span></span>  
  
- <span data-ttu-id="c6423-109">Usare i <xref:System.Windows.Forms.Control.ControlCollection.Find%2A> metodi <xref:System.Windows.Forms.Control.Focus%2A> e per specificare il nome del controllo da trovare e fornire lo stato attivo a.</span><span class="sxs-lookup"><span data-stu-id="c6423-109">Use the <xref:System.Windows.Forms.Control.ControlCollection.Find%2A> and <xref:System.Windows.Forms.Control.Focus%2A> methods to specify the name of the control to find and give focus to.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#1)]  
  
### <a name="to-access-an-image-in-an-image-collection"></a><span data-ttu-id="c6423-110">Per accedere a un'immagine in una raccolta di immagini</span><span class="sxs-lookup"><span data-stu-id="c6423-110">To access an image in an image collection</span></span>  
  
- <span data-ttu-id="c6423-111">Usare la <xref:System.Windows.Forms.ImageList.ImageCollection.Item%2A> proprietà per specificare il nome dell'immagine a cui si vuole accedere.</span><span class="sxs-lookup"><span data-stu-id="c6423-111">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Item%2A> property to specify the name of the image you want to access.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#2)]  
  
### <a name="to-set-a-tab-page-as-the-selected-tab"></a><span data-ttu-id="c6423-112">Per impostare una scheda come scheda selezionata</span><span class="sxs-lookup"><span data-stu-id="c6423-112">To set a tab page as the selected tab</span></span>  
  
- <span data-ttu-id="c6423-113">Utilizzare la <xref:System.Windows.Forms.TabControl.SelectedTab%2A> proprietà insieme <xref:System.Windows.Forms.TabControl.TabPageCollection.Item%2A> alla proprietà per specificare il nome della scheda da impostare come scheda selezionata.</span><span class="sxs-lookup"><span data-stu-id="c6423-113">Use the <xref:System.Windows.Forms.TabControl.SelectedTab%2A> property together with the <xref:System.Windows.Forms.TabControl.TabPageCollection.Item%2A> property to specify the name of the tab page to set as the selected tab.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="c6423-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c6423-114">See also</span></span>

- [<span data-ttu-id="c6423-115">Guida introduttiva a Windows Form</span><span class="sxs-lookup"><span data-stu-id="c6423-115">Getting Started with Windows Forms</span></span>](getting-started-with-windows-forms.md)
- [<span data-ttu-id="c6423-116">Procedura: Aggiungere o rimuovere immagini con il componente Windows Forms ImageList</span><span class="sxs-lookup"><span data-stu-id="c6423-116">How to: Add or Remove Images with the Windows Forms ImageList Component</span></span>](./controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)
