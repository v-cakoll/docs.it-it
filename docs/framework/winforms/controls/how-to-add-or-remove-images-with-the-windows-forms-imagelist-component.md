---
title: Aggiungere o rimuovere immagini con il componente ImageList
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
ms.openlocfilehash: f531003377395bf219775e5ddb48ceb0822ff0ea
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741508"
---
# <a name="how-to-add-or-remove-images-with-the-windows-forms-imagelist-component"></a><span data-ttu-id="54808-102">Procedura: Aggiungere o rimuovere immagini tramite il componente ImageList di Windows Form</span><span class="sxs-lookup"><span data-stu-id="54808-102">How to: Add or Remove Images with the Windows Forms ImageList Component</span></span>
<span data-ttu-id="54808-103">Il componente Windows Forms <xref:System.Windows.Forms.ImageList> viene in genere popolato con le immagini prima che sia associato a un controllo.</span><span class="sxs-lookup"><span data-stu-id="54808-103">The Windows Forms <xref:System.Windows.Forms.ImageList> component is typically populated with images before it is associated with a control.</span></span> <span data-ttu-id="54808-104">Tuttavia, è possibile aggiungere e rimuovere immagini dopo avere associato l'elenco di immagini a un controllo.</span><span class="sxs-lookup"><span data-stu-id="54808-104">However, you can add and remove images after associating the image list with a control.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="54808-105">Quando si rimuovono le immagini, verificare che la proprietà <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> di tutti i controlli associati sia ancora valida.</span><span class="sxs-lookup"><span data-stu-id="54808-105">When you remove images, verify that the <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> property of any associated controls is still valid.</span></span>  
  
### <a name="to-add-images-programmatically"></a><span data-ttu-id="54808-106">Per aggiungere immagini a livello di codice</span><span class="sxs-lookup"><span data-stu-id="54808-106">To add images programmatically</span></span>  
  
- <span data-ttu-id="54808-107">Usare il metodo <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> della proprietà <xref:System.Windows.Forms.ImageList.Images%2A> dell'elenco immagini.</span><span class="sxs-lookup"><span data-stu-id="54808-107">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> method of the image list's <xref:System.Windows.Forms.ImageList.Images%2A> property.</span></span>  
  
     <span data-ttu-id="54808-108">Nell'esempio di codice seguente il percorso impostato per il percorso dell'immagine è la cartella **documenti** .</span><span class="sxs-lookup"><span data-stu-id="54808-108">In the following code example, the path set for the location of the image is the **My Documents** folder.</span></span> <span data-ttu-id="54808-109">Questo percorso viene utilizzato in quanto è possibile presupporre che la maggior parte dei computer che eseguono il sistema operativo Windows includa questa cartella.</span><span class="sxs-lookup"><span data-stu-id="54808-109">This location is used because you can assume that most computers that are running the Windows operating system will include this folder.</span></span> <span data-ttu-id="54808-110">La scelta di questo percorso consente anche agli utenti con livelli di accesso di sistema minimi di eseguire l'applicazione in modo più sicuro.</span><span class="sxs-lookup"><span data-stu-id="54808-110">Choosing this location also lets users who have minimal system access levels more safely run the application.</span></span> <span data-ttu-id="54808-111">Per l'esempio di codice seguente è necessario disporre di un modulo con un controllo <xref:System.Windows.Forms.ImageList> già aggiunto.</span><span class="sxs-lookup"><span data-stu-id="54808-111">The following code example requires that you have a form with an <xref:System.Windows.Forms.ImageList> control already added.</span></span>  
  
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
  
### <a name="to-add-images-with-a-key-value"></a><span data-ttu-id="54808-112">Per aggiungere immagini con un valore di chiave.</span><span class="sxs-lookup"><span data-stu-id="54808-112">To add images with a key value.</span></span>  
  
