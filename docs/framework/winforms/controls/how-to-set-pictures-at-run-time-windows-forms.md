---
title: 'Procedura: impostare le immagini in fase di esecuzione (Windows Form)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- pictures [Windows Forms], setting display
- examples [Windows Forms], PictureBox control
- bitmaps [Windows Forms], displaying in PictureBox control [Windows Forms]
- PictureBox control [Windows Forms], adding images
- images [Windows Forms], adding with PictureBox control [Windows Forms]
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 18ca41d0-68a5-4660-985e-a6c1fbc01d76
ms.openlocfilehash: fedddf56966c3ab11a1dfb20c1d4cbd8a45fb1a9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33533474"
---
# <a name="how-to-set-pictures-at-run-time-windows-forms"></a>Procedura: impostare le immagini in fase di esecuzione (Windows Form)
È possibile impostare a livello di codice l'immagine visualizzata da un Windows Form <xref:System.Windows.Forms.PictureBox> controllo.  
  
### <a name="to-set-a-picture-programmatically"></a>Per impostare un'immagine a livello di codice  
  
-   Impostare il <xref:System.Windows.Forms.PictureBox.Image%2A> proprietà utilizzando il <xref:System.Drawing.Image.FromFile%2A> metodo la <xref:System.Drawing.Image> classe.  
  
     Nell'esempio seguente, il percorso impostato per la posizione dell'immagine è la cartella documenti. Ciò accade in quanto è possibile presupporre che la maggior parte dei computer che eseguono il sistema operativo Windows includerà questa directory. Ciò consente inoltre agli utenti del sistema con livelli di accesso minimo di eseguire l'applicazione senza problemi. Nell'esempio seguente si presuppone un form con un <xref:System.Windows.Forms.PictureBox> controllo già aggiunto.  
  
    ```vb  
    Private Sub LoadNewPict()  
       ' You should replace the bold image   
       ' in the sample below with an icon of your own choosing.  
       PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
    End Sub  
    ```  
  
    ```csharp  
    private void LoadNewPict(){  
       // You should replace the bold image   
       // in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       pictureBox1.Image = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
    }  
    ```  
  
    ```cpp  
    private:  
       void LoadNewPict()  
       {  
          // You should replace the bold image   
          // in the sample below with an icon of your own choosing.  
          pictureBox1->Image = Image::FromFile(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
       }  
    ```  
  
### <a name="to-clear-a-graphic"></a>Per cancellare un'immagine  
  
-   Innanzitutto, rilasciare la memoria utilizzata dall'immagine e quindi deselezionare l'icona. Operazione di Garbage collection consente di liberare la memoria in un secondo momento se la gestione della memoria diventa un problema.  
  
    ```vb  
    If Not (PictureBox1.Image Is Nothing) Then  
       PictureBox1.Image.Dispose()  
       PictureBox1.Image = Nothing  
    End If  
    ```  
  
    ```csharp  
    if (pictureBox1.Image != null)   
    {  
       pictureBox1.Image.Dispose();  
       pictureBox1.Image = null;  
    }  
    ```  
  
    ```cpp  
    if (pictureBox1->Image != nullptr)  
    {  
       pictureBox1->Image->Dispose();  
       pictureBox1->Image = nullptr;  
    }  
    ```  
  
    > [!NOTE]
    >  Per ulteriori informazioni sui motivi per cui è necessario utilizzare il <xref:System.Drawing.Image.Dispose%2A> metodo in questo modo, vedere [la pulizia di risorse non gestite](../../../../docs/standard/garbage-collection/unmanaged.md).  
  
     Questo codice l'immagine verrà cancellata anche se è stata caricata nel controllo in fase di progettazione.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.PictureBox>  
 <xref:System.Drawing.Image.FromFile%2A?displayProperty=nameWithType>  
 [Panoramica sul controllo PictureBox](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)  
 [Procedura: Caricare un'immagine usando la finestra di progettazione](../../../../docs/framework/winforms/controls/how-to-load-a-picture-using-the-designer-windows-forms.md)  
 [Procedura: Modificare le dimensioni o la posizione di un'immagine in fase di esecuzione](../../../../docs/framework/winforms/controls/how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)  
 [Controllo PictureBox](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)
