---
title: 'Procedura: accedere a raccolte con chiavi in Windows Form'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keyed collections [Windows Forms]
- collections [Windows Forms], accessing with keys
ms.assetid: b9b79b8b-d9bf-4f8c-b9d6-9578bc3219d3
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2bca9b56f37c815bfa9f1520467ae0ae864c14ac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-access-keyed-collections-in-windows-forms"></a><span data-ttu-id="439ee-102">Procedura: accedere a raccolte con chiavi in Windows Form</span><span class="sxs-lookup"><span data-stu-id="439ee-102">How to: Access Keyed Collections in Windows Forms</span></span>
-   <span data-ttu-id="439ee-103">È possibile accedere a singoli elementi dell'insieme dalla chiave.</span><span class="sxs-lookup"><span data-stu-id="439ee-103">You can access individual collection items by key.</span></span> <span data-ttu-id="439ee-104">Questa funzionalità è stata aggiunta a molte classi di raccolta che vengono in genere utilizzate dalle applicazioni Windows Form.</span><span class="sxs-lookup"><span data-stu-id="439ee-104">This functionality has been added to many collection classes that are typically used by Windows Forms applications.</span></span> <span data-ttu-id="439ee-105">Nell'elenco seguente sono illustrate alcune delle classi di raccolte che sono accessibili raccolte con chiave:</span><span class="sxs-lookup"><span data-stu-id="439ee-105">The following list shows some of the collection classes that have accessible keyed collections:</span></span>  
  
-   <xref:System.Windows.Forms.ListView.ListViewItemCollection>  
  
-   <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection>  
  
-   <xref:System.Windows.Forms.Control.ControlCollection>  
  
-   <xref:System.Windows.Forms.TabControl.TabPageCollection>  
  
-   <xref:System.Windows.Forms.TreeNodeCollection>  
  
 <span data-ttu-id="439ee-106">La chiave associata a un elemento in una raccolta è in genere il nome dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="439ee-106">The key associated with an item in a collection is typically the name of the item.</span></span> <span data-ttu-id="439ee-107">Le procedure seguenti viene illustrato come utilizzare le classi di raccolta per eseguire attività comuni.</span><span class="sxs-lookup"><span data-stu-id="439ee-107">The following procedures show you how to use collection classes to perform common tasks.</span></span>  
  
### <a name="to-find-and-give-focus-to-a-nested-control-in-a-control-collection"></a><span data-ttu-id="439ee-108">Per trovare e fornire lo stato attivo a un controllo in una raccolta di controllo annidate</span><span class="sxs-lookup"><span data-stu-id="439ee-108">To find and give focus to a nested control in a control collection</span></span>  
  
-   <span data-ttu-id="439ee-109">Utilizzare il <xref:System.Windows.Forms.Control.ControlCollection.Find%2A> e <xref:System.Windows.Forms.Control.Focus%2A> metodi per specificare il nome del controllo da trovare e portare lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="439ee-109">Use the <xref:System.Windows.Forms.Control.ControlCollection.Find%2A> and <xref:System.Windows.Forms.Control.Focus%2A> methods to specify the name of the control to find and give focus to.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#1)]  
  
### <a name="to-access-an-image-in-an-image-collection"></a><span data-ttu-id="439ee-110">Per accedere a un'immagine in una raccolta di immagini</span><span class="sxs-lookup"><span data-stu-id="439ee-110">To access an image in an image collection</span></span>  
  
-   <span data-ttu-id="439ee-111">Utilizzare il <xref:System.Windows.Forms.ImageList.ImageCollection.Item%2A> proprietà per specificare il nome dell'immagine di cui si desidera accedere.</span><span class="sxs-lookup"><span data-stu-id="439ee-111">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Item%2A> property to specify the name of the image you want to access.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#2)]  
  
### <a name="to-set-a-tab-page-as-the-selected-tab"></a><span data-ttu-id="439ee-112">Per impostare una pagina della scheda come scheda selezionata</span><span class="sxs-lookup"><span data-stu-id="439ee-112">To set a tab page as the selected tab</span></span>  
  
-   <span data-ttu-id="439ee-113">Utilizzare il <xref:System.Windows.Forms.TabControl.SelectedTab%2A> proprietà con il <xref:System.Windows.Forms.TabControl.TabPageCollection.Item%2A> proprietà per specificare il nome della scheda per impostare come scheda selezionata.</span><span class="sxs-lookup"><span data-stu-id="439ee-113">Use the <xref:System.Windows.Forms.TabControl.SelectedTab%2A> property together with the <xref:System.Windows.Forms.TabControl.TabPageCollection.Item%2A> property to specify the name of the tab page to set as the selected tab.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="439ee-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="439ee-114">See Also</span></span>  
 [<span data-ttu-id="439ee-115">Guida introduttiva a Windows Form</span><span class="sxs-lookup"><span data-stu-id="439ee-115">Getting Started with Windows Forms</span></span>](../../../docs/framework/winforms/getting-started-with-windows-forms.md)  
 [<span data-ttu-id="439ee-116">Procedura: Aggiungere o rimuovere immagini con il componente ImageList di Windows Form</span><span class="sxs-lookup"><span data-stu-id="439ee-116">How to: Add or Remove Images with the Windows Forms ImageList Component</span></span>](../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)
