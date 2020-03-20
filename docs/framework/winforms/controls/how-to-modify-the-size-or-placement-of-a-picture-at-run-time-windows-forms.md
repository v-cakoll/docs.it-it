---
title: "Procedura: modificare le dimensioni o la posizione di un'immagine in fase di esecuzione"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- images [Windows Forms], controlling placement in PictureBox control [Windows Forms]
- examples [Windows Forms], PictureBox control
- PictureBox control [Windows Forms], picture size and alignment
- pictures [Windows Forms], controlling placement in PictureBox control [Windows Forms]
ms.assetid: d0b332a3-fae2-4891-957c-dc3e17743326
ms.openlocfilehash: fea813d7b9fe585e35b729b8b64e3a5f414ef76d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141966"
---
# <a name="how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms"></a>Procedura: modificare le dimensioni o la posizione di un'immagine in fase di esecuzione (Windows Form)
Se si utilizza <xref:System.Windows.Forms.PictureBox> il controllo Windows Form in <xref:System.Windows.Forms.PictureBox.SizeMode%2A> un form, è possibile impostare la proprietà su di esso su:  
  
- Allineare l'angolo superiore sinistro dell'immagine con l'angolo superiore sinistro del controllo  
  
- Centrare l'immagine all'interno del controllo  
  
- Regolare le dimensioni del controllo per adattarlo all'immagine visualizzata  
  
- Allungare qualsiasi immagine visualizzata per adattarla al controllo  
  
 L'allungamento di un'immagine (in particolare una in formato bitmap) può produrre una perdita di qualità dell'immagine. I metafile, che sono elenchi di istruzioni grafiche per disegnare immagini in fase di esecuzione, sono più adatti per l'allungamento rispetto alle bitmap.  
  
### <a name="to-set-the-sizemode-property-at-run-time"></a>Per impostare la proprietà SizeMode in fase di esecuzioneTo set the SizeMode property at run time  
  
1. <xref:System.Windows.Forms.PictureBox.SizeMode%2A> Impostare su <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (impostazione <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>predefinita), , <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>o <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>. <xref:System.Windows.Forms.PictureBoxSizeMode.Normal>indica che l'immagine viene posizionata nell'angolo superiore sinistro del controllo; se l'immagine è più grande del controllo, i bordi inferiore e destro vengono ritagliati. <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>indica che l'immagine è centrata all'interno del controllo; se l'immagine è più grande del controllo, i bordi esterni dell'immagine vengono ritagliati. <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>indica che le dimensioni del controllo vengono regolate in base alle dimensioni dell'immagine. <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>è il contrario e significa che le dimensioni dell'immagine vengono regolate in base alle dimensioni del controllo.  
  
     Nell'esempio seguente, il percorso impostato per il percorso dell'immagine è la cartella Documenti. Questo viene fatto, perché si può supporre che la maggior parte dei computer che eseguono il sistema operativo Windows includerà questa directory. Ciò consente inoltre agli utenti del sistema con livelli di accesso minimo di eseguire l'applicazione senza problemi. Nell'esempio riportato di <xref:System.Windows.Forms.PictureBox> seguito si presuppone che un form con un controllo sia già stato aggiunto.  
  
    ```vb  
    Private Sub StretchPic()  
       ' Stretch the picture to fit the control.  
       PictureBox1.SizeMode = PictureBoxSizeMode.StretchImage  
       ' Load the picture into the control.  
       ' You should replace the bold image
       ' in the sample below with an icon of your own choosing.  
       PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
    End Sub  
    ```  
  
    ```csharp  
    private void StretchPic(){  
       // Stretch the picture to fit the control.  
       PictureBox1.SizeMode = PictureBoxSizeMode.StretchImage;  
       // Load the picture into the control.  
       // You should replace the bold image
       // in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       + @"\Image.gif")  
    }  
    ```  
  
    ```cpp  
    private:  
       void StretchPic()  
       {  
          // Stretch the picture to fit the control.  
          pictureBox1->SizeMode = PictureBoxSizeMode::StretchImage;  
          // Load the picture into the control.  
          // You should replace the bold image
          // in the sample below with an icon of your own choosing.  
          pictureBox1->Image = Image::FromFile(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
       }  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.PictureBox>
- [Procedura: caricare un'immagine utilizzando la finestra di progettazione](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [Cenni preliminari sul controllo PictureBox](picturebox-control-overview-windows-forms.md)
- [Procedura: impostare le immagini in fase di esecuzione](how-to-set-pictures-at-run-time-windows-forms.md)
- [Controllo PictureBox](picturebox-control-windows-forms.md)
