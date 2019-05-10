---
title: Impossibile leggere i campi delimitati. Le virgolette non sono un delimitatore consentito se EscapeQuotes è impostato su True
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_IllegalDelimiter
ms.assetid: ab8a0c3a-b89c-4617-9e31-7e81f5dca433
ms.openlocfilehash: ca764d5258daf54a7149661549a78b3aca709718
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64619808"
---
# <a name="unable-to-read-delimited-fields-because-a-double-quote-is-not-a-legal-delimiter-when-escapequotes-is-set-to-true"></a>Impossibile leggere i campi delimitati. Le virgolette non sono un delimitatore consentito se EscapeQuotes è impostato su True
`TextFieldParser` non può leggere dal file perché sono state fornite le virgolette (") come delimitatore e `EscapeQuotes` è impostato su `True`.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Impostare `EscapeQuotes` su `False`.  
  
## <a name="see-also"></a>Vedere anche

- [Metodo TextFieldParser.SetDelimiters](xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetDelimiters%2A)
- [Proprietà TextFieldParser. Delimiters](xref:Microsoft.VisualBasic.FileIO.TextFieldParser.Delimiters%2A)
- [Procedura: Leggere da file di testo con valori delimitati da virgole](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)
- [Oggetto TextFieldParser](../../visual-basic/language-reference/objects/textfieldparser-object.md)
