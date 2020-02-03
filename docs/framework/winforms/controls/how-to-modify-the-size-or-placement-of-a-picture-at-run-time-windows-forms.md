---
title: "Procedura: modificare le dimensioni o la posizione di un'immagine in fase di esecuzione"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- images [Windows Forms], controlling placement in PictureBox control [Windows Forms]
- examples [Windows Forms], PictureBox control
- PictureBox control [Windows Forms], picture size and alignment
- pictures [Windows Forms], controlling placement in PictureBox control [Windows Forms]
ms.assetid: d0b332a3-fae2-4891-957c-dc3e17743326
ms.openlocfilehash: 9bb094ce0b7945f23a2e9b8614e56c9492d5f832
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736030"
---
# <a name="how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms"></a><span data-ttu-id="e6142-102">Procedura: modificare le dimensioni o la posizione di un'immagine in fase di esecuzione (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="e6142-102">How to: Modify the Size or Placement of a Picture at Run Time (Windows Forms)</span></span>
<span data-ttu-id="e6142-103">Se si usa il controllo Windows Forms <xref:System.Windows.Forms.PictureBox> in un modulo, è possibile impostare la proprietà <xref:System.Windows.Forms.PictureBox.SizeMode%2A> su di esso per:</span><span class="sxs-lookup"><span data-stu-id="e6142-103">If you use the Windows Forms <xref:System.Windows.Forms.PictureBox> control on a form, you can set the <xref:System.Windows.Forms.PictureBox.SizeMode%2A> property on it to:</span></span>  
  
- <span data-ttu-id="e6142-104">Allinea l'angolo superiore sinistro dell'immagine all'angolo superiore sinistro del controllo</span><span class="sxs-lookup"><span data-stu-id="e6142-104">Align the picture's upper left corner with the control's upper left corner</span></span>  
  
- <span data-ttu-id="e6142-105">Centrare l'immagine all'interno del controllo</span><span class="sxs-lookup"><span data-stu-id="e6142-105">Center the picture within the control</span></span>  
  
- <span data-ttu-id="e6142-106">Regolare le dimensioni del controllo in modo da adattarle all'immagine visualizzata</span><span class="sxs-lookup"><span data-stu-id="e6142-106">Adjust the size of the control to fit the picture it displays</span></span>  
  
- <span data-ttu-id="e6142-107">Estendi tutte le immagini visualizzate per adattarle al controllo</span><span class="sxs-lookup"><span data-stu-id="e6142-107">Stretch any picture it displays to fit the control</span></span>  
  
 <span data-ttu-id="e6142-108">L'estensione di un'immagine, in particolare un formato bitmap, può causare una perdita di qualità dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="e6142-108">Stretching a picture (especially one in bitmap format) can produce a loss in image quality.</span></span> <span data-ttu-id="e6142-109">I metafile, che sono elenchi di istruzioni grafiche per il disegno di immagini in fase di esecuzione, sono più adatti per l'estensione delle bitmap.</span><span class="sxs-lookup"><span data-stu-id="e6142-109">Metafiles, which are lists of graphics instructions for drawing images at run time, are better suited for stretching than bitmaps are.</span></span>  
  
### <a name="to-set-the-sizemode-property-at-run-time"></a><span data-ttu-id="e6142-110">Per impostare la proprietà SizeMode in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="e6142-110">To set the SizeMode property at run time</span></span>  
  
