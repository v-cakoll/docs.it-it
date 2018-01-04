---
title: 'Procedura: modificare le dimensioni o la posizione di un''immagine in fase di esecuzione (Windows Form)'
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
- images [Windows Forms], controlling placement in PictureBox control [Windows Forms]
- examples [Windows Forms], PictureBox control
- PictureBox control [Windows Forms], picture size and alignment
- pictures [Windows Forms], controlling placement in PictureBox control [Windows Forms]
ms.assetid: d0b332a3-fae2-4891-957c-dc3e17743326
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e02ea1cbcb1fdd86d182bfba23241acb91c4b54a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms"></a>Procedura: modificare le dimensioni o la posizione di un'immagine in fase di esecuzione (Windows Form)
Se si utilizza Windows Form <xref:System.Windows.Forms.PictureBox> controllo in un form, è possibile impostare il <xref:System.Windows.Forms.PictureBox.SizeMode%2A> proprietà in modo da:  
  
-   Allineamento nell'angolo superiore sinistro dell'immagine con l'angolo superiore sinistro del controllo  
  
-   Centrare l'immagine all'interno del controllo  
  
-   Regolare le dimensioni del controllo per adattare l'immagine da visualizzare  
  
-   Estensione qualsiasi immagine da visualizzare per adattarla al controllo  
  
 Estensione di un'immagine (in particolare se in formato bitmap) può causare una perdita della qualità dell'immagine. Metafile, che sono elenchi di istruzioni di grafica per la creazione di immagini in fase di esecuzione, sono più adatti per l'estensione rispetto alle immagini bitmap.  
  
### <a name="to-set-the-sizemode-property-at-run-time"></a>Per impostare la proprietà in fase di esecuzione  
  
1.  Impostare <xref:System.Windows.Forms.PictureBox.SizeMode%2A> a <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (impostazione predefinita), <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>, <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>, o <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>. <xref:System.Windows.Forms.PictureBoxSizeMode.Normal>indica che l'immagine viene posizionata nell'angolo superiore sinistro del controllo. Se l'immagine è più grande del controllo, vengono tagliati relativi bordi inferiori e destro. <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>indica che l'immagine viene centrata all'interno del controllo; Se l'immagine è più grande del controllo, vengono tagliati bordi esterni dell'immagine. <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>significa che le dimensioni del controllo vengano regolata per le dimensioni dell'immagine. <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>è l'opposto e significa che le dimensioni dell'immagine vengono adattate alle dimensioni del controllo.  
  
     Nell'esempio seguente, il percorso impostato per la posizione dell'immagine è la cartella documenti. Ciò accade in quanto è possibile presupporre che la maggior parte dei computer che eseguono il sistema operativo Windows includerà questa directory. Ciò consente inoltre agli utenti del sistema con livelli di accesso minimo di eseguire l'applicazione senza problemi. Nell'esempio seguente si presuppone un form con un <xref:System.Windows.Forms.PictureBox> controllo già aggiunto.  
  
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
 <xref:System.Windows.Forms.PictureBox>  
 [Procedura: Caricare un'immagine usando la finestra di progettazione](../../../../docs/framework/winforms/controls/how-to-load-a-picture-using-the-designer-windows-forms.md)  
 [Panoramica sul controllo PictureBox](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)  
 [Procedura: Impostare le immagini in fase di esecuzione](../../../../docs/framework/winforms/controls/how-to-set-pictures-at-run-time-windows-forms.md)  
 [Controllo PictureBox](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)
