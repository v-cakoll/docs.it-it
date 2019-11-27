---
title: 'Procedura: creare una stringa da una matrice di valori Char'
ms.date: 07/20/2015
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
ms.openlocfilehash: 03138a851afc55f735cc66edeb345817428a0452
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344392"
---
# <a name="how-to-create-a-string-from-an-array-of-char-values-visual-basic"></a>Procedura: creare una stringa da una matrice di valori Char (Visual Basic)
In questo esempio viene creata la stringa "abcd" da singoli caratteri.  
  
## <a name="example"></a>Esempio  
 [!code-vb[VbVbalrStrings#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#61)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Questo metodo non ha requisiti particolari.  
  
 La sintassi `"a"c`, in cui un singolo `c` segue un singolo carattere racchiuso tra virgolette, viene usato per creare un valore letterale carattere.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 I caratteri null (equivalenti a `Chr(0)`) nella stringa portano a risultati imprevisti quando si usa la stringa. Il carattere null verrà incluso nella stringa, ma in alcune situazioni i caratteri che seguono il carattere null non verranno visualizzati.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.String>
- [Tipo di dati Char](../../../../visual-basic/language-reference/data-types/char-data-type.md)
- [Tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
