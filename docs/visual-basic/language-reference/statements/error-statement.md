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
ms.openlocfilehash: 7b926214d3be7f5f57783a8599acf1bb1042f956
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944448"
---
# <a name="error-statement"></a>Istruzione Error
Simula l'occorrenza di un errore.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Error errornumber  
```  
  
## <a name="parts"></a>Parti  
 `errornumber`  
 Richiesto. Può essere qualsiasi numero di errore valido.  
  
## <a name="remarks"></a>Note  
 L' `Error` istruzione è supportata per la compatibilità con le versioni precedenti. Nel nuovo codice, in particolare quando si creano oggetti, `Err` utilizzare il `Raise` metodo dell'oggetto per generare errori di run-time.  
  
 Se `errornumber` è definito, l' `Error` istruzione chiama il gestore degli errori `Err` dopo che alle proprietà dell'oggetto sono stati assegnati i valori predefiniti seguenti:  
  
|Proprietà|Value|  
|--------------|-----------|  
|`Number`|Valore specificato come argomento `Error` dell'istruzione. Può essere qualsiasi numero di errore valido.|  
|`Source`|Nome del progetto Visual Basic corrente.|  
|`Description`|Espressione stringa corrispondente al valore restituito della `Error` funzione per l'oggetto specificato `Number`, se questa stringa esiste. Se la stringa non esiste, `Description` contiene una stringa di lunghezza zero ("").|  
|`HelpFile`|L'unità, il percorso e il nome file completi del file della Guida Visual Basic appropriato.|  
|`HelpContext`|ID del contesto del file della Guida Visual Basic appropriato per l'errore corrispondente `Number` alla proprietà.|  
|`LastDLLError`|Zero.|  
  
 Se non esiste alcun gestore di errori o se non ne è abilitato alcuno, viene creato un messaggio di errore `Err` che viene visualizzato dalle proprietà dell'oggetto.  
  
> [!NOTE]
> Alcune applicazioni host Visual Basic non possono creare oggetti. Per determinare se è possibile creare classi e oggetti, vedere la documentazione dell'applicazione host.  
  
## <a name="example"></a>Esempio  
 In questo esempio viene `Error` utilizzata l'istruzione per generare il numero di errore 11.  
  
```  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## <a name="requirements"></a>Requisiti  
 **Spazio dei nomi:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Assembly** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>
- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>
- [Istruzione On Error](../../../visual-basic/language-reference/statements/on-error-statement.md)
- [Istruzione Resume](../../../visual-basic/language-reference/statements/resume-statement.md)
- [Messaggi di errore](../../../visual-basic/language-reference/error-messages/index.md)
