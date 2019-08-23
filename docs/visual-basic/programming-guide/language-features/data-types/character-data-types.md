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
ms.openlocfilehash: d29e8771d61c04cf35aa71b5ba7fbba0d308c730
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965683"
---
# <a name="character-data-types-visual-basic"></a>Dati di tipo carattere (Visual Basic)
Visual Basic fornisce *tipi di dati di tipo carattere* per gestire i caratteri stampabili e visualizzabili. Mentre entrambi gestiscono i caratteri Unicode, `Char` contiene un singolo carattere mentre `String` contiene un numero di caratteri indefinito.  
  
 Per una tabella in cui viene visualizzato un confronto affiancato dei tipi di dati Visual Basic, vedere [tipi di dati](../../../../visual-basic/language-reference/data-types/index.md).  
  
## <a name="char-type"></a>Tipo char  
 Il `Char` tipo di dati è un singolo carattere Unicode a due byte (a 16 bit). Se una variabile archivia sempre esattamente un carattere, dichiararlo `Char`come. Ad esempio:  
  
 [!code-vb[VbVbalrCharTypes#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#1)]
  
 Ogni valore possibile in una `Char` variabile `String` o è un *punto di codice*, o codice carattere, nel set di caratteri Unicode. I caratteri Unicode includono il set di caratteri ASCII di base, diverse altre lettere di alfabeto, accenti, simboli di valuta, frazioni, segni diacritici e simboli matematici e tecnici.  
  
> [!NOTE]
> Il set di caratteri Unicode riserva i punti di codice da D800 a DFFF (da 55296 a 55551 Decimal) per le *coppie*di surrogati, che richiedono valori 2 16 bit per rappresentare un singolo punto di codice. Una `Char` variabile non può avere una coppia di surrogati `String` e un oggetto usa due posizioni per mantenere tale coppia.  
  
 Per altre informazioni, vedere [tipo di dati char](../../../../visual-basic/language-reference/data-types/char-data-type.md).  
  
## <a name="string-type"></a>Tipo stringa  
 Il `String` tipo di dati è una sequenza di zero o più caratteri Unicode a 2 byte (a 16 bit). Se una variabile può contenere un numero indefinito di caratteri, dichiararla `String`come. Ad esempio:  
  
 [!code-vb[VbVbalrCharTypes#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#2)]
  
 Per ulteriori informazioni, vedere [tipo di dati String](../../../../visual-basic/language-reference/data-types/string-data-type.md).  
  
## <a name="see-also"></a>Vedere anche

- [Tipi di dati elementari](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [Tipi di dati compositi](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [Generic Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Conversioni di tipi in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Risoluzione dei problemi relativi ai tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Caratteri tipo](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
