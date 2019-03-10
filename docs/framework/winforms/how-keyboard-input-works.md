---
title: Funzionamento dell'input da tastiera
ms.date: 03/30/2017
helpviewer_keywords:
- keyboard input [Windows Forms], about keyboard input
- keyboards [Windows Forms], keyboard input
- Windows Forms, keyboard input
ms.assetid: 9a29433c-a180-49bb-b74c-d187786584c8
ms.openlocfilehash: a7965c1dcf36e956abd7930b8ff0154b13173b76
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57718025"
---
# <a name="how-keyboard-input-works"></a>Funzionamento dell'input da tastiera
Windows Forms elabora gli input della tastiera generando eventi di tastiera in risposta ai messaggi di Windows. La maggioranza delle applicazioni Windows Forms elabora gli input della tastiera tramite la gestione dei relativi eventi. Tuttavia è necessario conoscere il funzionano dei messaggi della tastiera per poter implementare scenari più avanzati di input dalla tastiera, ad esempio l'intercettazione dei tasti prima che raggiungano un controllo. Questo argomento descrive i tipi di dati di tasti che Windows Forms riconosce e fornisce una panoramica del modo in cui vengono instradati i messaggi della tastiera. Per informazioni sugli eventi della tastiera, vedere [Utilizzo degli eventi di tastiera](using-keyboard-events.md).  
  
## <a name="types-of-keys"></a>Tipi di tasti  
 Windows Forms identifica gli input da tastiera come codici di tasti virtuali rappresentati dai bit per bit <xref:System.Windows.Forms.Keys> enumerazione. Con la <xref:System.Windows.Forms.Keys> enumerazione, è possibile combinare una serie di tasti premuti in un singolo valore. Questi valori corrispondono ai valori che accompagnano i messaggi di Windows WM_KEYDOWN e WM_SYSKEYDOWN. È possibile rilevare pressioni di tasti più fisiche gestendo il <xref:System.Windows.Forms.Control.KeyDown> o <xref:System.Windows.Forms.Control.KeyUp> gli eventi. I tasti carattere sono un sottoinsieme del <xref:System.Windows.Forms.Keys> enumerazione e corrispondono ai valori che accompagnano i messaggi WM_CHAR e WM_SYSCHAR Windows. Se la combinazione di tasti premuti genera un carattere, è possibile rilevare il carattere gestendo il <xref:System.Windows.Forms.Control.KeyPress> evento. In alternativa, è possibile usare <xref:Microsoft.VisualBasic.Devices.Keyboard>, esposta dall'interfaccia di programmazione Visual Basic, per individuare i tasti premuti e inviare le chiavi. Per altre informazioni, vedere [Accesso alla tastiera](~/docs/visual-basic/developing-apps/programming/computer-resources/accessing-the-keyboard.md).  
  
## <a name="order-of-keyboard-events"></a>Ordine degli eventi di tastiera  
 Come indicato in precedenza, ci sono 3 eventi correlati alla tastiera che possono verificarsi in un controllo. La sequenza seguente illustra l'ordine generale degli eventi:  
  
1.  L'utente preme il tasto "a", il tasto viene pre-elaborato, inviato e un <xref:System.Windows.Forms.Control.KeyDown> evento si verifica.  
  
2.  L'utente tiene premuto il tasto "a", il tasto viene pre-elaborato, inviato e un <xref:System.Windows.Forms.Control.KeyPress> evento si verifica.  
  
     Questo evento si verifica più volte quando l'utente tiene premuto un tasto.  
  
3.  L'utente rilascia il tasto "a", il tasto viene pre-elaborato, inviato e un <xref:System.Windows.Forms.Control.KeyUp> evento si verifica.  
  
## <a name="preprocessing-keys"></a>Pre-elaborazione dei tasti  
 Come gli altri messaggi, i messaggi della tastiera vengono elaborati nel <xref:System.Windows.Forms.Control.WndProc%2A> metodo di un form o controllo. Tuttavia, prima della tastiera vengono elaborati i messaggi, il <xref:System.Windows.Forms.Control.PreProcessMessage%2A> metodo chiama uno o più metodi che possono essere sostituiti per gestire le chiavi di caratteri speciali e i tasti fisici. È possibile eseguire l'override di questi metodi per rilevare e filtrare alcuni tasti prima che i messaggi vengano elaborati dal controllo. La tabella seguente mostra l'azione che viene eseguita e il relativo metodo correlato che si verifica, nell'ordine in cui il metodo si verifica.  
  
