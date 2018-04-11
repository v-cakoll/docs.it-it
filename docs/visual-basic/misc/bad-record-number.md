---
title: Numero di record non valido
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID63
ms.assetid: 1fcc33f8-822a-4de9-a6e3-228ddb5824a6
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: be04987353498775ec7dcef50b6acc1e6b4ec149
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="bad-record-number"></a>Numero di record non valido
Il numero di record nell'istruzione `a FileGet`, `FilePut`, `FileGetObject`o `FilePutObject` è minore o uguale a zero.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Controllare i calcoli usati per generare il numero di record. Controllare l'ortografia delle variabili che contengono il numero di record o usati per calcolare i numeri di record. Un nome di variabile contenente errori di ortografia è dichiarato in modo implicito e inizializzato su zero, a meno che non sia stato usato `Option Explicit On` nel modulo.  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Option Explicit](../../visual-basic/language-reference/statements/option-explicit-statement.md)
