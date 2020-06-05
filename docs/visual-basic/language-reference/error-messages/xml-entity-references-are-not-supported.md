---
title: Riferimenti a entità XML non supportati
ms.date: 07/20/2015
f1_keywords:
- vbc31180
- bc31180
helpviewer_keywords:
- BC31180
ms.assetid: 2a393327-d8e2-4187-85b1-642b4f53b4ae
ms.openlocfilehash: ae997d853a93999a3b29215ea1257da7a1d48c84
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406456"
---
# <a name="xml-entity-references-are-not-supported"></a>Riferimenti a entità XML non supportati
Un riferimento all'entità, ad esempio, `©` che non è definito nella specifica xml 1,0 è incluso come valore per un valore letterale XML. `&` `"` `<` `>` `'` Nei valori letterali XML sono supportati solo i riferimenti a entità,,, e XML.  
  
 **ID errore:** BC31180  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Rimuovere il riferimento all'entità non supportato.  
  
## <a name="see-also"></a>Vedere anche

- [Valori letterali XML e specifica XML 1.0](../../programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)
- [Valori letterali XML](../xml-literals/index.md)
- [XML](../../programming-guide/language-features/xml/index.md)
