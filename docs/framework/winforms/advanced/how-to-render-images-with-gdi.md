---
title: 'Procedura: eseguire il rendering delle immagini con GDI+'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- images [Windows Forms], creating
- GDI+, rendering existing images
ms.assetid: c128b79a-3e31-47d8-9e66-3470f570a056
ms.openlocfilehash: fffe1f1052d7323d234985b7e752866f2e89657d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182510"
---
# <a name="how-to-render-images-with-gdi"></a><span data-ttu-id="31720-102">Procedura: eseguire il rendering delle immagini con GDI+</span><span class="sxs-lookup"><span data-stu-id="31720-102">How to: Render Images with GDI+</span></span>
<span data-ttu-id="31720-103">È possibile utilizzare GDI per eseguire il rendering delle immagini esistenti come file nelle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="31720-103">You can use GDI+ to render images that exist as files in your applications.</span></span> <span data-ttu-id="31720-104">A tale scopo, creare un <xref:System.Drawing.Image> nuovo oggetto <xref:System.Drawing.Bitmap>di <xref:System.Drawing.Graphics> una classe (ad esempio ), creare un <xref:System.Drawing.Graphics.DrawImage%2A> oggetto che <xref:System.Drawing.Graphics> fa riferimento alla superficie di disegno che si desidera utilizzare e chiamare il metodo dell'oggetto .</span><span class="sxs-lookup"><span data-stu-id="31720-104">You do this by creating a new object of an <xref:System.Drawing.Image> class (such as <xref:System.Drawing.Bitmap>), creating a <xref:System.Drawing.Graphics> object that refers to the drawing surface you want to use, and calling the <xref:System.Drawing.Graphics.DrawImage%2A> method of the <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="31720-105">L'immagine verrà disegnata sulla superficie da disegno rappresentata dalla classe della grafica.</span><span class="sxs-lookup"><span data-stu-id="31720-105">The image will be painted onto the drawing surface represented by the graphics class.</span></span> <span data-ttu-id="31720-106">È possibile utilizzare l'editor di immagini per creare e modificare i file di immagine in fase di progettazione ed eseguirne il rendering con GDI.</span><span class="sxs-lookup"><span data-stu-id="31720-106">You can use the Image Editor to create and edit image files at design time, and render them with GDI+ at run time.</span></span> <span data-ttu-id="31720-107">Per altre informazioni, vedere [Image Editor for Icons](/cpp/windows/image-editor-for-icons) (Editor di immagini per le icone).</span><span class="sxs-lookup"><span data-stu-id="31720-107">For more information, see [Image Editor for Icons](/cpp/windows/image-editor-for-icons).</span></span>  
  
### <a name="to-render-an-image-with-gdi"></a><span data-ttu-id="31720-108">Per eseguire il rendering di un'immagine con GDI+</span><span class="sxs-lookup"><span data-stu-id="31720-108">To render an image with GDI+</span></span>  
  
1. <span data-ttu-id="31720-109">Creare un oggetto che rappresenti l'immagine che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="31720-109">Create an object representing the image you want to display.</span></span> <span data-ttu-id="31720-110">Questo oggetto deve essere un membro di <xref:System.Drawing.Image>una <xref:System.Drawing.Bitmap> classe <xref:System.Drawing.Imaging.Metafile>che eredita da , ad esempio o .</span><span class="sxs-lookup"><span data-stu-id="31720-110">This object must be a member of a class that inherits from <xref:System.Drawing.Image>, such as <xref:System.Drawing.Bitmap> or <xref:System.Drawing.Imaging.Metafile>.</span></span> <span data-ttu-id="31720-111">Esempio:</span><span class="sxs-lookup"><span data-stu-id="31720-111">An example is shown:</span></span>  
  
    ```vb  
    ' Uses the System.Environment.GetFolderPath to get the path to the
    ' current user's MyPictures folder.  
    Dim myBitmap as New Bitmap _  
       (System.Environment.GetFolderPath _  
          (System.Environment.SpecialFolder.MyPictures))  
    ```  
  
    ```csharp  
    // Uses the System.Environment.GetFolderPath to get the path to the
    // current user's MyPictures folder.  
    Bitmap myBitmap = new Bitmap  
       (System.Environment.GetFolderPath  
          (System.Environment.SpecialFolder.MyPictures));  
    ```  
  
    ```cpp  
    // Uses the System.Environment.GetFolderPath to get the path to the
    // current user's MyPictures folder.  
    Bitmap^ myBitmap = gcnew Bitmap  
       (System::Environment::GetFolderPath  
          (System::Environment::SpecialFolder::MyPictures));  
    ```  
  
