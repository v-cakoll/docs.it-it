---
title: 'Procedura: Determinare quale tasto di modifica è stato premuto'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- keyboard input
- shift keys
- events [Windows Forms], mouse
- Keys.ControlKey enumeration member
- keys [Windows Forms], control keys
- user input [Windows Forms], checking for keyboard
- keys [Windows Forms], determining last pressed
- keys [Windows Forms], shift keys
- keys [Windows Forms], modifier keys
- control keys
- keys [Windows Forms], alt keys
- alt keys
- Keys.Shift enumeration member
- events [Windows Forms], keyboard
- keyboards [Windows Forms], keyboard input
- Keys.Alt enumeration member
- modifier keys
ms.assetid: 1e184048-0ae3-4067-a200-d4ba31dbc2cb
ms.openlocfilehash: 37fa897f5a2e1c65cbd5db9189f1500e3427c920
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964318"
---
# <a name="how-to-determine-which-modifier-key-was-pressed"></a>Procedura: Determinare quale tasto di modifica è stato premuto
Quando si crea un'applicazione che accetta le sequenze di tasti dell'utente, può essere utile monitorare anche i tasti di modifica, ad esempio i tasti MAIUSC, ALT e CTRL. Quando si preme un tasto di modifica in combinazione con altre chiavi o con clic del mouse, l'applicazione può rispondere in modo appropriato. Se, ad esempio, si preme la lettera S, è possibile che venga visualizzato uno "s" sullo schermo, ma se vengono premuti i tasti CTRL + S, è possibile salvare il documento corrente. Se si gestisce l' <xref:System.Windows.Forms.Control.KeyDown> evento, la <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> proprietà dell'oggetto <xref:System.Windows.Forms.KeyEventArgs> ricevuto dal gestore eventi specifica i tasti di modifica che vengono premuti. In alternativa, la <xref:System.Windows.Forms.KeyEventArgs.KeyData%2A> proprietà di <xref:System.Windows.Forms.KeyEventArgs> specifica il carattere premuto e tutti i tasti di modifica combinati con un OR bit per bit. Tuttavia, se si gestisce l' <xref:System.Windows.Forms.Control.KeyPress> evento o un evento del mouse, il gestore eventi non riceve queste informazioni. In questo caso, è necessario usare la <xref:System.Windows.Forms.Control.ModifierKeys%2A> proprietà <xref:System.Windows.Forms.Control> della classe. In entrambi i casi, è necessario eseguire un operatore and bit per <xref:System.Windows.Forms.Keys> bit del valore appropriato e il valore che si sta testando. L' <xref:System.Windows.Forms.Keys> enumerazione offre varianti di ogni tasto di modifica, quindi è importante eseguire l'operatore and bit per bit con il valore corretto. Ad esempio, il tasto MAIUSC è rappresentato da <xref:System.Windows.Forms.Keys.Shift> <xref:System.Windows.Forms.Keys.RShiftKey> , <xref:System.Windows.Forms.Keys.ShiftKey>e <xref:System.Windows.Forms.Keys.LShiftKey> il valore corretto per testare lo spostamento come un tasto di modifica <xref:System.Windows.Forms.Keys.Shift>è. Analogamente, per verificare la presenza di tasti CTRL e ALT come modificatori <xref:System.Windows.Forms.Keys.Control> , <xref:System.Windows.Forms.Keys.Alt> è necessario usare rispettivamente i valori e.  
  
> [!NOTE]
> I programmatori Visual Basic possono anche accedere alle informazioni chiave <xref:Microsoft.VisualBasic.Devices.Computer.Keyboard%2A> tramite la proprietà  
  
### <a name="to-determine-which-modifier-key-was-pressed"></a>Per determinare quale tasto di modifica è stato premuto  
  
- Usare l'operatore `AND` bit per bit <xref:System.Windows.Forms.Control.ModifierKeys%2A> con la proprietà <xref:System.Windows.Forms.Keys> e un valore dell'enumerazione per determinare se viene premuto un particolare tasto di modifica. Nell'esempio di codice seguente viene illustrato come determinare se il tasto MAIUSC è premuto in <xref:System.Windows.Forms.Control.KeyPress> un gestore eventi.  
  
     [!code-cpp[System.Windows.Forms.DetermineModifierKey#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/cpp/form1.cpp#5)]
     [!code-csharp[System.Windows.Forms.DetermineModifierKey#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/CS/form1.cs#5)]
     [!code-vb[System.Windows.Forms.DetermineModifierKey#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/VB/form1.vb#5)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.ModifierKeys%2A>
- [Input da tastiera in un'applicazione Windows Forms](keyboard-input-in-a-windows-forms-application.md)
- [Procedura: Determinare se CapsLock è on in Visual Basic](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9c9d1fz9(v=vs.100))
