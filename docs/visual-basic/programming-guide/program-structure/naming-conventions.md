---
title: Convenzioni di denominazione
ms.date: 07/20/2015
helpviewer_keywords:
- names [Visual Basic], Visual Basic rules
- naming conventions
- naming conventions [Visual Basic], Visual Basic
- Visual Basic code, naming conventions
- conventions [Visual Basic], Visual Basic coding
- names [Visual Basic], naming conventions
- naming conventions [Visual Basic], classes
ms.assetid: 164949a4-2a7c-4736-9d82-9c3078e2e56c
ms.openlocfilehash: 98fdda2934c9df1b33f41b6e0442a39246efe168
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347315"
---
# <a name="visual-basic-naming-conventions"></a>Convenzioni di denominazione di Visual Basic
Quando si rinomina un elemento nell'applicazione Visual Basic, il primo carattere del nome deve essere un carattere alfabetico o un carattere di sottolineatura. Si noti, tuttavia, che i nomi che iniziano con un carattere di sottolineatura non sono conformi all' [indipendenza del linguaggio e a CLS (Language-independent Components](../../../standard/language-independence-and-language-independent-components.md) ).  
  
 I suggerimenti seguenti si applicano alla denominazione.  
  
- Iniziare ogni parola separata in un nome con una lettera maiuscola, come in `FindLastRecord` e `RedrawMyForm`.  
  
- Iniziare i nomi di funzione e metodo con un verbo, come in `InitNameArray` o `CloseDialog`.  
  
- Iniziare i nomi di classe, struttura, modulo e proprietà con un sostantivo, come in `EmployeeName` o `CarAccessory`.  
  
- Iniziare i nomi di interfaccia con il prefisso "I", seguito da un sostantivo o da una frase nominale, ad esempio `IComponent`, o con un aggettivo che descrive il comportamento dell'interfaccia, ad esempio `IPersistable`. Non usare il carattere di sottolineatura e usare le abbreviazioni sporadicamente, perché le abbreviazioni possono causare confusione.  
  
- Iniziare i nomi dei gestori eventi con un sostantivo che descrive il tipo di evento seguito dal suffisso "`EventHandler`", come in "`MouseEventHandler`".  
  
- Nei nomi delle classi di argomenti dell'evento includere il suffisso "`EventArgs`".  
  
- Se un evento ha un concetto di "before" o "After", usare un suffisso presente o passato, come in "`ControlAdd`" o "`ControlAdded`".  
  
- Per i termini usati lungo o di frequente, usare le abbreviazioni per tenere ragionevoli le lunghezze dei nomi, ad esempio, "HTML" invece di "Hypertext Markup Language". In generale, i nomi delle variabili maggiori di 32 caratteri sono difficili da leggere in un monitor impostato su una risoluzione bassa. Inoltre, assicurarsi che le abbreviazioni siano coerenti nell'intera applicazione. Il cambio casuale di un progetto tra "HTML" e "Hypertext Markup Language" può causare confusione.  
  
- Evitare di usare nomi in un ambito interno identici a quelli in un ambito esterno. Se si accede a una variabile errata, possono verificarsi errori. Se si verifica un conflitto tra una variabile e la parola chiave con lo stesso nome, è necessario identificare la parola chiave facendola precedere dalla libreria dei tipi appropriata. Se, ad esempio, si dispone di una variabile denominata `Date`, è possibile utilizzare la funzione intrinseca `Date` solo chiamando <xref:System.DateTime.Date%2A?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche

- [Parole chiave come nomi di elementi nel codice](../../../visual-basic/programming-guide/program-structure/keywords-as-element-names-in-code.md)
- [Me, My, MyBase e MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Nomi di elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [Struttura del programma e convenzioni di scrittura del codice](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [Riferimenti per il linguaggio Visual Basic](../../../visual-basic/language-reference/index.md)
