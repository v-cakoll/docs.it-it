---
title: 'Procedura: aggiungere o rimuovere immagini ImageList con la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- ImageList component [Windows Forms], adding images
- ImageList component [Windows Forms], removing images
- images [Windows Forms], adding to ImageList component
ms.assetid: 5699b244-e37c-4d20-bc35-7441e55c1e3a
ms.openlocfilehash: cdc7b563a0ee4f8779b99b4e9a6786e78f8d500f
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628722"
---
# <a name="how-to-add-or-remove-imagelist-images-with-the-designer"></a><span data-ttu-id="01f74-102">Procedura: aggiungere o rimuovere immagini ImageList con la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="01f74-102">How to: Add or Remove ImageList Images with the Designer</span></span>

<span data-ttu-id="01f74-103">È possibile aggiungere immagini a un componente <xref:System.Windows.Forms.ImageList> in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="01f74-103">You can add images to an <xref:System.Windows.Forms.ImageList> component several different ways.</span></span> <span data-ttu-id="01f74-104">È possibile aggiungere immagini molto rapidamente usando lo smart tag associato all'<xref:System.Windows.Forms.ImageList>o, se si impostano diverse altre proprietà nella <xref:System.Windows.Forms.ImageList>, potrebbe risultare più comodo aggiungere immagini con il Finestra Proprietà.</span><span class="sxs-lookup"><span data-stu-id="01f74-104">You can add images very quickly by using the smart tag associated with the <xref:System.Windows.Forms.ImageList>, or if you are setting several other properties on the <xref:System.Windows.Forms.ImageList>, you may find it more convenient to add images with the Properties window.</span></span> <span data-ttu-id="01f74-105">È anche possibile aggiungere immagini usando il codice.</span><span class="sxs-lookup"><span data-stu-id="01f74-105">You can also add images by using code.</span></span> <span data-ttu-id="01f74-106">Per altre informazioni su come aggiungere immagini con il codice, vedere [procedura: aggiungere o rimuovere immagini con il componente Windows Forms ImageList](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span><span class="sxs-lookup"><span data-stu-id="01f74-106">For more information about how to add images with code, see [How to: Add or Remove Images with the Windows Forms ImageList Component](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span> <span data-ttu-id="01f74-107">In genere, il componente <xref:System.Windows.Forms.ImageList> viene popolato con le immagini prima che sia associato a un controllo, ma ciò non è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="01f74-107">Typically you populate the <xref:System.Windows.Forms.ImageList> component with images before it is associated with a control, but this is not required.</span></span>

### <a name="to-add-or-remove-images-by-using-the-properties-window"></a><span data-ttu-id="01f74-108">Per aggiungere o rimuovere immagini tramite il Finestra Proprietà</span><span class="sxs-lookup"><span data-stu-id="01f74-108">To add or remove images by using the Properties window</span></span>

1. <span data-ttu-id="01f74-109">Selezionare il componente <xref:System.Windows.Forms.ImageList> o aggiungerne uno al modulo.</span><span class="sxs-lookup"><span data-stu-id="01f74-109">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>

2. <span data-ttu-id="01f74-110">Nella Finestra Proprietà fare clic sul pulsante con i puntini di sospensione (![pulsante con i puntini di sospensione (...) nella Finestra Proprietà di Visual Studio.](./media/visual-studio-ellipsis-button.png)) accanto alla proprietà <xref:System.Windows.Forms.ImageList.Images%2A>.</span><span class="sxs-lookup"><span data-stu-id="01f74-110">In the Properties window, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.ImageList.Images%2A> property.</span></span>

3. <span data-ttu-id="01f74-111">**Nell'Editor raccolta immagini**fare clic su **Aggiungi** o **Rimuovi** per aggiungere o rimuovere immagini dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="01f74-111">In the **Image Collection Editor**, click **Add** or **Remove** to add or remove images from the list.</span></span>

### <a name="to-add-or-remove-images-using-the-smart-tag"></a><span data-ttu-id="01f74-112">Per aggiungere o rimuovere immagini tramite lo smart tag</span><span class="sxs-lookup"><span data-stu-id="01f74-112">To add or remove images using the smart tag</span></span>

1. <span data-ttu-id="01f74-113">Selezionare il componente <xref:System.Windows.Forms.ImageList> o aggiungerne uno al modulo.</span><span class="sxs-lookup"><span data-stu-id="01f74-113">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>

2. <span data-ttu-id="01f74-114">Fare clic sul glifo azioni della finestra di progettazione (</span><span class="sxs-lookup"><span data-stu-id="01f74-114">Click the designer actions glyph (</span></span>![Piccola freccia nera](./media/designer-actions-glyph.gif)<span data-ttu-id="01f74-116">)</span><span class="sxs-lookup"><span data-stu-id="01f74-116">)</span></span>

3. <span data-ttu-id="01f74-117">Nella finestra di dialogo **attività ImageList** selezionare **Scegli Immagini**.</span><span class="sxs-lookup"><span data-stu-id="01f74-117">In the **ImageList Tasks** dialog box, select **Choose Images**.</span></span>

4. <span data-ttu-id="01f74-118">Nell' **Editor dell'insieme immagini** fare clic su **Aggiungi** o **Rimuovi** per aggiungere o rimuovere immagini dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="01f74-118">In the **Images Collection Editor** click **Add** or **Remove** to add or remove images from the list.</span></span>

## <a name="see-also"></a><span data-ttu-id="01f74-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01f74-119">See also</span></span>

- [<span data-ttu-id="01f74-120">Immagini, bitmap e metafile</span><span class="sxs-lookup"><span data-stu-id="01f74-120">Images, Bitmaps, and Metafiles</span></span>](../advanced/images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="01f74-121">Procedura dettagliata: eseguire attività comuni utilizzando le azioni della finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="01f74-121">Walkthrough: Perform common tasks using designer actions</span></span>](perform-common-tasks-design-actions.md)
- [<span data-ttu-id="01f74-122">Componente ImageList</span><span class="sxs-lookup"><span data-stu-id="01f74-122">ImageList Component</span></span>](imagelist-component-windows-forms.md)
