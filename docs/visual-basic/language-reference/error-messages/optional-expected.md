---
title: Previsto 'Optional'
ms.date: 07/20/2015
f1_keywords:
- bc30202
- vbc30202
helpviewer_keywords:
- BC30202
ms.assetid: 6f75060c-2db4-4a79-b5d1-5780c09a74cd
ms.openlocfilehash: 411e3248409ab0184666f4efefb4ec4becf7cab1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409348"
---
# <a name="optional-expected"></a>Previsto 'Optional'
Un argomento facoltativo in una dichiarazione di routine è seguito da un argomento obbligatorio. Ogni argomento che segue un argomento facoltativo deve anche essere facoltativo.  
  
 **ID errore:** BC30202  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Se l'argomento deve essere necessario, spostarlo in modo che preceda il primo argomento facoltativo nell'elenco di argomenti.  
  
2. Se l'argomento è destinato a essere facoltativo, usare la `Optional` parola chiave.  
  
## <a name="see-also"></a>Vedere anche

- [Parametri facoltativi](../../programming-guide/language-features/procedures/optional-parameters.md)
