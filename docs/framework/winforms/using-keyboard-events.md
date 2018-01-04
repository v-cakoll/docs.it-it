---
title: Utilizzo degli eventi di tastiera
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- KeyPress event [Windows Forms]
- keyboards [Windows Forms], keyboard events
- KeyUp event
- KeyDown event
- keyboard events
- events [Windows Forms], keyboard
ms.assetid: d3f3e14b-a459-4ee6-9875-8957e34f8ee9
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 394ebc503338ad73001aa9859e0aa0d9c3fa42b4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="using-keyboard-events"></a>Utilizzo degli eventi di tastiera
La maggioranza dei programmi di Windows Form elabora gli input della tastiera tramite gestione dei relativi eventi. Questo argomento fornisce una panoramica degli eventi di tastiera, inclusi dettagli su quando usare ogni evento e sui dati forniti per ogni evento.  Vedere anche [panoramica dei gestori eventi (Windows Form)](http://msdn.microsoft.com/library/be6fx1bb\(v=vs.110\)), [Cenni preliminari sugli eventi (Windows Form)](http://msdn.microsoft.com/library/1h12f09z\(v=vs.110\)).  
  
## <a name="keyboard-events"></a>Eventi della tastiera  
 Windows Form include due eventi che si verificano quando un utente preme un tasto e un evento che si verifica quando un utente rilascia un tasto:  
  
-   L'evento <xref:System.Windows.Forms.Control.KeyDown> si verifica una volta.  
  
-   L'evento <xref:System.Windows.Forms.Control.KeyPress>, che può verificarsi più volte quando un utente tiene premuto lo stesso tasto.  
  
-   L'evento <xref:System.Windows.Forms.Control.KeyUp> si verifica una volta quando un utente rilascia un tasto.   
  
 Quando un utente preme un tasto, Windows Form determina quale evento generare in base al fatto che il messaggio della tastiera specifichi un tasto carattere o fisico. Per ulteriori informazioni sulle chiavi fisiche e di carattere, vedere [tastiera funzionamento dell'Input](../../../docs/framework/winforms/how-keyboard-input-works.md).  
  
 La tabella seguente illustra i tre eventi di tastiera.  
  
|Evento della tastiera|Descrizione|Risultati|  
|--------------------|-----------------|-------------|  
|<xref:System.Windows.Forms.Control.KeyDown>|L'evento viene generato quando un utente preme un tasto fisico.|Il gestore per <xref:System.Windows.Forms.Control.KeyDown> riceve:<br /><br /> <ul><li>Un parametro <xref:System.Windows.Forms.KeyEventArgs>, che fornisce la proprietà <xref:System.Windows.Forms.KeyEventArgs.KeyCode%2A> (che specifica un tasto fisico).</li><li>La proprietà <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> (MAIUSC, CTRL o ALT).</li><li>La proprietà <xref:System.Windows.Forms.KeyEventArgs.KeyData%2A>, che combina il codice tasto e il modificatore. Il parametro <xref:System.Windows.Forms.KeyEventArgs> include inoltre:<br /><br /> <ul><li>La proprietà <xref:System.Windows.Forms.KeyEventArgs.Handled%2A>, che può essere impostata per impedire al controllo sottostante di ricevere il tasto.</li><li>La proprietà <xref:System.Windows.Forms.KeyEventArgs.SuppressKeyPress%2A>, utilizzabile per eliminare gli eventi <xref:System.Windows.Forms.Control.KeyPress> e <xref:System.Windows.Forms.Control.KeyUp> per la sequenza di tasti.</li></ul></li></ul>|  
|<xref:System.Windows.Forms.Control.KeyPress>|L'evento viene generato quando il tasto o i tasti premuti corrispondono a un carattere. Ad esempio, se un utente preme i tasti MAIUSC e "a" minuscola, il risultato sarà la lettera "A" maiuscola.|<xref:System.Windows.Forms.Control.KeyPress> viene generato dopo <xref:System.Windows.Forms.Control.KeyDown>.<br /><br /> <ul><li>Il gestore per <xref:System.Windows.Forms.Control.KeyPress> riceve:</li><li>Un parametro <xref:System.Windows.Forms.KeyPressEventArgs>, che include il codice carattere del tasto premuto. Il codice carattere è univoco per ogni combinazione di tasto carattere e tasto modificatore.<br /><br />     Ad esempio, il tasto "A" avrà il risultato seguente:<br /><br /> <ul><li>Il codice carattere 65, se premuto con il tasto MAIUSC</li><li>Oppure il tasto BLOC MAIUSC, 97 se premuto da solo</li><li>E 1, se premuto con il tasto CTRL</li></ul></li></ul>|  
|<xref:System.Windows.Forms.Control.KeyUp>|L'evento viene generato quando un utente rilascia un tasto fisico.|Il gestore per <xref:System.Windows.Forms.Control.KeyUp> riceve:<br /><br /> <ul><li>Un parametro <xref:System.Windows.Forms.KeyEventArgs>:<br /><br /> <ul><li>Che fornisce la proprietà <xref:System.Windows.Forms.KeyEventArgs.KeyCode%2A> (che specifica un tasto fisico).</li><li>La proprietà <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> (MAIUSC, CTRL o ALT).</li><li>La proprietà <xref:System.Globalization.SortKey.KeyData%2A>, che combina il codice tasto e il modificatore.</li></ul></li></ul>|  
  
## <a name="see-also"></a>Vedere anche  
 [Input da tastiera in un'applicazione Windows Forms](../../../docs/framework/winforms/keyboard-input-in-a-windows-forms-application.md)  
 [Funzionamento dell'input da tastiera](../../../docs/framework/winforms/how-keyboard-input-works.md)  
 [Input del mouse in un'applicazione Windows Forms](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)
