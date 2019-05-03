---
title: Un delimitatore non può essere Nothing o una stringa vuota
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_DelimiterNothing
ms.assetid: 8885fcd1-c201-409d-9a32-6ff2b13c0c13
ms.openlocfilehash: ff21545bfe12fb8f6eccd50fd00c138bbab92b97
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940712"
---
# <a name="a-delimiter-cannot-be-nothing-or-an-empty-string"></a>Un delimitatore non può essere Nothing o una stringa vuota
`TextFieldParser` non riesce a leggere i contenuti dal file perché la proprietà `Delimiters` è impostata su `Nothing` o corrisponde a un oggetto `String` vuoto ("").  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Specificare un valore valido per `Delimiters`.  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetDelimiters%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.Delimiters>
- [Procedura: Leggere da file di testo con valori delimitati da virgole](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)
- [Oggetto TextFieldParser](../../visual-basic/language-reference/objects/textfieldparser-object.md)
- [Analisi dei file di testo con l'oggetto TextFieldParser](../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)
