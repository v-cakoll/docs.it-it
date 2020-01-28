---
title: Modalità di selezione di un controllo Button
ms.date: 03/30/2017
helpviewer_keywords:
- Button control [Windows Forms], selecting
ms.assetid: fe2fc058-5118-4f70-b264-6147d64a7a8d
ms.openlocfilehash: 145166d182f1ec51068ab3e0c23c12b471b69231
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740011"
---
# <a name="ways-to-select-a-windows-forms-button-control"></a>Modalità di selezione di un controllo Button Windows Form
È possibile selezionare un pulsante Windows Forms nei modi seguenti:  
  
- Utilizzare un mouse per fare clic sul pulsante.  
  
- Richiama l'evento <xref:System.Windows.Forms.Control.Click> del pulsante nel codice.  
  
- Spostare lo stato attivo sul pulsante premendo il tasto TAB, quindi scegliere il pulsante premendo la barra SPAZIAtrice o invio.  
  
- Premere il tasto di accesso (ALT + la lettera sottolineata) per il pulsante. Per altre informazioni sulle chiavi di accesso, vedere [procedura: creare chiavi di accesso per controlli Windows Forms](how-to-create-access-keys-for-windows-forms-controls.md).  
  
- Se il pulsante è il pulsante "Accetto" del modulo, premendo invio viene scelto il pulsante, anche se un altro controllo ha lo stato attivo, ad eccezione del fatto che un altro controllo è un altro pulsante, una casella di testo a più righe o un controllo personalizzato che intrappola il tasto INVIO.  
  
- Se il pulsante è il pulsante "Annulla" del modulo, premendo ESC viene scelto il pulsante anche se un altro controllo ha lo stato attivo.  
  
- Chiamare il metodo <xref:System.Windows.Forms.Button.PerformClick%2A> per selezionare il pulsante a livello di codice.  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica sul controllo Button](button-control-overview-windows-forms.md)
- [Procedura: Rispondere alla selezione dei pulsanti di Windows Form](how-to-respond-to-windows-forms-button-clicks.md)
- [Controllo Button](button-control-windows-forms.md)
