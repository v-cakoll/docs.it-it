---
title: 'Procedura: creare una stringa da una matrice di valori Char (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
ms.openlocfilehash: 104b329011d69e10a2926f31ce5d296759a3cce8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647178"
---
# <a name="how-to-create-a-string-from-an-array-of-char-values-visual-basic"></a>Procedura: creare una stringa da una matrice di valori Char (Visual Basic)
Questo esempio crea la stringa "abcd" da singoli caratteri.  
  
## <a name="example"></a>Esempio  
 [!code-vb[VbVbalrStrings#61](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-create-a-string-from-an-array-of-char-values_1.vb)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Questo metodo non ha presenta requisiti speciali.  
  
 La sintassi `"a"c`, in cui un singolo `c` segue un singolo carattere tra virgolette, viene utilizzato per creare un carattere letterale.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Caratteri null (equivalente a `Chr(0)`) nella stringa di produrre risultati imprevisti quando si utilizza la stringa. Il carattere null sarà incluso nella stringa, ma non caratteri che seguono il carattere null verranno visualizzati in alcune situazioni.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.String>  
 [Tipo di dati Char](../../../../visual-basic/language-reference/data-types/char-data-type.md)  
 [Tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
