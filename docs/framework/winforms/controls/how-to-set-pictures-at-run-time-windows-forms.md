---
title: 'Procedura: impostare le immagini in fase di esecuzione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- pictures [Windows Forms], setting display
- examples [Windows Forms], PictureBox control
- bitmaps [Windows Forms], displaying in PictureBox control [Windows Forms]
- PictureBox control [Windows Forms], adding images
- images [Windows Forms], adding with PictureBox control [Windows Forms]
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 18ca41d0-68a5-4660-985e-a6c1fbc01d76
ms.openlocfilehash: bd0509c05fd9c1cfc0c631fcd613c64d20296f6b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746741"
---
# <a name="how-to-set-pictures-at-run-time-windows-forms"></a><span data-ttu-id="3f668-102">Procedura: impostare le immagini in fase di esecuzione (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="3f668-102">How to: Set Pictures at Run Time (Windows Forms)</span></span>
<span data-ttu-id="3f668-103">È possibile impostare a livello di codice l'immagine visualizzata da un Windows Forms controllo <xref:System.Windows.Forms.PictureBox>.</span><span class="sxs-lookup"><span data-stu-id="3f668-103">You can programmatically set the image displayed by a Windows Forms <xref:System.Windows.Forms.PictureBox> control.</span></span>  
  
### <a name="to-set-a-picture-programmatically"></a><span data-ttu-id="3f668-104">Per impostare un'immagine a livello di codice</span><span class="sxs-lookup"><span data-stu-id="3f668-104">To set a picture programmatically</span></span>  
  
- <span data-ttu-id="3f668-105">Impostare la proprietà <xref:System.Windows.Forms.PictureBox.Image%2A> utilizzando il metodo <xref:System.Drawing.Image.FromFile%2A> della classe <xref:System.Drawing.Image>.</span><span class="sxs-lookup"><span data-stu-id="3f668-105">Set the <xref:System.Windows.Forms.PictureBox.Image%2A> property using the <xref:System.Drawing.Image.FromFile%2A> method of the <xref:System.Drawing.Image> class.</span></span>  
  
     <span data-ttu-id="3f668-106">Nell'esempio seguente, il percorso impostato per il percorso dell'immagine è la cartella documenti.</span><span class="sxs-lookup"><span data-stu-id="3f668-106">In the example below, the path set for the location of the image is the My Documents folder.</span></span> <span data-ttu-id="3f668-107">Questa operazione viene eseguita perché è possibile presupporre che la maggior parte dei computer che eseguono il sistema operativo Windows includa questa directory.</span><span class="sxs-lookup"><span data-stu-id="3f668-107">This is done, because you can assume that most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="3f668-108">Ciò consente inoltre agli utenti del sistema con livelli di accesso minimo di eseguire l'applicazione senza problemi.</span><span class="sxs-lookup"><span data-stu-id="3f668-108">This also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="3f668-109">Nell'esempio seguente si presuppone un modulo con un controllo <xref:System.Windows.Forms.PictureBox> già aggiunto.</span><span class="sxs-lookup"><span data-stu-id="3f668-109">The example below assumes a form with a <xref:System.Windows.Forms.PictureBox> control already added.</span></span>  
  
    ```vb  
    Private Sub LoadNewPict()  
       ' You should replace the bold image   
       ' in the sample below with an icon of your own choosing.  
       PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
    End Sub  
    ```  
  
    ```csharp  
    private void LoadNewPict(){  
       // You should replace the bold image   
       // in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       pictureBox1.Image = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
    }  
    ```  
  
    ```cpp  
    private:  
       void LoadNewPict()  
       {  
          // You should replace the bold image   
          // in the sample below with an icon of your own choosing.  
          pictureBox1->Image = Image::FromFile(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
       }  
    ```  
  
### <a name="to-clear-a-graphic"></a><span data-ttu-id="3f668-110">Per cancellare una rappresentazione grafica</span><span class="sxs-lookup"><span data-stu-id="3f668-110">To clear a graphic</span></span>  
  
- <span data-ttu-id="3f668-111">Per prima cosa, rilasciare la memoria usata dall'immagine, quindi deselezionare la rappresentazione grafica.</span><span class="sxs-lookup"><span data-stu-id="3f668-111">First, release the memory being used by the image, and then clear the graphic.</span></span> <span data-ttu-id="3f668-112">Il processo di Garbage Collection libera la memoria in un secondo momento se la gestione della memoria costituisce un problema.</span><span class="sxs-lookup"><span data-stu-id="3f668-112">Garbage collection will free up the memory later if memory management becomes a problem.</span></span>  
  
    ```vb  
    If Not (PictureBox1.Image Is Nothing) Then  
       PictureBox1.Image.Dispose()  
       PictureBox1.Image = Nothing  
    End If  
    ```  
  
    ```csharp  
    if (pictureBox1.Image != null)   
    {  
       pictureBox1.Image.Dispose();  
       pictureBox1.Image = null;  
    }  
    ```  
  
    ```cpp  
    if (pictureBox1->Image != nullptr)  
    {  
       pictureBox1->Image->Dispose();  
       pictureBox1->Image = nullptr;  
    }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="3f668-113">Per altre informazioni sui motivi per cui è necessario usare il metodo <xref:System.Drawing.Image.Dispose%2A> in questo modo, vedere [pulizia delle risorse non gestite](../../../standard/garbage-collection/unmanaged.md).</span><span class="sxs-lookup"><span data-stu-id="3f668-113">For more information on why you should use the <xref:System.Drawing.Image.Dispose%2A> method in this way, see [Cleaning Up Unmanaged Resources](../../../standard/garbage-collection/unmanaged.md).</span></span>  
  
     <span data-ttu-id="3f668-114">Questo codice cancellerà l'immagine anche se un grafico è stato caricato nel controllo in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="3f668-114">This code will clear the image even if a graphic was loaded into the control at design time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f668-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f668-115">See also</span></span>

- <xref:System.Windows.Forms.PictureBox>
- <xref:System.Drawing.Image.FromFile%2A?displayProperty=nameWithType>
- [<span data-ttu-id="3f668-116">Panoramica sul controllo PictureBox</span><span class="sxs-lookup"><span data-stu-id="3f668-116">PictureBox Control Overview</span></span>](picturebox-control-overview-windows-forms.md)
- [<span data-ttu-id="3f668-117">Procedura: Caricare un'immagine usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="3f668-117">How to: Load a Picture Using the Designer</span></span>](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [<span data-ttu-id="3f668-118">Procedura: Modificare le dimensioni o la posizione di un'immagine in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="3f668-118">How to: Modify the Size or Placement of a Picture at Run Time</span></span>](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [<span data-ttu-id="3f668-119">Controllo PictureBox</span><span class="sxs-lookup"><span data-stu-id="3f668-119">PictureBox Control</span></span>](picturebox-control-windows-forms.md)
