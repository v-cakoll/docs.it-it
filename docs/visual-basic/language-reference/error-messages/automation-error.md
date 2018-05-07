---
title: Errore di automazione
ms.date: 07/20/2015
f1_keywords:
- vbrID440
ms.assetid: 2c4be5c5-2f0d-4a2b-96fe-d1b24f08fc4c
ms.openlocfilehash: fdd77510d03cd9e5228be1ba9ec9f746dcc0dfe4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="automation-error"></a>Errore di automazione
Si è verificato un errore durante l'esecuzione di un metodo o durante il recupero o l'impostazione di una proprietà di una variabile oggetto. L'errore è stato segnalato dall'applicazione che ha creato l'oggetto.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Verificare le proprietà dell'oggetto `Err` per determinare l'origine e la natura dell'errore.  
  
2.  Usare l'istruzione `On Error Resume Next` immediatamente prima dell'istruzione di accesso e quindi controllare subito la presenza di errori dopo l'istruzione di accesso.  
  
## <a name="see-also"></a>Vedere anche  
 [Tipi di errore](../../../visual-basic/programming-guide/language-features/error-types.md)  
 [Talk to Us](/visualstudio/ide/talk-to-us) (Comunicazioni con Microsoft)
