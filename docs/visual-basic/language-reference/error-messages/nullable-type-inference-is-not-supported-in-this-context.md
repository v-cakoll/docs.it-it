---
title: L'inferenza di tipi nullable non è supportata in questo contesto
ms.date: 07/20/2015
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
ms.openlocfilehash: 9f7f878649d8b96f050b56d5b878eb3d67e027ff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61918222"
---
# <a name="nullable-type-inference-is-not-supported-in-this-context"></a>L'inferenza di tipi nullable non è supportata in questo contesto
Strutture e tipi di valore possono essere dichiarate nullable.  
  
```vb  
Dim a? As Integer  
Dim b As Integer?  
```  
  
 Tuttavia, è possibile usare la dichiarazione che ammette valori null in combinazione con l'inferenza del tipo. Gli esempi seguenti causano questo errore.  
  
```vb  
' Not valid.  
' Dim c? = 10  
' Dim d? = a  
```  
  
 **ID errore:** BC36629  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Usare un `As` clausola per dichiarare la variabile come nullable.  
  
## <a name="see-also"></a>Vedere anche

- [Tipi di valori nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [Inferenza del tipo di variabile locale](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
