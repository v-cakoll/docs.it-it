---
title: Aggiunta o rimozione di immagini con componente ImageList
ms.date: 03/30/2017
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
ms.openlocfilehash: e045be7ea9407bc379b0c22282fcd2184ff5db51
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182293"
---
# <a name="how-to-add-or-remove-images-with-the-windows-forms-imagelist-component"></a><span data-ttu-id="b40c8-102">Procedura: aggiungere o rimuovere immagini tramite il componente ImageList Windows Form</span><span class="sxs-lookup"><span data-stu-id="b40c8-102">How to: Add or Remove Images with the Windows Forms ImageList Component</span></span>
<span data-ttu-id="b40c8-103">Il componente <xref:System.Windows.Forms.ImageList> Windows Form viene in genere popolato con immagini prima di essere associato a un controllo.</span><span class="sxs-lookup"><span data-stu-id="b40c8-103">The Windows Forms <xref:System.Windows.Forms.ImageList> component is typically populated with images before it is associated with a control.</span></span> <span data-ttu-id="b40c8-104">Tuttavia, è possibile aggiungere e rimuovere immagini dopo aver associato l'elenco immagini a un controllo.</span><span class="sxs-lookup"><span data-stu-id="b40c8-104">However, you can add and remove images after associating the image list with a control.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b40c8-105">Quando si rimuovono <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> immagini, verificare che la proprietà di tutti i controlli associati sia ancora valida.</span><span class="sxs-lookup"><span data-stu-id="b40c8-105">When you remove images, verify that the <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> property of any associated controls is still valid.</span></span>  
  
### <a name="to-add-images-programmatically"></a><span data-ttu-id="b40c8-106">Per aggiungere immagini a livello di codiceTo add images programmatically</span><span class="sxs-lookup"><span data-stu-id="b40c8-106">To add images programmatically</span></span>  
  
- <span data-ttu-id="b40c8-107">Utilizzare <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> il metodo della proprietà <xref:System.Windows.Forms.ImageList.Images%2A> dell'elenco immagini.</span><span class="sxs-lookup"><span data-stu-id="b40c8-107">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> method of the image list's <xref:System.Windows.Forms.ImageList.Images%2A> property.</span></span>  
  
     <span data-ttu-id="b40c8-108">Nell'esempio di codice seguente, il percorso impostato per il percorso dell'immagine è la cartella **Documenti.**</span><span class="sxs-lookup"><span data-stu-id="b40c8-108">In the following code example, the path set for the location of the image is the **My Documents** folder.</span></span> <span data-ttu-id="b40c8-109">Questo percorso viene utilizzato perché è possibile presupporre che la maggior parte dei computer che eseguono il sistema operativo Windows includerà questa cartella.</span><span class="sxs-lookup"><span data-stu-id="b40c8-109">This location is used because you can assume that most computers that are running the Windows operating system will include this folder.</span></span> <span data-ttu-id="b40c8-110">La scelta di questo percorso consente inoltre agli utenti che dispongono di livelli minimi di accesso al sistema di eseguire l'applicazione in modo più sicuro.</span><span class="sxs-lookup"><span data-stu-id="b40c8-110">Choosing this location also lets users who have minimal system access levels more safely run the application.</span></span> <span data-ttu-id="b40c8-111">Nell'esempio di codice riportato di <xref:System.Windows.Forms.ImageList> seguito è necessario disporre di un form con un controllo già aggiunto.</span><span class="sxs-lookup"><span data-stu-id="b40c8-111">The following code example requires that you have a form with an <xref:System.Windows.Forms.ImageList> control already added.</span></span>  
  
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
  
### <a name="to-add-images-with-a-key-value"></a><span data-ttu-id="b40c8-112">Per aggiungere immagini con un valore chiave.</span><span class="sxs-lookup"><span data-stu-id="b40c8-112">To add images with a key value.</span></span>  
  
