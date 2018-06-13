---
title: Impossibile leggere i campi delimitati. Le virgolette non sono un delimitatore consentito se EscapeQuotes è impostato su True
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_IllegalDelimiter
ms.assetid: ab8a0c3a-b89c-4617-9e31-7e81f5dca433
ms.openlocfilehash: 66116e6f3d8338db3884cd375aeb880930c8d861
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33639285"
---
# <a name="unable-to-read-delimited-fields-because-a-double-quote-is-not-a-legal-delimiter-when-escapequotes-is-set-to-true"></a>Impossibile leggere i campi delimitati. Le virgolette non sono un delimitatore consentito se EscapeQuotes è impostato su True
`TextFieldParser` non può leggere dal file perché sono state fornite le virgolette (") come delimitatore e `EscapeQuotes` è impostato su `True`.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Impostare `EscapeQuotes` su `False`.  
  
## <a name="see-also"></a>Vedere anche  
 [Metodo TextFieldParser. SetDelimiters](http://msdn.microsoft.com/library/21fa40ec-5866-4d0e-9fd9-c708a190dcc9)  
 [Proprietà TextFieldParser. Delimiters](http://msdn.microsoft.com/library/4eb18f4d-3011-40a9-b668-be93eed0444f)  
 [Procedura: leggere da file di testo delimitati da virgola](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)  
 [Oggetto TextFieldParser](../../visual-basic/language-reference/objects/textfieldparser-object.md)
