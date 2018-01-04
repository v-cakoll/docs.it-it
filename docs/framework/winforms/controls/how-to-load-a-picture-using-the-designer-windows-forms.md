---
title: 'Procedura: caricare un''immagine utilizzando la finestra di progettazione (Windows Form)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- picture formats
- images [Windows Forms], displaying on Windows Forms
- pictures [Windows Forms], displaying
- forms [Windows Forms], displaying images
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9ca3e3eef1aa9e7414d3c279de5943585703bf9f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a><span data-ttu-id="da085-102">Procedura: caricare un'immagine utilizzando la finestra di progettazione (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="da085-102">How to: Load a Picture Using the Designer (Windows Forms)</span></span>
<span data-ttu-id="da085-103">Windows Form <xref:System.Windows.Forms.PictureBox> (controllo), è possibile caricare e visualizzare un'immagine in un form in fase di progettazione, impostando il <xref:System.Windows.Forms.PictureBox.Image%2A> proprietà su un'immagine valida.</span><span class="sxs-lookup"><span data-stu-id="da085-103">With the Windows Forms <xref:System.Windows.Forms.PictureBox> control, you can load and display a picture on a form at design time by setting the <xref:System.Windows.Forms.PictureBox.Image%2A> property to a valid picture.</span></span> <span data-ttu-id="da085-104">La tabella seguente illustra i tipi di file consentiti.</span><span class="sxs-lookup"><span data-stu-id="da085-104">The following table shows the acceptable file types.</span></span>  
  
|<span data-ttu-id="da085-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="da085-105">Type</span></span>|<span data-ttu-id="da085-106">Estensione di file</span><span class="sxs-lookup"><span data-stu-id="da085-106">File name extension</span></span>|  
|----------|-------------------------|  
|<span data-ttu-id="da085-107">Bitmap</span><span class="sxs-lookup"><span data-stu-id="da085-107">Bitmap</span></span>|<span data-ttu-id="da085-108">file con estensione bmp</span><span class="sxs-lookup"><span data-stu-id="da085-108">.bmp</span></span>|  
|<span data-ttu-id="da085-109">Icona</span><span class="sxs-lookup"><span data-stu-id="da085-109">Icon</span></span>|<span data-ttu-id="da085-110">ico</span><span class="sxs-lookup"><span data-stu-id="da085-110">.ico</span></span>|  
|<span data-ttu-id="da085-111">GIF</span><span class="sxs-lookup"><span data-stu-id="da085-111">GIF</span></span>|<span data-ttu-id="da085-112">.gif</span><span class="sxs-lookup"><span data-stu-id="da085-112">.gif</span></span>|  
|<span data-ttu-id="da085-113">Metafile</span><span class="sxs-lookup"><span data-stu-id="da085-113">Metafile</span></span>|<span data-ttu-id="da085-114">WMF</span><span class="sxs-lookup"><span data-stu-id="da085-114">.wmf</span></span>|  
|<span data-ttu-id="da085-115">JPEG</span><span class="sxs-lookup"><span data-stu-id="da085-115">JPEG</span></span>|<span data-ttu-id="da085-116">jpg</span><span class="sxs-lookup"><span data-stu-id="da085-116">.jpg</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="da085-117">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="da085-117">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="da085-118">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="da085-118">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="da085-119">Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="da085-119">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-display-a-picture-at-design-time"></a><span data-ttu-id="da085-120">Per visualizzare un'immagine in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="da085-120">To display a picture at design time</span></span>  
  
1.  <span data-ttu-id="da085-121">Disegnare un <xref:System.Windows.Forms.PictureBox> controllo in un form.</span><span class="sxs-lookup"><span data-stu-id="da085-121">Draw a <xref:System.Windows.Forms.PictureBox> control on a form.</span></span>  
  
2.  <span data-ttu-id="da085-122">Nella finestra Proprietà, selezionare il <xref:System.Windows.Forms.PictureBox.Image%2A> proprietà, quindi fare clic sul pulsante con i puntini di sospensione per visualizzare il **aprire** la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="da085-122">On the Properties window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property, then click the ellipsis button to display the **Open** dialog box.</span></span>  
  
3.  <span data-ttu-id="da085-123">Se si sta cercando un tipo di file specifico (ad esempio, il file con estensione gif), selezionarla nel **i file di tipo** casella.</span><span class="sxs-lookup"><span data-stu-id="da085-123">If you are looking for a specific file type (for example, .gif files), select it in the **Files of type** box.</span></span>  
  
4.  <span data-ttu-id="da085-124">Selezionare il file che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="da085-124">Select the file you want to display.</span></span>  
  
### <a name="to-clear-the-picture-at-design-time"></a><span data-ttu-id="da085-125">Per rimuovere l'immagine in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="da085-125">To clear the picture at design time</span></span>  
  
1.  <span data-ttu-id="da085-126">Nel **proprietà** finestra, seleziona il <xref:System.Windows.Forms.PictureBox.Image%2A> proprietà e il pulsante destro del mouse l'immagine di anteprima di piccole dimensioni che viene visualizzato a sinistra del nome dell'oggetto immagine.</span><span class="sxs-lookup"><span data-stu-id="da085-126">On the **Properties** window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property and right-click the small thumbnail image that appears to the left of the name of the image object.</span></span> <span data-ttu-id="da085-127">Scegliere **reimpostare**.</span><span class="sxs-lookup"><span data-stu-id="da085-127">Choose **Reset**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da085-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da085-128">See Also</span></span>  
 <xref:System.Windows.Forms.PictureBox>  
 [<span data-ttu-id="da085-129">Panoramica sul controllo PictureBox</span><span class="sxs-lookup"><span data-stu-id="da085-129">PictureBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)  
 [<span data-ttu-id="da085-130">Procedura: Modificare le dimensioni o la posizione di un'immagine in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="da085-130">How to: Modify the Size or Placement of a Picture at Run Time</span></span>](../../../../docs/framework/winforms/controls/how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)  
 [<span data-ttu-id="da085-131">Procedura: Impostare le immagini in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="da085-131">How to: Set Pictures at Run Time</span></span>](../../../../docs/framework/winforms/controls/how-to-set-pictures-at-run-time-windows-forms.md)  
 [<span data-ttu-id="da085-132">Controllo PictureBox</span><span class="sxs-lookup"><span data-stu-id="da085-132">PictureBox Control</span></span>](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)
