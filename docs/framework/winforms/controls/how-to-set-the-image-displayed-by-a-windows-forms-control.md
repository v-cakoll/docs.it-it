---
title: "Procedura: impostare l'immagine visualizzata da un controllo Windows Form"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Button control [Windows Forms], images
- Windows Forms controls, images
- controls [Windows Forms], images
- images [Windows Forms], Windows Forms controls
- examples [Windows Forms], controls
ms.assetid: 9445af8f-4f62-48b0-a3f6-068058964b9f
ms.openlocfilehash: 4870f9e2acc48a90e1e2193d514926fedee05f61
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33533741"
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control"></a><span data-ttu-id="566e6-102">Procedura: impostare l'immagine visualizzata da un controllo Windows Form</span><span class="sxs-lookup"><span data-stu-id="566e6-102">How to: Set the Image Displayed by a Windows Forms Control</span></span>
<span data-ttu-id="566e6-103">Vari controlli Windows Form consente di visualizzare immagini.</span><span class="sxs-lookup"><span data-stu-id="566e6-103">Several Windows Forms controls can display images.</span></span> <span data-ttu-id="566e6-104">Queste immagini possono essere le icone che illustrano la finalità del controllo, ad esempio un'icona del dischetto su un pulsante indica il **salvare** comando.</span><span class="sxs-lookup"><span data-stu-id="566e6-104">These images can be icons that clarify the purpose of the control, such as a diskette icon on a button denoting the **Save** command.</span></span> <span data-ttu-id="566e6-105">In alternativa, le icone possono essere immagini di sfondo per fornire il controllo, l'aspetto e il comportamento desiderato.</span><span class="sxs-lookup"><span data-stu-id="566e6-105">Alternatively, the icons can be background images to give the control the appearance and behavior you want.</span></span>  
  
### <a name="to-set-the-image-displayed-by-a-control"></a><span data-ttu-id="566e6-106">Per impostare l'immagine visualizzata da un controllo</span><span class="sxs-lookup"><span data-stu-id="566e6-106">To set the image displayed by a control</span></span>  
  
1.  <span data-ttu-id="566e6-107">Impostare il controllo `Image` o `BackgroundImage` proprietà a un oggetto di tipo <xref:System.Drawing.Image>.</span><span class="sxs-lookup"><span data-stu-id="566e6-107">Set the control's `Image` or `BackgroundImage` property to an object of type <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="566e6-108">In genere, si verrà caricata l'immagine da un file utilizzando il <xref:System.Drawing.Image.FromFile%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="566e6-108">Generally, you will be loading the image from a file by using the <xref:System.Drawing.Image.FromFile%2A> method.</span></span>  
  
     <span data-ttu-id="566e6-109">Nell'esempio di codice riportato di seguito, il percorso impostato per la posizione dell'immagine è il **immagini** cartella.</span><span class="sxs-lookup"><span data-stu-id="566e6-109">In the following code example, the path set for the location of the image is the **My Pictures** folder.</span></span> <span data-ttu-id="566e6-110">La maggior parte dei computer che eseguono il sistema operativo Windows includerà questa directory.</span><span class="sxs-lookup"><span data-stu-id="566e6-110">Most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="566e6-111">Ciò consente inoltre agli utenti con livelli di accesso di sistema minimi eseguire l'applicazione in modo sicuro.</span><span class="sxs-lookup"><span data-stu-id="566e6-111">This also enables users with minimal system access levels to run the application safely.</span></span> <span data-ttu-id="566e6-112">Esempio di codice seguente richiede che si dispone già di un form con un <xref:System.Windows.Forms.PictureBox> controllo aggiunto.</span><span class="sxs-lookup"><span data-stu-id="566e6-112">The following code example requires that you already have a form with a <xref:System.Windows.Forms.PictureBox> control added.</span></span>  
  
    ```vb  
    ' Replace the image named below  
    ' with an icon of your own choosing.  
    PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.MyPictures) _  
       & "\Image.gif")  
    ```  
  
    ```csharp  
    // Replace the image named below  
    // with an icon of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    pictureBox1.Image = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.MyPictures)  
       + @"\Image.gif");  
    ```  
  
    ```cpp  
    // Replace the image named below  
    // with an icon of your own choosing.  
    pictureBox1->Image = Image::FromFile(String::Concat  
       (System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::MyPictures),  
       "\\Image.gif"));  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="566e6-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="566e6-113">See Also</span></span>  
 <xref:System.Drawing.Image.FromFile%2A>  
 <xref:System.Drawing.Image>  
 <xref:System.Windows.Forms.Control.BackgroundImage%2A>
