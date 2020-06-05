---
title: Impossibile convertire il valore di tipo 'type1' in 'type2'
ms.date: 07/20/2015
f1_keywords:
- vbc31194
- bc31194
helpviewer_keywords:
- BC31194
ms.assetid: 03d50c31-addd-4c90-9c53-725b84f9782e
ms.openlocfilehash: f19f157bd4c76f481aa3232bc33c2a0c6ac21367
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400279"
---
# <a name="value-of-type-type1-cannot-be-converted-to-type2"></a>Impossibile convertire il valore di tipo 'type1' in 'type2'
Non è possibile convertire il valore di tipo ' tipo1' in ' tipo2'. È possibile usare la proprietà' value ' per ottenere il valore stringa del primo elemento di ' \<parentElement> '.  
  
 Si è provato a eseguire implicitamente il cast di un valore letterale XML a un tipo specifico. Non è possibile eseguire implicitamente il cast del valore letterale XML al tipo specificato.  
  
 **ID errore:** BC31194  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Usare la proprietà `Value` del valore letterale XML per fare riferimento al relativo valore come `String`. Usare la funzione `CType` , un'altra funzione di conversione del tipo oppure la classe <xref:System.Convert> per eseguire il cast del valore come tipo specificato.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Convert>
- [CString](../functions/type-conversion-functions.md)
- [Valori letterali XML](../xml-literals/index.md)
- [XML](../../programming-guide/language-features/xml/index.md)
