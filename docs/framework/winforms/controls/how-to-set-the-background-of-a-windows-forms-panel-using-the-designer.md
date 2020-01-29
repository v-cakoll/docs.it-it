---
title: Impostare lo sfondo di un pannello utilizzando la finestra di progettazione
ms.date: 03/30/2017
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: db83cf54-3c69-4b08-ac6c-25b9b5abb1b0
ms.openlocfilehash: 8bdefba433632f7ba02f549a549c52c7aa56c2d7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731927"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel-using-the-designer"></a>Procedura: impostare lo sfondo di un pannello di Windows Forms utilizzando la finestra di progettazione

Un controllo Windows Forms <xref:System.Windows.Forms.Panel> può visualizzare sia un colore di sfondo che un'immagine di sfondo. La proprietà <xref:System.Windows.Forms.Control.BackColor%2A> imposta il colore di sfondo per i controlli contenuti nel pannello, ad esempio etichette e pulsanti di opzione. Se la proprietà <xref:System.Windows.Forms.Control.BackgroundImage%2A> non è impostata, la selezione <xref:System.Windows.Forms.Control.BackColor%2A> compilerà tutto il pannello. Se la proprietà <xref:System.Windows.Forms.Control.BackgroundImage%2A> è impostata, l'immagine verrà visualizzata dietro i controlli contenuti nel pannello.

Per la procedura seguente è necessario un progetto di **applicazione Windows** con un modulo che contiene un controllo <xref:System.Windows.Forms.Panel>. Per informazioni su come configurare tale progetto in Visual Studio, vedere [procedura: creare un progetto Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [procedura: aggiungere controlli a Windows Forms](how-to-add-controls-to-windows-forms.md).

## <a name="set-the-background-in-the-windows-forms-designer"></a>Impostare lo sfondo nell'Progettazione Windows Form

1. Aprire il progetto in Visual Studio e selezionare il controllo <xref:System.Windows.Forms.Panel>.

2. Nella finestra **Proprietà** fare clic sul pulsante freccia accanto alla proprietà <xref:System.Windows.Forms.Control.BackColor%2A> per visualizzare una finestra con tre schede.

3. Selezionare la scheda **personalizzata** per visualizzare una tavolozza di colori.

4. Selezionare la scheda **Web** o **sistema** per visualizzare un elenco di nomi predefiniti per i colori, quindi selezionare un colore.

5. Nella finestra **Proprietà** fare clic sul pulsante freccia accanto alla proprietà <xref:System.Windows.Forms.Control.BackgroundImage%2A>.

6. Nella finestra di dialogo **Apri** selezionare il file che si desidera visualizzare.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Control.BackColor%2A>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [Controllo Panel](panel-control-windows-forms.md)
- [Panoramica sul controllo Panel](panel-control-overview-windows-forms.md)
- [Procedura: Raggruppare i controlli con il controllo Panel di Windows Form nella finestra di progettazione](group-controls-with-wf-panel-control-using-the-designer.md)
