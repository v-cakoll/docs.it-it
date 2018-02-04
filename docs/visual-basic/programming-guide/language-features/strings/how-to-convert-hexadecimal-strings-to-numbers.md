---
title: 'Procedura: convertire stringhe esadecimali in numeri (Visual Basic)'
ms.custom: 
ms.date: 01/31/2018
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- numbers [Visual Basic], hexadecimals
- hexadecimals [Visual Basic], decimals
- examples [Visual Basic], string conversion
- decimals [Visual Basic], hexadecimals
- string conversion [Visual Basic], hexadecimal to numbers
ms.assetid: 76675807-eadb-4c08-bd50-e6c6ff4b8ced
author: petrusha
ms.author: ronpet
ms.manager: wpickett
ms.openlocfilehash: c35ac615e3f87710f934a1cf66e6546625298bd0
ms.sourcegitcommit: d2da0142247ef42a219a5d2907f153e62dc6ea0d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2018
---
# <a name="how-to-convert-hexadecimal-strings-to-numbers-visual-basic"></a>Procedura: convertire stringhe esadecimali in numeri (Visual Basic)
In questo esempio converte una stringa esadecimale in un intero usando la <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType> metodo.  
  
## <a name="to-convert-a-hexadecimal-string-to-a-number"></a>Per convertire una stringa esadecimale di un numero  
  
-   Utilizzare il <xref:System.Convert.ToInt32(System.String,System.Int32)> metodo per convertire il numero espresso in base 16 in un numero intero.  
  
     Il primo argomento del <xref:System.Convert.ToInt32(System.String,System.Int32)> metodo è la stringa da convertire. Il secondo argomento descrive la base il numero è espresso nel; esadecimale base 16.  
  
     [!code-vb[HexConversion](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-hexadecimal-strings-to-numbers_1.vb)]  

- Si noti che la stringa esadecimale presenta le restrizioni seguenti:

   - Non può includere il `&h` prefisso.
   - Non può includere il `_` il separatore di cifre.

   Se il prefisso o un separatore di cifre è presente, la chiamata al <xref:System.Convert.ToInt32(System.String,System.Int32)> metodo genera un <xref:System.FormatException>.

## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.Conversion.Hex%2A>  
 <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType>
