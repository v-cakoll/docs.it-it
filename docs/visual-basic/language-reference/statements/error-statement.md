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
ms.openlocfilehash: 668ffbc7b8db73a706c5771bb0734a77f8fc0206
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351240"
---
# <a name="error-statement"></a>Istruzione Error
Simula l'occorrenza di un errore.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
Error errornumber  
```  
  
## <a name="parts"></a>Parti  
 `errornumber`  
 Obbligatoria. Può essere qualsiasi numero di errore valido.  
  
## <a name="remarks"></a>Note  
 L'istruzione `Error` è supportata per la compatibilità con le versioni precedenti. Nel nuovo codice, in particolare quando si creano oggetti, utilizzare il metodo `Raise` dell'oggetto `Err` per generare errori di run-time.  
  
 Se `errornumber` è stato definito, l'istruzione `Error` chiama il gestore degli errori dopo che alle proprietà dell'oggetto `Err` vengono assegnati i valori predefiniti seguenti:  
  
|Proprietà|Valore|  
|--------------|-----------|  
|`Number`|Valore specificato come argomento per `Error` istruzione. Può essere qualsiasi numero di errore valido.|  
|`Source`|Nome del progetto Visual Basic corrente.|  
|`Description`|Espressione stringa corrispondente al valore restituito della funzione `Error` per la `Number`specificata, se questa stringa esiste. Se la stringa non esiste, `Description` contiene una stringa di lunghezza zero ("").|  
|`HelpFile`|L'unità, il percorso e il nome file completi del file della Guida Visual Basic appropriato.|  
|`HelpContext`|ID del contesto del file della Guida Visual Basic appropriato per l'errore corrispondente alla proprietà `Number`.|  
|`LastDLLError`|Zero.|  
  
 Se non esiste alcun gestore di errori o se non ne è abilitato alcuno, viene creato e visualizzato un messaggio di errore dalle proprietà dell'oggetto `Err`.  
  
> [!NOTE]
> Alcune applicazioni host Visual Basic non possono creare oggetti. Per determinare se è possibile creare classi e oggetti, vedere la documentazione dell'applicazione host.  
  
## <a name="example"></a>Esempio  
 In questo esempio viene utilizzata l'istruzione `Error` per generare il numero di errore 11.  
  
```vb  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## <a name="requirements"></a>Requisiti  
 **Spazio dei nomi:** [Microsoft. VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Assembly:** Libreria di runtime Visual Basic (in Microsoft. VisualBasic. dll)  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>
- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>
- [Istruzione On Error](../../../visual-basic/language-reference/statements/on-error-statement.md)
- [Istruzione Resume](../../../visual-basic/language-reference/statements/resume-statement.md)
- [Messaggi di errore](../../../visual-basic/language-reference/error-messages/index.md)
