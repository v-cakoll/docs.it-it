---
title: Istruzione Error
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
ms.openlocfilehash: 35ba1f19654d1d23ac1ec73564bc36b0af4f6777
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404745"
---
# <a name="error-statement"></a>Istruzione Error
Simula l'occorrenza di un errore.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
Error errornumber  
```  
  
## <a name="parts"></a>Parti  
 `errornumber`  
 Obbligatorio. Può essere qualsiasi numero di errore valido.  
  
## <a name="remarks"></a>Commenti  
 L' `Error` istruzione è supportata per la compatibilità con le versioni precedenti. Nel nuovo codice, in particolare quando si creano oggetti, utilizzare il `Err` metodo dell'oggetto `Raise` per generare errori di run-time.  
  
 Se `errornumber` è definito, l' `Error` istruzione chiama il gestore degli errori dopo che alle proprietà dell' `Err` oggetto sono stati assegnati i valori predefiniti seguenti:  
  
|Proprietà|valore|  
|--------------|-----------|  
|`Number`|Valore specificato come argomento dell' `Error` istruzione. Può essere qualsiasi numero di errore valido.|  
|`Source`|Nome del progetto Visual Basic corrente.|  
|`Description`|Espressione stringa corrispondente al valore restituito della `Error` funzione per l'oggetto specificato `Number` , se questa stringa esiste. Se la stringa non esiste, `Description` contiene una stringa di lunghezza zero ("").|  
|`HelpFile`|L'unità, il percorso e il nome file completi del file della Guida Visual Basic appropriato.|  
|`HelpContext`|ID del contesto del file della Guida Visual Basic appropriato per l'errore corrispondente alla `Number` Proprietà.|  
|`LastDLLError`|Zero.|  
  
 Se non esiste alcun gestore di errori o se non ne è abilitato alcuno, viene creato un messaggio di errore che viene visualizzato dalle `Err` proprietà dell'oggetto.  
  
> [!NOTE]
> Alcune applicazioni host Visual Basic non possono creare oggetti. Per determinare se è possibile creare classi e oggetti, vedere la documentazione dell'applicazione host.  
  
## <a name="example"></a>Esempio  
 In questo esempio viene utilizzata l' `Error` istruzione per generare il numero di errore 11.  
  
```vb  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## <a name="requirements"></a>Requisiti  
 **Spazio dei nomi:** [Microsoft. VisualBasic](../runtime-library-members.md)  
  
 **Assembly:** Libreria di runtime Visual Basic (in Microsoft. VisualBasic. dll)  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>
- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>
- [Istruzione On Error](on-error-statement.md)
- [Istruzione Resume](resume-statement.md)
- [messaggi di errore](../error-messages/index.md)
