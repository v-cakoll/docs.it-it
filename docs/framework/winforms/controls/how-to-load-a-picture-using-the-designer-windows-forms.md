---
title: "Procedura: Caricare un'immagine utilizzando la finestra di progettazione (Windows Forms)"
ms.date: 03/30/2017
helpviewer_keywords:
- picture formats
- images [Windows Forms], displaying on Windows Forms
- pictures [Windows Forms], displaying
- forms [Windows Forms], displaying images
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
ms.openlocfilehash: 818bc63b5b3bea6c73804f716a72ba3cd1a62b4c
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039686"
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a><span data-ttu-id="75bbf-102">Procedura: Caricare un'immagine utilizzando la finestra di progettazione (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="75bbf-102">How to: Load a Picture Using the Designer (Windows Forms)</span></span>

<span data-ttu-id="75bbf-103">Con il controllo <xref:System.Windows.Forms.PictureBox> Windows Forms è possibile caricare e visualizzare un'immagine in un form in fase di progettazione impostando la <xref:System.Windows.Forms.PictureBox.Image%2A> proprietà su un'immagine valida.</span><span class="sxs-lookup"><span data-stu-id="75bbf-103">With the Windows Forms <xref:System.Windows.Forms.PictureBox> control, you can load and display a picture on a form at design time by setting the <xref:System.Windows.Forms.PictureBox.Image%2A> property to a valid picture.</span></span> <span data-ttu-id="75bbf-104">Nella tabella seguente sono elencati i tipi di file accettabili.</span><span class="sxs-lookup"><span data-stu-id="75bbf-104">The following table shows the acceptable file types.</span></span>

|<span data-ttu-id="75bbf-105">Type</span><span class="sxs-lookup"><span data-stu-id="75bbf-105">Type</span></span>|<span data-ttu-id="75bbf-106">Estensione del file</span><span class="sxs-lookup"><span data-stu-id="75bbf-106">File name extension</span></span>|
|---|---|
|<span data-ttu-id="75bbf-107">Bitmap</span><span class="sxs-lookup"><span data-stu-id="75bbf-107">Bitmap</span></span>|<span data-ttu-id="75bbf-108">.bmp</span><span class="sxs-lookup"><span data-stu-id="75bbf-108">.bmp</span></span>|
|<span data-ttu-id="75bbf-109">Icona</span><span class="sxs-lookup"><span data-stu-id="75bbf-109">Icon</span></span>|<span data-ttu-id="75bbf-110">ico</span><span class="sxs-lookup"><span data-stu-id="75bbf-110">.ico</span></span>|
|<span data-ttu-id="75bbf-111">GIF</span><span class="sxs-lookup"><span data-stu-id="75bbf-111">GIF</span></span>|<span data-ttu-id="75bbf-112">.gif</span><span class="sxs-lookup"><span data-stu-id="75bbf-112">.gif</span></span>|
|<span data-ttu-id="75bbf-113">Metafile</span><span class="sxs-lookup"><span data-stu-id="75bbf-113">Metafile</span></span>|<span data-ttu-id="75bbf-114">.wmf</span><span class="sxs-lookup"><span data-stu-id="75bbf-114">.wmf</span></span>|
|<span data-ttu-id="75bbf-115">JPEG</span><span class="sxs-lookup"><span data-stu-id="75bbf-115">JPEG</span></span>|<span data-ttu-id="75bbf-116">.jpg</span><span class="sxs-lookup"><span data-stu-id="75bbf-116">.jpg</span></span>|

## <a name="to-display-a-picture-at-design-time"></a><span data-ttu-id="75bbf-117">Per visualizzare un'immagine in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="75bbf-117">To display a picture at design time</span></span>

1. <span data-ttu-id="75bbf-118">Creare un <xref:System.Windows.Forms.PictureBox> controllo in un form.</span><span class="sxs-lookup"><span data-stu-id="75bbf-118">Draw a <xref:System.Windows.Forms.PictureBox> control on a form.</span></span>

2. <span data-ttu-id="75bbf-119">Nella finestra **Proprietà** selezionare la <xref:System.Windows.Forms.PictureBox.Image%2A> proprietà, quindi fare clic sul pulsante con i puntini di sospensione per visualizzare la finestra di dialogo **Apri** .</span><span class="sxs-lookup"><span data-stu-id="75bbf-119">In the **Properties** window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property, then select the ellipsis button to display the **Open** dialog box.</span></span>

3. <span data-ttu-id="75bbf-120">Se si sta cercando un tipo di file specifico, ad esempio file con estensione gif, selezionarlo nella casella **file di tipo** .</span><span class="sxs-lookup"><span data-stu-id="75bbf-120">If you're looking for a specific file type (for example, .gif files), select it in the **Files of type** box.</span></span>

4. <span data-ttu-id="75bbf-121">Selezionare il file che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="75bbf-121">Select the file you want to display.</span></span>

## <a name="to-clear-the-picture-at-design-time"></a><span data-ttu-id="75bbf-122">Per cancellare l'immagine in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="75bbf-122">To clear the picture at design time</span></span>

1. <span data-ttu-id="75bbf-123">Nella finestra **Proprietà** selezionare la <xref:System.Windows.Forms.PictureBox.Image%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="75bbf-123">In the **Properties** window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property.</span></span> <span data-ttu-id="75bbf-124">Fare clic con il pulsante destro del mouse sull'immagine di anteprima ridotta che viene visualizzata a sinistra del nome dell'oggetto immagine, quindi scegliere **Reimposta**.</span><span class="sxs-lookup"><span data-stu-id="75bbf-124">Right-click the small thumbnail image that appears to the left of the name of the image object, and then choose **Reset**.</span></span>

## <a name="see-also"></a><span data-ttu-id="75bbf-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75bbf-125">See also</span></span>

- <xref:System.Windows.Forms.PictureBox>
- [<span data-ttu-id="75bbf-126">Panoramica sul controllo PictureBox</span><span class="sxs-lookup"><span data-stu-id="75bbf-126">PictureBox Control Overview</span></span>](picturebox-control-overview-windows-forms.md)
- [<span data-ttu-id="75bbf-127">Procedura: Modificare le dimensioni o la posizione di un'immagine in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="75bbf-127">How to: Modify the Size or Placement of a Picture at Run Time</span></span>](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [<span data-ttu-id="75bbf-128">Procedura: Impostare le immagini in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="75bbf-128">How to: Set Pictures at Run Time</span></span>](how-to-set-pictures-at-run-time-windows-forms.md)
- [<span data-ttu-id="75bbf-129">Controllo PictureBox</span><span class="sxs-lookup"><span data-stu-id="75bbf-129">PictureBox Control</span></span>](picturebox-control-windows-forms.md)
