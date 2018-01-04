---
title: "Procedura: determinare quale tasto di modifica è stato premuto"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ffe09cc07b3eb36184a7242d418fd6782219806e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-determine-which-modifier-key-was-pressed"></a>Procedura: determinare quale tasto di modifica è stato premuto
Quando si crea un'applicazione che accetta le sequenze di tasti dell'utente, si potrebbe anche decidere di monitorare i tasti di modifica, ad esempio i tasti MAIUSC, ALT e CTRL. Quando viene premuto un tasto di modifica in combinazione con altre chiavi, o con clic del mouse, l'applicazione può rispondere in modo appropriato. Ad esempio, se si preme la lettera S, ciò può comportare semplicemente una "s" venga visualizzato sullo schermo, ma se vengono premuti i tasti CTRL + S, può essere salvato il documento corrente. Se si gestisce il <xref:System.Windows.Forms.Control.KeyDown> evento, il <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> proprietà del <xref:System.Windows.Forms.KeyEventArgs> ricevuto dall'evento gestore specifica vengono premuti i tasti di modifica. In alternativa, il <xref:System.Windows.Forms.KeyEventArgs.KeyData%2A> proprietà <xref:System.Windows.Forms.KeyEventArgs> specifica il carattere che è stato premuto anche come tasti di modifica combinati con un OR bit per bit. Tuttavia, se si sta gestendo il <xref:System.Windows.Forms.Control.KeyPress> evento o un mouse, il gestore dell'evento non riceve le informazioni. In questo caso, è necessario utilizzare il <xref:System.Windows.Forms.Control.ModifierKeys%2A> proprietà la <xref:System.Windows.Forms.Control> classe. In entrambi i casi, è necessario eseguire un'operazione con AND bit per bit dei <xref:System.Windows.Forms.Keys> valore e il valore di cui si sta testando. Il <xref:System.Windows.Forms.Keys> enumerazione offre variazioni di ogni chiave di modificatore, pertanto è importante eseguire bit per bit e con il valore corretto. Ad esempio, il tasto MAIUSC è rappresentato da <xref:System.Windows.Forms.Keys.Shift>, <xref:System.Windows.Forms.Keys.ShiftKey>, <xref:System.Windows.Forms.Keys.RShiftKey> e <xref:System.Windows.Forms.Keys.LShiftKey> il valore corretto per eseguire il test MAIUSC come un tasto di modifica è <xref:System.Windows.Forms.Keys.Shift>. Analogamente, per verificare CTRL e ALT come modificatori è necessario utilizzare il <xref:System.Windows.Forms.Keys.Control> e <xref:System.Windows.Forms.Keys.Alt> rispettivamente i valori.  
  
> [!NOTE]
>  I programmatori Visual Basic possono inoltre accedere a informazioni chiave tramite la <xref:Microsoft.VisualBasic.Devices.Computer.Keyboard%2A> proprietà  
  
### <a name="to-determine-which-modifier-key-was-pressed"></a>Per determinare quale tasto di modifica premuto  
  
-   Utilizzare bit per bit `AND` operatore con il <xref:System.Windows.Forms.Control.ModifierKeys%2A> proprietà e il valore di <xref:System.Windows.Forms.Keys> enumerazione per determinare se viene premuto un tasto di modifica specifico. Esempio di codice seguente viene illustrato come determinare se è premuto il tasto MAIUSC all'interno di un <xref:System.Windows.Forms.Control.KeyPress> gestore dell'evento.  
  
     [!code-cpp[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/cpp/form1.cpp#5)]
     [!code-csharp[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/CS/form1.cs#5)]
     [!code-vb[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/VB/form1.vb#5)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.Keys>  
 <xref:System.Windows.Forms.Control.ModifierKeys%2A>  
 [Input da tastiera in un'applicazione Windows Forms](../../../docs/framework/winforms/keyboard-input-in-a-windows-forms-application.md)  
 [Procedura: determinare se BLOC MAIUSC è attivato in Visual Basic](http://msdn.microsoft.com/en-us/91e60f5c-dd61-4222-ba5f-39af803afd8c)
