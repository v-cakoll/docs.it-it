---
title: 'Procedura: Impostare lo sfondo di un controllo Panel di Windows Forms usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: db83cf54-3c69-4b08-ac6c-25b9b5abb1b0
ms.openlocfilehash: e66d8c81114a4550f0473f75a8101e79e8db2c76
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59103714"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel-using-the-designer"></a>Procedura: Impostare lo sfondo di un controllo Panel di Windows Forms usando la finestra di progettazione
Un controllo Windows Form <xref:System.Windows.Forms.Panel> controllo può visualizzare un colore di sfondo sia un'immagine di sfondo. Il <xref:System.Windows.Forms.Control.BackColor%2A> proprietà imposta il colore di sfondo per i controlli che sono contenuti nel pannello, ad esempio le etichette e i pulsanti di opzione. Se il <xref:System.Windows.Forms.Control.BackgroundImage%2A> non è impostata, il <xref:System.Windows.Forms.Control.BackColor%2A> compilerà tutte del Pannello di selezione. Se il <xref:System.Windows.Forms.Control.BackgroundImage%2A> è impostata, verrà visualizzata l'immagine dietro i controlli contenuti nel pannello.  
  
 La procedura seguente richiede un **applicazione di Windows** progetto con un modulo che contiene un <xref:System.Windows.Forms.Panel> controllo. Per informazioni su come configurare un progetto di questo tipo, vedere [come: Creare un progetto Windows Forms application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [come: Aggiungere controlli a un Windows Form](how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-set-the-background-in-the-windows-forms-designer"></a>Per impostare lo sfondo in Progettazione Windows Form  
  
1.  Selezionare il controllo <xref:System.Windows.Forms.Panel>.  
  
2.  Nel **delle proprietà** fare clic sulla freccia accanto al <xref:System.Windows.Forms.Control.BackColor%2A> proprietà per visualizzare una finestra con tre schede.  
  
3.  Selezionare il **Custom** pressione di tab per visualizzare una tavolozza dei colori.  
  
4.  Selezionare il **Web** oppure **sistema** scheda per visualizzare un elenco di nomi predefiniti per i colori e quindi selezionare un colore.  
  
5.  Nel **delle proprietà** fare clic sulla freccia accanto al <xref:System.Windows.Forms.Control.BackgroundImage%2A> proprietà.  
  
6.  Nel **aperto** finestra di dialogo, selezionare il file che si desidera visualizzare.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Control.BackColor%2A>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [Controllo Panel](panel-control-windows-forms.md)
- [Panoramica del controllo Panel](panel-control-overview-windows-forms.md)
- [Procedura: Raggruppare i controlli con il controllo Panel di Windows Forms usando la finestra di progettazione](group-controls-with-wf-panel-control-using-the-designer.md)
