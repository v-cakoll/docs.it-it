---
title: Caratteristiche di elementi dichiarati
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic], lifetime
- access levels, declared elements
- declared elements [Visual Basic], scope
- visibility [Visual Basic], declared elements
- elements [Visual Basic], programming
- scope [Visual Basic], declared elements
- lifetime [Visual Basic], declared elements
- declared elements [Visual Basic], access level
- data types [Visual Basic], declared elements
- declared elements [Visual Basic], visibility
ms.assetid: 1bc40fb8-b67c-4428-90a4-76b630ae2583
ms.openlocfilehash: 4e03cd28fed5e0ae109337739251c11a0ff3424a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74331632"
---
# <a name="declared-element-characteristics-visual-basic"></a>Caratteristiche di elementi dichiarati (Visual Basic)
A *characteristic* of a declared element is an aspect of that element that affects how code can interact with it. Every declared element has one or more of the following characteristics associated with it:  
  
- *Data type* — the values the element can hold, and how it stores those values. Per altre informazioni, vedere [Tipi di dati](../../../../visual-basic/language-reference/data-types/index.md).  
  
- *Lifetime* — the period of execution time during which the element is available for use. For more information, see [Lifetime in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).  
  
- *Scope* — the set of all code that can refer to the element without qualifying its name. For more information, see [How to: Control the Scope of a Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md).  
  
- *Access level* — the permission for code to make use of the element. For more information, see [How to: Control the Availability of a Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-availability-of-a-variable.md).  
  
## <a name="characteristics-of-the-elements"></a>Characteristics of the Elements  
 The following table shows the declared elements and the characteristics that apply to each one.  
  
|Elemento|Tipo di dati|Durata|Scope <sup>1</sup>|Access Level|  
|-------------|---------------|--------------|------------------------|------------------|  
|Variabile|Yes|Yes|Yes|Yes|  
|Costante|Yes|No|Yes|Yes|  
|Enumerazione|Yes|No|Yes|Yes|  
|Struttura|No|No|Yes|Yes|  
|proprietà|Yes|Yes|Yes|Yes|  
|Metodo|No|Yes|Yes|Yes|  
|Procedure (`Sub` or `Function`)|No|Yes|Yes|Yes|  
|Parametro di routine|Yes|Yes|Yes|No|  
|Function return|Yes|Yes|Yes|No|  
|??|Yes|No|Yes|Yes|  
|Interfaccia|No|No|Yes|Yes|  
|Class|No|No|Yes|Yes|  
|event|No|No|Yes|Yes|  
|delegato|No|No|Yes|Yes|  
  
 <sup>1</sup> Scope is sometimes referred to as *visibility*.  
  
## <a name="see-also"></a>Vedere anche

- [Elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md)
- [Nomi di elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [Riferimenti a elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Lifetime in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [Access levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Dichiarazione di variabile](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
