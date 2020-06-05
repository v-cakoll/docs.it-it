---
title: Istruzione End
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
ms.openlocfilehash: fe17a82662c4014069c77f2da76723a051ab9084
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404706"
---
# <a name="end-statement"></a>Istruzione End
Termina immediatamente l'esecuzione.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
End  
```  
  
## <a name="remarks"></a>Osservazioni  
 È possibile inserire l' `End` istruzione in un punto qualsiasi di una procedura per forzare l'arresto dell'esecuzione dell'intera applicazione. `End`chiude tutti i file aperti con un' `Open` istruzione e cancella tutte le variabili dell'applicazione. L'applicazione viene chiusa non appena non è presente alcun altro programma che contiene riferimenti ai relativi oggetti e nessun codice è in esecuzione.  
  
> [!NOTE]
> L' `End` istruzione arresta l'esecuzione del codice improvvisamente e non richiama il `Dispose` metodo o o `Finalize` qualsiasi altro codice Visual Basic. I riferimenti agli oggetti contenuti in altri programmi vengono invalidati. Se `End` viene rilevata un'istruzione all'interno di un `Try` `Catch` blocco o, il controllo non passa al `Finally` blocco corrispondente.  
  
 L' `Stop` istruzione sospende l'esecuzione, ma, a differenza di `End` , non chiude alcun file né cancella alcuna variabile, a meno che non venga rilevata in un file eseguibile compilato (exe).  
  
 Poiché `End` termina l'applicazione senza dover partecipare a risorse che potrebbero essere aperte, provare a chiuderla prima di usarla. Se ad esempio nell'applicazione sono presenti moduli aperti, è necessario chiuderli prima che il controllo raggiunga l' `End` istruzione.  
  
 Si consiglia `End` di usare con parsimonia e solo quando è necessario arrestare immediatamente. I modi normali per terminare una procedura (istruzione[return](return-statement.md) e [istruzione Exit](exit-statement.md)) non solo chiudono la stored procedure, ma forniscono anche al codice chiamante la possibilità di chiudere in modo corretto. Un'applicazione console, ad esempio, può semplicemente `Return` dalla `Main` procedura.  
  
> [!IMPORTANT]
> L' `End` istruzione chiama il <xref:System.Environment.Exit%2A> metodo della <xref:System.Environment> classe nello <xref:System> spazio dei nomi. <xref:System.Environment.Exit%2A>richiede l' `UnmanagedCode` autorizzazione. In caso contrario, <xref:System.Security.SecurityException> si verificherà un errore.  
  
 Quando seguito da una parola chiave aggiuntiva, l' [ \<keyword> istruzione End](end-keyword-statement.md) delimita la fine della definizione della procedura o del blocco appropriato. Ad esempio, `End Function` termina la definizione di una `Function` stored procedure.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzata l' `End` istruzione per terminare l'esecuzione del codice se richiesto dall'utente.  
  
 [!code-vb[VbVersHelp60Controls#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVersHelp60Controls/VB/Form1.vb#64)]  
  
## <a name="smart-device-developer-notes"></a>Note per gli sviluppatori di Smart Device  
 Questa istruzione non è supportata.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Security.Permissions.SecurityPermissionFlag>
- [Istruzione Stop](stop-statement.md)
- [\<keyword>Istruzione End](end-keyword-statement.md)
