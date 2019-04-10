---
title: 'Procedura: Designare un pulsante Windows Forms come pulsante di conferma usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], default on Windows Forms
- Accept button on Windows Forms
- Button control [Windows Forms], designating as default
- Windows Forms controls, default button on form
ms.assetid: a1da0590-755f-49f2-aca7-609fac6351bf
ms.openlocfilehash: e0eaa90c8450888ea325470db5d4adae555f8d82
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59304168"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button-using-the-designer"></a>Procedura: Designare un pulsante Windows Forms come pulsante di conferma usando la finestra di progettazione
In qualsiasi forma di Windows, è possibile designare un <xref:System.Windows.Forms.Button> controllo pulsante di conferma, noto anche come pulsante predefinito. Ogni volta che l'utente preme il tasto INVIO, viene scelto il pulsante predefinito indipendentemente da quale altro controllo sul form ha lo stato attivo. Le eccezioni a questo si verifica se il controllo con lo stato attivo è un altro pulsante, in tal caso, verrà fatto clic sul pulsante con lo stato attivo, o una casella di testo su più righe o un controllo personalizzato che intercetta il tasto INVIO.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-designate-the-accept-button"></a>Per designare il pulsante accept  
  
1. Selezionare il form in cui risiede il pulsante.  
  
2. Nel **delle proprietà** finestra, impostare il modulo <xref:System.Windows.Forms.Form.AcceptButton%2A> proprietà per il <xref:System.Windows.Forms.Button> nome del controllo.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Form.AcceptButton%2A>
- [Panoramica del controllo Button](button-control-overview-windows-forms.md)
- [Modalità di selezione di un controllo Button Windows Form](ways-to-select-a-windows-forms-button-control.md)
- [Procedura: Rispondere alla selezione dei pulsanti Windows Forms](how-to-respond-to-windows-forms-button-clicks.md)
- [Procedura: Designare un pulsante Windows Forms come pulsante di annullamento usando la finestra di progettazione](designate-a-wf-button-as-the-cancel-button-using-the-designer.md)
- [Controllo Button](button-control-windows-forms.md)
