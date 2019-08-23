---
title: 'Procedura: Aggiungere o rimuovere immagini con il componente ImageList di Windows Forms'
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
ms.openlocfilehash: 430b7f573b115c21b9e2fa87f0ace74205717285
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925126"
---
# <a name="how-to-add-or-remove-images-with-the-windows-forms-imagelist-component"></a>Procedura: Aggiungere o rimuovere immagini con il componente ImageList di Windows Forms
Il componente <xref:System.Windows.Forms.ImageList> Windows Forms viene in genere popolato con le immagini prima che sia associato a un controllo. Tuttavia, è possibile aggiungere e rimuovere immagini dopo avere associato l'elenco di immagini a un controllo.  
  
> [!NOTE]
> Quando si rimuovono le immagini, verificare <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> che la proprietà di tutti i controlli associati sia ancora valida.  
  
### <a name="to-add-images-programmatically"></a>Per aggiungere immagini a livello di codice  
  
- Usare il <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> metodo della <xref:System.Windows.Forms.ImageList.Images%2A> proprietà dell'elenco immagini.  
  
     Nell'esempio di codice seguente il percorso impostato per il percorso dell'immagine è la cartella **documenti** . Questo percorso viene utilizzato in quanto è possibile presupporre che la maggior parte dei computer che eseguono il sistema operativo Windows includa questa cartella. La scelta di questo percorso consente anche agli utenti con livelli di accesso di sistema minimi di eseguire l'applicazione in modo più sicuro. Per l'esempio di codice seguente è necessario disporre di un modulo <xref:System.Windows.Forms.ImageList> con un controllo già aggiunto.  
  
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
  
- Usare uno dei <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> metodi della <xref:System.Windows.Forms.ImageList.Images%2A> proprietà dell'elenco immagini che accetta un valore di chiave.  
  
     Nell'esempio di codice seguente il percorso impostato per il percorso dell'immagine è la cartella **documenti** . Questo percorso viene utilizzato in quanto è possibile presupporre che la maggior parte dei computer che eseguono il sistema operativo Windows includa questa cartella. La scelta di questo percorso consente anche agli utenti con livelli di accesso di sistema minimi di eseguire l'applicazione in modo più sicuro. Per l'esempio di codice seguente è necessario disporre di un modulo <xref:System.Windows.Forms.ImageList> con un controllo già aggiunto.  
  
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
  
### <a name="to-remove-all-images-programmatically"></a>Per rimuovere tutte le immagini a livello di codice  
  
- Usare il <xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A> metodo per rimuovere una singola immagine  
  
     , o-  
  
     Usare il <xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A> metodo per cancellare tutte le immagini nell'elenco immagini.  
  
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
  
### <a name="to-remove-images-by-key"></a>Per rimuovere le immagini in base alla chiave  
  
- Usare il <xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A> metodo per rimuovere una singola immagine in base alla relativa chiave.  
  
    ```vb  
    ' Removes the image named "myPhoto" from the list.  
    ImageList1.Images.RemoveByKey("myPhoto")  
    ```  
  
```csharp  
// Removes the image named "myPhoto" from the list.  
imageList1.Images.RemoveByKey("myPhoto");  
```  
  
## <a name="see-also"></a>Vedere anche

- [Componente ImageList](imagelist-component-windows-forms.md)
- [Panoramica sul componente ImageList](imagelist-component-overview-windows-forms.md)
- [Immagini, bitmap e metafile](../advanced/images-bitmaps-and-metafiles.md)
