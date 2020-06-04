---
title: Tipi di dati carattere
ms.date: 07/20/2015
helpviewer_keywords:
- data types [Visual Basic], character
- String data type [Visual Basic], character data types
- character data types [Visual Basic]
- Char data type [Visual Basic], character data types
- data types [Visual Basic], choosing
ms.assetid: 902479ef-1679-47fc-9911-0c1c5008226c
ms.openlocfilehash: 33dd4c62776ae8c5ec0ce0a6d0858a7ed0d047fb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401992"
---
# <a name="character-data-types-visual-basic"></a>Dati di tipo carattere (Visual Basic)
Visual Basic fornisce *tipi di dati di tipo carattere* per gestire i caratteri stampabili e visualizzabili. Mentre entrambi gestiscono i caratteri Unicode, contiene `Char` un singolo carattere mentre `String` contiene un numero di caratteri indefinito.  
  
 Per una tabella in cui viene visualizzato un confronto affiancato dei tipi di dati Visual Basic, vedere [tipi di dati](../../../language-reference/data-types/index.md).  
  
## <a name="char-type"></a>Tipo char  
 Il `Char` tipo di dati è un singolo carattere Unicode a due byte (a 16 bit). Se una variabile archivia sempre esattamente un carattere, dichiararlo come `Char` . Ad esempio:  
  
 [!code-vb[VbVbalrCharTypes#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#1)]
  
 Ogni valore possibile in una `Char` `String` variabile o è un *punto di codice*, o codice carattere, nel set di caratteri Unicode. I caratteri Unicode includono il set di caratteri ASCII di base, diverse altre lettere di alfabeto, accenti, simboli di valuta, frazioni, segni diacritici e simboli matematici e tecnici.  
  
> [!NOTE]
> Il set di caratteri Unicode riserva i punti di codice da D800 a DFFF (da 55296 a 55551 Decimal) per le *coppie di surrogati*, che richiedono valori 2 16 bit per rappresentare un singolo punto di codice. Una `Char` variabile non può avere una coppia di surrogati e un oggetto `String` Usa due posizioni per mantenere tale coppia.  
  
 Per altre informazioni, vedere [tipo di dati char](../../../language-reference/data-types/char-data-type.md).  
  
## <a name="string-type"></a>Tipo di stringa  
 Il `String` tipo di dati è una sequenza di zero o più caratteri Unicode a 2 byte (a 16 bit). Se una variabile può contenere un numero indefinito di caratteri, dichiararla come `String` . Ad esempio:  
  
 [!code-vb[VbVbalrCharTypes#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#2)]
  
 Per ulteriori informazioni, vedere [tipo di dati String](../../../language-reference/data-types/string-data-type.md).  
  
## <a name="see-also"></a>Vedere anche

- [Tipi di dati elementari](elementary-data-types.md)
- [Tipi di dati compositi](composite-data-types.md)
- [Generic Types in Visual Basic](generic-types.md)
- [Value Types and Reference Types](value-types-and-reference-types.md)
- [Conversioni di tipi in Visual Basic](type-conversions.md)
- [Risoluzione dei problemi relativi ai tipi di dati](troubleshooting-data-types.md)
- [Caratteri tipo](type-characters.md)
