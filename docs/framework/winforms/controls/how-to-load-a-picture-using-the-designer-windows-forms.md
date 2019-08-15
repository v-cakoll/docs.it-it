---
title: "Procedura: Caricare un'immagine utilizzando la finestra di progettazione (Windows Forms)"
ms.date: 03/30/2017
helpviewer_keywords:
- picture formats
- images [Windows Forms], displaying on Windows Forms
- pictures [Windows Forms], displaying
- forms [Windows Forms], displaying images
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
ms.openlocfilehash: 818bc63b5b3bea6c73804f716a72ba3cd1a62b4c
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039686"
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a>Procedura: Caricare un'immagine utilizzando la finestra di progettazione (Windows Forms)

Con il controllo <xref:System.Windows.Forms.PictureBox> Windows Forms è possibile caricare e visualizzare un'immagine in un form in fase di progettazione impostando la <xref:System.Windows.Forms.PictureBox.Image%2A> proprietà su un'immagine valida. Nella tabella seguente sono elencati i tipi di file accettabili.

|Type|Estensione del file|
|---|---|
|Bitmap|.bmp|
|Icona|ico|
|GIF|.gif|
|Metafile|.wmf|
|JPEG|.jpg|

## <a name="to-display-a-picture-at-design-time"></a>Per visualizzare un'immagine in fase di progettazione

1. Creare un <xref:System.Windows.Forms.PictureBox> controllo in un form.

2. Nella finestra **Proprietà** selezionare la <xref:System.Windows.Forms.PictureBox.Image%2A> proprietà, quindi fare clic sul pulsante con i puntini di sospensione per visualizzare la finestra di dialogo **Apri** .

3. Se si sta cercando un tipo di file specifico, ad esempio file con estensione gif, selezionarlo nella casella **file di tipo** .

4. Selezionare il file che si desidera visualizzare.

## <a name="to-clear-the-picture-at-design-time"></a>Per cancellare l'immagine in fase di progettazione

1. Nella finestra **Proprietà** selezionare la <xref:System.Windows.Forms.PictureBox.Image%2A> proprietà. Fare clic con il pulsante destro del mouse sull'immagine di anteprima ridotta che viene visualizzata a sinistra del nome dell'oggetto immagine, quindi scegliere **Reimposta**.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.PictureBox>
- [Panoramica sul controllo PictureBox](picturebox-control-overview-windows-forms.md)
- [Procedura: Modificare le dimensioni o la posizione di un'immagine in fase di esecuzione](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [Procedura: Impostare le immagini in fase di esecuzione](how-to-set-pictures-at-run-time-windows-forms.md)
- [Controllo PictureBox](picturebox-control-windows-forms.md)
