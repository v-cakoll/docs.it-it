---
title: Valore di tipo &#39;type1&#39; non può essere convertito in &#39;type2&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc31194
- bc31194
helpviewer_keywords:
- BC31194
ms.assetid: 03d50c31-addd-4c90-9c53-725b84f9782e
ms.openlocfilehash: 9e59d3bc5e2bfca3628248d08ffc475334d4da79
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="value-of-type-39type139-cannot-be-converted-to-39type239"></a>Valore di tipo &#39;type1&#39; non può essere convertito in &#39;type2&#39;
Valore di tipo 'type1' non può essere convertito in 'type2'. È possibile utilizzare la proprietà 'Value' per ottenere il valore di stringa del primo elemento di '\<ElementoPadre >'.  
  
 Si è provato a eseguire implicitamente il cast di un valore letterale XML a un tipo specifico. Non è possibile eseguire implicitamente il cast del valore letterale XML al tipo specificato.  
  
 **ID errore:** BC31194  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Usare la proprietà `Value` del valore letterale XML per fare riferimento al relativo valore come `String`. Usare la funzione `CType` , un'altra funzione di conversione del tipo oppure la classe <xref:System.Convert> per eseguire il cast del valore come tipo specificato.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Convert>  
 [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Valori letterali XML](../../../visual-basic/language-reference/xml-literals/index.md)  
 [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)
