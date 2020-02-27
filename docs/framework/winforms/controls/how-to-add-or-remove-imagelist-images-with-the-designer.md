---
title: 'Procedura: aggiungere o rimuovere immagini ImageList con la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- ImageList component [Windows Forms], adding images
- ImageList component [Windows Forms], removing images
- images [Windows Forms], adding to ImageList component
ms.assetid: 5699b244-e37c-4d20-bc35-7441e55c1e3a
ms.openlocfilehash: cdc7b563a0ee4f8779b99b4e9a6786e78f8d500f
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628722"
---
# <a name="how-to-add-or-remove-imagelist-images-with-the-designer"></a>Procedura: aggiungere o rimuovere immagini ImageList con la finestra di progettazione

È possibile aggiungere immagini a un componente <xref:System.Windows.Forms.ImageList> in modi diversi. È possibile aggiungere immagini molto rapidamente usando lo smart tag associato all'<xref:System.Windows.Forms.ImageList>o, se si impostano diverse altre proprietà nella <xref:System.Windows.Forms.ImageList>, potrebbe risultare più comodo aggiungere immagini con il Finestra Proprietà. È anche possibile aggiungere immagini usando il codice. Per altre informazioni su come aggiungere immagini con il codice, vedere [procedura: aggiungere o rimuovere immagini con il componente Windows Forms ImageList](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md). In genere, il componente <xref:System.Windows.Forms.ImageList> viene popolato con le immagini prima che sia associato a un controllo, ma ciò non è obbligatorio.

### <a name="to-add-or-remove-images-by-using-the-properties-window"></a>Per aggiungere o rimuovere immagini tramite il Finestra Proprietà

1. Selezionare il componente <xref:System.Windows.Forms.ImageList> o aggiungerne uno al modulo.

2. Nella Finestra Proprietà fare clic sul pulsante con i puntini di sospensione (![pulsante con i puntini di sospensione (...) nella Finestra Proprietà di Visual Studio.](./media/visual-studio-ellipsis-button.png)) accanto alla proprietà <xref:System.Windows.Forms.ImageList.Images%2A>.

3. **Nell'Editor raccolta immagini**fare clic su **Aggiungi** o **Rimuovi** per aggiungere o rimuovere immagini dall'elenco.

### <a name="to-add-or-remove-images-using-the-smart-tag"></a>Per aggiungere o rimuovere immagini tramite lo smart tag

1. Selezionare il componente <xref:System.Windows.Forms.ImageList> o aggiungerne uno al modulo.

2. Fare clic sul glifo azioni della finestra di progettazione (![Piccola freccia nera](./media/designer-actions-glyph.gif))

3. Nella finestra di dialogo **attività ImageList** selezionare **Scegli Immagini**.

4. Nell' **Editor dell'insieme immagini** fare clic su **Aggiungi** o **Rimuovi** per aggiungere o rimuovere immagini dall'elenco.

## <a name="see-also"></a>Vedere anche

- [Immagini, bitmap e metafile](../advanced/images-bitmaps-and-metafiles.md)
- [Procedura dettagliata: eseguire attività comuni utilizzando le azioni della finestra di progettazione](perform-common-tasks-design-actions.md)
- [Componente ImageList](imagelist-component-windows-forms.md)
