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
# <a name="how-to-add-or-remove-images-with-the-windows-forms-imagelist-component"></a>Procedura: aggiungere o rimuovere immagini tramite il componente ImageList Windows Form
Il componente <xref:System.Windows.Forms.ImageList> Windows Form viene in genere popolato con immagini prima di essere associato a un controllo. Tuttavia, è possibile aggiungere e rimuovere immagini dopo aver associato l'elenco immagini a un controllo.  
  
> [!NOTE]
> Quando si rimuovono <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> immagini, verificare che la proprietà di tutti i controlli associati sia ancora valida.  
  
### <a name="to-add-images-programmatically"></a>Per aggiungere immagini a livello di codiceTo add images programmatically  
  
- Utilizzare <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> il metodo della proprietà <xref:System.Windows.Forms.ImageList.Images%2A> dell'elenco immagini.  
  
     Nell'esempio di codice seguente, il percorso impostato per il percorso dell'immagine è la cartella **Documenti.** Questo percorso viene utilizzato perché è possibile presupporre che la maggior parte dei computer che eseguono il sistema operativo Windows includerà questa cartella. La scelta di questo percorso consente inoltre agli utenti che dispongono di livelli minimi di accesso al sistema di eseguire l'applicazione in modo più sicuro. Nell'esempio di codice riportato di <xref:System.Windows.Forms.ImageList> seguito è necessario disporre di un form con un controllo già aggiunto.  
  
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
  
### <a name="to-add-images-with-a-key-value"></a>Per aggiungere immagini con un valore chiave.  
  
- Utilizzare uno <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> dei metodi della proprietà <xref:System.Windows.Forms.ImageList.Images%2A> dell'elenco immagini che accetta un valore di chiave.  
  
     Nell'esempio di codice seguente, il percorso impostato per il percorso dell'immagine è la cartella **Documenti.** Questo percorso viene utilizzato perché è possibile presupporre che la maggior parte dei computer che eseguono il sistema operativo Windows includerà questa cartella. La scelta di questo percorso consente inoltre agli utenti che dispongono di livelli minimi di accesso al sistema di eseguire l'applicazione in modo più sicuro. Nell'esempio di codice riportato di <xref:System.Windows.Forms.ImageList> seguito è necessario disporre di un form con un controllo già aggiunto.  
  
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
  
### <a name="to-remove-all-images-programmatically"></a>Per rimuovere tutte le immagini a livello di codiceTo remove all images programmatically  
  
- Utilizzare <xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A> il metodo per rimuovere una singola immagine  
  
     ,oppure-  
  
     Utilizzare <xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A> il metodo per cancellare tutte le immagini nell'elenco immagini.  
  
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
  
### <a name="to-remove-images-by-key"></a>Per rimuovere le immagini per chiave  
  
- Utilizzare <xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A> il metodo per rimuovere una singola immagine in base alla relativa chiave.  
  
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
- [Panoramica del componente ImageList](imagelist-component-overview-windows-forms.md)
- [Immagini, bitmap e metafile](../advanced/images-bitmaps-and-metafiles.md)
