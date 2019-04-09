---
title: "Procedura: Modificare le dimensioni o la posizione di un'immagine in fase di esecuzione (Windows Form)"
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
ms.openlocfilehash: 5d817d34e47253b2e35afa7bb41c59eea06e1f94
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178828"
---
# <a name="how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms"></a>Procedura: Modificare le dimensioni o la posizione di un'immagine in fase di esecuzione (Windows Form)
Se si usa moduli di Windows <xref:System.Windows.Forms.PictureBox> controllo in un form, è possibile impostare il <xref:System.Windows.Forms.PictureBox.SizeMode%2A> proprietà in modo da:  
  
-   Allineamento nell'angolo superiore sinistro dell'immagine con l'angolo superiore sinistro del controllo  
  
-   Centrare l'immagine all'interno del controllo  
  
-   Regolare le dimensioni del controllo da adattare l'immagine da visualizzare.  
  
-   Estendere qualsiasi immagine da visualizzare per adattarla al controllo  
  
 Estensione di un'immagine (specialmente uno in formato bitmap) può causare una perdita della qualità dell'immagine. Metafile, che sono elenchi di istruzioni di grafica per la creazione di immagini in fase di esecuzione, sono più adatti per l'estensione rispetto alle immagini bitmap.  
  
### <a name="to-set-the-sizemode-property-at-run-time"></a>Per impostare la proprietà in fase di esecuzione  
  
1.  Impostare <xref:System.Windows.Forms.PictureBox.SizeMode%2A> al <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (impostazione predefinita), <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>, <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>, o <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>. <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> significa che l'immagine viene posizionato nell'angolo superiore sinistro del controllo; Se l'immagine è superiore a quello del controllo, vengono ritagliati i bordi inferiore e destro. <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage> significa che l'immagine viene centrata all'interno del controllo; Se l'immagine è superiore a quello del controllo, vengono tagliati bordi esterni dell'immagine. <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> significa che le dimensioni del controllo vengano regolata per le dimensioni dell'immagine. <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage> è l'opposto e significa che le dimensioni dell'immagine sono regolata per le dimensioni del controllo.  
  
     Nell'esempio seguente, il percorso impostato per la posizione dell'immagine è la cartella documenti. Questa operazione viene eseguita, perché si presume che la maggior parte dei computer che eseguono il sistema operativo Windows sarà inclusa questa directory. Ciò consente inoltre agli utenti del sistema con livelli di accesso minimo di eseguire l'applicazione senza problemi. L'esempio seguente si presuppone un form con un <xref:System.Windows.Forms.PictureBox> controllo già aggiunto.  
  
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
- [Procedura: Caricare un'immagine usando la finestra di progettazione](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [Panoramica del controllo PictureBox](picturebox-control-overview-windows-forms.md)
- [Procedura: Impostare le immagini in fase di esecuzione](how-to-set-pictures-at-run-time-windows-forms.md)
- [Controllo PictureBox](picturebox-control-windows-forms.md)
