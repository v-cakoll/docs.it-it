---
title: Convenzioni di denominazione di Visual Basic
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
ms.openlocfilehash: 46f59403feced4baafef4662065cb7daedbeaa7b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050376"
---
# <a name="visual-basic-naming-conventions"></a>Convenzioni di denominazione di Visual Basic
Quando si assegna un elemento in un'applicazione Visual Basic, il primo carattere del nome deve essere un carattere alfabetico o un carattere di sottolineatura. Si noti tuttavia che i nomi che iniziano con un carattere di sottolineatura non sono conformi con la [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS).  
  
 I suggerimenti seguenti si applicano per la denominazione.  
  
- Iniziare a ciascuna parola in un nome con una lettera maiuscola, come in `FindLastRecord` e `RedrawMyForm`.  
  
- La funzione e metodo nomi devono iniziare con un verbo, come `InitNameArray` o `CloseDialog`.  
  
- Iniziare classe, struttura, modulo e i nomi di proprietà con un nome, ad esempio `EmployeeName` o `CarAccessory`.  
  
- Interfaccia nomi devono iniziare con il prefisso "I", seguito da un sostantivo o da un sintagma nominale, ad esempio `IComponent`, o con un aggettivo che descrive il comportamento dell'interfaccia, ad esempio `IPersistable`. Non usare il carattere di sottolineatura e usare le abbreviazioni sporadicamente, perché le abbreviazioni possono causare confusione.  
  
- I nomi dei gestori eventi devono iniziare con una che descrive il tipo di evento aggiungendo i "`EventHandler`"suffisso, come in"`MouseEventHandler`".  
  
- Nei nomi delle classi di argomento degli eventi, includere il "`EventArgs`" suffisso.  
  
- Se un evento è un concetto di "before" o "after", usare un suffisso presente o passato, come in "`ControlAdd`"o"`ControlAdded`".  
  
- Per i termini di tempo o utilizzate di frequente, usare le abbreviazioni per mantenere la lunghezza del nome ragionevole, ad esempio, "HTML", invece di "Hypertext Markup Language". In generale, i nomi delle variabili maggiore di 32 caratteri sono difficili da leggere su un monitor impostato a bassa risoluzione. Inoltre, assicurarsi che le abbreviazioni siano coerenti in tutta l'applicazione. All'interno di un progetto tra "HTML" e "Hypertext Markup Language" può generare confusione.  
  
- Evitare di usare nomi in un ambito interno che sono gli stessi nomi in un ambito esterno. Gli errori possono verificarsi se si accede alla variabile non corretta. Se si verifica un conflitto tra la parola chiave lo stesso nome e una variabile, è necessario identificare la parola chiave anteponendovi la libreria dei tipi appropriati. Ad esempio, se si dispone di una variabile denominata `Date`, è possibile usare la funzione intrinseca `Date` funzione solo chiamando <xref:System.DateTime.Date%2A?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche

- [Parole chiave come nomi di elementi nel codice](../../../visual-basic/programming-guide/program-structure/keywords-as-element-names-in-code.md)
- [Me, My, MyBase e MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Nomi di elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [Struttura del programma e convenzioni di scrittura del codice](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [Riferimenti per il linguaggio Visual Basic](../../../visual-basic/language-reference/index.md)
