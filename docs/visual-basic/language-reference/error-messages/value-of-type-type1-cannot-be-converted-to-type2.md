---
title: "Valore di tipo &#39; type1 &#39; non può essere convertito in &#39; type2 &#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31194
- bc31194
helpviewer_keywords:
- BC31194
ms.assetid: 03d50c31-addd-4c90-9c53-725b84f9782e
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: efa6fcd4d996fb3277cc4cac2af16a86a2d65977
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="value-of-type-39type139-cannot-be-converted-to-39type239"></a>Valore di tipo &#39; type1 &#39; non può essere convertito in &#39; type2 &#39;
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
