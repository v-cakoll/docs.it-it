---
title: Istruzione End
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.End
- End
helpviewer_keywords:
- execution [Visual Basic], ending
- files [Visual Basic], closing
- End keyword [Visual Basic], End statements
- programs [Visual Basic], quitting
- code, exiting
- program termination
- End statement [Visual Basic]
- execution [Visual Basic], stopping
ms.assetid: 0e64467c-0f34-4aab-9ddd-43f8b9d55d90
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b692409f2895f5e9b713c57fc35ff2def40bce75
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="end-statement"></a>Istruzione End
Termina immediatamente l'esecuzione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
End  
```  
  
## <a name="remarks"></a>Note  
 È possibile inserire il `End` istruzione in un punto qualsiasi in una procedura per imporre l'intera applicazione a interrompere l'esecuzione. `End`Chiude qualsiasi file aperto con un `Open` istruzione e Cancella tutte le variabili dell'applicazione. La chiusura dell'applicazione, non appena non sono presenti altri programmi che contiene riferimenti a oggetti e nessuna parte del codice è in esecuzione.  
  
> [!NOTE]
>  Il `End` istruzione interruzione dell'esecuzione di codice e non viene richiamato il `Dispose` o `Finalize` metodo, o qualsiasi altro codice di Visual Basic. I riferimenti agli oggetti attivati da altri programmi vengono invalidati. Se un `End` viene rilevata un'istruzione all'interno di un `Try` o `Catch` blocco di controllo, non viene passato al corrispondente `Finally` blocco.  
  
 Il `Stop` istruzione sospende l'esecuzione, ma a differenza `End`, non chiudere qualsiasi file o deselezionare tutte le variabili, a meno che non viene rilevata in un file eseguibile compilato (.exe).  
  
 Poiché `End` termina l'applicazione senza tenere conto di tutte le risorse che possono essere aperte, è consigliabile provare a chiudere correttamente prima di utilizzarlo. Ad esempio, se l'applicazione presenta i form aperti, è necessario chiuderli prima che venga raggiunta la `End` istruzione.  
  
 È consigliabile utilizzare `End` sporadicamente e solo quando è necessario arrestare immediatamente. Le modalità usuali per interrompere una routine ([istruzione Return](../../../visual-basic/language-reference/statements/return-statement.md) e [istruzione Exit](../../../visual-basic/language-reference/statements/exit-statement.md)) non solo la routine, ma offre inoltre il codice chiamante la possibilità di chiudere correttamente l'applicazione. Un'applicazione console, ad esempio, può semplicemente `Return` dal `Main` stored procedure.  
  
> [!IMPORTANT]
>  Il `End` istruzione chiama il <xref:System.Environment.Exit%2A> metodo il <xref:System.Environment> classe il <xref:System> dello spazio dei nomi. <xref:System.Environment.Exit%2A>è necessario disporre `UnmanagedCode` autorizzazione. In caso contrario, un <xref:System.Security.SecurityException> si verifica l'errore.  
  
 Quando è seguito da una parola chiave aggiuntiva, [fine \<parola chiave > istruzione](../../../visual-basic/language-reference/statements/end-keyword-statement.md) delinea la fine della definizione di procedura appropriata o il blocco. Ad esempio, `End Function` termina la definizione di un `Function` stored procedure.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `End` istruzione per terminare l'esecuzione di codice se richiesto dall'utente.  
  
 [!code-vb[VbVersHelp60Controls#64](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/end-statement_1.vb)]  
  
## <a name="smart-device-developer-notes"></a>Note per gli sviluppatori di Smart Device  
 Questa istruzione non è supportata.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Security.Permissions.SecurityPermissionFlag>  
 [Istruzione Stop](../../../visual-basic/language-reference/statements/stop-statement.md)  
 [Fine \<parola chiave > istruzione](../../../visual-basic/language-reference/statements/end-keyword-statement.md)
