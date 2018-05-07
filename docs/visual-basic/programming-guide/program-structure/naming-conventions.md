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
ms.openlocfilehash: cb7e9f2a577e95e09fde885df1a78aea4e7fa466
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="visual-basic-naming-conventions"></a>Convenzioni di denominazione di Visual Basic
Quando si assegna un elemento nell'applicazione Visual Basic, il primo carattere del nome deve essere un carattere alfabetico o un carattere di sottolineatura. Si noti tuttavia che i nomi che iniziano con un carattere di sottolineatura non sono compatibili con la [indipendenza del linguaggio e componenti indipendenti dal linguaggio](../../../standard/language-independence-and-language-independent-components.md) (CLS).  
  
 I suggerimenti seguenti si applicano a denominazione.  
  
-   Iniziare di ciascuna parola in un nome con una lettera maiuscola, ad esempio `FindLastRecord` e `RedrawMyForm`.  
  
-   Funzioni e metodi nomi devono iniziare con un verbo HTTP, come `InitNameArray` o `CloseDialog`.  
  
-   Iniziare classe, struttura, modulo e i nomi delle proprietà e un sostantivo, ad esempio `EmployeeName` o `CarAccessory`.  
  
-   Interfaccia nomi devono iniziare con il prefisso "I", seguito da un sostantivo o un sintagma nominale, ad esempio `IComponent`, oppure con un aggettivo che descrive il comportamento dell'interfaccia, ad esempio `IPersistable`. Non utilizzare il carattere di sottolineatura e abbreviazioni con cautela, perché le abbreviazioni possono provocare confusione.  
  
-   I nomi dei gestori eventi devono iniziare con una che descrive il tipo di evento aggiungendo il "`EventHandler`"suffisso, come in"`MouseEventHandler`".  
  
-   Il nome delle classi di argomenti di evento, includere il "`EventArgs`" suffisso.  
  
-   Se un evento è un concetto di "before" o "after", utilizzare un suffisso presente o passato, come in "`ControlAdd`"o"`ControlAdded`".  
  
-   Per i termini di tempo o utilizzati di frequente, le abbreviazioni per mantenere la lunghezza del nome ragionevole, ad esempio, "HTML", anziché "Hypertext Markup Language". In generale, i nomi delle variabili maggiore di 32 caratteri sono difficili da leggere su un monitor impostato a bassa risoluzione. Assicurarsi inoltre che le abbreviazioni sono coerenti in tutta l'applicazione. All'interno di un progetto tra "HTML" e "Hypertext Markup Language" può generare confusione.  
  
-   Evitare di utilizzare nomi in un ambito interno che sono gli stessi nomi in un ambito esterno. Possono verificarsi errori se si accede alla variabile non corretta. Se si verifica un conflitto tra una variabile e la parola chiave con lo stesso nome, è necessario identificare la parola chiave anteponendovi la libreria dei tipi appropriati. Ad esempio, se si dispone di una variabile denominata `Date`, è possibile utilizzare la funzione intrinseca `Date` funzione solo per la chiamata <xref:System.DateTime.Date%2A?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche  
 [Parole chiave come nomi di elementi nel codice](../../../visual-basic/programming-guide/program-structure/keywords-as-element-names-in-code.md)  
 [Me, My, MyBase e MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [Nomi di elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [Struttura del programma e convenzioni di scrittura del codice](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [Riferimenti per il linguaggio Visual Basic](../../../visual-basic/language-reference/index.md)