1. <span data-ttu-id="e6142-111">Impostare <xref:System.Windows.Forms.PictureBox.SizeMode%2A> su <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (impostazione predefinita), <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>, <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>o <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>.</span><span class="sxs-lookup"><span data-stu-id="e6142-111">Set <xref:System.Windows.Forms.PictureBox.SizeMode%2A> to <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (the default), <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>, <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>, or <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>.</span></span> <span data-ttu-id="e6142-112"><xref:System.Windows.Forms.PictureBoxSizeMode.Normal> significa che l'immagine viene posizionata nell'angolo superiore sinistro del controllo; Se l'immagine è più grande del controllo, i bordi inferiore e destro vengono ritagliati.</span><span class="sxs-lookup"><span data-stu-id="e6142-112"><xref:System.Windows.Forms.PictureBoxSizeMode.Normal> means that the image is placed in the control's upper-left corner; if the image is larger than the control, its lower and right edges are clipped.</span></span> <span data-ttu-id="e6142-113"><xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage> significa che l'immagine è centrata all'interno del controllo; Se l'immagine è più grande del controllo, i bordi esterni dell'immagine vengono ritagliati.</span><span class="sxs-lookup"><span data-stu-id="e6142-113"><xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage> means that the image is centered within the control; if the image is larger than the control, the picture's outside edges are clipped.</span></span> <span data-ttu-id="e6142-114"><xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> significa che la dimensione del controllo viene adattata alle dimensioni dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="e6142-114"><xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> means that the size of the control is adjusted to the size of the image.</span></span> <span data-ttu-id="e6142-115"><xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage> è l'inverso e indica che le dimensioni dell'immagine vengono modificate in modo da determinare le dimensioni del controllo.</span><span class="sxs-lookup"><span data-stu-id="e6142-115"><xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage> is the reverse, and means that the size of the image is adjusted to the size of the control.</span></span>  
  
     <span data-ttu-id="e6142-116">Nell'esempio seguente, il percorso impostato per il percorso dell'immagine è la cartella documenti.</span><span class="sxs-lookup"><span data-stu-id="e6142-116">In the example below, the path set for the location of the image is the My Documents folder.</span></span> <span data-ttu-id="e6142-117">Questa operazione viene eseguita perché è possibile presupporre che la maggior parte dei computer che eseguono il sistema operativo Windows includa questa directory.</span><span class="sxs-lookup"><span data-stu-id="e6142-117">This is done, because you can assume that most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="e6142-118">Ciò consente inoltre agli utenti del sistema con livelli di accesso minimo di eseguire l'applicazione senza problemi.</span><span class="sxs-lookup"><span data-stu-id="e6142-118">This also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="e6142-119">Nell'esempio seguente si presuppone un modulo con un controllo <xref:System.Windows.Forms.PictureBox> già aggiunto.</span><span class="sxs-lookup"><span data-stu-id="e6142-119">The example below assumes a form with a <xref:System.Windows.Forms.PictureBox> control already added.</span></span>  
  
    ```vb  
    Private Sub StretchPic()  
       ' Stretch the picture to fit the control.  
       PictureBox1.SizeMode = PictureBoxSizeMode.StretchImage  
       ' Load the picture into the control.  
       ' You should replace the bold image   
       ' in the sample below with an icon of your own choosing.  
       PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
    End Sub  
    ```  
  
    ```csharp  
    private void StretchPic(){  
       // Stretch the picture to fit the control.  
       PictureBox1.SizeMode = PictureBoxSizeMode.StretchImage;  
       // Load the picture into the control.  
       // You should replace the bold image   
       // in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       + @"\Image.gif")  
    }  
    ```  
  
    ```cpp  
    private:  
       void StretchPic()  
       {  
          // Stretch the picture to fit the control.  
          pictureBox1->SizeMode = PictureBoxSizeMode::StretchImage;  
          // Load the picture into the control.  
          // You should replace the bold image   
          // in the sample below with an icon of your own choosing.  
          pictureBox1->Image = Image::FromFile(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e6142-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e6142-120">See also</span></span>

- <xref:System.Windows.Forms.PictureBox>
- [<span data-ttu-id="e6142-121">Procedura: Caricare un'immagine usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="e6142-121">How to: Load a Picture Using the Designer</span></span>](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [<span data-ttu-id="e6142-122">Panoramica sul controllo PictureBox</span><span class="sxs-lookup"><span data-stu-id="e6142-122">PictureBox Control Overview</span></span>](picturebox-control-overview-windows-forms.md)
- [<span data-ttu-id="e6142-123">Procedura: Impostare le immagini in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="e6142-123">How to: Set Pictures at Run Time</span></span>](how-to-set-pictures-at-run-time-windows-forms.md)
- [<span data-ttu-id="e6142-124">Controllo PictureBox</span><span class="sxs-lookup"><span data-stu-id="e6142-124">PictureBox Control</span></span>](picturebox-control-windows-forms.md)
