---
title: 'Procedura: caricare un''immagine utilizzando la finestra di progettazione (Windows Form)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- picture formats
- images [Windows Forms], displaying on Windows Forms
- pictures [Windows Forms], displaying
- forms [Windows Forms], displaying images
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9ca3e3eef1aa9e7414d3c279de5943585703bf9f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a>Procedura: caricare un'immagine utilizzando la finestra di progettazione (Windows Form)
Windows Form <xref:System.Windows.Forms.PictureBox> (controllo), è possibile caricare e visualizzare un'immagine in un form in fase di progettazione, impostando il <xref:System.Windows.Forms.PictureBox.Image%2A> proprietà su un'immagine valida. La tabella seguente illustra i tipi di file consentiti.  
  
|Tipo|Estensione di file|  
|----------|-------------------------|  
|Bitmap|file con estensione bmp|  
|Icona|ico|  
|GIF|.gif|  
|Metafile|WMF|  
|JPEG|jpg|  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-display-a-picture-at-design-time"></a>Per visualizzare un'immagine in fase di progettazione  
  
1.  Disegnare un <xref:System.Windows.Forms.PictureBox> controllo in un form.  
  
2.  Nella finestra Proprietà, selezionare il <xref:System.Windows.Forms.PictureBox.Image%2A> proprietà, quindi fare clic sul pulsante con i puntini di sospensione per visualizzare il **aprire** la finestra di dialogo.  
  
3.  Se si sta cercando un tipo di file specifico (ad esempio, il file con estensione gif), selezionarla nel **i file di tipo** casella.  
  
4.  Selezionare il file che si desidera visualizzare.  
  
### <a name="to-clear-the-picture-at-design-time"></a>Per rimuovere l'immagine in fase di progettazione  
  
1.  Nel **proprietà** finestra, seleziona il <xref:System.Windows.Forms.PictureBox.Image%2A> proprietà e il pulsante destro del mouse l'immagine di anteprima di piccole dimensioni che viene visualizzato a sinistra del nome dell'oggetto immagine. Scegliere **reimpostare**.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.PictureBox>  
 [Panoramica sul controllo PictureBox](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)  
 [Procedura: Modificare le dimensioni o la posizione di un'immagine in fase di esecuzione](../../../../docs/framework/winforms/controls/how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)  
 [Procedura: Impostare le immagini in fase di esecuzione](../../../../docs/framework/winforms/controls/how-to-set-pictures-at-run-time-windows-forms.md)  
 [Controllo PictureBox](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)
