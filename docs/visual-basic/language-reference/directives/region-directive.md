---
title: '#Direttiva Region (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.Region
- vb.#Region
helpviewer_keywords:
- Visual Basic compiler, compiler directives
- '#region directive'
- region directive (#region)
- '#Region keyword [Visual Basic]'
ms.assetid: 90a6a104-3cbf-47d0-bdc4-b585d0921b87
ms.openlocfilehash: d0abbdb9cb96ad9977a9af542f90eaad8a7e160e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56969713"
---
# <a name="region-directive"></a>Direttiva #Region
Comprime e nasconde sezioni di codice in file di Visual Basic.  
  
## <a name="syntax"></a>Sintassi  

```vb
#Region "identifier_string"  
#End Region  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`identifier_string`|Obbligatorio. Stringa che funge da titolo di un'area quando viene compressa. Le aree sono compresse per impostazione predefinita.|  
|`#End Region`|Termina il blocco `#Region`.|  
  
## <a name="remarks"></a>Note  
 Usare la direttiva `#Region` per specificare un blocco di codice da espandere o comprimere durante l'uso della funzionalità di struttura dell'editor di Visual Studio Code. È possibile inserire, oppure *annidare*, aree all'interno di altre aree per raggruppare aree simili.  
  
## <a name="example"></a>Esempio  
 In questo esempio viene usata la direttiva `#Region`.  
  
 [!code-vb[VbVbalrConditionalComp#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#4)]  
  
## <a name="see-also"></a>Vedere anche
- [Direttive #If...Then...#Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [Struttura](/visualstudio/ide/outlining)
- [Procedura: Comprimere e nascondere sezioni di codice](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)