- <span data-ttu-id="b40c8-113">Utilizzare uno <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> dei metodi della proprietà <xref:System.Windows.Forms.ImageList.Images%2A> dell'elenco immagini che accetta un valore di chiave.</span><span class="sxs-lookup"><span data-stu-id="b40c8-113">Use one of the <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> methods of the image list's <xref:System.Windows.Forms.ImageList.Images%2A> property that takes a key value.</span></span>  
  
     <span data-ttu-id="b40c8-114">Nell'esempio di codice seguente, il percorso impostato per il percorso dell'immagine è la cartella **Documenti.**</span><span class="sxs-lookup"><span data-stu-id="b40c8-114">In the following code example, the path set for the location of the image is the **My Documents** folder.</span></span> <span data-ttu-id="b40c8-115">Questo percorso viene utilizzato perché è possibile presupporre che la maggior parte dei computer che eseguono il sistema operativo Windows includerà questa cartella.</span><span class="sxs-lookup"><span data-stu-id="b40c8-115">This location is used because you can assume that most computers that are running the Windows operating system will include this folder.</span></span> <span data-ttu-id="b40c8-116">La scelta di questo percorso consente inoltre agli utenti che dispongono di livelli minimi di accesso al sistema di eseguire l'applicazione in modo più sicuro.</span><span class="sxs-lookup"><span data-stu-id="b40c8-116">Choosing this location also lets users who have minimal system access levels more safely run the application.</span></span> <span data-ttu-id="b40c8-117">Nell'esempio di codice riportato di <xref:System.Windows.Forms.ImageList> seguito è necessario disporre di un form con un controllo già aggiunto.</span><span class="sxs-lookup"><span data-stu-id="b40c8-117">The following code example requires that you have a form with an <xref:System.Windows.Forms.ImageList> control already added.</span></span>  
  
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
  
### <a name="to-remove-all-images-programmatically"></a><span data-ttu-id="b40c8-118">Per rimuovere tutte le immagini a livello di codiceTo remove all images programmatically</span><span class="sxs-lookup"><span data-stu-id="b40c8-118">To remove all images programmatically</span></span>  
  
- <span data-ttu-id="b40c8-119">Utilizzare <xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A> il metodo per rimuovere una singola immagine</span><span class="sxs-lookup"><span data-stu-id="b40c8-119">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A> method to remove a single image</span></span>  
  
     <span data-ttu-id="b40c8-120">,oppure-</span><span class="sxs-lookup"><span data-stu-id="b40c8-120">,-or-</span></span>  
  
     <span data-ttu-id="b40c8-121">Utilizzare <xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A> il metodo per cancellare tutte le immagini nell'elenco immagini.</span><span class="sxs-lookup"><span data-stu-id="b40c8-121">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A> method to clear all images in the image list.</span></span>  
  
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
  
### <a name="to-remove-images-by-key"></a><span data-ttu-id="b40c8-122">Per rimuovere le immagini per chiave</span><span class="sxs-lookup"><span data-stu-id="b40c8-122">To remove images by key</span></span>  
  
- <span data-ttu-id="b40c8-123">Utilizzare <xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A> il metodo per rimuovere una singola immagine in base alla relativa chiave.</span><span class="sxs-lookup"><span data-stu-id="b40c8-123">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A> method to remove a single image by its key.</span></span>  
  
    ```vb  
    ' Removes the image named "myPhoto" from the list.  
    ImageList1.Images.RemoveByKey("myPhoto")  
    ```  
  
```csharp  
// Removes the image named "myPhoto" from the list.  
imageList1.Images.RemoveByKey("myPhoto");  
```  
  
## <a name="see-also"></a><span data-ttu-id="b40c8-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b40c8-124">See also</span></span>

- [<span data-ttu-id="b40c8-125">Componente ImageList</span><span class="sxs-lookup"><span data-stu-id="b40c8-125">ImageList Component</span></span>](imagelist-component-windows-forms.md)
- [<span data-ttu-id="b40c8-126">Panoramica del componente ImageList</span><span class="sxs-lookup"><span data-stu-id="b40c8-126">ImageList Component Overview</span></span>](imagelist-component-overview-windows-forms.md)
- [<span data-ttu-id="b40c8-127">Immagini, bitmap e metafile</span><span class="sxs-lookup"><span data-stu-id="b40c8-127">Images, Bitmaps, and Metafiles</span></span>](../advanced/images-bitmaps-and-metafiles.md)
