---
title: 'Procedura: eseguire il rendering delle immagini con GDI+'
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
- images [Windows Forms], creating
- GDI+, rendering existing images
ms.assetid: c128b79a-3e31-47d8-9e66-3470f570a056
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a6edc48c93f83611bdc2be5b7398ab0abe843407
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-render-images-with-gdi"></a>Procedura: eseguire il rendering delle immagini con GDI+
È possibile usare [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] per il rendering delle immagini presenti sotto forma di file nelle applicazioni. Farlo creando un nuovo oggetto di un <xref:System.Drawing.Image> classe (ad esempio <xref:System.Drawing.Bitmap>), creando un <xref:System.Drawing.Graphics> dell'oggetto che fa riferimento all'area di disegno che si desidera utilizzare e la chiamata il <xref:System.Drawing.Graphics.DrawImage%2A> metodo il <xref:System.Drawing.Graphics> oggetto. L'immagine verrà disegnata sulla superficie da disegno rappresentata dalla classe della grafica. È possibile usare l'editor di immagini per creare e modificare i file di immagine in fase di progettazione ed eseguire su di loro il rendering con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] in fase di esecuzione. Per altre informazioni, vedere [Image Editor for Icons](/cpp/windows/image-editor-for-icons) (Editor di immagini per le icone).  
  
### <a name="to-render-an-image-with-gdi"></a>Per eseguire il rendering di un'immagine con GDI+  
  
1.  Creare un oggetto che rappresenti l'immagine che si desidera visualizzare. L'oggetto deve essere un membro di una classe che eredita da <xref:System.Drawing.Image>, ad esempio <xref:System.Drawing.Bitmap> o <xref:System.Drawing.Imaging.Metafile>. Esempio:  
  
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
  
2.  Creare un <xref:System.Drawing.Graphics> oggetto che rappresenta la superficie di disegno che si desidera utilizzare. Per altre informazioni, vedere [Procedura: Creare oggetti Graphics per disegnare](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md).  
  
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
  
3.  Chiamare il <xref:System.Drawing.Graphics.DrawImage%2A> dell'oggetto graphics per il rendering dell'immagine. È necessario specificare l'immagine da disegnare e le coordinate in cui deve essere disegnata.  
  
    ```vb  
    g.DrawImage(myBitmap, 1, 1)  
    ```  
  
    ```csharp  
    g.DrawImage(myBitmap, 1, 1);  
    ```  
  
    ```cpp  
    g->DrawImage(myBitmap, 1, 1);  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 [Introduzione alla programmazione grafica](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [Procedura: Creare oggetti Graphics per disegnare](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [Penne, linee e rettangoli in GDI+](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)  
 [Procedura: Disegnare testo in un Windows Form](../../../../docs/framework/winforms/advanced/how-to-draw-text-on-a-windows-form.md)  
 [Grafica e disegno in Windows Form](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [Disegno di linee o figure chiuse](/cpp/windows/drawing-lines-or-closed-figures-image-editor-for-icons)  
 [Editor di immagini per le icone](/cpp/windows/image-editor-for-icons)
