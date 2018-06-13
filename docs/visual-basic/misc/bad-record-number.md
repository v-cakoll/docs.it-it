---
title: Numero di record non valido
ms.date: 07/20/2015
f1_keywords:
- vbrID63
ms.assetid: 1fcc33f8-822a-4de9-a6e3-228ddb5824a6
ms.openlocfilehash: 400879ba37c6b3215d9570ca6eb8eaa06edea03b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33600805"
---
# <a name="bad-record-number"></a>Numero di record non valido
Il numero di record nell'istruzione `a FileGet`, `FilePut`, `FileGetObject`o `FilePutObject` è minore o uguale a zero.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Controllare i calcoli usati per generare il numero di record. Controllare l'ortografia delle variabili che contengono il numero di record o usati per calcolare i numeri di record. Un nome di variabile contenente errori di ortografia è dichiarato in modo implicito e inizializzato su zero, a meno che non sia stato usato `Option Explicit On` nel modulo.  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Option Explicit](../../visual-basic/language-reference/statements/option-explicit-statement.md)
