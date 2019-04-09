---
title: 'Procedura: Designare un pulsante Windows Forms come pulsante di annullamento usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 30e77d9c-d565-4ab5-a84a-62c043af8822
ms.openlocfilehash: be0847d1837ec85ed9d82dc7cc879d0cffa19cd6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59156221"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button-using-the-designer"></a>Procedura: Designare un pulsante Windows Forms come pulsante di annullamento usando la finestra di progettazione
In qualsiasi forma di Windows, è possibile designare un <xref:System.Windows.Forms.Button> controllo pulsante di annullamento. Ogni volta che l'utente preme il tasto ESC, indipendentemente da quale altro controllo sul form ha lo stato attivo, viene scelto un pulsante Annulla. Il pulsante di annullamento viene in genere programmate per consentire all'utente di abbandonare un'operazione senza il commit di alcuna azione.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-designate-the-cancel-button"></a>Per designare il pulsante Annulla  
  
1.  Selezionare il form in cui risiede il pulsante.  
  
2.  Nel **delle proprietà** finestra, impostare il modulo <xref:System.Windows.Forms.Form.CancelButton%2A> proprietà per il <xref:System.Windows.Forms.Button> nome del controllo.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Form.CancelButton%2A>
- [Panoramica del controllo Button](button-control-overview-windows-forms.md)
- [Modalità di selezione di un controllo Button Windows Form](ways-to-select-a-windows-forms-button-control.md)
- [Procedura: Rispondere alla selezione dei pulsanti Windows Forms](how-to-respond-to-windows-forms-button-clicks.md)
- [Procedura: Designare un pulsante Windows Forms come pulsante di conferma usando la finestra di progettazione](designate-a-wf-button-as-the-accept-button-using-the-designer.md)
- [Controllo Button](button-control-windows-forms.md)
