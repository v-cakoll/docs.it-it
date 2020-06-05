---
title: Nomi di elementi e attributi XML dichiarati
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [XML in Visual Basic]
- element names [XML in Visual Basic]
- names in XML literals [Visual Basic]
- attribute names [XML in Visual Basic]
- XML literals [Visual Basic], element names
ms.assetid: cc110118-b6cf-4ff9-a4e4-6233c90c9fbf
ms.openlocfilehash: 043243eeee7c24d8c63105047fa3e7e0ed58c7b0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84374668"
---
# <a name="names-of-declared-xml-elements-and-attributes-visual-basic"></a>Nomi di elementi e attributi XML dichiarati (Visual Basic)
In questo argomento vengono fornite Visual Basic linee guida per la denominazione di elementi e attributi XML nei valori letterali XML.  In un valore letterale XML è possibile specificare un nome locale o un nome completo. Un nome completo è costituito da un prefisso dello spazio dei nomi XML, da due punti e da un nome locale. Per ulteriori informazioni sui prefissi degli spazi dei nomi XML, vedere [valore letterale elemento XML](../../../language-reference/xml-literals/xml-element-literal.md).  
  
## <a name="rules"></a>Regole  
 Il nome locale di un elemento o di un attributo in Visual Basic deve rispettare le regole seguenti.  
  
- Può iniziare con uno spazio dei nomi. Deve iniziare con un carattere alfabetico o un carattere di sottolineatura ( `_` ).  
  
- Deve contenere solo caratteri alfabetici, cifre decimali, caratteri di sottolineatura, punti (.) e trattini (-).  
  
- La lunghezza non deve superare i 1.024 caratteri.  
  
- I due punti visualizzati nei nomi indicano la delimitazione dello spazio dei nomi. Pertanto, è possibile utilizzare i due punti solo per specificare uno spazio dei nomi XML per un determinato nome.  
  
 Inoltre, è necessario rispettare le linee guida seguenti.  
  
- La specifica XML 1,0 riserva tutti i nomi che iniziano con la stringa "XML", di qualsiasi variazione di maiuscole e minuscole. Pertanto, non utilizzare tali nomi per i nomi di elemento e di attributo.  
  
### <a name="name-length-guidelines"></a>Linee guida per la lunghezza del nome  
 In pratica, un nome deve essere il più breve possibile, pur identificando chiaramente la natura dell'elemento. In questo modo è possibile migliorare la leggibilità del codice e ridurre la lunghezza delle righe e le dimensioni del file di origine.  
  
 Il nome, tuttavia, non deve essere così breve da descrivere in modo adeguato l'elemento o il modo in cui il codice lo usa. Questo è importante per la leggibilità del codice. Se un altro utente sta provando a comprenderlo o se si sta esaminando molto tempo dopo averlo scritto, i nomi di elemento appropriati possono risparmiare tempo.  
  
## <a name="case-sensitivity-in-names"></a>Distinzione maiuscole/minuscole nei nomi  
 Con distinzione tra maiuscole e minuscole. Ciò significa che quando il compilatore di Visual Basic confronta due nomi che differiscono solo per i casi alfabetici, li interpreta come nomi diversi. Ad esempio, interpreta `ABC` e `abc` come riferimento a elementi distinti.  
  
## <a name="xml-namespaces"></a>Spazi dei nomi XML  
 Quando si crea un valore letterale elemento XML, è possibile specificare il prefisso dello spazio dei nomi XML per il nome dell'elemento. Per altre informazioni, vedere [valore letterale elemento XML](../../../language-reference/xml-literals/xml-element-literal.md).  
  
## <a name="see-also"></a>Vedere anche

- [Creazione di XML in Visual Basic](creating-xml.md)
- [Valore letterale di elemento XML](../../../language-reference/xml-literals/xml-element-literal.md)
