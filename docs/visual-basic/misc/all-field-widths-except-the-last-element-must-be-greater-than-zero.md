---
title: Le larghezze di tutti i campi, ad eccezione dell'ultimo elemento, devono essere maggiori di zero
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_FieldWidthsMustPositive
ms.assetid: 41d8c661-a749-4c89-be56-905c6e7c3c9d
ms.openlocfilehash: 806dcef7b7a29afa8804a581659023c817662434
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940660"
---
# <a name="all-field-widths-except-the-last-element-must-be-greater-than-zero"></a>Le larghezze di tutti i campi, ad eccezione dell'ultimo elemento, devono essere maggiori di zero
Le larghezze di tutti i campi, ad eccezione dell'ultimo elemento, devono essere maggiori di zero. Una larghezza di campo inferiore o uguale a zero nell'ultimo elemento indica che l'ultimo campo è di lunghezza variabile.  
  
 L'operazione ha avuto esito negativo perché la larghezza di un campo che non è l'ultimo elemento è impostata su un valore uguale o minore di zero. È possibile usare una larghezza di campo con un valore minore o uguale a zero nell'ultimo elemento per indicare che l'ultimo campo è di lunghezza variabile, ma non è possibile usarla per nessun altro elemento.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Impostare la larghezza del campo di lunghezza corretta.  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetFieldWidths%2A?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.FieldWidths>
- [Procedura: Leggere da file di testo a larghezza fissa](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md)
- [Oggetto TextFieldParser](../../visual-basic/language-reference/objects/textfieldparser-object.md)
