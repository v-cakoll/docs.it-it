---
title: I valori letterali XML e le proprietà XML all'interno del codice incorporato non sono supportati in ASP.NET.
ms.date: 07/20/2015
f1_keywords:
- vbc31200
- bc31200
helpviewer_keywords:
- BC31200
ms.assetid: 053e8cba-8584-45cc-9fa0-43d122779772
ms.openlocfilehash: 7bec146f0100971d78eed69412ce27889e7a6263
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54597164"
---
# <a name="xml-literals-and-xml-properties-are-not-supported-in-embedded-code-within-aspnet"></a>I valori letterali XML e le proprietà XML all'interno del codice incorporato non sono supportati in ASP.NET.
Valori letterali XML e proprietà XML non sono supportate nel codice incorporato all'interno di ASP.NET. Per usare le funzionalità XML, spostare il codice nel code-behind.  
  
 Un valore letterale XML o una proprietà axis XML è definita all'interno di codice incorporato (`<%= =>`) in un file di ASP.NET.  
  
 **ID errore:** BC31200  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Spostare il codice che include il valore letterale XML o una proprietà axis XML in un file code-behind ASP.NET.  
  
## <a name="see-also"></a>Vedere anche
- [Valori letterali XML](../../../visual-basic/language-reference/xml-literals/index.md)
- [Proprietà Axis XML](../../../visual-basic/language-reference/xml-axis/index.md)
- [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)
