---
title: L'inferenza di tipi nullable non è supportata in questo contesto
ms.date: 07/20/2015
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
ms.openlocfilehash: 42bde0b1843e52bbc16118bb056ade791591904e
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249500"
---
# <a name="nullable-type-inference-is-not-supported-in-this-context"></a>L'inferenza di tipi nullable non è supportata in questo contesto
I tipi di valore e le strutture possono essere dichiarati nullable.  
  
```vb  
Dim a? As Integer  
Dim b As Integer?  
```  
  
 Tuttavia, non è possibile utilizzare la dichiarazione nullable in combinazione con l'inferenza del tipo. Gli esempi seguenti causano questo errore.  
  
```vb  
' Not valid.  
' Dim c? = 10  
' Dim d? = a  
```  
  
 **ID errore:** BC36629 (informazioni in inglese)  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Utilizzare `As` una clausola per dichiarare la variabile come tipo di valore nullable.  
  
## <a name="see-also"></a>Vedere anche

- [Tipi di valore nullableNullable Value Types](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [Inferenza del tipo di variabile locale](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
