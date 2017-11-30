---
title: "Procedura: inserire più valori in una variabile (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- classes [Visual Basic], composite data types
- composite types [Visual Basic]
- composite data types [Visual Basic]
- data types [Visual Basic], composite
- arrays [Visual Basic], composite data types
- structures [Visual Basic], composite data types
- arrays [Visual Basic], compilation errors
- types [Visual Basic], composite
ms.assetid: 5fe0e558-aac2-4a40-b7f2-7cfea7336917
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c8c567ec2ba01d094819c98a2937af75cd105956
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-hold-more-than-one-value-in-a-variable-visual-basic"></a>Procedura: inserire più valori in una variabile (Visual Basic)
Una variabile contiene più di un valore se si dichiara come un *tipo di dati composito*.  
  
 [Tipi di dati compositi](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) includono classi, matrici e strutture. Una variabile di un tipo di dati composito può contenere una combinazione di tipi di dati elementari e altri tipi compositi. Classi e le strutture possono contenere codice, nonché i dati.  
  
### <a name="to-hold-more-than-one-value-in-a-variable"></a>Per contenere più di un valore in una variabile  
  
1.  Determinare il tipo di dati composito che si desidera utilizzare per la variabile.  
  
2.  Se il tipo di dati composito non è già stato definito, è possibile definirlo in modo che la variabile è possibile utilizzarlo.  
  
    -   Definire una struttura con un [istruzione Structure](../../../../visual-basic/language-reference/statements/structure-statement.md).  
  
    -   Definire una matrice con un [Dim (istruzione)](../../../../visual-basic/language-reference/statements/dim-statement.md).  
  
    -   Definire una classe con un [istruzione Class](../../../../visual-basic/language-reference/statements/class-statement.md).  
  
3.  Dichiarare la variabile con un `Dim` istruzione.  
  
4.  Dopo il nome della variabile con un `As` clausola.  
  
5.  Seguire il `As` (parola chiave) con il nome del tipo di dati composito appropriato.  
  
## <a name="see-also"></a>Vedere anche  
 [Tipi di dati](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Caratteri tipo](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)  
 [Tipi di dati compositi](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)  
 [Strutture](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Array](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [Oggetti e classi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [Tipi valore e tipi riferimento](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
