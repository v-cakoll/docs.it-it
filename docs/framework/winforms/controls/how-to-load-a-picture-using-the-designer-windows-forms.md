---
title: "Procedura: caricare un'immagine utilizzando la finestra di progettazione"
ms.date: 03/30/2017
helpviewer_keywords:
- picture formats
- images [Windows Forms], displaying on Windows Forms
- pictures [Windows Forms], displaying
- forms [Windows Forms], displaying images
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
ms.openlocfilehash: 12b90d561a18fcffaafb9c45b7fa6be6dd060215
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736332"
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a>Procedura: caricare un'immagine utilizzando la finestra di progettazione (Windows Form)

Con il controllo Windows Forms <xref:System.Windows.Forms.PictureBox>, è possibile caricare e visualizzare un'immagine in un form in fase di progettazione impostando la proprietà <xref:System.Windows.Forms.PictureBox.Image%2A> su un'immagine valida. Nella tabella seguente sono elencati i tipi di file accettabili.

|Type|Estensione del nome di file|
|---|---|
|Bitmap|.bmp|
|Icona|ico|
|GIF|.gif|
|Metafile|.wmf|
|JPEG|.jpg|

## <a name="to-display-a-picture-at-design-time"></a>Per visualizzare un'immagine in fase di progettazione

1. Creare un controllo <xref:System.Windows.Forms.PictureBox> in un form.

2. Nella finestra **Proprietà** selezionare la proprietà <xref:System.Windows.Forms.PictureBox.Image%2A>, quindi fare clic sul pulsante con i puntini di sospensione per visualizzare la finestra di dialogo **Apri** .

3. Se si sta cercando un tipo di file specifico, ad esempio file con estensione gif, selezionarlo nella casella **file di tipo** .

4. Selezionare il file che si desidera visualizzare.

## <a name="to-clear-the-picture-at-design-time"></a>Per cancellare l'immagine in fase di progettazione

1. Nella finestra **Proprietà** selezionare la proprietà <xref:System.Windows.Forms.PictureBox.Image%2A>. Fare clic con il pulsante destro del mouse sull'immagine di anteprima ridotta che viene visualizzata a sinistra del nome dell'oggetto immagine, quindi scegliere **Reimposta**.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.PictureBox>
- [Panoramica sul controllo PictureBox](picturebox-control-overview-windows-forms.md)
- [Procedura: Modificare le dimensioni o la posizione di un'immagine in fase di esecuzione](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [Procedura: Impostare le immagini in fase di esecuzione](how-to-set-pictures-at-run-time-windows-forms.md)
- [Controllo PictureBox](picturebox-control-windows-forms.md)
