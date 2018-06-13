---
title: Nomi di elementi e attributi XML dichiarati (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [XML in Visual Basic]
- element names [XML in Visual Basic]
- names in XML literals [Visual Basic]
- attribute names [XML in Visual Basic]
- XML literals [Visual Basic], element names
ms.assetid: cc110118-b6cf-4ff9-a4e4-6233c90c9fbf
ms.openlocfilehash: 9b586936281bfbf2dcace7cf2892bebf305fc842
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650426"
---
# <a name="names-of-declared-xml-elements-and-attributes-visual-basic"></a>Nomi di elementi e attributi XML dichiarati (Visual Basic)
In questo argomento vengono fornite linee guida di Visual Basic per denominare gli elementi XML e attributi nei valori letterali XML.  In un valore letterale XML, è possibile specificare un nome locale o un nome completo. Un nome completo è costituito da un prefisso dello spazio dei nomi XML, i due punti e un nome locale. Per ulteriori informazioni sui prefissi dello spazio dei nomi XML, vedere [XML elemento Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).  
  
## <a name="rules"></a>Regole  
 Un nome locale di un elemento o attributo in Visual Basic deve essere conformi alle regole seguenti.  
  
-   Può iniziare con uno spazio dei nomi. Deve iniziare con un carattere alfabetico o un carattere di sottolineatura (`_`).  
  
-   Deve contenere solo caratteri alfabetici, cifre decimali, caratteri di sottolineatura, punti (.) e trattini (-).  
  
-   Non deve essere più di 1.024 caratteri.  
  
-   I due punti nei nomi visualizzati indicano delimitazione dello spazio dei nomi. Pertanto, è possibile utilizzare i due punti solo per specificare uno spazio dei nomi XML per un determinato nome.  
  
 Inoltre, è necessario rispettare le linee guida seguente.  
  
-   La specifica XML 1.0 si riserva tutti i nomi che iniziano con la stringa "xml", di qualsiasi variazione di maiuscole/minuscole. Pertanto, non utilizzare tali nomi per l'elemento e i nomi di attributo.  
  
### <a name="name-length-guidelines"></a>Linee guida di lunghezza nome  
 In pratica, un nome deve essere il più breve possibile identificando chiaramente la natura dell'elemento. Questo migliora la leggibilità del codice e ridurre la dimensione del file di origine e di lunghezza riga.  
  
 Tuttavia, il nome non deve essere breve in modo che non adeguatamente descrive l'elemento o come utilizzato dal codice. Questo è importante per la leggibilità del codice. Se un altro utente sta tentando di capire, o se manualmente cercata è molto tempo dopo che è stata scritta, i nomi di elemento appropriato possono risparmiare tempo.  
  
## <a name="case-sensitivity-in-names"></a>Distinzione maiuscole/minuscole nei nomi  
 I nomi degli elementi XML vengono tra maiuscole e minuscole. Ciò significa che quando il compilatore Visual Basic Confronta due nomi che differiscono solo i case in ordine alfabetico, li interpreta come nomi diversi. Ad esempio, vengono interpretati `ABC` e `abc` come riferiti a elementi distinti.  
  
## <a name="xml-namespaces"></a>Spazi dei nomi XML  
 Quando si crea il valore letterale elemento XML, è possibile specificare il prefisso dello spazio dei nomi XML per il nome dell'elemento. Per ulteriori informazioni, vedere [XML elemento Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Creazione di XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [Valore letterale elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
