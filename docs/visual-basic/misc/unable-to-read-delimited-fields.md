---
title: Impossibile leggere i campi delimitati. Le virgolette non sono un delimitatore consentito se EscapeQuotes è impostato su True
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_IllegalDelimiter
ms.assetid: ab8a0c3a-b89c-4617-9e31-7e81f5dca433
ms.openlocfilehash: a119bf2592982b87c4bd361f9d125e6e8b7173c1
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44087225"
---
# <a name="unable-to-read-delimited-fields-because-a-double-quote-is-not-a-legal-delimiter-when-escapequotes-is-set-to-true"></a>Impossibile leggere i campi delimitati. Le virgolette non sono un delimitatore consentito se EscapeQuotes è impostato su True
`TextFieldParser` non può leggere dal file perché sono state fornite le virgolette (") come delimitatore e `EscapeQuotes` è impostato su `True`.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Impostare `EscapeQuotes` su `False`.  
  
## <a name="see-also"></a>Vedere anche

- [Metodo TextFieldParser. SetDelimiters](xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetDelimiters%2A)  
- [Proprietà TextFieldParser. Delimiters](xref:Microsoft.VisualBasic.FileIO.TextFieldParser.Delimiters%2A)  
- [Procedura: leggere da file di testo delimitati da virgola](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)  
- [Oggetto TextFieldParser](../../visual-basic/language-reference/objects/textfieldparser-object.md)