### <a name="preprocessing-for-a-keydown-event"></a>Pre-elaborazione per un evento KeyDown  
  
|Operazione|Metodo correlato|Note|  
|------------|--------------------|-----------|  
|Cercare un tasto di comando, ad esempio un tasto acceleratore o un tasto di menu di scelta rapida.|<xref:System.Windows.Forms.Control.ProcessCmdKey%2A>|Questo metodo elabora un tasto di comando, che ha la precedenza sui tasti normali. Se questo metodo restituisce `true`, il messaggio del tasto non viene inviato e non si verifica alcun evento del tasto. Se viene restituito `false`, <xref:System.Windows.Forms.Control.IsInputKey%2A> viene chiamato`.`|  
|Verificare la presenza di un tasto speciale che richiede una pre-elaborazione o un tasto carattere normale che deve generare un <xref:System.Windows.Forms.Control.KeyDown> evento ed essere inviato a un controllo.|<xref:System.Windows.Forms.Control.IsInputKey%2A>|Se il metodo restituisce `true`, significa che il controllo è un carattere normale e un <xref:System.Windows.Forms.Control.KeyDown> viene generato l'evento. Se `false`, <xref:System.Windows.Forms.Control.ProcessDialogKey%2A> viene chiamato. **Nota:**  Per garantire un controllo ottiene una chiave o una combinazione di chiavi, è possibile gestire il <xref:System.Windows.Forms.Control.PreviewKeyDown> evento e impostare <xref:System.Windows.Forms.PreviewKeyDownEventArgs.IsInputKey%2A> delle <xref:System.Windows.Forms.PreviewKeyDownEventArgs> a `true` per uno o più tasti desiderati.|  
|Cercare un tasto di spostamento (ESC, TAB, INVIO o tasti di direzione).|<xref:System.Windows.Forms.Control.ProcessDialogKey%2A>|Questo metodo elabora un tasto fisico che impiega funzionalità speciali all'interno del controllo, ad esempio spostando lo stato attivo tra il controllo e il relativo elemento padre. Se il controllo immediato non gestisce la chiave, il <xref:System.Windows.Forms.Control.ProcessDialogKey%2A> viene chiamato sul controllo padre e così via fino al primo controllo nella gerarchia. Se questo metodo restituisce `true`, la pre-elaborazione è completa e non viene generato alcun evento di tasto. Se viene restituito `false`, un <xref:System.Windows.Forms.Control.KeyDown> evento si verifica.|  
  
### <a name="preprocessing-for-a-keypress-event"></a>Pre-elaborazione per un evento KeyPress  
  
|Operazione|Metodo correlato|Note|  
|------------|--------------------|-----------|  
|Verificare se il tasto è un carattere normale che deve essere elaborato dal controllo|<xref:System.Windows.Forms.Control.IsInputChar%2A>|Se il carattere è un carattere normale, questo metodo restituisce `true`, il <xref:System.Windows.Forms.Control.KeyPress> l'evento viene generato e alcuna ulteriore elaborazione si verifica. In caso contrario <xref:System.Windows.Forms.Control.ProcessDialogChar%2A> verrà chiamato.|  
|Verificare se il carattere è un tasto di scelta (ad esempio &OK su un pulsante)|<xref:System.Windows.Forms.Control.ProcessDialogChar%2A>|Questo metodo, simile a <xref:System.Windows.Forms.Control.ProcessDialogKey%2A>, verrà chiamato sulla gerarchia dei controlli. Se il controllo è un controllo contenitore, controlla i tasti di scelta chiamando <xref:System.Windows.Forms.Control.ProcessMnemonic%2A> su se stesso e i relativi controlli figlio. Se <xref:System.Windows.Forms.Control.ProcessDialogChar%2A> restituisce `true`, un <xref:System.Windows.Forms.Control.KeyPress> non vengono generati eventi.|  
  
## <a name="processing-keyboard-messages"></a>Elaborazione dei messaggi della tastiera  
 Dopo che i messaggi della tastiera raggiungono il <xref:System.Windows.Forms.Control.WndProc%2A> metodo di un form o controllo, vengono elaborati da un set di metodi che è possibile eseguire l'override. Ognuno di questi metodi restituisce un <xref:System.Boolean> valore che specifica se il messaggio della tastiera è stato elaborato e utilizzato dal controllo. Se uno dei metodi restituisce `true`, il messaggio viene considerato gestito e non viene passato alla base o all'elemento padre del controllo per un'ulteriore elaborazione. In caso contrario il messaggio rimane nella coda dei messaggi e può essere elaborato in un altro metodo nella base o nell'elemento padre del controllo. La tabella seguente presenta i metodi che elaborano i messaggi della tastiera.  
  
