---
title: "Procedura: Impostare l'immagine visualizzata da un controllo di Windows Forms"
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
ms.openlocfilehash: 1de835bda5ac906837ac3fbd97b87f68f14d1953
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59771530"
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control"></a><span data-ttu-id="f0c7e-102">Procedura: Impostare l'immagine visualizzata da un controllo di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f0c7e-102">How to: Set the Image Displayed by a Windows Forms Control</span></span>
<span data-ttu-id="f0c7e-103">Vari controlli Windows Form consente di visualizzare immagini.</span><span class="sxs-lookup"><span data-stu-id="f0c7e-103">Several Windows Forms controls can display images.</span></span> <span data-ttu-id="f0c7e-104">Queste immagini possono essere le icone che chiariscono lo scopo del controllo, ad esempio un'icona del dischetto su un pulsante indica la **salvare** comando.</span><span class="sxs-lookup"><span data-stu-id="f0c7e-104">These images can be icons that clarify the purpose of the control, such as a diskette icon on a button denoting the **Save** command.</span></span> <span data-ttu-id="f0c7e-105">In alternativa, le icone possono essere immagini di sfondo per fornire il controllo, l'aspetto e il comportamento desiderato.</span><span class="sxs-lookup"><span data-stu-id="f0c7e-105">Alternatively, the icons can be background images to give the control the appearance and behavior you want.</span></span>  
  
### <a name="to-set-the-image-displayed-by-a-control"></a><span data-ttu-id="f0c7e-106">Per impostare l'immagine visualizzata da un controllo</span><span class="sxs-lookup"><span data-stu-id="f0c7e-106">To set the image displayed by a control</span></span>  
  
1. <span data-ttu-id="f0c7e-107">Impostare il controllo `Image` oppure `BackgroundImage` proprietà di un oggetto di tipo <xref:System.Drawing.Image>.</span><span class="sxs-lookup"><span data-stu-id="f0c7e-107">Set the control's `Image` or `BackgroundImage` property to an object of type <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="f0c7e-108">In generale, è caricata l'immagine da un file usando il <xref:System.Drawing.Image.FromFile%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="f0c7e-108">Generally, you will be loading the image from a file by using the <xref:System.Drawing.Image.FromFile%2A> method.</span></span>  
  
     <span data-ttu-id="f0c7e-109">Nell'esempio di codice seguente, il percorso impostato per il percorso dell'immagine è il **My Pictures** cartella.</span><span class="sxs-lookup"><span data-stu-id="f0c7e-109">In the following code example, the path set for the location of the image is the **My Pictures** folder.</span></span> <span data-ttu-id="f0c7e-110">La maggior parte dei computer che eseguono il sistema operativo Windows includeranno questa directory.</span><span class="sxs-lookup"><span data-stu-id="f0c7e-110">Most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="f0c7e-111">Ciò consente inoltre agli utenti con livelli di accesso di sistema minimi eseguire l'applicazione in modo sicuro.</span><span class="sxs-lookup"><span data-stu-id="f0c7e-111">This also enables users with minimal system access levels to run the application safely.</span></span> <span data-ttu-id="f0c7e-112">Esempio di codice seguente richiede che hai già un form con un <xref:System.Windows.Forms.PictureBox> controllo aggiunto.</span><span class="sxs-lookup"><span data-stu-id="f0c7e-112">The following code example requires that you already have a form with a <xref:System.Windows.Forms.PictureBox> control added.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f0c7e-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0c7e-113">See also</span></span>

- <xref:System.Drawing.Image.FromFile%2A>
- <xref:System.Drawing.Image>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
