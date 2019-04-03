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
ms.openlocfilehash: 2221f2677183cf360fa82a4d73a679a8b68927d1
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58819684"
---
# <a name="names-of-declared-xml-elements-and-attributes-visual-basic"></a>Nomi di elementi e attributi XML dichiarati (Visual Basic)
In questo argomento vengono fornite linee guida di Visual Basic per denominare gli elementi XML e attributi nei valori letterali XML.  In un valore letterale XML, è possibile specificare un nome locale o un nome completo. Un nome completo è costituito da un prefisso dello spazio dei nomi XML, i due punti e un nome locale. Per altre informazioni sui prefissi dello spazio dei nomi XML, vedere [letterale elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).  
  
## <a name="rules"></a>Regole  
 Un nome locale di un elemento o attributo in Visual Basic deve essere conformi alle regole seguenti.  
  
-   È possibile iniziare con uno spazio dei nomi. Deve iniziare con un carattere alfabetico o un carattere di sottolineatura (`_`).  
  
-   Deve contenere solo caratteri alfabetici, cifre decimali, caratteri di sottolineatura, punti (.) e trattini (-).  
  
-   Non deve essere lungo più di 1.024 caratteri.  
  
-   I due punti che vengono visualizzati nei nomi indicano demarcazione dello spazio dei nomi. Pertanto, è possibile usare i due punti solo per specificare uno spazio dei nomi XML per un determinato nome.  
  
 Inoltre, è necessario rispettare le linee guida seguenti.  
  
-   La specifica XML 1.0 si riserva tutti i nomi che iniziano con la stringa "xml", di qualsiasi variazione di maiuscole/minuscole. Pertanto, non utilizzare tali nomi per l'elemento e i nomi degli attributi.  
  
### <a name="name-length-guidelines"></a>Nome lunghezza orientamenti  
 Ai fini pratici, un nome deve essere più corte possibili durante identificare chiaramente la natura dell'elemento. Ciò migliora la leggibilità del codice e riduce le dimensioni di file di origine e lunghezza riga.  
  
 Tuttavia, il nome non deve essere così breve che non in modo adeguato descrive l'elemento o come utilizzato dal codice. Questo è importante per la leggibilità del codice. Se qualcun altro tenta di comprenderne il concetto, o se ne sta analizzando, molto tempo dopo che è stato scritto, i nomi degli elementi appropriati può risparmiare tempo.  
  
## <a name="case-sensitivity-in-names"></a>Distinzione maiuscole/minuscole nei nomi  
 Nomi degli elementi XML sono tra maiuscole e minuscole. Ciò significa che quando il compilatore Visual Basic consente di confrontare due nomi che differiscono solo i case in ordine alfabetico, li interpreta come nomi diversi. Ad esempio, interpreta `ABC` e `abc` come se facessero riferimento a elementi distinti.  
  
## <a name="xml-namespaces"></a>Spazi dei nomi XML  
 Quando si crea un elemento XML letterale, è possibile specificare il prefisso dello spazio dei nomi XML per il nome dell'elemento. Per altre informazioni, vedere [letterale elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).  
  
## <a name="see-also"></a>Vedere anche

- [Creazione di XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Valore letterale elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
