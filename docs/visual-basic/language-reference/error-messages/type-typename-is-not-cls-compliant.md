---
title: Tipo &lt;typename&gt; non è conforme a CLS
ms.date: 07/20/2015
f1_keywords:
- bc40041
- vbc40041
helpviewer_keywords:
- BC40041
ms.assetid: 634132c2-5646-44aa-98c6-f773e2e63882
ms.openlocfilehash: 9911b4fe7b88996f17cb5e9eec7d4a5f2c254b76
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33594608"
---
# <a name="type-lttypenamegt-is-not-cls-compliant"></a>Tipo &lt;typename&gt; non è conforme a CLS
Una funzione, una proprietà o una variabile viene dichiarata con un tipo di dati che non è conforme a CLS.  
  
 Per un'applicazione sia compatibile con il [indipendenza del linguaggio e componenti indipendenti dal linguaggio](../../../standard/language-independence-and-language-independent-components.md) (CLS), è necessario utilizzare solo tipi conformi a CLS.  
  
 I seguenti tipi di dati Visual Basic non sono conformi a CLS:  
  
-   [Tipo di dati SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [Tipo di dati UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [Tipo di dati ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [Tipo di dati UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 **ID errore:** BC40041  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Se l'applicazione deve essere conforme a CLS, modificare il tipo di dati di questo elemento per il tipo conforme a CLS più vicino. Al posto di `UInteger` ad esempio può essere possibile usare `Integer` se non è necessario l'intervallo di valore al di sopra di 2.147.483.647. Se è necessario l'intervallo esteso, è possibile sostituire `UInteger` con `Long`.  
  
-   Se l'applicazione non deve essere conforme a CLS, non è necessario apportare alcuna modifica. È necessario essere consapevoli di conformità, tuttavia.