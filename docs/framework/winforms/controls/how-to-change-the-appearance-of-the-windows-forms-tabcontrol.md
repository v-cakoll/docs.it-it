---
title: 'Procedura: modificare l''aspetto del controllo TabControl Windows Form'
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
- cpp
helpviewer_keywords:
- icons [Windows Forms], displaying on tabs
- TabControl control [Windows Forms], changing page appearance
- tabs [Windows Forms], controlling appearance
- buttons [Windows Forms], displaying tabs as
ms.assetid: 7c6cc443-ed62-4d26-b94d-b8913b44f773
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 61fb11b79459da14384af974dbc403024faa377f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-tabcontrol"></a><span data-ttu-id="0c0cc-102">Procedura: modificare l'aspetto del controllo TabControl Windows Form</span><span class="sxs-lookup"><span data-stu-id="0c0cc-102">How to: Change the Appearance of the Windows Forms TabControl</span></span>
<span data-ttu-id="0c0cc-103">È possibile modificare l'aspetto delle schede in Windows Form utilizzando le proprietà del <xref:System.Windows.Forms.TabControl> e <xref:System.Windows.Forms.TabPage> gli oggetti che costituiscono le singole schede del controllo.</span><span class="sxs-lookup"><span data-stu-id="0c0cc-103">You can change the appearance of tabs in Windows Forms by using properties of the <xref:System.Windows.Forms.TabControl> and the <xref:System.Windows.Forms.TabPage> objects that make up the individual tabs on the control.</span></span> <span data-ttu-id="0c0cc-104">L'impostazione di queste proprietà è possibile visualizzare immagini sulle schede, visualizzare le schede in verticale anziché in orizzontale, la visualizzazione di più righe di schede e abilitare o disabilitare le schede a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="0c0cc-104">By setting these properties, you can display images on tabs, display tabs vertically instead of horizontally, display multiple rows of tabs, and enable or disable tabs programmatically.</span></span>  
  
### <a name="to-display-an-icon-on-the-label-part-of-a-tab"></a><span data-ttu-id="0c0cc-105">Per visualizzare un'icona nella parte dell'etichetta di una scheda</span><span class="sxs-lookup"><span data-stu-id="0c0cc-105">To display an icon on the label part of a tab</span></span>  
  
1.  <span data-ttu-id="0c0cc-106">Aggiungere un <xref:System.Windows.Forms.ImageList> al form.</span><span class="sxs-lookup"><span data-stu-id="0c0cc-106">Add an <xref:System.Windows.Forms.ImageList> control to the form.</span></span>  
  