- <span data-ttu-id="54808-113">Usare uno dei metodi <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> della proprietà <xref:System.Windows.Forms.ImageList.Images%2A> dell'elenco immagini che accetta un valore di chiave.</span><span class="sxs-lookup"><span data-stu-id="54808-113">Use one of the <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> methods of the image list's <xref:System.Windows.Forms.ImageList.Images%2A> property that takes a key value.</span></span>  
  
     <span data-ttu-id="54808-114">Nell'esempio di codice seguente il percorso impostato per il percorso dell'immagine è la cartella **documenti** .</span><span class="sxs-lookup"><span data-stu-id="54808-114">In the following code example, the path set for the location of the image is the **My Documents** folder.</span></span> <span data-ttu-id="54808-115">Questo percorso viene utilizzato in quanto è possibile presupporre che la maggior parte dei computer che eseguono il sistema operativo Windows includa questa cartella.</span><span class="sxs-lookup"><span data-stu-id="54808-115">This location is used because you can assume that most computers that are running the Windows operating system will include this folder.</span></span> <span data-ttu-id="54808-116">La scelta di questo percorso consente anche agli utenti con livelli di accesso di sistema minimi di eseguire l'applicazione in modo più sicuro.</span><span class="sxs-lookup"><span data-stu-id="54808-116">Choosing this location also lets users who have minimal system access levels more safely run the application.</span></span> <span data-ttu-id="54808-117">Per l'esempio di codice seguente è necessario disporre di un modulo con un controllo <xref:System.Windows.Forms.ImageList> già aggiunto.</span><span class="sxs-lookup"><span data-stu-id="54808-117">The following code example requires that you have a form with an <xref:System.Windows.Forms.ImageList> control already added.</span></span>  
  
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
  
### <a name="to-remove-all-images-programmatically"></a><span data-ttu-id="54808-118">Per rimuovere tutte le immagini a livello di codice</span><span class="sxs-lookup"><span data-stu-id="54808-118">To remove all images programmatically</span></span>  
  
- <span data-ttu-id="54808-119">Usare il metodo <xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A> per rimuovere una singola immagine</span><span class="sxs-lookup"><span data-stu-id="54808-119">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A> method to remove a single image</span></span>  
  
     <span data-ttu-id="54808-120">, o-</span><span class="sxs-lookup"><span data-stu-id="54808-120">,-or-</span></span>  
  
     <span data-ttu-id="54808-121">Usare il metodo <xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A> per cancellare tutte le immagini nell'elenco immagini.</span><span class="sxs-lookup"><span data-stu-id="54808-121">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A> method to clear all images in the image list.</span></span>  
  
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
  
### <a name="to-remove-images-by-key"></a><span data-ttu-id="54808-122">Per rimuovere le immagini in base alla chiave</span><span class="sxs-lookup"><span data-stu-id="54808-122">To remove images by key</span></span>  
  
- <span data-ttu-id="54808-123">Usare il metodo <xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A> per rimuovere una singola immagine in base alla relativa chiave.</span><span class="sxs-lookup"><span data-stu-id="54808-123">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A> method to remove a single image by its key.</span></span>  
  
    ```vb  
    ' Removes the image named "myPhoto" from the list.  
    ImageList1.Images.RemoveByKey("myPhoto")  
    ```  
  
```csharp  
// Removes the image named "myPhoto" from the list.  
imageList1.Images.RemoveByKey("myPhoto");  
```  
  
## <a name="see-also"></a><span data-ttu-id="54808-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54808-124">See also</span></span>

- [<span data-ttu-id="54808-125">Componente ImageList</span><span class="sxs-lookup"><span data-stu-id="54808-125">ImageList Component</span></span>](imagelist-component-windows-forms.md)
- [<span data-ttu-id="54808-126">Panoramica sul componente ImageList</span><span class="sxs-lookup"><span data-stu-id="54808-126">ImageList Component Overview</span></span>](imagelist-component-overview-windows-forms.md)
- [<span data-ttu-id="54808-127">Immagini, bitmap e metafile</span><span class="sxs-lookup"><span data-stu-id="54808-127">Images, Bitmaps, and Metafiles</span></span>](../advanced/images-bitmaps-and-metafiles.md)
