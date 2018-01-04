---
title: 'Procedura: aggiungere o rimuovere immagini ImageList con la finestra di progettazione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ImageList component [Windows Forms], adding images
- ImageList component [Windows Forms], removing images
- images [Windows Forms], adding to ImageList component
ms.assetid: 5699b244-e37c-4d20-bc35-7441e55c1e3a
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 05dd1e06c2cba31bca1282e8d409ab1b5610d1dd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-or-remove-imagelist-images-with-the-designer"></a><span data-ttu-id="04452-102">Procedura: aggiungere o rimuovere immagini ImageList con la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="04452-102">How to: Add or Remove ImageList Images with the Designer</span></span>
<span data-ttu-id="04452-103">È possibile aggiungere immagini a un <xref:System.Windows.Forms.ImageList> componente diversi modi.</span><span class="sxs-lookup"><span data-stu-id="04452-103">You can add images to an <xref:System.Windows.Forms.ImageList> component several different ways.</span></span> <span data-ttu-id="04452-104">È possibile aggiungere molto rapidamente le immagini tramite lo smart tag associato con il <xref:System.Windows.Forms.ImageList>, o se si imposta su molte altre proprietà di <xref:System.Windows.Forms.ImageList>, potrebbe essere più opportuno aggiungere immagini con la finestra Proprietà.</span><span class="sxs-lookup"><span data-stu-id="04452-104">You can add images very quickly by using the smart tag associated with the <xref:System.Windows.Forms.ImageList>, or if you are setting several other properties on the <xref:System.Windows.Forms.ImageList>, you may find it more convenient to add images with the Properties window.</span></span> <span data-ttu-id="04452-105">È anche possibile aggiungere immagini tramite il codice.</span><span class="sxs-lookup"><span data-stu-id="04452-105">You can also add images by using code.</span></span> <span data-ttu-id="04452-106">Per ulteriori informazioni sull'aggiunta di immagini con il codice, vedere [procedura: aggiungere o rimuovere immagini con il componente ImageList di Windows Form](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span><span class="sxs-lookup"><span data-stu-id="04452-106">For more information about how to add images with code, see [How to: Add or Remove Images with the Windows Forms ImageList Component](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span> <span data-ttu-id="04452-107">In genere viene popolato il <xref:System.Windows.Forms.ImageList> componente con immagini prima è associata a un controllo, ma non è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="04452-107">Typically you populate the <xref:System.Windows.Forms.ImageList> component with images before it is associated with a control, but this is not required.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="04452-108">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="04452-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="04452-109">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="04452-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="04452-110">Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="04452-110">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-add-or-remove-images-by-using-the-properties-window"></a><span data-ttu-id="04452-111">Per aggiungere o rimuovere immagini tramite la finestra proprietà</span><span class="sxs-lookup"><span data-stu-id="04452-111">To add or remove images by using the Properties window</span></span>  
  
1.  <span data-ttu-id="04452-112">Selezionare il <xref:System.Windows.Forms.ImageList> , componente o aggiungerne uno al form.</span><span class="sxs-lookup"><span data-stu-id="04452-112">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>  
  
2.  <span data-ttu-id="04452-113">Nella finestra Proprietà fare clic sul pulsante con puntini di sospensione (![schermata VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) accanto al <xref:System.Windows.Forms.ImageList.Images%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="04452-113">In the Properties window, click the ellipsis button (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.ImageList.Images%2A> property.</span></span>  
  
3.  <span data-ttu-id="04452-114">Nel **Editor della raccolta immagini**, fare clic su **Aggiungi** o **rimuovere** per aggiungere o rimuovere immagini dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="04452-114">In the **Image Collection Editor**, click **Add** or **Remove** to add or remove images from the list.</span></span>  
  
### <a name="to-add-or-remove-images-using-the-smart-tag"></a><span data-ttu-id="04452-115">Per aggiungere o rimuovere immagini tramite lo smart tag</span><span class="sxs-lookup"><span data-stu-id="04452-115">To add or remove images using the smart tag</span></span>  
  
1.  <span data-ttu-id="04452-116">Selezionare il <xref:System.Windows.Forms.ImageList> , componente o aggiungerne uno al form.</span><span class="sxs-lookup"><span data-stu-id="04452-116">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>  
  
2.  <span data-ttu-id="04452-117">Fare clic sul glifo smart tag (![Smart Tag glifo](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))</span><span class="sxs-lookup"><span data-stu-id="04452-117">Click the smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))</span></span>  
  
3.  <span data-ttu-id="04452-118">Nel **attività ImageList** nella finestra di dialogo **scegliere immagini**.</span><span class="sxs-lookup"><span data-stu-id="04452-118">In the **ImageList Tasks** dialog box, select **Choose Images**.</span></span>  
  
4.  <span data-ttu-id="04452-119">Nel **Editor della raccolta immagini** fare clic su **Aggiungi** o **rimuovere** per aggiungere o rimuovere immagini dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="04452-119">In the **Images Collection Editor** click **Add** or **Remove** to add or remove images from the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04452-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04452-120">See Also</span></span>  
 [<span data-ttu-id="04452-121">Immagini, bitmap e metafile</span><span class="sxs-lookup"><span data-stu-id="04452-121">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [<span data-ttu-id="04452-122">Procedura dettagliata: esecuzione di attività comuni usando gli smart tag nei controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="04452-122">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/performing-common-tasks-using-smart-tags-on-wf-controls.md)  
 [<span data-ttu-id="04452-123">Componente ImageList</span><span class="sxs-lookup"><span data-stu-id="04452-123">ImageList Component</span></span>](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)
