---
title: "Procedura: caricare un'immagine utilizzando la finestra di progettazione"
description: Informazioni su come usare il controllo PictureBox Windows Forms per caricare e visualizzare un'immagine in un modulo in fase di progettazione.
ms.date: 03/30/2017
helpviewer_keywords:
- picture formats
- images [Windows Forms], displaying on Windows Forms
- pictures [Windows Forms], displaying
- forms [Windows Forms], displaying images
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
ms.openlocfilehash: a05ffe19412fc7a4e3e02f01336d89cce39fac8a
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325598"
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a>Procedura: caricare un'immagine utilizzando la finestra di progettazione (Windows Form)

Con il <xref:System.Windows.Forms.PictureBox> controllo Windows Forms è possibile caricare e visualizzare un'immagine in un form in fase di progettazione impostando la <xref:System.Windows.Forms.PictureBox.Image%2A> proprietà su un'immagine valida. Nella tabella seguente sono elencati i tipi di file accettabili.

|Type|Estensione del file|
|---|---|
|Bitmap|bmp|
|Icona|ico|
|GIF|gif|
|Metafile|WMF|
|JPEG|jpg|

## <a name="to-display-a-picture-at-design-time"></a>Per visualizzare un'immagine in fase di progettazione

1. Creare un <xref:System.Windows.Forms.PictureBox> controllo in un form.

2. Nella finestra **Proprietà** selezionare la <xref:System.Windows.Forms.PictureBox.Image%2A> proprietà, quindi fare clic sul pulsante con i puntini di sospensione per visualizzare la finestra di dialogo **Apri** .

3. Se si sta cercando un tipo di file specifico, ad esempio file con estensione gif, selezionarlo nella casella **file di tipo** .

4. Selezionare il file che si desidera visualizzare.

## <a name="to-clear-the-picture-at-design-time"></a>Per cancellare l'immagine in fase di progettazione

1. Nella finestra **Proprietà** selezionare la <xref:System.Windows.Forms.PictureBox.Image%2A> Proprietà. Fare clic con il pulsante destro del mouse sull'immagine di anteprima ridotta che viene visualizzata a sinistra del nome dell'oggetto immagine, quindi scegliere **Reimposta**.

## <a name="see-also"></a>Vedi anche

- <xref:System.Windows.Forms.PictureBox>
- [Cenni preliminari sul controllo PictureBox](picturebox-control-overview-windows-forms.md)
- [Procedura: modificare le dimensioni o la posizione di un'immagine in fase di esecuzione](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [Procedura: impostare le immagini in fase di esecuzione](how-to-set-pictures-at-run-time-windows-forms.md)
- [Controllo PictureBox](picturebox-control-windows-forms.md)
