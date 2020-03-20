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
ms.openlocfilehash: fea813d7b9fe585e35b729b8b64e3a5f414ef76d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141966"
---
# <a name="how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms"></a><span data-ttu-id="71ffb-102">Procedura: modificare le dimensioni o la posizione di un'immagine in fase di esecuzione (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="71ffb-102">How to: Modify the Size or Placement of a Picture at Run Time (Windows Forms)</span></span>
<span data-ttu-id="71ffb-103">Se si utilizza <xref:System.Windows.Forms.PictureBox> il controllo Windows Form in <xref:System.Windows.Forms.PictureBox.SizeMode%2A> un form, è possibile impostare la proprietà su di esso su:</span><span class="sxs-lookup"><span data-stu-id="71ffb-103">If you use the Windows Forms <xref:System.Windows.Forms.PictureBox> control on a form, you can set the <xref:System.Windows.Forms.PictureBox.SizeMode%2A> property on it to:</span></span>  
  
- <span data-ttu-id="71ffb-104">Allineare l'angolo superiore sinistro dell'immagine con l'angolo superiore sinistro del controllo</span><span class="sxs-lookup"><span data-stu-id="71ffb-104">Align the picture's upper left corner with the control's upper left corner</span></span>  
  
- <span data-ttu-id="71ffb-105">Centrare l'immagine all'interno del controllo</span><span class="sxs-lookup"><span data-stu-id="71ffb-105">Center the picture within the control</span></span>  
  
- <span data-ttu-id="71ffb-106">Regolare le dimensioni del controllo per adattarlo all'immagine visualizzata</span><span class="sxs-lookup"><span data-stu-id="71ffb-106">Adjust the size of the control to fit the picture it displays</span></span>  
  
- <span data-ttu-id="71ffb-107">Allungare qualsiasi immagine visualizzata per adattarla al controllo</span><span class="sxs-lookup"><span data-stu-id="71ffb-107">Stretch any picture it displays to fit the control</span></span>  
  
 <span data-ttu-id="71ffb-108">L'allungamento di un'immagine (in particolare una in formato bitmap) può produrre una perdita di qualità dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="71ffb-108">Stretching a picture (especially one in bitmap format) can produce a loss in image quality.</span></span> <span data-ttu-id="71ffb-109">I metafile, che sono elenchi di istruzioni grafiche per disegnare immagini in fase di esecuzione, sono più adatti per l'allungamento rispetto alle bitmap.</span><span class="sxs-lookup"><span data-stu-id="71ffb-109">Metafiles, which are lists of graphics instructions for drawing images at run time, are better suited for stretching than bitmaps are.</span></span>  
  
### <a name="to-set-the-sizemode-property-at-run-time"></a><span data-ttu-id="71ffb-110">Per impostare la proprietà SizeMode in fase di esecuzioneTo set the SizeMode property at run time</span><span class="sxs-lookup"><span data-stu-id="71ffb-110">To set the SizeMode property at run time</span></span>  
  
1. <span data-ttu-id="71ffb-111"><xref:System.Windows.Forms.PictureBox.SizeMode%2A> Impostare su <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (impostazione <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>predefinita), , <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>o <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>.</span><span class="sxs-lookup"><span data-stu-id="71ffb-111">Set <xref:System.Windows.Forms.PictureBox.SizeMode%2A> to <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (the default), <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>, <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>, or <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>.</span></span> <span data-ttu-id="71ffb-112"><xref:System.Windows.Forms.PictureBoxSizeMode.Normal>indica che l'immagine viene posizionata nell'angolo superiore sinistro del controllo; se l'immagine è più grande del controllo, i bordi inferiore e destro vengono ritagliati.</span><span class="sxs-lookup"><span data-stu-id="71ffb-112"><xref:System.Windows.Forms.PictureBoxSizeMode.Normal> means that the image is placed in the control's upper-left corner; if the image is larger than the control, its lower and right edges are clipped.</span></span> <span data-ttu-id="71ffb-113"><xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>indica che l'immagine è centrata all'interno del controllo; se l'immagine è più grande del controllo, i bordi esterni dell'immagine vengono ritagliati.</span><span class="sxs-lookup"><span data-stu-id="71ffb-113"><xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage> means that the image is centered within the control; if the image is larger than the control, the picture's outside edges are clipped.</span></span> <span data-ttu-id="71ffb-114"><xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>indica che le dimensioni del controllo vengono regolate in base alle dimensioni dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="71ffb-114"><xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> means that the size of the control is adjusted to the size of the image.</span></span> <span data-ttu-id="71ffb-115"><xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>è il contrario e significa che le dimensioni dell'immagine vengono regolate in base alle dimensioni del controllo.</span><span class="sxs-lookup"><span data-stu-id="71ffb-115"><xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage> is the reverse, and means that the size of the image is adjusted to the size of the control.</span></span>  
  
     <span data-ttu-id="71ffb-116">Nell'esempio seguente, il percorso impostato per il percorso dell'immagine è la cartella Documenti.</span><span class="sxs-lookup"><span data-stu-id="71ffb-116">In the example below, the path set for the location of the image is the My Documents folder.</span></span> <span data-ttu-id="71ffb-117">Questo viene fatto, perché si può supporre che la maggior parte dei computer che eseguono il sistema operativo Windows includerà questa directory.</span><span class="sxs-lookup"><span data-stu-id="71ffb-117">This is done, because you can assume that most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="71ffb-118">Ciò consente inoltre agli utenti del sistema con livelli di accesso minimo di eseguire l'applicazione senza problemi.</span><span class="sxs-lookup"><span data-stu-id="71ffb-118">This also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="71ffb-119">Nell'esempio riportato di <xref:System.Windows.Forms.PictureBox> seguito si presuppone che un form con un controllo sia già stato aggiunto.</span><span class="sxs-lookup"><span data-stu-id="71ffb-119">The example below assumes a form with a <xref:System.Windows.Forms.PictureBox> control already added.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="71ffb-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="71ffb-120">See also</span></span>

- <xref:System.Windows.Forms.PictureBox>
- [<span data-ttu-id="71ffb-121">Procedura: caricare un'immagine utilizzando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="71ffb-121">How to: Load a Picture Using the Designer</span></span>](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [<span data-ttu-id="71ffb-122">Cenni preliminari sul controllo PictureBox</span><span class="sxs-lookup"><span data-stu-id="71ffb-122">PictureBox Control Overview</span></span>](picturebox-control-overview-windows-forms.md)
- [<span data-ttu-id="71ffb-123">Procedura: impostare le immagini in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="71ffb-123">How to: Set Pictures at Run Time</span></span>](how-to-set-pictures-at-run-time-windows-forms.md)
- [<span data-ttu-id="71ffb-124">Controllo PictureBox</span><span class="sxs-lookup"><span data-stu-id="71ffb-124">PictureBox Control</span></span>](picturebox-control-windows-forms.md)
