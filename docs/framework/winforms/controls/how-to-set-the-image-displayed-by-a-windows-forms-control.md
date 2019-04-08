---
title: "Procedura: Impostare l'immagine visualizzata da un controllo di Windows Forms"
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
ms.openlocfilehash: 031ddcb3b852e75353fed7420735350e79f23df3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59085090"
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control"></a>Procedura: Impostare l'immagine visualizzata da un controllo di Windows Forms
Vari controlli Windows Form consente di visualizzare immagini. Queste immagini possono essere le icone che chiariscono lo scopo del controllo, ad esempio un'icona del dischetto su un pulsante indica la **salvare** comando. In alternativa, le icone possono essere immagini di sfondo per fornire il controllo, l'aspetto e il comportamento desiderato.  
  
### <a name="to-set-the-image-displayed-by-a-control"></a>Per impostare l'immagine visualizzata da un controllo  
  
1.  Impostare il controllo `Image` oppure `BackgroundImage` proprietà di un oggetto di tipo <xref:System.Drawing.Image>. In generale, è caricata l'immagine da un file usando il <xref:System.Drawing.Image.FromFile%2A> (metodo).  
  
     Nell'esempio di codice seguente, il percorso impostato per il percorso dell'immagine è il **My Pictures** cartella. La maggior parte dei computer che eseguono il sistema operativo Windows includeranno questa directory. Ciò consente inoltre agli utenti con livelli di accesso di sistema minimi eseguire l'applicazione in modo sicuro. Esempio di codice seguente richiede che hai già un form con un <xref:System.Windows.Forms.PictureBox> controllo aggiunto.  
  
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

- <xref:System.Drawing.Image.FromFile%2A>
- <xref:System.Drawing.Image>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
