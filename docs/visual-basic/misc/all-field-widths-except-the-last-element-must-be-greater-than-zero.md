---
title: Le larghezze di tutti i campi, ad eccezione dell'ultimo elemento, devono essere maggiori di zero
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrTextFieldParser_FieldWidthsMustPositive
ms.assetid: 41d8c661-a749-4c89-be56-905c6e7c3c9d
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 442e271c7661ece24baff966cee5fe866d783eab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="all-field-widths-except-the-last-element-must-be-greater-than-zero"></a>Le larghezze di tutti i campi, ad eccezione dell'ultimo elemento, devono essere maggiori di zero
Le larghezze di tutti i campi, ad eccezione dell'ultimo elemento, devono essere maggiori di zero. Una larghezza di campo inferiore o uguale a zero nell'ultimo elemento indica che l'ultimo campo è di lunghezza variabile.  
  
 L'operazione ha avuto esito negativo perché la larghezza di un campo che non è l'ultimo elemento è impostata su un valore uguale o minore di zero. È possibile usare una larghezza di campo con un valore minore o uguale a zero nell'ultimo elemento per indicare che l'ultimo campo è di lunghezza variabile, ma non è possibile usarla per nessun altro elemento.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Impostare la larghezza del campo di lunghezza corretta.  
  
## <a name="see-also"></a>Vedere anche  
 [Metodo TextFieldParser SetFieldWidths](http://msdn.microsoft.com/en-us/958fed9f-e0f3-4fc5-83b4-386156bdf036)  
 [Proprietà TextFieldParser FieldWidths](http://msdn.microsoft.com/en-us/c6985360-60c6-494e-89e7-43b6b73f2597)  
 [Procedura: leggere da file di testo a larghezza fissa](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md)  
 [Oggetto TextFieldParser](../../visual-basic/language-reference/objects/textfieldparser-object.md)
