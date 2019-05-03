---
title: Impossibile convertire il valore di tipo 'type1' in 'type2'
ms.date: 07/20/2015
f1_keywords:
- vbc31194
- bc31194
helpviewer_keywords:
- BC31194
ms.assetid: 03d50c31-addd-4c90-9c53-725b84f9782e
ms.openlocfilehash: c8480c6fab2bff931950ebc21d0a8affe3c41c66
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774816"
---
# <a name="value-of-type-type1-cannot-be-converted-to-type2"></a>Impossibile convertire il valore di tipo 'type1' in 'type2'
Valore di tipo 'type1' non può essere convertito in 'type2'. È possibile usare la proprietà 'Value' per ottenere il valore di stringa del primo elemento di '\<ElementoPadre >'.  
  
 Si è provato a eseguire implicitamente il cast di un valore letterale XML a un tipo specifico. Non è possibile eseguire implicitamente il cast del valore letterale XML al tipo specificato.  
  
 **ID errore:** BC31194  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Usare la proprietà `Value` del valore letterale XML per fare riferimento al relativo valore come `String`. Usare la funzione `CType` , un'altra funzione di conversione del tipo oppure la classe <xref:System.Convert> per eseguire il cast del valore come tipo specificato.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Convert>
- [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Valori letterali XML](../../../visual-basic/language-reference/xml-literals/index.md)
- [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)
