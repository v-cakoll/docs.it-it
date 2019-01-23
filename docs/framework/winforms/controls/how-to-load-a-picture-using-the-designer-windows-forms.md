---
title: "Procedura: Caricare un'immagine utilizzando la finestra di progettazione (Windows Form)"
ms.date: 03/30/2017
helpviewer_keywords:
- picture formats
- images [Windows Forms], displaying on Windows Forms
- pictures [Windows Forms], displaying
- forms [Windows Forms], displaying images
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
ms.openlocfilehash: 6142474c2009e0998852dc28d346e73f4abbf1b0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54539090"
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a>Procedura: Caricare un'immagine utilizzando la finestra di progettazione (Windows Form)
Con i moduli di Windows <xref:System.Windows.Forms.PictureBox> (controllo), è possibile caricare e visualizzare un'immagine in un form in fase di progettazione, impostando il <xref:System.Windows.Forms.PictureBox.Image%2A> proprietà su un'immagine valida. La tabella seguente illustra i tipi di file consentiti.  
  
|Tipo|Estensione del file|  
|----------|-------------------------|  
|Bitmap|.bmp|  
|Icona|ico|  
|GIF|.gif|  
|Metafile|.wmf|  
|JPEG|.jpg|  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-display-a-picture-at-design-time"></a>Per visualizzare un'immagine in fase di progettazione  
  
1.  Disegnare un <xref:System.Windows.Forms.PictureBox> controllo in un form.  
  
2.  Nella finestra Proprietà selezionare la <xref:System.Windows.Forms.PictureBox.Image%2A> proprietà, quindi fare clic sul pulsante dei puntini di sospensione per visualizzare il **Open** nella finestra di dialogo.  
  
3.  Se si sta cercando un tipo di file specifico (ad esempio, il file con estensione gif), selezionarla nel **file di tipo** casella.  
  
4.  Selezionare il file che si desidera visualizzare.  
  
### <a name="to-clear-the-picture-at-design-time"></a>Per rimuovere l'immagine in fase di progettazione  
  
1.  Nel **delle proprietà** finestra, seleziona il <xref:System.Windows.Forms.PictureBox.Image%2A> proprietà e il pulsante destro del mouse il piccolo immagine di anteprima visualizzata a sinistra del nome dell'oggetto immagine. Scegli **reimpostare**.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.PictureBox>
- [Panoramica sul controllo PictureBox](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)
- [Procedura: Modificare le dimensioni o la posizione di un'immagine in fase di esecuzione](../../../../docs/framework/winforms/controls/how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [Procedura: Impostare le immagini in fase di esecuzione](../../../../docs/framework/winforms/controls/how-to-set-pictures-at-run-time-windows-forms.md)
- [Controllo PictureBox](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)
