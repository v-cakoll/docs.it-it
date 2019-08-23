---
title: Istruzione End (Visual Basic)
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
ms.openlocfilehash: 9307cf10e6125441bd49baa0e663a5a13f234005
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944459"
---
# <a name="end-statement"></a>Istruzione End
Termina immediatamente l'esecuzione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
End  
```  
  
## <a name="remarks"></a>Note  
 È possibile inserire l' `End` istruzione in un punto qualsiasi di una procedura per forzare l'arresto dell'esecuzione dell'intera applicazione. `End`chiude tutti i file aperti con `Open` un'istruzione e cancella tutte le variabili dell'applicazione. L'applicazione viene chiusa non appena non è presente alcun altro programma che contiene riferimenti ai relativi oggetti e nessun codice è in esecuzione.  
  
> [!NOTE]
> L' `End` istruzione arresta l'esecuzione del codice improvvisamente e non richiama il `Dispose` metodo o `Finalize` o qualsiasi altro codice Visual Basic. I riferimenti agli oggetti contenuti in altri programmi vengono invalidati. Se viene `End` rilevata un'istruzione `Try` all' `Catch` interno di un blocco o, il controllo non `Finally` passa al blocco corrispondente.  
  
 L' `Stop` istruzione sospende l'esecuzione, ma, a `End`differenza di, non chiude alcun file né cancella alcuna variabile, a meno che non venga rilevata in un file eseguibile compilato (exe).  
  
 Poiché `End` termina l'applicazione senza dover partecipare a risorse che potrebbero essere aperte, provare a chiuderla prima di usarla. Se ad esempio nell'applicazione sono presenti moduli aperti, è necessario chiuderli prima che il controllo raggiunga l' `End` istruzione.  
  
 Si consiglia di `End` usare con parsimonia e solo quando è necessario arrestare immediatamente. I modi normali per terminare una procedura (istruzione[return](../../../visual-basic/language-reference/statements/return-statement.md) e [istruzione Exit](../../../visual-basic/language-reference/statements/exit-statement.md)) non solo chiudono la stored procedure, ma forniscono anche al codice chiamante la possibilità di chiudere in modo corretto. Un'applicazione console, ad esempio, può semplicemente `Return` `Main` dalla procedura.  
  
> [!IMPORTANT]
> L' `End` istruzione chiama il <xref:System.Environment.Exit%2A> <xref:System.Environment> metodo<xref:System> della classe nello spazio dei nomi. <xref:System.Environment.Exit%2A>richiede l' `UnmanagedCode` autorizzazione. In caso contrario, si verificherà un <xref:System.Security.SecurityException> errore.  
  
 Quando seguito da una parola chiave aggiuntiva, la [parola chiave End \<> istruzione](../../../visual-basic/language-reference/statements/end-keyword-statement.md) delimita la fine della definizione della procedura o del blocco appropriato. Ad esempio, `End Function` termina la definizione di una `Function` stored procedure.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzata `End` l'istruzione per terminare l'esecuzione del codice se richiesto dall'utente.  
  
 [!code-vb[VbVersHelp60Controls#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVersHelp60Controls/VB/Form1.vb#64)]  
  
## <a name="smart-device-developer-notes"></a>Note per gli sviluppatori di Smart Device  
 Questa istruzione non è supportata.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Security.Permissions.SecurityPermissionFlag>
- [Istruzione Stop](../../../visual-basic/language-reference/statements/stop-statement.md)
- [Istruzione \<end > parola chiave](../../../visual-basic/language-reference/statements/end-keyword-statement.md)
