---
title: 'Procedura: impostare lo sfondo di un controllo Panel Windows Form mediante la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: db83cf54-3c69-4b08-ac6c-25b9b5abb1b0
ms.openlocfilehash: 896aa61f3f0900760dffd09bcab6a08bbc01628d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33535718"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel-using-the-designer"></a>Procedura: impostare lo sfondo di un controllo Panel Windows Form mediante la finestra di progettazione
Un Windows Form <xref:System.Windows.Forms.Panel> controllo può visualizzare un colore di sfondo sia un'immagine di sfondo. Il <xref:System.Windows.Forms.Control.BackColor%2A> proprietà imposta il colore di sfondo per i controlli contenuti nel pannello, ad esempio le etichette e pulsanti di opzione. Se il <xref:System.Windows.Forms.Control.BackgroundImage%2A> non è impostata, il <xref:System.Windows.Forms.Control.BackColor%2A> tutto il pannello verrà riempito dalla selezione. Se il <xref:System.Windows.Forms.Control.BackgroundImage%2A> è impostata, verrà visualizzata l'immagine dietro i controlli contenuti nel pannello.  
  
 La procedura seguente richiede un **applicazione Windows** progetto con un modulo che contiene un <xref:System.Windows.Forms.Panel> controllo. Per informazioni su come configurare questo tipo di progetto, vedere [procedura: creare un progetto di applicazione Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) e [procedura: aggiungere controlli a un Windows Form](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-set-the-background-in-the-windows-forms-designer"></a>Per impostare lo sfondo in Progettazione Windows Form  
  
1.  Selezionare il controllo <xref:System.Windows.Forms.Panel>.  
  
2.  Nel **proprietà** finestra fare clic sulla freccia accanto al <xref:System.Windows.Forms.Control.BackColor%2A> proprietà per visualizzare una finestra con tre schede.  
  
3.  Selezionare il **personalizzato** scheda per visualizzare una tavolozza di colori.  
  
4.  Selezionare il **Web** o **sistema** scheda per visualizzare un elenco di nomi predefiniti dei colori e quindi selezionare un colore.  
  
5.  Nel **proprietà** finestra fare clic sulla freccia accanto al <xref:System.Windows.Forms.Control.BackgroundImage%2A> proprietà.  
  
6.  Nel **aprire** finestra di dialogo, selezionare il file che si desidera visualizzare.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.Control.BackColor%2A>  
 <xref:System.Windows.Forms.Control.BackgroundImage%2A>  
 [Controllo Panel](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)  
 [Panoramica sul controllo Panel](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)  
 [Procedura: Raggruppare i controlli con il controllo Panel di Windows Form nella finestra di progettazione](../../../../docs/framework/winforms/controls/group-controls-with-wf-panel-control-using-the-designer.md)
