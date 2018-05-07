---
title: "Procedura: impostare l'immagine visualizzata da un controllo Windows Form"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Button control [Windows Forms], images
- Windows Forms controls, images
- controls [Windows Forms], images
- images [Windows Forms], Windows Forms controls
- examples [Windows Forms], controls
ms.assetid: 9445af8f-4f62-48b0-a3f6-068058964b9f
ms.openlocfilehash: 4870f9e2acc48a90e1e2193d514926fedee05f61
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control"></a>Procedura: impostare l'immagine visualizzata da un controllo Windows Form
Vari controlli Windows Form consente di visualizzare immagini. Queste immagini possono essere le icone che illustrano la finalità del controllo, ad esempio un'icona del dischetto su un pulsante indica il **salvare** comando. In alternativa, le icone possono essere immagini di sfondo per fornire il controllo, l'aspetto e il comportamento desiderato.  
  
### <a name="to-set-the-image-displayed-by-a-control"></a>Per impostare l'immagine visualizzata da un controllo  
  
1.  Impostare il controllo `Image` o `BackgroundImage` proprietà a un oggetto di tipo <xref:System.Drawing.Image>. In genere, si verrà caricata l'immagine da un file utilizzando il <xref:System.Drawing.Image.FromFile%2A> metodo.  
  
     Nell'esempio di codice riportato di seguito, il percorso impostato per la posizione dell'immagine è il **immagini** cartella. La maggior parte dei computer che eseguono il sistema operativo Windows includerà questa directory. Ciò consente inoltre agli utenti con livelli di accesso di sistema minimi eseguire l'applicazione in modo sicuro. Esempio di codice seguente richiede che si dispone già di un form con un <xref:System.Windows.Forms.PictureBox> controllo aggiunto.  
  
    ```vb  
    ' Replace the image named below  
    ' with an icon of your own choosing.  
    PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.MyPictures) _  
       & "\Image.gif")  
    ```  
  
    ```csharp  
    // Replace the image named below  
    // with an icon of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    pictureBox1.Image = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.MyPictures)  
       + @"\Image.gif");  
    ```  
  
    ```cpp  
    // Replace the image named below  
    // with an icon of your own choosing.  
    pictureBox1->Image = Image::FromFile(String::Concat  
       (System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::MyPictures),  
       "\\Image.gif"));  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Drawing.Image.FromFile%2A>  
 <xref:System.Drawing.Image>  
 <xref:System.Windows.Forms.Control.BackgroundImage%2A>
