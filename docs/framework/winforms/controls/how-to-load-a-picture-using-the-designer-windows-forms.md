---
title: "Procedura: caricare un'immagine utilizzando la finestra di progettazione"
description: Informazioni su come usare il controllo PictureBox Windows Forms per caricare e visualizzare un'immagine in un modulo in fase di progettazione.
ms.date: 03/30/2017
helpviewer_keywords:
- picture formats
- images [Windows Forms], displaying on Windows Forms
- pictures [Windows Forms], displaying
- forms [Windows Forms], displaying images
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
ms.openlocfilehash: a05ffe19412fc7a4e3e02f01336d89cce39fac8a
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325598"
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a><span data-ttu-id="baf59-103">Procedura: caricare un'immagine utilizzando la finestra di progettazione (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="baf59-103">How to: Load a Picture Using the Designer (Windows Forms)</span></span>

<span data-ttu-id="baf59-104">Con il <xref:System.Windows.Forms.PictureBox> controllo Windows Forms è possibile caricare e visualizzare un'immagine in un form in fase di progettazione impostando la <xref:System.Windows.Forms.PictureBox.Image%2A> proprietà su un'immagine valida.</span><span class="sxs-lookup"><span data-stu-id="baf59-104">With the Windows Forms <xref:System.Windows.Forms.PictureBox> control, you can load and display a picture on a form at design time by setting the <xref:System.Windows.Forms.PictureBox.Image%2A> property to a valid picture.</span></span> <span data-ttu-id="baf59-105">Nella tabella seguente sono elencati i tipi di file accettabili.</span><span class="sxs-lookup"><span data-stu-id="baf59-105">The following table shows the acceptable file types.</span></span>

|<span data-ttu-id="baf59-106">Type</span><span class="sxs-lookup"><span data-stu-id="baf59-106">Type</span></span>|<span data-ttu-id="baf59-107">Estensione del file</span><span class="sxs-lookup"><span data-stu-id="baf59-107">File name extension</span></span>|
|---|---|
|<span data-ttu-id="baf59-108">Bitmap</span><span class="sxs-lookup"><span data-stu-id="baf59-108">Bitmap</span></span>|<span data-ttu-id="baf59-109">bmp</span><span class="sxs-lookup"><span data-stu-id="baf59-109">.bmp</span></span>|
|<span data-ttu-id="baf59-110">Icona</span><span class="sxs-lookup"><span data-stu-id="baf59-110">Icon</span></span>|<span data-ttu-id="baf59-111">ico</span><span class="sxs-lookup"><span data-stu-id="baf59-111">.ico</span></span>|
|<span data-ttu-id="baf59-112">GIF</span><span class="sxs-lookup"><span data-stu-id="baf59-112">GIF</span></span>|<span data-ttu-id="baf59-113">gif</span><span class="sxs-lookup"><span data-stu-id="baf59-113">.gif</span></span>|
|<span data-ttu-id="baf59-114">Metafile</span><span class="sxs-lookup"><span data-stu-id="baf59-114">Metafile</span></span>|<span data-ttu-id="baf59-115">WMF</span><span class="sxs-lookup"><span data-stu-id="baf59-115">.wmf</span></span>|
|<span data-ttu-id="baf59-116">JPEG</span><span class="sxs-lookup"><span data-stu-id="baf59-116">JPEG</span></span>|<span data-ttu-id="baf59-117">jpg</span><span class="sxs-lookup"><span data-stu-id="baf59-117">.jpg</span></span>|

## <a name="to-display-a-picture-at-design-time"></a><span data-ttu-id="baf59-118">Per visualizzare un'immagine in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="baf59-118">To display a picture at design time</span></span>

1. <span data-ttu-id="baf59-119">Creare un <xref:System.Windows.Forms.PictureBox> controllo in un form.</span><span class="sxs-lookup"><span data-stu-id="baf59-119">Draw a <xref:System.Windows.Forms.PictureBox> control on a form.</span></span>

2. <span data-ttu-id="baf59-120">Nella finestra **Proprietà** selezionare la <xref:System.Windows.Forms.PictureBox.Image%2A> proprietà, quindi fare clic sul pulsante con i puntini di sospensione per visualizzare la finestra di dialogo **Apri** .</span><span class="sxs-lookup"><span data-stu-id="baf59-120">In the **Properties** window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property, then select the ellipsis button to display the **Open** dialog box.</span></span>

3. <span data-ttu-id="baf59-121">Se si sta cercando un tipo di file specifico, ad esempio file con estensione gif, selezionarlo nella casella **file di tipo** .</span><span class="sxs-lookup"><span data-stu-id="baf59-121">If you're looking for a specific file type (for example, .gif files), select it in the **Files of type** box.</span></span>

4. <span data-ttu-id="baf59-122">Selezionare il file che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="baf59-122">Select the file you want to display.</span></span>

## <a name="to-clear-the-picture-at-design-time"></a><span data-ttu-id="baf59-123">Per cancellare l'immagine in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="baf59-123">To clear the picture at design time</span></span>

1. <span data-ttu-id="baf59-124">Nella finestra **Proprietà** selezionare la <xref:System.Windows.Forms.PictureBox.Image%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="baf59-124">In the **Properties** window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property.</span></span> <span data-ttu-id="baf59-125">Fare clic con il pulsante destro del mouse sull'immagine di anteprima ridotta che viene visualizzata a sinistra del nome dell'oggetto immagine, quindi scegliere **Reimposta**.</span><span class="sxs-lookup"><span data-stu-id="baf59-125">Right-click the small thumbnail image that appears to the left of the name of the image object, and then choose **Reset**.</span></span>

## <a name="see-also"></a><span data-ttu-id="baf59-126">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="baf59-126">See also</span></span>

- <xref:System.Windows.Forms.PictureBox>
- [<span data-ttu-id="baf59-127">Cenni preliminari sul controllo PictureBox</span><span class="sxs-lookup"><span data-stu-id="baf59-127">PictureBox Control Overview</span></span>](picturebox-control-overview-windows-forms.md)
- [<span data-ttu-id="baf59-128">Procedura: modificare le dimensioni o la posizione di un'immagine in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="baf59-128">How to: Modify the Size or Placement of a Picture at Run Time</span></span>](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [<span data-ttu-id="baf59-129">Procedura: impostare le immagini in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="baf59-129">How to: Set Pictures at Run Time</span></span>](how-to-set-pictures-at-run-time-windows-forms.md)
- [<span data-ttu-id="baf59-130">Controllo PictureBox</span><span class="sxs-lookup"><span data-stu-id="baf59-130">PictureBox Control</span></span>](picturebox-control-windows-forms.md)
