---
title: Numero di record non valido
ms.date: 07/20/2015
f1_keywords:
- vbrID63
ms.assetid: 1fcc33f8-822a-4de9-a6e3-228ddb5824a6
ms.openlocfilehash: abd0a1467c0991a40b93e74a1d7a7889367fb8ca
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59340802"
---
# <a name="bad-record-number"></a>Numero di record non valido
Il numero di record nell'istruzione `a FileGet`, `FilePut`, `FileGetObject`o `FilePutObject` è minore o uguale a zero.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Controllare i calcoli usati per generare il numero di record. Controllare l'ortografia delle variabili che contengono il numero di record o usati per calcolare i numeri di record. Un nome di variabile contenente errori di ortografia è dichiarato in modo implicito e inizializzato su zero, a meno che non sia stato usato `Option Explicit On` nel modulo.  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Option Explicit](../../visual-basic/language-reference/statements/option-explicit-statement.md)
