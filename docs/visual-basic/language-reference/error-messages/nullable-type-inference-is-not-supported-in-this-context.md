---
title: L'inferenza di tipi nullable non è supportata in questo contesto
ms.date: 07/20/2015
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
ms.openlocfilehash: 52e5391fbcf30a4dada4d64a0e810c900ea85806
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409387"
---
# <a name="nullable-type-inference-is-not-supported-in-this-context"></a>L'inferenza di tipi nullable non è supportata in questo contesto
I tipi di valore e le strutture possono essere dichiarati nullable.  
  
```vb  
Dim a? As Integer  
Dim b As Integer?  
```  
  
 Tuttavia, non è possibile usare la dichiarazione nullable in combinazione con l'inferenza del tipo. Nell'esempio seguente viene generato questo errore.  
  
```vb  
' Not valid.  
' Dim c? = 10  
' Dim d? = a  
```  
  
 **ID errore:** BC36629  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Usare una `As` clausola per dichiarare la variabile come tipo di valore Nullable.  
  
## <a name="see-also"></a>Vedere anche

- [Tipi di valore Nullable](../../programming-guide/language-features/data-types/nullable-value-types.md)
- [Inferenza del tipo di variabile locale](../../programming-guide/language-features/variables/local-type-inference.md)
