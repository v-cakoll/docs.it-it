---
title: 'Procedura: Creare una stringa da una matrice di valori Char (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
ms.openlocfilehash: 1f72cb86ffa38dc929062fab2f5592a781f2de27
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58831826"
---
# <a name="how-to-create-a-string-from-an-array-of-char-values-visual-basic"></a>Procedura: Creare una stringa da una matrice di valori Char (Visual Basic)
Questo esempio crea la stringa di "abcd" da singoli caratteri.  
  
## <a name="example"></a>Esempio  
 [!code-vb[VbVbalrStrings#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#61)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Questo metodo non presenta particolari requisiti.  
  
 La sintassi `"a"c`, in cui un singolo `c` segue un singolo carattere racchiuso tra virgolette, è possibile creare un carattere letterale.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Caratteri null (equivalente a `Chr(0)`) nella stringa di provocare risultati imprevisti quando si usa la stringa. Il carattere null verranno incluso con la stringa, ma non verranno visualizzati caratteri che seguono il carattere null in alcune situazioni.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.String>
- [Tipo di dati Char](../../../../visual-basic/language-reference/data-types/char-data-type.md)
- [Tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
