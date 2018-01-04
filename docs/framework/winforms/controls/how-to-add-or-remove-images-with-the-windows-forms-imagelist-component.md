---
title: 'Procedura: aggiungere o rimuovere immagini tramite il componente ImageList Windows Form'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- images [Windows Forms], removing from ImageList component
- images [Windows Forms], storing for controls
- ImageList component [Windows Forms], adding images
- ImageList component [Windows Forms], removing images
- images [Windows Forms], adding to ImageList component
- images [Windows Forms], displaying with controls
ms.assetid: c5eacc56-f769-4e2e-bfb7-f756620913db
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4e09448cb834453a4c8fce4494ab9fbb53eb0dc3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-or-remove-images-with-the-windows-forms-imagelist-component"></a><span data-ttu-id="e63a6-102">Procedura: aggiungere o rimuovere immagini tramite il componente ImageList Windows Form</span><span class="sxs-lookup"><span data-stu-id="e63a6-102">How to: Add or Remove Images with the Windows Forms ImageList Component</span></span>
<span data-ttu-id="e63a6-103">Windows Form <xref:System.Windows.Forms.ImageList> componente in genere viene popolato con le immagini prima che venga associato al controllo.</span><span class="sxs-lookup"><span data-stu-id="e63a6-103">The Windows Forms <xref:System.Windows.Forms.ImageList> component is typically populated with images before it is associated with a control.</span></span> <span data-ttu-id="e63a6-104">Tuttavia, è possibile aggiungere e rimuovere immagini dopo aver associato l'elenco di immagini a un controllo.</span><span class="sxs-lookup"><span data-stu-id="e63a6-104">However, you can add and remove images after associating the image list with a control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e63a6-105">Se si rimuovono le immagini, verificare che il <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> proprietà dei controlli associati è ancora valido.</span><span class="sxs-lookup"><span data-stu-id="e63a6-105">When you remove images, verify that the <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> property of any associated controls is still valid.</span></span>  
  
### <a name="to-add-images-programmatically"></a><span data-ttu-id="e63a6-106">Per aggiungere immagini a livello di codice</span><span class="sxs-lookup"><span data-stu-id="e63a6-106">To add images programmatically</span></span>  
  
-   <span data-ttu-id="e63a6-107">Utilizzare il <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> metodo per l'elenco di immagini <xref:System.Windows.Forms.ImageList.Images%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="e63a6-107">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> method of the image list's <xref:System.Windows.Forms.ImageList.Images%2A> property.</span></span>  
  
     <span data-ttu-id="e63a6-108">Nell'esempio di codice riportato di seguito, il percorso impostato per la posizione dell'immagine è il **documenti** cartella.</span><span class="sxs-lookup"><span data-stu-id="e63a6-108">In the following code example, the path set for the location of the image is the **My Documents** folder.</span></span> <span data-ttu-id="e63a6-109">Questo percorso viene utilizzato perché è possibile presupporre che la maggior parte dei computer che eseguono il sistema operativo Windows sarà inclusa in questa cartella.</span><span class="sxs-lookup"><span data-stu-id="e63a6-109">This location is used because you can assume that most computers that are running the Windows operating system will include this folder.</span></span> <span data-ttu-id="e63a6-110">Questa scelta consente anche agli utenti che dispongono di livelli minimi di sistema accesso più sicuro eseguiti l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e63a6-110">Choosing this location also lets users who have minimal system access levels more safely run the application.</span></span> <span data-ttu-id="e63a6-111">Esempio di codice seguente è necessario disporre un form con un <xref:System.Windows.Forms.ImageList> controllo già aggiunto.</span><span class="sxs-lookup"><span data-stu-id="e63a6-111">The following code example requires that you have a form with an <xref:System.Windows.Forms.ImageList> control already added.</span></span>  
  
    ```vb  
    Public Sub LoadImage()  
       Dim myImage As System.Drawing.Image = _  
         Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
       ImageList1.Images.Add(myImage)  
    End Sub  
    ```  
  
    ```csharp  
    public void addImage()  
    {  
    // Be sure that you use an appropriate escape sequence (such as the   
    // @) when specifying the location of the file.  
       System.Drawing.Image myImage =   
         Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
       imageList1.Images.Add(myImage);  
    }  
    ```  
  
    ```cpp  
    public:  
       void addImage()  
       {  
       // Replace the bold image in the following sample   
       // with your own icon.  
       // Be sure that you use an appropriate escape sequence (such as   
       // \\) when specifying the location of the file.  
          System::Drawing::Image ^ myImage =   
             Image::FromFile(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
          imageList1->Images->Add(myImage);  
       }  
    ```  
  
### <a name="to-add-images-with-a-key-value"></a><span data-ttu-id="e63a6-112">Per aggiungere immagini con un valore di chiave.</span><span class="sxs-lookup"><span data-stu-id="e63a6-112">To add images with a key value.</span></span>  
  
