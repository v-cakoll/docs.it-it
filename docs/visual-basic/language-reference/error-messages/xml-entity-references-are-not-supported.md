---
title: Riferimenti a entità XML non supportati
ms.date: 07/20/2015
f1_keywords:
- vbc31180
- bc31180
helpviewer_keywords:
- BC31180
ms.assetid: 2a393327-d8e2-4187-85b1-642b4f53b4ae
ms.openlocfilehash: dd86600f29fbc7c16c74085d63bfb52a4a5f76f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595826"
---
# <a name="xml-entity-references-are-not-supported"></a>Riferimenti a entità XML non supportati
Un riferimento all'entità (ad esempio, `©`) che non è definito nella specifica XML 1.0 è inclusa come un valore per un valore letterale XML specifica. Solo `&`, `"`, `<`, `>`, e `'` riferimenti a entità XML sono supportati nei valori letterali XML.  
  
 **ID errore:** BC31180  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Rimuovere il riferimento all'entità non supportato.  
  
## <a name="see-also"></a>Vedere anche  
 [Valori letterali XML e specifica XML 1.0](../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)  
 [Valori letterali XML](../../../visual-basic/language-reference/xml-literals/index.md)  
 [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)
