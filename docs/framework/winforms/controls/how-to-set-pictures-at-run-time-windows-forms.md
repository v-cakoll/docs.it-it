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
ms.openlocfilehash: cd599ac7e07b5210f8bcff1ffbc76b3d9ee563d7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182112"
---
# <a name="how-to-set-pictures-at-run-time-windows-forms"></a><span data-ttu-id="63171-102">Procedura: impostare le immagini in fase di esecuzione (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="63171-102">How to: Set Pictures at Run Time (Windows Forms)</span></span>
<span data-ttu-id="63171-103">È possibile impostare a livello di <xref:System.Windows.Forms.PictureBox> codice l'immagine visualizzata da un controllo Windows Form.You can programmatically set the image displayed by a Windows Forms control.</span><span class="sxs-lookup"><span data-stu-id="63171-103">You can programmatically set the image displayed by a Windows Forms <xref:System.Windows.Forms.PictureBox> control.</span></span>  
  
### <a name="to-set-a-picture-programmatically"></a><span data-ttu-id="63171-104">Per impostare un'immagine a livello di codiceTo set a picture programmatically</span><span class="sxs-lookup"><span data-stu-id="63171-104">To set a picture programmatically</span></span>  
  
- <span data-ttu-id="63171-105">Impostare <xref:System.Windows.Forms.PictureBox.Image%2A> la <xref:System.Drawing.Image.FromFile%2A> proprietà utilizzando <xref:System.Drawing.Image> il metodo della classe .</span><span class="sxs-lookup"><span data-stu-id="63171-105">Set the <xref:System.Windows.Forms.PictureBox.Image%2A> property using the <xref:System.Drawing.Image.FromFile%2A> method of the <xref:System.Drawing.Image> class.</span></span>  
  
     <span data-ttu-id="63171-106">Nell'esempio seguente, il percorso impostato per il percorso dell'immagine è la cartella Documenti.</span><span class="sxs-lookup"><span data-stu-id="63171-106">In the example below, the path set for the location of the image is the My Documents folder.</span></span> <span data-ttu-id="63171-107">Questo viene fatto, perché si può supporre che la maggior parte dei computer che eseguono il sistema operativo Windows includerà questa directory.</span><span class="sxs-lookup"><span data-stu-id="63171-107">This is done, because you can assume that most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="63171-108">Ciò consente inoltre agli utenti del sistema con livelli di accesso minimo di eseguire l'applicazione senza problemi.</span><span class="sxs-lookup"><span data-stu-id="63171-108">This also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="63171-109">Nell'esempio riportato di <xref:System.Windows.Forms.PictureBox> seguito si presuppone che un form con un controllo sia già stato aggiunto.</span><span class="sxs-lookup"><span data-stu-id="63171-109">The example below assumes a form with a <xref:System.Windows.Forms.PictureBox> control already added.</span></span>  
  
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
  
### <a name="to-clear-a-graphic"></a><span data-ttu-id="63171-110">Per cancellare un elemento grafico</span><span class="sxs-lookup"><span data-stu-id="63171-110">To clear a graphic</span></span>  
  
- <span data-ttu-id="63171-111">Rilasciare innanzitutto la memoria utilizzata dall'immagine, quindi cancellare l'elemento grafico.</span><span class="sxs-lookup"><span data-stu-id="63171-111">First, release the memory being used by the image, and then clear the graphic.</span></span> <span data-ttu-id="63171-112">Garbage Collection rilascerà la memoria in un secondo momento se la gestione della memoria diventa un problema.</span><span class="sxs-lookup"><span data-stu-id="63171-112">Garbage collection will free up the memory later if memory management becomes a problem.</span></span>  
  
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
    > <span data-ttu-id="63171-113">Per ulteriori informazioni sui motivi <xref:System.Drawing.Image.Dispose%2A> per cui è necessario utilizzare il metodo in questo modo, vedere [Pulizia delle risorse non gestite](../../../standard/garbage-collection/unmanaged.md).</span><span class="sxs-lookup"><span data-stu-id="63171-113">For more information on why you should use the <xref:System.Drawing.Image.Dispose%2A> method in this way, see [Cleaning Up Unmanaged Resources](../../../standard/garbage-collection/unmanaged.md).</span></span>  
  
     <span data-ttu-id="63171-114">Questo codice cancellerà l'immagine anche se un elemento grafico è stato caricato nel controllo in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="63171-114">This code will clear the image even if a graphic was loaded into the control at design time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63171-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63171-115">See also</span></span>

- <xref:System.Windows.Forms.PictureBox>
- <xref:System.Drawing.Image.FromFile%2A?displayProperty=nameWithType>
- [<span data-ttu-id="63171-116">Cenni preliminari sul controllo PictureBox</span><span class="sxs-lookup"><span data-stu-id="63171-116">PictureBox Control Overview</span></span>](picturebox-control-overview-windows-forms.md)
- [<span data-ttu-id="63171-117">Procedura: caricare un'immagine utilizzando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="63171-117">How to: Load a Picture Using the Designer</span></span>](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [<span data-ttu-id="63171-118">Procedura: modificare le dimensioni o la posizione di un'immagine in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="63171-118">How to: Modify the Size or Placement of a Picture at Run Time</span></span>](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [<span data-ttu-id="63171-119">Controllo PictureBox</span><span class="sxs-lookup"><span data-stu-id="63171-119">PictureBox Control</span></span>](picturebox-control-windows-forms.md)