2. <span data-ttu-id="31720-112">Creare <xref:System.Drawing.Graphics> un oggetto che rappresenta la superficie di disegno che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="31720-112">Create a <xref:System.Drawing.Graphics> object that represents the drawing surface you want to use.</span></span> <span data-ttu-id="31720-113">Per altre informazioni, vedere [Procedura: Creare oggetti Graphics per disegnare](how-to-create-graphics-objects-for-drawing.md).</span><span class="sxs-lookup"><span data-stu-id="31720-113">For more information, see [How to: Create Graphics Objects for Drawing](how-to-create-graphics-objects-for-drawing.md).</span></span>  
  
    ```vb  
    ' Creates a Graphics object that represents the drawing surface of
    ' Button1.  
    Dim g as Graphics = Button1.CreateGraphics  
    ```  
  
    ```csharp  
    // Creates a Graphics object that represents the drawing surface of
    // Button1.  
    Graphics g = Button1.CreateGraphics();  
    ```  
  
    ```cpp  
    // Creates a Graphics object that represents the drawing surface of
    // Button1.  
    Graphics^ g = button1->CreateGraphics();  
    ```  
  
3. <span data-ttu-id="31720-114">Chiamare <xref:System.Drawing.Graphics.DrawImage%2A> l'oggetto grafico per eseguire il rendering dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="31720-114">Call the <xref:System.Drawing.Graphics.DrawImage%2A> of your graphics object to render the image.</span></span> <span data-ttu-id="31720-115">È necessario specificare l'immagine da disegnare e le coordinate in cui deve essere disegnata.</span><span class="sxs-lookup"><span data-stu-id="31720-115">You must specify both the image to be drawn, and the coordinates where it is to be drawn.</span></span>  
  
    ```vb  
    g.DrawImage(myBitmap, 1, 1)  
    ```  
  
    ```csharp  
    g.DrawImage(myBitmap, 1, 1);  
    ```  
  
    ```cpp  
    g->DrawImage(myBitmap, 1, 1);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="31720-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="31720-116">See also</span></span>

- [<span data-ttu-id="31720-117">Introduzione alla programmazione grafica</span><span class="sxs-lookup"><span data-stu-id="31720-117">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="31720-118">Procedura: creare oggetti Graphics per disegnare</span><span class="sxs-lookup"><span data-stu-id="31720-118">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="31720-119">Penne, linee e rettangoli in GDI+</span><span class="sxs-lookup"><span data-stu-id="31720-119">Pens, Lines, and Rectangles in GDI+</span></span>](pens-lines-and-rectangles-in-gdi.md)
- [<span data-ttu-id="31720-120">Procedura: disegnare testo in un Windows Form</span><span class="sxs-lookup"><span data-stu-id="31720-120">How to: Draw Text on a Windows Form</span></span>](how-to-draw-text-on-a-windows-form.md)
- [<span data-ttu-id="31720-121">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="31720-121">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="31720-122">Disegno di linee o figure chiuse</span><span class="sxs-lookup"><span data-stu-id="31720-122">Drawing Lines or Closed Figures</span></span>](/cpp/windows/drawing-lines-or-closed-figures-image-editor-for-icons)
- <span data-ttu-id="31720-123">[Image Editor for Icons](/cpp/windows/image-editor-for-icons) (Editor di immagini per icone)</span><span class="sxs-lookup"><span data-stu-id="31720-123">[Image Editor for Icons](/cpp/windows/image-editor-for-icons)</span></span>
