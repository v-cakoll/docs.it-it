---
title: Errore di automazione
ms.date: 07/20/2015
f1_keywords:
- vbrID440
ms.assetid: 2c4be5c5-2f0d-4a2b-96fe-d1b24f08fc4c
ms.openlocfilehash: d62ba57db8bffefb2cfebed705251d87fe285602
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409894"
---
# <a name="automation-error"></a>Errore di automazione

Si è verificato un errore durante l'esecuzione di un metodo o durante il recupero o l'impostazione di una proprietà di una variabile oggetto. L'errore è stato segnalato dall'applicazione che ha creato l'oggetto.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Verificare le proprietà dell'oggetto `Err` per determinare l'origine e la natura dell'errore.  
  
2. Usare l'istruzione `On Error Resume Next` immediatamente prima dell'istruzione di accesso e quindi controllare subito la presenza di errori dopo l'istruzione di accesso.  
  
## <a name="see-also"></a>Vedere anche

- [Tipi di errore](../../programming-guide/language-features/error-types.md)
- [Comunica con Microsoft](/visualstudio/ide/feedback-options)