2.  <span data-ttu-id="0c0cc-107">Aggiungere immagini all'elenco di immagini.</span><span class="sxs-lookup"><span data-stu-id="0c0cc-107">Add images to the image list.</span></span>  
  
     <span data-ttu-id="0c0cc-108">Per ulteriori informazioni sugli elenchi di immagini, vedere [componente ImageList](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) e [procedura: aggiungere o rimuovere immagini con il componente ImageList di Windows Form](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span><span class="sxs-lookup"><span data-stu-id="0c0cc-108">For more information about image lists, see [ImageList Component](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) and [How to: Add or Remove Images with the Windows Forms ImageList Component](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span>  
  
3.  <span data-ttu-id="0c0cc-109">Impostare il <xref:System.Windows.Forms.TabControl.ImageList%2A> proprietà del <xref:System.Windows.Forms.TabControl> per il <xref:System.Windows.Forms.ImageList> controllo.</span><span class="sxs-lookup"><span data-stu-id="0c0cc-109">Set the <xref:System.Windows.Forms.TabControl.ImageList%2A> property of the <xref:System.Windows.Forms.TabControl> to the <xref:System.Windows.Forms.ImageList> control.</span></span>  
  
4.  <span data-ttu-id="0c0cc-110">Impostare il <xref:System.Windows.Forms.TabPage.ImageIndex%2A> proprietà del <xref:System.Windows.Forms.TabPage> all'indice di un'immagine appropriata nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="0c0cc-110">Set the <xref:System.Windows.Forms.TabPage.ImageIndex%2A> property of the <xref:System.Windows.Forms.TabPage> to the index of an appropriate image in the list.</span></span>  
  
### <a name="to-create-multiple-rows-of-tabs"></a><span data-ttu-id="0c0cc-111">Per creare più righe di schede</span><span class="sxs-lookup"><span data-stu-id="0c0cc-111">To create multiple rows of tabs</span></span>  
  
1.  <span data-ttu-id="0c0cc-112">Aggiungere il numero di schede desiderato.</span><span class="sxs-lookup"><span data-stu-id="0c0cc-112">Add the number of tab pages you want.</span></span>  
  
2.  <span data-ttu-id="0c0cc-113">Impostare il <xref:System.Windows.Forms.TabControl.Multiline%2A> proprietà del <xref:System.Windows.Forms.TabControl> a `true`.</span><span class="sxs-lookup"><span data-stu-id="0c0cc-113">Set the <xref:System.Windows.Forms.TabControl.Multiline%2A> property of the <xref:System.Windows.Forms.TabControl> to `true`.</span></span>  
  
3.  <span data-ttu-id="0c0cc-114">Se le schede non è già visualizzata in più righe, impostare il <xref:System.Windows.Forms.Control.Width%2A> proprietà del <xref:System.Windows.Forms.TabControl> di larghezza di tutte le schede.</span><span class="sxs-lookup"><span data-stu-id="0c0cc-114">If the tabs do not already appear in multiple rows, set the <xref:System.Windows.Forms.Control.Width%2A> property of the <xref:System.Windows.Forms.TabControl> to be narrower than all the tabs.</span></span>  
  
### <a name="to-arrange-tabs-on-the-side-of-the-control"></a><span data-ttu-id="0c0cc-115">Per disporre le schede sul lato del controllo</span><span class="sxs-lookup"><span data-stu-id="0c0cc-115">To arrange tabs on the side of the control</span></span>  
  
-   <span data-ttu-id="0c0cc-116">Impostare il <xref:System.Windows.Forms.TabControl.Alignment%2A> proprietà del <xref:System.Windows.Forms.TabControl> a <xref:System.Windows.Forms.TabAlignment.Left> o <xref:System.Windows.Forms.TabAlignment.Right>.</span><span class="sxs-lookup"><span data-stu-id="0c0cc-116">Set the <xref:System.Windows.Forms.TabControl.Alignment%2A> property of the <xref:System.Windows.Forms.TabControl> to <xref:System.Windows.Forms.TabAlignment.Left> or <xref:System.Windows.Forms.TabAlignment.Right>.</span></span>  
  
### <a name="to-programmatically-enable-or-disable-all-controls-on-a-tab"></a><span data-ttu-id="0c0cc-117">A livello di codice, abilitare o disabilitare tutti i controlli in una scheda</span><span class="sxs-lookup"><span data-stu-id="0c0cc-117">To programmatically enable or disable all controls on a tab</span></span>  
  
1.  <span data-ttu-id="0c0cc-118">Impostare il <xref:System.Windows.Forms.TabPage.Enabled%2A> proprietà del <xref:System.Windows.Forms.TabPage> a `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="0c0cc-118">Set the <xref:System.Windows.Forms.TabPage.Enabled%2A> property of the <xref:System.Windows.Forms.TabPage> to `true` or `false`.</span></span>  
  
    ```vb  
    TabPage1.Enabled = False  
    ```  
  
    ```csharp  
    tabPage1.Enabled = false;  
    ```  
  
    ```cpp  
    tabPage1->Enabled = false;  
    ```  
  
### <a name="to-display-tabs-as-buttons"></a><span data-ttu-id="0c0cc-119">Per visualizzare le schede come pulsanti</span><span class="sxs-lookup"><span data-stu-id="0c0cc-119">To display tabs as buttons</span></span>  
  
-   <span data-ttu-id="0c0cc-120">Impostare il <xref:System.Windows.Forms.TabControl.Appearance%2A> proprietà del <xref:System.Windows.Forms.TabControl> a <xref:System.Windows.Forms.TabAppearance.Buttons> o <xref:System.Windows.Forms.TabAppearance.FlatButtons>.</span><span class="sxs-lookup"><span data-stu-id="0c0cc-120">Set the <xref:System.Windows.Forms.TabControl.Appearance%2A> property of the <xref:System.Windows.Forms.TabControl> to <xref:System.Windows.Forms.TabAppearance.Buttons> or <xref:System.Windows.Forms.TabAppearance.FlatButtons>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c0cc-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c0cc-121">See Also</span></span>  
 [<span data-ttu-id="0c0cc-122">Controllo TabControl</span><span class="sxs-lookup"><span data-stu-id="0c0cc-122">TabControl Control</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)  
 [<span data-ttu-id="0c0cc-123">Panoramica del controllo TabControl</span><span class="sxs-lookup"><span data-stu-id="0c0cc-123">TabControl Control Overview</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 [<span data-ttu-id="0c0cc-124">Procedura: Aggiungere un controllo a un oggetto TabPage</span><span class="sxs-lookup"><span data-stu-id="0c0cc-124">How to: Add a Control to a Tab Page</span></span>](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)  
 [<span data-ttu-id="0c0cc-125">Procedura: Disabilitare le schede</span><span class="sxs-lookup"><span data-stu-id="0c0cc-125">How to: Disable Tab Pages</span></span>](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)  
 [<span data-ttu-id="0c0cc-126">Procedura: Aggiungere e rimuovere schede con il controllo TabControl di Windows Form</span><span class="sxs-lookup"><span data-stu-id="0c0cc-126">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
