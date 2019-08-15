---
title: 'Procedura: Aggiungere o rimuovere immagini ImageList con la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- ImageList component [Windows Forms], adding images
- ImageList component [Windows Forms], removing images
- images [Windows Forms], adding to ImageList component
ms.assetid: 5699b244-e37c-4d20-bc35-7441e55c1e3a
ms.openlocfilehash: 63692a797ad49f0adc3a0c5b0bfff1aebbc65257
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2019
ms.locfileid: "69038273"
---
# <a name="how-to-add-or-remove-imagelist-images-with-the-designer"></a><span data-ttu-id="a99e0-102">Procedura: Aggiungere o rimuovere immagini ImageList con la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="a99e0-102">How to: Add or Remove ImageList Images with the Designer</span></span>

<span data-ttu-id="a99e0-103">È possibile aggiungere immagini a un <xref:System.Windows.Forms.ImageList> componente in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="a99e0-103">You can add images to an <xref:System.Windows.Forms.ImageList> component several different ways.</span></span> <span data-ttu-id="a99e0-104">È possibile aggiungere immagini molto rapidamente usando lo smart tag associato a <xref:System.Windows.Forms.ImageList>o, se si impostano diverse altre proprietà <xref:System.Windows.Forms.ImageList>in, potrebbe risultare più comodo aggiungere immagini con la finestra Proprietà.</span><span class="sxs-lookup"><span data-stu-id="a99e0-104">You can add images very quickly by using the smart tag associated with the <xref:System.Windows.Forms.ImageList>, or if you are setting several other properties on the <xref:System.Windows.Forms.ImageList>, you may find it more convenient to add images with the Properties window.</span></span> <span data-ttu-id="a99e0-105">È anche possibile aggiungere immagini usando il codice.</span><span class="sxs-lookup"><span data-stu-id="a99e0-105">You can also add images by using code.</span></span> <span data-ttu-id="a99e0-106">Per ulteriori informazioni su come aggiungere immagini con il codice, vedere [procedura: Aggiungere o rimuovere immagini con il componente](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)Windows Forms ImageList.</span><span class="sxs-lookup"><span data-stu-id="a99e0-106">For more information about how to add images with code, see [How to: Add or Remove Images with the Windows Forms ImageList Component](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span> <span data-ttu-id="a99e0-107">In genere, il <xref:System.Windows.Forms.ImageList> componente viene popolato con le immagini prima che sia associato a un controllo, ma ciò non è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a99e0-107">Typically you populate the <xref:System.Windows.Forms.ImageList> component with images before it is associated with a control, but this is not required.</span></span>


### <a name="to-add-or-remove-images-by-using-the-properties-window"></a><span data-ttu-id="a99e0-108">Per aggiungere o rimuovere immagini tramite il Finestra Proprietà</span><span class="sxs-lookup"><span data-stu-id="a99e0-108">To add or remove images by using the Properties window</span></span>

1. <span data-ttu-id="a99e0-109">Selezionare il <xref:System.Windows.Forms.ImageList> componente o aggiungerne uno al modulo.</span><span class="sxs-lookup"><span data-stu-id="a99e0-109">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>

2. <span data-ttu-id="a99e0-110">Nella finestra Proprietà fare clic sul pulsante con i puntini di sospensione (![pulsante con i puntini di sospensione (...) nell'finestra proprietà di Visual Studio.](./media/visual-studio-ellipsis-button.png)) accanto alla <xref:System.Windows.Forms.ImageList.Images%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="a99e0-110">In the Properties window, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.ImageList.Images%2A> property.</span></span>

3. <span data-ttu-id="a99e0-111">**Nell'Editor raccolta immagini**fare clic su **Aggiungi** o **Rimuovi** per aggiungere o rimuovere immagini dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="a99e0-111">In the **Image Collection Editor**, click **Add** or **Remove** to add or remove images from the list.</span></span>

### <a name="to-add-or-remove-images-using-the-smart-tag"></a><span data-ttu-id="a99e0-112">Per aggiungere o rimuovere immagini tramite lo smart tag</span><span class="sxs-lookup"><span data-stu-id="a99e0-112">To add or remove images using the smart tag</span></span>

1. <span data-ttu-id="a99e0-113">Selezionare il <xref:System.Windows.Forms.ImageList> componente o aggiungerne uno al modulo.</span><span class="sxs-lookup"><span data-stu-id="a99e0-113">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>

2. <span data-ttu-id="a99e0-114">Fare clic sul glifo smart tag (![glifo smart tag](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))</span><span class="sxs-lookup"><span data-stu-id="a99e0-114">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))</span></span>

3. <span data-ttu-id="a99e0-115">Nella finestra di dialogo **attività ImageList** selezionare **Scegli Immagini**.</span><span class="sxs-lookup"><span data-stu-id="a99e0-115">In the **ImageList Tasks** dialog box, select **Choose Images**.</span></span>

4. <span data-ttu-id="a99e0-116">Nell' **Editor dell'insieme immagini** fare clic su **Aggiungi** o **Rimuovi** per aggiungere o rimuovere immagini dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="a99e0-116">In the **Images Collection Editor** click **Add** or **Remove** to add or remove images from the list.</span></span>

## <a name="see-also"></a><span data-ttu-id="a99e0-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a99e0-117">See also</span></span>

- [<span data-ttu-id="a99e0-118">Immagini, bitmap e metafile</span><span class="sxs-lookup"><span data-stu-id="a99e0-118">Images, Bitmaps, and Metafiles</span></span>](../advanced/images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="a99e0-119">Procedura dettagliata: Esecuzione di attività comuni tramite smart tag sui controlli Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a99e0-119">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>](performing-common-tasks-using-smart-tags-on-wf-controls.md)
- [<span data-ttu-id="a99e0-120">Componente ImageList</span><span class="sxs-lookup"><span data-stu-id="a99e0-120">ImageList Component</span></span>](imagelist-component-windows-forms.md)
