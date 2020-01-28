---
title: 'Procedura: impostare le immagini in fase di esecuzione'
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
ms.openlocfilehash: bd0509c05fd9c1cfc0c631fcd613c64d20296f6b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746741"
---
# <a name="how-to-set-pictures-at-run-time-windows-forms"></a>Procedura: impostare le immagini in fase di esecuzione (Windows Form)
È possibile impostare a livello di codice l'immagine visualizzata da un Windows Forms controllo <xref:System.Windows.Forms.PictureBox>.  
  
### <a name="to-set-a-picture-programmatically"></a>Per impostare un'immagine a livello di codice  
  
- Impostare la proprietà <xref:System.Windows.Forms.PictureBox.Image%2A> utilizzando il metodo <xref:System.Drawing.Image.FromFile%2A> della classe <xref:System.Drawing.Image>.  
  
     Nell'esempio seguente, il percorso impostato per il percorso dell'immagine è la cartella documenti. Questa operazione viene eseguita perché è possibile presupporre che la maggior parte dei computer che eseguono il sistema operativo Windows includa questa directory. Ciò consente inoltre agli utenti del sistema con livelli di accesso minimo di eseguire l'applicazione senza problemi. Nell'esempio seguente si presuppone un modulo con un controllo <xref:System.Windows.Forms.PictureBox> già aggiunto.  
  
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
  
### <a name="to-clear-a-graphic"></a>Per cancellare una rappresentazione grafica  
  
- Per prima cosa, rilasciare la memoria usata dall'immagine, quindi deselezionare la rappresentazione grafica. Il processo di Garbage Collection libera la memoria in un secondo momento se la gestione della memoria costituisce un problema.  
  
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
    > Per altre informazioni sui motivi per cui è necessario usare il metodo <xref:System.Drawing.Image.Dispose%2A> in questo modo, vedere [pulizia delle risorse non gestite](../../../standard/garbage-collection/unmanaged.md).  
  
     Questo codice cancellerà l'immagine anche se un grafico è stato caricato nel controllo in fase di progettazione.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.PictureBox>
- <xref:System.Drawing.Image.FromFile%2A?displayProperty=nameWithType>
- [Panoramica sul controllo PictureBox](picturebox-control-overview-windows-forms.md)
- [Procedura: Caricare un'immagine usando la finestra di progettazione](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [Procedura: Modificare le dimensioni o la posizione di un'immagine in fase di esecuzione](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [Controllo PictureBox](picturebox-control-windows-forms.md)
