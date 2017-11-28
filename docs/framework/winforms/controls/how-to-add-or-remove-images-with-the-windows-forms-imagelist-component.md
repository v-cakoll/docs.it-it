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
ms.openlocfilehash: ce13ba3413c13ced7ff9a967e23d87622309feb7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-or-remove-images-with-the-windows-forms-imagelist-component"></a>Procedura: aggiungere o rimuovere immagini tramite il componente ImageList Windows Form
Windows Form <xref:System.Windows.Forms.ImageList> componente in genere viene popolato con le immagini prima che venga associato al controllo. Tuttavia, è possibile aggiungere e rimuovere immagini dopo aver associato l'elenco di immagini a un controllo.  
  
> [!NOTE]
>  Se si rimuovono le immagini, verificare che il <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> proprietà dei controlli associati è ancora valido.  
  
### <a name="to-add-images-programmatically"></a>Per aggiungere immagini a livello di codice  
  
-   Utilizzare il <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> metodo per l'elenco di immagini <xref:System.Windows.Forms.ImageList.Images%2A> proprietà.  
  
     Nell'esempio di codice riportato di seguito, il percorso impostato per la posizione dell'immagine è il **documenti** cartella. Questo percorso viene utilizzato perché è possibile presupporre che la maggior parte dei computer che eseguono il sistema operativo Windows sarà inclusa in questa cartella. Questa scelta consente anche agli utenti che dispongono di livelli minimi di sistema accesso più sicuro eseguiti l'applicazione. Esempio di codice seguente è necessario disporre un form con un <xref:System.Windows.Forms.ImageList> controllo già aggiunto.  
  
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
  
### <a name="to-add-images-with-a-key-value"></a>Per aggiungere immagini con un valore di chiave.  
  
-   Utilizzare uno del <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> metodi dell'elenco immagini <xref:System.Windows.Forms.ImageList.Images%2A> proprietà che accetta un valore di chiave.  
  
     Nell'esempio di codice riportato di seguito, il percorso impostato per la posizione dell'immagine è il **documenti** cartella. Questo percorso viene utilizzato perché è possibile presupporre che la maggior parte dei computer che eseguono il sistema operativo Windows sarà inclusa in questa cartella. Questa scelta consente anche agli utenti che dispongono di livelli minimi di sistema accesso più sicuro eseguiti l'applicazione. Esempio di codice seguente è necessario disporre un form con un <xref:System.Windows.Forms.ImageList> controllo già aggiunto.  
  
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
  
### <a name="to-remove-all-images-programmatically"></a>Per rimuovere tutte le immagini a livello di codice  
  
-   Utilizzare il <xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A> metodo per rimuovere una singola immagine  
  
     , - o -  
  
     Utilizzare il <xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A> metodo per cancellare tutte le immagini nell'elenco delle immagini.  
  
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
  
### <a name="to-remove-images-by-key"></a>Per rimuovere le immagini dalla chiave  
  
-   Utilizzare il <xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A> metodo per rimuovere una singola immagine in base alla chiave.  
  
    ```vb  
    ' Removes the image named "myPhoto" from the list.  
    ImageList1.Images.RemoveByKey("myPhoto")  
    ```  
  
```csharp  
// Removes the image named "myPhoto" from the list.  
imageList1.Images.RemoveByKey("myPhoto");  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Componente ImageList](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)  
 [Panoramica sul componente ImageList](../../../../docs/framework/winforms/controls/imagelist-component-overview-windows-forms.md)  
 [Immagini, bitmap e metafile](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
