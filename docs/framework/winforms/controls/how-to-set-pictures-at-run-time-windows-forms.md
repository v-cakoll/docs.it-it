---
title: 'Procedura: Impostare le immagini in fase di esecuzione (Windows Form)'
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
ms.openlocfilehash: 8275961a8f11332a04f89561fac779f4cdf9f8d8
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64609406"
---
# <a name="how-to-set-pictures-at-run-time-windows-forms"></a><span data-ttu-id="65fe2-102">Procedura: Impostare le immagini in fase di esecuzione (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="65fe2-102">How to: Set Pictures at Run Time (Windows Forms)</span></span>
<span data-ttu-id="65fe2-103">È possibile impostare a livello di codice l'immagine visualizzata da un controllo Windows Form <xref:System.Windows.Forms.PictureBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="65fe2-103">You can programmatically set the image displayed by a Windows Forms <xref:System.Windows.Forms.PictureBox> control.</span></span>  
  
### <a name="to-set-a-picture-programmatically"></a><span data-ttu-id="65fe2-104">Per impostare un'immagine a livello di codice</span><span class="sxs-lookup"><span data-stu-id="65fe2-104">To set a picture programmatically</span></span>  
  
- <span data-ttu-id="65fe2-105">Impostare il <xref:System.Windows.Forms.PictureBox.Image%2A> proprietà utilizzando il <xref:System.Drawing.Image.FromFile%2A> metodo il <xref:System.Drawing.Image> classe.</span><span class="sxs-lookup"><span data-stu-id="65fe2-105">Set the <xref:System.Windows.Forms.PictureBox.Image%2A> property using the <xref:System.Drawing.Image.FromFile%2A> method of the <xref:System.Drawing.Image> class.</span></span>  
  
     <span data-ttu-id="65fe2-106">Nell'esempio seguente, il percorso impostato per la posizione dell'immagine è la cartella documenti.</span><span class="sxs-lookup"><span data-stu-id="65fe2-106">In the example below, the path set for the location of the image is the My Documents folder.</span></span> <span data-ttu-id="65fe2-107">Questa operazione viene eseguita, perché si presume che la maggior parte dei computer che eseguono il sistema operativo Windows sarà inclusa questa directory.</span><span class="sxs-lookup"><span data-stu-id="65fe2-107">This is done, because you can assume that most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="65fe2-108">Ciò consente inoltre agli utenti del sistema con livelli di accesso minimo di eseguire l'applicazione senza problemi.</span><span class="sxs-lookup"><span data-stu-id="65fe2-108">This also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="65fe2-109">L'esempio seguente si presuppone un form con un <xref:System.Windows.Forms.PictureBox> controllo già aggiunto.</span><span class="sxs-lookup"><span data-stu-id="65fe2-109">The example below assumes a form with a <xref:System.Windows.Forms.PictureBox> control already added.</span></span>  
  
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
  
### <a name="to-clear-a-graphic"></a><span data-ttu-id="65fe2-110">Per cancellare un'immagine</span><span class="sxs-lookup"><span data-stu-id="65fe2-110">To clear a graphic</span></span>  
  
- <span data-ttu-id="65fe2-111">In primo luogo, rilasciare la memoria utilizzata dall'immagine e quindi deselezionare l'icona.</span><span class="sxs-lookup"><span data-stu-id="65fe2-111">First, release the memory being used by the image, and then clear the graphic.</span></span> <span data-ttu-id="65fe2-112">Operazione di Garbage collection consente di liberare la memoria in un secondo momento se la gestione della memoria diventa un problema.</span><span class="sxs-lookup"><span data-stu-id="65fe2-112">Garbage collection will free up the memory later if memory management becomes a problem.</span></span>  
  
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
    >  <span data-ttu-id="65fe2-113">Per altre informazioni sui motivi per cui è consigliabile usare la <xref:System.Drawing.Image.Dispose%2A> metodo in questo modo, vedere [pulizia di risorse non gestite](../../../standard/garbage-collection/unmanaged.md).</span><span class="sxs-lookup"><span data-stu-id="65fe2-113">For more information on why you should use the <xref:System.Drawing.Image.Dispose%2A> method in this way, see [Cleaning Up Unmanaged Resources](../../../standard/garbage-collection/unmanaged.md).</span></span>  
  
     <span data-ttu-id="65fe2-114">Questo codice verrà cancellata l'immagine, anche se un oggetto grafico è stato caricato nel controllo in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="65fe2-114">This code will clear the image even if a graphic was loaded into the control at design time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65fe2-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65fe2-115">See also</span></span>

- <xref:System.Windows.Forms.PictureBox>
- <xref:System.Drawing.Image.FromFile%2A?displayProperty=nameWithType>
- [<span data-ttu-id="65fe2-116">Panoramica sul controllo PictureBox</span><span class="sxs-lookup"><span data-stu-id="65fe2-116">PictureBox Control Overview</span></span>](picturebox-control-overview-windows-forms.md)
- [<span data-ttu-id="65fe2-117">Procedura: Caricare un'immagine utilizzando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="65fe2-117">How to: Load a Picture Using the Designer</span></span>](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [<span data-ttu-id="65fe2-118">Procedura: Modificare le dimensioni o la posizione di un'immagine in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="65fe2-118">How to: Modify the Size or Placement of a Picture at Run Time</span></span>](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [<span data-ttu-id="65fe2-119">Controllo PictureBox</span><span class="sxs-lookup"><span data-stu-id="65fe2-119">PictureBox Control</span></span>](picturebox-control-windows-forms.md)
