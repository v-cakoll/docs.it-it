---
title: 'Procedura: Impostare lo sfondo di un controllo Panel di Windows Forms usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: db83cf54-3c69-4b08-ac6c-25b9b5abb1b0
ms.openlocfilehash: 6927a7118c43ced03623a9764a3ef1e0814c95cb
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211635"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel-using-the-designer"></a>Procedura: Impostare lo sfondo di un controllo panel Windows Form usando la finestra di progettazione

Un controllo Windows Form <xref:System.Windows.Forms.Panel> controllo può visualizzare un colore di sfondo sia un'immagine di sfondo. Il <xref:System.Windows.Forms.Control.BackColor%2A> proprietà imposta il colore di sfondo per i controlli che sono contenuti nel pannello, ad esempio le etichette e i pulsanti di opzione. Se il <xref:System.Windows.Forms.Control.BackgroundImage%2A> non è impostata, il <xref:System.Windows.Forms.Control.BackColor%2A> compilerà tutte del Pannello di selezione. Se il <xref:System.Windows.Forms.Control.BackgroundImage%2A> è impostata, verrà visualizzata l'immagine dietro i controlli contenuti nel pannello.

La procedura seguente richiede un **applicazione di Windows** progetto con un modulo che contiene un <xref:System.Windows.Forms.Panel> controllo. Per informazioni su come configurare tali progetti in Visual Studio, vedere [come: Creare un progetto Windows Forms application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [come: Aggiungere controlli a un Windows Form](how-to-add-controls-to-windows-forms.md).

## <a name="set-the-background-in-the-windows-forms-designer"></a>Impostare lo sfondo in Progettazione Windows Form

1. Aprire il progetto in Visual Studio e selezionare il <xref:System.Windows.Forms.Panel> controllo.

2. Nel **delle proprietà** fare clic sulla freccia accanto al <xref:System.Windows.Forms.Control.BackColor%2A> proprietà per visualizzare una finestra con tre schede.

3. Selezionare il **Custom** pressione di tab per visualizzare una tavolozza dei colori.

4. Selezionare il **Web** oppure **sistema** scheda per visualizzare un elenco di nomi predefiniti per i colori e quindi selezionare un colore.

5. Nel **delle proprietà** fare clic sulla freccia accanto al <xref:System.Windows.Forms.Control.BackgroundImage%2A> proprietà.

6. Nel **aperto** finestra di dialogo, selezionare il file che si desidera visualizzare.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Control.BackColor%2A>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [Controllo Panel](panel-control-windows-forms.md)
- [Panoramica sul controllo Panel](panel-control-overview-windows-forms.md)
- [Procedura: Controlli di gruppo con il controllo Panel di Windows Form usando la finestra di progettazione](group-controls-with-wf-panel-control-using-the-designer.md)
