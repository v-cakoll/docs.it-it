---
title: 'Procedura: Aggiungere o rimuovere immagini ImageList con la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- ImageList component [Windows Forms], adding images
- ImageList component [Windows Forms], removing images
- images [Windows Forms], adding to ImageList component
ms.assetid: 5699b244-e37c-4d20-bc35-7441e55c1e3a
ms.openlocfilehash: f03ad1735d7da450d6ebc10c227e3f2bbb41a3d8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54688142"
---
# <a name="how-to-add-or-remove-imagelist-images-with-the-designer"></a><span data-ttu-id="8ca44-102">Procedura: Aggiungere o rimuovere immagini ImageList con la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="8ca44-102">How to: Add or Remove ImageList Images with the Designer</span></span>
<span data-ttu-id="8ca44-103">È possibile aggiungere immagini a un <xref:System.Windows.Forms.ImageList> componente diversi modi.</span><span class="sxs-lookup"><span data-stu-id="8ca44-103">You can add images to an <xref:System.Windows.Forms.ImageList> component several different ways.</span></span> <span data-ttu-id="8ca44-104">È possibile aggiungere molto rapidamente immagini tramite lo smart tag associati con la <xref:System.Windows.Forms.ImageList>, o se si imposta su molte altre proprietà di <xref:System.Windows.Forms.ImageList>, può risultare più comodo aggiungere le immagini con la finestra Proprietà.</span><span class="sxs-lookup"><span data-stu-id="8ca44-104">You can add images very quickly by using the smart tag associated with the <xref:System.Windows.Forms.ImageList>, or if you are setting several other properties on the <xref:System.Windows.Forms.ImageList>, you may find it more convenient to add images with the Properties window.</span></span> <span data-ttu-id="8ca44-105">È anche possibile aggiungere immagini tramite il codice.</span><span class="sxs-lookup"><span data-stu-id="8ca44-105">You can also add images by using code.</span></span> <span data-ttu-id="8ca44-106">Per altre informazioni su come aggiungere immagini con il codice, vedere [come: Aggiungere o rimuovere immagini tramite il Windows Form componente ImageList](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span><span class="sxs-lookup"><span data-stu-id="8ca44-106">For more information about how to add images with code, see [How to: Add or Remove Images with the Windows Forms ImageList Component](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span> <span data-ttu-id="8ca44-107">In genere si popola la <xref:System.Windows.Forms.ImageList> componente con le immagini prima è associato un controllo, ma non è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="8ca44-107">Typically you populate the <xref:System.Windows.Forms.ImageList> component with images before it is associated with a control, but this is not required.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8ca44-108">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="8ca44-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="8ca44-109">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="8ca44-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="8ca44-110">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="8ca44-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-or-remove-images-by-using-the-properties-window"></a><span data-ttu-id="8ca44-111">Per aggiungere o rimuovere immagini tramite la finestra proprietà</span><span class="sxs-lookup"><span data-stu-id="8ca44-111">To add or remove images by using the Properties window</span></span>  
  
1.  <span data-ttu-id="8ca44-112">Selezionare il <xref:System.Windows.Forms.ImageList> componente, o aggiungerne uno al form.</span><span class="sxs-lookup"><span data-stu-id="8ca44-112">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>  
  
2.  <span data-ttu-id="8ca44-113">Nella finestra Proprietà, fare clic sul pulsante con puntini di sospensione (![schermata di VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) accanto al <xref:System.Windows.Forms.ImageList.Images%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="8ca44-113">In the Properties window, click the ellipsis button (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.ImageList.Images%2A> property.</span></span>  
  
3.  <span data-ttu-id="8ca44-114">Nel **Editor raccolta di immagini**, fare clic su **Add** oppure **rimuovere** per aggiungere o rimuovere immagini dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="8ca44-114">In the **Image Collection Editor**, click **Add** or **Remove** to add or remove images from the list.</span></span>  
  
### <a name="to-add-or-remove-images-using-the-smart-tag"></a><span data-ttu-id="8ca44-115">Per aggiungere o rimuovere immagini tramite lo smart tag</span><span class="sxs-lookup"><span data-stu-id="8ca44-115">To add or remove images using the smart tag</span></span>  
  
1.  <span data-ttu-id="8ca44-116">Selezionare il <xref:System.Windows.Forms.ImageList> componente, o aggiungerne uno al form.</span><span class="sxs-lookup"><span data-stu-id="8ca44-116">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>  
  
2.  <span data-ttu-id="8ca44-117">Fare clic sul glifo dello smart tag (![glifo Smart Tag](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))</span><span class="sxs-lookup"><span data-stu-id="8ca44-117">Click the smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))</span></span>  
  
3.  <span data-ttu-id="8ca44-118">Nel **attività ImageList** finestra di dialogo **immagini scegliere**.</span><span class="sxs-lookup"><span data-stu-id="8ca44-118">In the **ImageList Tasks** dialog box, select **Choose Images**.</span></span>  
  
4.  <span data-ttu-id="8ca44-119">Nel **Editor Kolekce Images** fare clic su **Add** oppure **rimuovere** per aggiungere o rimuovere immagini dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="8ca44-119">In the **Images Collection Editor** click **Add** or **Remove** to add or remove images from the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ca44-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ca44-120">See also</span></span>
- [<span data-ttu-id="8ca44-121">Immagini, bitmap e metafile</span><span class="sxs-lookup"><span data-stu-id="8ca44-121">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="8ca44-122">Procedura dettagliata: Esecuzione di attività comuni usando gli Smart tag nei Windows Form controlli</span><span class="sxs-lookup"><span data-stu-id="8ca44-122">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/performing-common-tasks-using-smart-tags-on-wf-controls.md)
- [<span data-ttu-id="8ca44-123">Componente ImageList</span><span class="sxs-lookup"><span data-stu-id="8ca44-123">ImageList Component</span></span>](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)
