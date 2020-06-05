---
title: I valori letterali XML e le proprietà XML all'interno del codice incorporato non sono supportati in ASP.NET.
ms.date: 07/20/2015
f1_keywords:
- vbc31200
- bc31200
helpviewer_keywords:
- BC31200
ms.assetid: 053e8cba-8584-45cc-9fa0-43d122779772
ms.openlocfilehash: bda92b4244631f66142499a94be562854b35437e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406469"
---
# <a name="xml-literals-and-xml-properties-are-not-supported-in-embedded-code-within-aspnet"></a>I valori letterali XML e le proprietà XML all'interno del codice incorporato non sono supportati in ASP.NET.
I valori letterali XML e le proprietà XML non sono supportati nel codice incorporato all'interno di ASP.NET. Per utilizzare le funzionalità XML, spostare il codice nel code-behind.  
  
 Un valore letterale XML o una proprietà Axis XML viene definito all'interno del codice incorporato ( `<%= =>` ) in un file ASP.NET.  
  
 **ID errore:** BC31200  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Spostare il codice che include il valore letterale XML o la proprietà Axis XML in un file code-behind ASP.NET.  
  
## <a name="see-also"></a>Vedere anche

- [Valori letterali XML](../xml-literals/index.md)
- [Proprietà Axis XML](../xml-axis/index.md)
- [XML](../../programming-guide/language-features/xml/index.md)