-   <span data-ttu-id="e63a6-113">Utilizzare uno del <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> metodi dell'elenco immagini <xref:System.Windows.Forms.ImageList.Images%2A> proprietà che accetta un valore di chiave.</span><span class="sxs-lookup"><span data-stu-id="e63a6-113">Use one of the <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> methods of the image list's <xref:System.Windows.Forms.ImageList.Images%2A> property that takes a key value.</span></span>  
  
     <span data-ttu-id="e63a6-114">Nell'esempio di codice riportato di seguito, il percorso impostato per la posizione dell'immagine è il **documenti** cartella.</span><span class="sxs-lookup"><span data-stu-id="e63a6-114">In the following code example, the path set for the location of the image is the **My Documents** folder.</span></span> <span data-ttu-id="e63a6-115">Questo percorso viene utilizzato perché è possibile presupporre che la maggior parte dei computer che eseguono il sistema operativo Windows sarà inclusa in questa cartella.</span><span class="sxs-lookup"><span data-stu-id="e63a6-115">This location is used because you can assume that most computers that are running the Windows operating system will include this folder.</span></span> <span data-ttu-id="e63a6-116">Questa scelta consente anche agli utenti che dispongono di livelli minimi di sistema accesso più sicuro eseguiti l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e63a6-116">Choosing this location also lets users who have minimal system access levels more safely run the application.</span></span> <span data-ttu-id="e63a6-117">Esempio di codice seguente è necessario disporre un form con un <xref:System.Windows.Forms.ImageList> controllo già aggiunto.</span><span class="sxs-lookup"><span data-stu-id="e63a6-117">The following code example requires that you have a form with an <xref:System.Windows.Forms.ImageList> control already added.</span></span>  
  
    ```vb  
    Public Sub LoadImage()  
       Dim myImage As System.Drawing.Image = _  
         Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
       ImageList1.Images.Add("myPhoto", myImage)  
    End Sub  
    ```  
  
```csharp  
public void addImage()  
{  
// Be sure that you use an appropriate escape sequence (such as the   
// @) when specifying the location of the file.  
   System.Drawing.Image myImage =   
     Image.FromFile  
   (System.Environment.GetFolderPath  
   (System.Environment.SpecialFolder.Personal)  
   + @"\Image.gif");  
   imageList1.Images.Add("myPhoto", myImage);  
}  
```  
  
1.  
  
### <a name="to-remove-all-images-programmatically"></a><span data-ttu-id="e63a6-118">Per rimuovere tutte le immagini a livello di codice</span><span class="sxs-lookup"><span data-stu-id="e63a6-118">To remove all images programmatically</span></span>  
  
-   <span data-ttu-id="e63a6-119">Utilizzare il <xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A> metodo per rimuovere una singola immagine</span><span class="sxs-lookup"><span data-stu-id="e63a6-119">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A> method to remove a single image</span></span>  
  
     <span data-ttu-id="e63a6-120">, - o -</span><span class="sxs-lookup"><span data-stu-id="e63a6-120">,-or-</span></span>  
  
     <span data-ttu-id="e63a6-121">Utilizzare il <xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A> metodo per cancellare tutte le immagini nell'elenco delle immagini.</span><span class="sxs-lookup"><span data-stu-id="e63a6-121">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A> method to clear all images in the image list.</span></span>  
  
    ```vb  
    ' Removes the first image in the image list  
    ImageList1.Images.Remove(myImage)  
    ' Clears all images in the image list  
    ImageList1.Images.Clear()  
    ```  
  
```csharp  
// Removes the first image in the image list.  
imageList1.Images.Remove(myImage);  
// Clears all images in the image list.  
imageList1.Images.Clear();  
```  
  
### <a name="to-remove-images-by-key"></a><span data-ttu-id="e63a6-122">Per rimuovere le immagini dalla chiave</span><span class="sxs-lookup"><span data-stu-id="e63a6-122">To remove images by key</span></span>  
  
-   <span data-ttu-id="e63a6-123">Utilizzare il <xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A> metodo per rimuovere una singola immagine in base alla chiave.</span><span class="sxs-lookup"><span data-stu-id="e63a6-123">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A> method to remove a single image by its key.</span></span>  
  
    ```vb  
    ' Removes the image named "myPhoto" from the list.  
    ImageList1.Images.RemoveByKey("myPhoto")  
    ```  
  
```csharp  
// Removes the image named "myPhoto" from the list.  
imageList1.Images.RemoveByKey("myPhoto");  
```  
  
## <a name="see-also"></a><span data-ttu-id="e63a6-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e63a6-124">See Also</span></span>  
 [<span data-ttu-id="e63a6-125">Componente ImageList</span><span class="sxs-lookup"><span data-stu-id="e63a6-125">ImageList Component</span></span>](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)  
 [<span data-ttu-id="e63a6-126">Panoramica sul componente ImageList</span><span class="sxs-lookup"><span data-stu-id="e63a6-126">ImageList Component Overview</span></span>](../../../../docs/framework/winforms/controls/imagelist-component-overview-windows-forms.md)  
 [<span data-ttu-id="e63a6-127">Immagini, bitmap e metafile</span><span class="sxs-lookup"><span data-stu-id="e63a6-127">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
