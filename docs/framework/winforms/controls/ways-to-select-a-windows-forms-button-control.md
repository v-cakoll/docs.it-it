---
title: Modalità di selezione di un controllo Button Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- Button control [Windows Forms], selecting
ms.assetid: fe2fc058-5118-4f70-b264-6147d64a7a8d
ms.openlocfilehash: f2881646a05d257044c6461f822a4c35a225f8c8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61759843"
---
# <a name="ways-to-select-a-windows-forms-button-control"></a>Modalità di selezione di un controllo Button Windows Form
È possibile selezionare un pulsante Windows Form nei modi seguenti:  
  
- Consente di fare clic sul pulsante del mouse.  
  
- Richiamo del pulsante <xref:System.Windows.Forms.Control.Click> evento nel codice.  
  
- Spostare lo stato attivo al pulsante premendo il tasto TAB e quindi scegliere il pulsante premendo la barra spaziatrice o INVIO.  
  
- Premere il tasto di scelta (ALT + lettera sottolineata) per il pulsante. Per altre informazioni sulle chiavi di accesso, vedere [come: Creare le chiavi di accesso per i controlli di Windows Form](how-to-create-access-keys-for-windows-forms-controls.md).  
  
- Se il pulsante è il pulsante "accept" del form, premendo INVIO sceglie il pulsante, anche se un altro controllo ha lo stato attivo, a meno che quest ' è un altro pulsante, una casella di testo su più righe o un controllo personalizzato che intercetta il tasto INVIO.  
  
- Se il pulsante è il pulsante "Annulla" del form, il tasto ESC sceglie il pulsante, anche se un altro controllo ha lo stato attivo.  
  
- Chiamare il <xref:System.Windows.Forms.Button.PerformClick%2A> metodo per selezionare il pulsante a livello di codice.  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica sul controllo Button](button-control-overview-windows-forms.md)
- [Procedura: Rispondere alle selezioni dei pulsanti di Windows Form](how-to-respond-to-windows-forms-button-clicks.md)
- [Controllo Button](button-control-windows-forms.md)
