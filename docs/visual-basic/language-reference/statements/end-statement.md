---
title: Istruzione end (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 8b189449044a48432a6cf05b75f39581be111495
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56979534"
---
# <a name="end-statement"></a>Istruzione End
Termina l'esecuzione immediatamente.  
  
## <a name="syntax"></a>Sintassi  
  
```  
End  
```  
  
## <a name="remarks"></a>Note  
 È possibile inserire il `End` istruzione in un punto qualsiasi in una procedura per forzare l'intera applicazione per arrestare l'esecuzione. `End` Chiude tutti i file aperti con un `Open` istruzione e Cancella tutte le variabili dell'applicazione. L'applicazione viene chiusa non appena non sono presenti altri programmi che contiene riferimenti a oggetti e non del relativo codice è in esecuzione.  
  
> [!NOTE]
>  Il `End` istruzione interrompe l'esecuzione di codice in modo anomalo e non richiama i `Dispose` o `Finalize` metodo o qualsiasi altro codice di Visual Basic. Riferimenti a oggetti attivati da altri programmi vengono invalidati. Se un' `End` viene rilevata l'istruzione all'interno di un `Try` oppure `Catch` blocco di controllo non viene passato al corrispondente `Finally` blocco.  
  
 Il `Stop` istruzione sospende l'esecuzione, ma a differenza `End`, non chiudere qualsiasi file o cancellare le variabili di qualsiasi tipo, a meno che non si è verificato in un file eseguibile compilato (.exe).  
  
 Poiché `End` termina l'applicazione senza tenere conto di tutte le risorse che potrebbero essere aperte, è consigliabile provare a chiudere correttamente l'applicazione prima di poterla usare. Ad esempio, se l'applicazione presenta i form aperti, è necessario chiuderli prima che venga raggiunta la `End` istruzione.  
  
 È consigliabile usare `End` sporadicamente e solo quando è necessario arrestare immediatamente. Le modalità usuali per interrompere una routine ([istruzione Return](../../../visual-basic/language-reference/statements/return-statement.md) e [Esci da istruzione](../../../visual-basic/language-reference/statements/exit-statement.md)) non solo la routine, ma anche offrire l'opportunità di chiudere correttamente il codice chiamante. Un'applicazione console, ad esempio, può semplicemente `Return` dal `Main` procedure.  
  
> [!IMPORTANT]
>  Il `End` istruzione chiama il <xref:System.Environment.Exit%2A> metodo il <xref:System.Environment> classe il <xref:System> dello spazio dei nomi. <xref:System.Environment.Exit%2A> è necessario disporre `UnmanagedCode` l'autorizzazione. In caso contrario, un <xref:System.Security.SecurityException> errore si verifica.  
  
 Quando è seguito da una parola chiave aggiuntiva, [finali \<parola chiave > istruzione](../../../visual-basic/language-reference/statements/end-keyword-statement.md) delinea la fine della definizione di procedura appropriata o il blocco. Ad esempio, `End Function` termina la definizione di un `Function` procedure.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `End` istruzione per terminare l'esecuzione di codice se l'utente lo richiede.  
  
 [!code-vb[VbVersHelp60Controls#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVersHelp60Controls/VB/Form1.vb#64)]  
  
## <a name="smart-device-developer-notes"></a>Note per gli sviluppatori di Smart Device  
 Questa istruzione non è supportata.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Security.Permissions.SecurityPermissionFlag>
- [Istruzione Stop](../../../visual-basic/language-reference/statements/stop-statement.md)
- [Fine \<parola chiave > istruzione](../../../visual-basic/language-reference/statements/end-keyword-statement.md)
