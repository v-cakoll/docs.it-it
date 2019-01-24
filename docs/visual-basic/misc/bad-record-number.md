---
title: Numero di record non valido
ms.date: 07/20/2015
f1_keywords:
- vbrID63
ms.assetid: 1fcc33f8-822a-4de9-a6e3-228ddb5824a6
ms.openlocfilehash: fbf1a2db97d0474fb758ff5ed572e94395a187da
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54664753"
---
# <a name="bad-record-number"></a>Numero di record non valido
Il numero di record nell'istruzione `a FileGet`, `FilePut`, `FileGetObject`o `FilePutObject` è minore o uguale a zero.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Controllare i calcoli usati per generare il numero di record. Controllare l'ortografia delle variabili che contengono il numero di record o usati per calcolare i numeri di record. Un nome di variabile contenente errori di ortografia è dichiarato in modo implicito e inizializzato su zero, a meno che non sia stato usato `Option Explicit On` nel modulo.  
  
## <a name="see-also"></a>Vedere anche
- [Istruzione Option Explicit](../../visual-basic/language-reference/statements/option-explicit-statement.md)
