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
ms.openlocfilehash: 66dba1df125a08b8ae05519a0c66edb6da15ceaa
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583421"
---
# <a name="end-statement"></a>Istruzione End
Termina immediatamente l'esecuzione.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
End  
```  
  
## <a name="remarks"></a>Note  
 È possibile inserire l'istruzione `End` in un punto qualsiasi di una procedura per forzare l'arresto dell'esecuzione dell'intera applicazione. `End` chiude tutti i file aperti con un'istruzione `Open` e cancella tutte le variabili dell'applicazione. L'applicazione viene chiusa non appena non è presente alcun altro programma che contiene riferimenti ai relativi oggetti e nessun codice è in esecuzione.  
  
> [!NOTE]
> L'istruzione `End` interrompe l'esecuzione del codice improvvisamente e non richiama il metodo `Dispose` o `Finalize` o qualsiasi altro codice Visual Basic. I riferimenti agli oggetti contenuti in altri programmi vengono invalidati. Se viene rilevata un'istruzione `End` all'interno di un blocco `Try` o `Catch`, il controllo non passa al blocco `Finally` corrispondente.  
  
 L'istruzione `Stop` sospende l'esecuzione, ma a differenza di `End` non chiude alcun file né cancella alcuna variabile, a meno che non venga rilevata in un file eseguibile compilato (exe).  
  
 Poiché `End` termina l'applicazione senza dover partecipare a risorse che potrebbero essere aperte, provare a chiuderla prima di usarla. Se ad esempio nell'applicazione sono presenti moduli aperti, è necessario chiuderli prima che il controllo raggiunga l'istruzione `End`.  
  
 È consigliabile utilizzare `End` sporadicamente e solo quando è necessario arrestare immediatamente. I modi normali per terminare una procedura (istruzione[return](../../../visual-basic/language-reference/statements/return-statement.md) e [istruzione Exit](../../../visual-basic/language-reference/statements/exit-statement.md)) non solo chiudono la stored procedure, ma forniscono anche al codice chiamante la possibilità di chiudere in modo corretto. Un'applicazione console, ad esempio, può semplicemente `Return` dalla procedura `Main`.  
  
> [!IMPORTANT]
> L'istruzione `End` chiama il metodo <xref:System.Environment.Exit%2A> della classe <xref:System.Environment> nello spazio dei nomi <xref:System>. per <xref:System.Environment.Exit%2A> è necessario disporre di `UnmanagedCode` autorizzazione. In caso contrario, si verifica un errore di <xref:System.Security.SecurityException>.  
  
 Quando seguito da una parola chiave aggiuntiva, [end \<keyword > istruzione](../../../visual-basic/language-reference/statements/end-keyword-statement.md) delimita la fine della definizione della procedura o del blocco appropriato. Ad esempio, `End Function` termina la definizione di una routine di `Function`.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzata l'istruzione `End` per terminare l'esecuzione del codice se richiesto dall'utente.  
  
 [!code-vb[VbVersHelp60Controls#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVersHelp60Controls/VB/Form1.vb#64)]  
  
## <a name="smart-device-developer-notes"></a>Note per gli sviluppatori di Smart Device  
 Questa istruzione non è supportata.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Security.Permissions.SecurityPermissionFlag>
- [Istruzione Stop](../../../visual-basic/language-reference/statements/stop-statement.md)
- [Istruzione End \<keyword >](../../../visual-basic/language-reference/statements/end-keyword-statement.md)
