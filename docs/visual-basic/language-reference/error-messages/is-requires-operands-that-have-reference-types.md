---
title: Gli operandi di 'Is' devono avere tipi di riferimento, ma questo operando ha un tipo di valore '<typename>'
ms.date: 07/20/2015
f1_keywords:
- bc30020
- vbc30020
helpviewer_keywords:
- BC30020
ms.assetid: 228afebd-1203-4bd3-8d7a-c5c56f3cedc4
ms.openlocfilehash: e5acc94a3738fca3a43740bdba727fc843132aa1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402811"
---
# <a name="is-requires-operands-that-have-reference-types-but-this-operand-has-the-value-type-typename"></a>Gli operandi di 'Is' devono avere tipi di riferimento, ma questo operando ha un tipo di valore '\<typename>'
L' `Is` operatore di confronto determina se due variabili oggetto fanno riferimento alla stessa istanza. Questo confronto non è definito per i tipi di valore.  
  
 **ID errore:** BC30020  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Utilizzare l'operatore di confronto aritmetico appropriato o l' `Like` operatore per confrontare due tipi di valore.  
  
## <a name="see-also"></a>Vedere anche

- [Operatore Is](../operators/is-operator.md)
- [Operatore Like](../operators/like-operator.md)
- [Operatori di confronto](../operators/comparison-operators.md)