|Metodo|Note|  
|------------|-----------|  
|<xref:System.Windows.Forms.Control.ProcessKeyMessage%2A>|Questo metodo elabora tutti i messaggi della tastiera che vengono ricevuti i <xref:System.Windows.Forms.Control.WndProc%2A> metodo del controllo.|  
|<xref:System.Windows.Forms.Control.ProcessKeyPreview%2A>|Questo metodo invia il messaggio della tastiera all'elemento padre del controllo. Se <xref:System.Windows.Forms.Control.ProcessKeyPreview%2A> restituisce `true`, non viene generato alcun evento di tasto, altrimenti <xref:System.Windows.Forms.Control.ProcessKeyEventArgs%2A> viene chiamato.|  
|<xref:System.Windows.Forms.Control.ProcessKeyEventArgs%2A>|Questo metodo genera le <xref:System.Windows.Forms.Control.KeyDown>, <xref:System.Windows.Forms.Control.KeyPress>, e <xref:System.Windows.Forms.Control.KeyUp> , gli eventi appropriati.|  
  
## <a name="overriding-keyboard-methods"></a>Override dei metodi della tastiera  
 Sono disponibili molti metodi di cui eseguire l'override quando un messaggio della tastiera viene pre-elaborato ed elaborato, tuttavia alcuni metodi sono preferibili ad altri. La tabella seguente mostra le attività che è possibile eseguire e il modo migliore per eseguire l'override dei metodi della tastiera. Per altre informazioni sull'override dei metodi, vedere [override di proprietà e metodi nelle classi derivate](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md#overriding-properties-and-methods-in-derived-classes).  
  
|Attività|Metodo|  
|----------|------------|  
|Intercettare un tasto di spostamento e generare un <xref:System.Windows.Forms.Control.KeyDown> evento. Ad esempio si desidera che TAB e INVIO siano gestiti in una casella di testo.|Eseguire l'override di <xref:System.Windows.Forms.Control.IsInputKey%2A>. **Nota:**  In alternativa, è possibile gestire il <xref:System.Windows.Forms.Control.PreviewKeyDown> evento e impostare <xref:System.Windows.Forms.PreviewKeyDownEventArgs.IsInputKey%2A> delle <xref:System.Windows.Forms.PreviewKeyDownEventArgs> a `true` per uno o più tasti desiderati.|  
|Eseguire la gestione di input speciali o dello spostamento su un controllo. Ad esempio si desidera che l'uso dei tasti di direzione nel controllo elenco cambi la voce selezionata.|Eseguire l'override di <xref:System.Windows.Forms.Control.ProcessDialogKey%2A>.|  
|Intercettare un tasto di spostamento e generare un <xref:System.Windows.Forms.Control.KeyPress> evento. Ad esempio in un controllo casella di selezione si desidera che più pressioni di un tasto di direzione accelerino lo spostamento tra le voci.|Eseguire l'override di <xref:System.Windows.Forms.Control.IsInputChar%2A>.|  
|Eseguire la gestione di input o di navigazione speciali durante un <xref:System.Windows.Forms.Control.KeyPress> evento. Ad esempio, in un controllo elenco, tenendo premuto il tasto "r" si passa fra le voci che iniziano con la lettera r.|Eseguire l'override di <xref:System.Windows.Forms.Control.ProcessDialogChar%2A>.|  
|Eseguire una gestione personalizzata dei tasti di scelta; ad esempio, si desidera gestire i tasti di scelta sui pulsanti disegnati dal proprietario contenuti in una barra degli strumenti.|Eseguire l'override di <xref:System.Windows.Forms.Control.ProcessMnemonic%2A>.|  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.WndProc%2A>
- <xref:System.Windows.Forms.Control.PreProcessMessage%2A>
- [Oggetto My.Computer.Keyboard](~/docs/visual-basic/language-reference/objects/my-computer-keyboard-object.md)
- [Accesso alla tastiera](~/docs/visual-basic/developing-apps/programming/computer-resources/accessing-the-keyboard.md)
- [Utilizzo degli eventi di tastiera](using-keyboard-events.md)
