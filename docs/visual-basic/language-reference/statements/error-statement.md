---
title: Istruzione Error (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.error
helpviewer_keywords:
- Error statement [Visual Basic], syntax
- Error statement [Visual Basic]
- Error keyword [Visual Basic]
- run-time errors [Visual Basic], codes
- errors [Visual Basic], simulating
ms.assetid: 85cd5c59-5224-4f02-aaf5-fcfefab17a29
ms.openlocfilehash: 84fce92183228cbfa5554a3ba45770a86e83bff5
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "47232937"
---
# <a name="error-statement"></a>Istruzione Error
Simula il verificarsi di un errore.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Error errornumber  
```  
  
## <a name="parts"></a>Parti  
 `errornumber`  
 Obbligatorio. Può essere qualsiasi numero errore valido.  
  
## <a name="remarks"></a>Note  
 Il `Error` istruzione è supportata per compatibilità con le versioni precedenti. Nel nuovo codice, soprattutto quando si creano oggetti, usare il `Err` dell'oggetto `Raise` metodo per generare errori di run-time.  
  
 Se `errornumber` è definito, il `Error` istruzione chiama il gestore degli errori dopo le proprietà del `Err` oggetto vengono assegnati i valori predefiniti seguenti:  
  
|Proprietà|Valore|  
|--------------|-----------|  
|`Number`|Valore specificato come argomento per `Error` istruzione. Può essere qualsiasi numero errore valido.|  
|`Source`|Nome del progetto Visual Basic corrente.|  
|`Description`|Espressione corrispondente al valore restituito della stringa di `Error` funzione per l'oggetto specificato `Number`, se questa stringa è presente. Se la stringa non esiste, `Description` contiene una stringa di lunghezza zero ("").|  
|`HelpFile`|Il completo dell'unità, percorso e nome file del file della Guida di Visual Basic appropriato.|  
|`HelpContext`|La Guida di Visual Basic di ID di contesto relativo all'errore corrispondente al file il `Number` proprietà.|  
|`LastDLLError`|Zero.|  
  
 Se nessun gestore di errori non esiste o non è attivato, un messaggio di errore verrà creato e visualizzato dal `Err` le proprietà dell'oggetto.  
  
> [!NOTE]
>  Alcune applicazioni di host di Visual Basic non è possibile creare oggetti. Vedere la documentazione dell'applicazione host per determinare se può creare classi e oggetti.  
  
## <a name="example"></a>Esempio  
 Questo esempio viene usato il `Error` istruzione per generare il numero di errore 11.  
  
```  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## <a name="requirements"></a>Requisiti  
 **Namespace:** [Microsoft. VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Assembly:** libreria di Runtime di Visual Basic (in VisualBasic)  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>  
 <xref:Microsoft.VisualBasic.Information.Err%2A>  
 <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>  
 [Istruzione On Error](../../../visual-basic/language-reference/statements/on-error-statement.md)  
 [Istruzione Resume](../../../visual-basic/language-reference/statements/resume-statement.md)  
 [Messaggi di errore](../../../visual-basic/language-reference/error-messages/index.md)
