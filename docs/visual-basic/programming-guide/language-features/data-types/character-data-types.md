---
title: Dati di tipo carattere (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- data types [Visual Basic], character
- String data type [Visual Basic], character data types
- character data types [Visual Basic]
- Char data type [Visual Basic], character data types
- data types [Visual Basic], choosing
ms.assetid: 902479ef-1679-47fc-9911-0c1c5008226c
ms.openlocfilehash: 5a6a8dae63f3c0b5e3038304c1c2242f9e8c9c9d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="character-data-types-visual-basic"></a>Dati di tipo carattere (Visual Basic)
Visual Basic fornisce *tipi di dati character* per la gestione dei caratteri stampabili e visualizzabili. Sebbene entrambi gestiscano i caratteri Unicode, `Char` contiene un singolo carattere mentre `String` contiene un numero indefinito di caratteri.  
  
 Per una tabella che visualizza un confronto side-by-side dei tipi di dati Visual Basic, vedere [tipi di dati](../../../../visual-basic/language-reference/data-types/data-type-summary.md).  
  
## <a name="char-type"></a>Char (tipo)  
 Il `Char` tipo di dati è un singolo carattere Unicode di due byte (16 bit). Se una variabile memorizza sempre esattamente un carattere, dichiararla come `Char`. Ad esempio:  
  
 [!code-vb[VbVbalrCharTypes#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#1)]
  
 Ogni valore possibile in un `Char` o `String` variabile è un *punto di codice*, o codice di carattere, nel set di caratteri Unicode. I caratteri Unicode includono set di caratteri ASCII di base, diverse altre lettere dell'alfabeto, accenti, simboli di valuta, frazioni, segni diacritici e i simboli matematici e tecnici.  
  
> [!NOTE]
>  I punti di codice D800 a DFFF (da 55296 55551 decimale) per le riserve di set di caratteri Unicode *coppie di surrogati*, che sono richiesti due valori a 16 bit per rappresentare un singolo punto di codice. Oggetto `Char` variabile non può contenere una coppia di surrogati e un `String` utilizza due posizioni per mantenere tale coppia.  
  
 Per ulteriori informazioni, vedere [tipo di dati Char](../../../../visual-basic/language-reference/data-types/char-data-type.md).  
  
## <a name="string-type"></a>Tipo di stringa  
 Il `String` tipo di dati è una sequenza di zero o più caratteri Unicode a due byte (16 bit). Se una variabile può contenere un numero indefinito di caratteri, dichiararla come `String`. Ad esempio:  
  
 [!code-vb[VbVbalrCharTypes#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#2)]
  
 Per ulteriori informazioni, vedere [tipo di dati stringa](../../../../visual-basic/language-reference/data-types/string-data-type.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Tipi di dati elementari](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [Tipi di dati compositi](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)  
 [Tipi generici in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [Tipi valore e tipi riferimento](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [Conversioni di tipi in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Risoluzione dei problemi relativi ai tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Caratteri tipo](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
