---
title: 'Procedura: Impostare le immagini in fase di esecuzione (Windows Form)'
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
ms.openlocfilehash: 8275961a8f11332a04f89561fac779f4cdf9f8d8
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64609406"
---
# <a name="how-to-set-pictures-at-run-time-windows-forms"></a>Procedura: Impostare le immagini in fase di esecuzione (Windows Form)
È possibile impostare a livello di codice l'immagine visualizzata da un controllo Windows Form <xref:System.Windows.Forms.PictureBox> controllo.  
  
### <a name="to-set-a-picture-programmatically"></a>Per impostare un'immagine a livello di codice  
  
- Impostare il <xref:System.Windows.Forms.PictureBox.Image%2A> proprietà utilizzando il <xref:System.Drawing.Image.FromFile%2A> metodo il <xref:System.Drawing.Image> classe.  
  
     Nell'esempio seguente, il percorso impostato per la posizione dell'immagine è la cartella documenti. Questa operazione viene eseguita, perché si presume che la maggior parte dei computer che eseguono il sistema operativo Windows sarà inclusa questa directory. Ciò consente inoltre agli utenti del sistema con livelli di accesso minimo di eseguire l'applicazione senza problemi. L'esempio seguente si presuppone un form con un <xref:System.Windows.Forms.PictureBox> controllo già aggiunto.  
  
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
  
- In primo luogo, rilasciare la memoria utilizzata dall'immagine e quindi deselezionare l'icona. Operazione di Garbage collection consente di liberare la memoria in un secondo momento se la gestione della memoria diventa un problema.  
  
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
    >  Per altre informazioni sui motivi per cui è consigliabile usare la <xref:System.Drawing.Image.Dispose%2A> metodo in questo modo, vedere [pulizia di risorse non gestite](../../../standard/garbage-collection/unmanaged.md).  
  
     Questo codice verrà cancellata l'immagine, anche se un oggetto grafico è stato caricato nel controllo in fase di progettazione.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.PictureBox>
- <xref:System.Drawing.Image.FromFile%2A?displayProperty=nameWithType>
- [Panoramica sul controllo PictureBox](picturebox-control-overview-windows-forms.md)
- [Procedura: Caricare un'immagine utilizzando la finestra di progettazione](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [Procedura: Modificare le dimensioni o la posizione di un'immagine in fase di esecuzione](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [Controllo PictureBox](picturebox-control-windows-forms.md)
