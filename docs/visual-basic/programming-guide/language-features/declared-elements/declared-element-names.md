---
title: Nomi di elementi dichiarati (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declared elements [Visual Basic], case sensitivity
- names [Visual Basic], Visual Basic rules
- naming conventions [Visual Basic]
- element names [Visual Basic]
- declared elements [Visual Basic], identifiers
- declarations [Visual Basic], elements
- declared elements [Visual Basic], valid names
- '[] escape characters [Visual Basic]'
- names [Visual Basic], elements
- declaration statements [Visual Basic], declared elements
- declaring elements [Visual Basic]
- identifiers [Visual Basic], declared elements
- case sensitivity, declared element names
- escape characters [Visual Basic]
- names [Visual Basic], declared elements
- declared elements [Visual Basic], about declared elements
- escaped names [Visual Basic]
- declared elements [Visual Basic], names
- names [Visual Basic], naming conventions
- identifiers [Visual Basic], elements
ms.assetid: 09d8843b-c0dc-4afe-9dab-87c439a69e66
caps.latest.revision: "27"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 22595eff2509d3954b3ce9d5038b19a681fbfbbe
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
---
# <a name="declared-element-names-visual-basic"></a>Nomi di elementi dichiarati (Visual Basic)
Ogni elemento dichiarato è un nome, detto anche un *identificatore*, il codice utilizzato per farvi riferimento.  
  
## <a name="rules"></a>Regole  
 Il nome di un elemento in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] deve rispettare le regole seguenti:  
  
-   Deve iniziare con un carattere alfabetico o un carattere di sottolineatura (`_`).  
  
-   Deve contenere solo caratteri alfabetici, cifre e caratteri di sottolineatura.  
  
-   Deve contenere almeno un carattere alfabetico o una cifra decimale se inizia con un carattere di sottolineatura.  
  
-   Non deve essere più di 1023 caratteri.  
  
 La lunghezza massima di 1023 caratteri si applica anche per l'intera stringa di un nome completo, ad esempio `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`.  
  
 L'esempio seguente mostra alcuni nomi di elemento valido.  
  
 `aB123__45`  
  
 `_567`  
  
 L'esempio seguente mostra alcuni nomi di elemento non valido. La prima riga contiene un carattere di sottolineatura, il secondo inizia con una cifra decimale e la terza colonna contiene un carattere non valido ($).  
  
 `' Three INVALID element names`  
  
 `_`  
  
 `12ABC`  
  
 `xyz$wv`  
  
> [!CAUTION]
>  I nomi degli elementi a partire da un carattere di sottolineatura (`_`) non fanno parte di [indipendenza del linguaggio e componenti indipendenti dal linguaggio](../../../../standard/language-independence-and-language-independent-components.md) (CLS), pertanto il codice conforme a CLS non è possibile utilizzare un componente che definisce tali nomi. Tuttavia, un carattere di sottolineatura in qualsiasi altra posizione nel nome di un elemento è conforme a CLS.  
  
### <a name="name-length-guidelines"></a>Linee guida di lunghezza nome  
 In pratica, il nome deve essere il più breve possibile identificando chiaramente la natura dell'elemento. Questo migliora la leggibilità del codice e ridurre la dimensione del file di origine e di lunghezza riga.  
  
 D'altra parte, il nome non deve essere breve in modo che non adeguatamente descrive ciò che rappresenta l'elemento e come utilizzato dal codice. Questo è importante per la leggibilità del codice. Se un altro utente sta tentando di capire, oppure se manualmente cercata è molto tempo dopo che è stato scritto, nomi di elemento appropriato possono salvare una considerevole quantità di tempo.  
  
## <a name="escaped-names"></a>Nomi con caratteri di escape  
 In genere, un nome di elemento non deve corrispondere alle parole chiave riservate dal [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], ad esempio `Case` o `Friend`. Tuttavia, è possibile definire un *nome forzato*, racchiuso tra parentesi (`[ ]`). Un nome con caratteri di escape può corrispondere a qualsiasi [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] (parola chiave), poiché le parentesi quadre rimuovere qualsiasi ambiguità. È inoltre possibile utilizzare le parentesi quando si fa riferimento al nome in un secondo momento nel codice.  
  
 In generale, è necessario utilizzare nomi con caratteri di escape solo quando:  
  
-   Il codice ha eseguito la migrazione da una versione precedente di [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] che non era riservata la parola chiave viene utilizzata come un nome; o  
  
-   Si sta usando il codice scritto in un altro linguaggio in cui la parola chiave specificata non è riservata.  
  
 In caso contrario, è necessario considerare la ridenominazione dell'elemento se il nome è in conflitto con una parola chiave. Ambiente di sviluppo integrato (IDE) fornisce un modo semplice per eseguire questa operazione. Per ulteriori informazioni, vedere [Refactoring](/visualstudio/vb-ide/refactoring-vb).  
  
## <a name="case-sensitivity-in-names"></a>Distinzione maiuscole/minuscole nei nomi  
 I nomi di elemento in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] sono tra maiuscole e minuscole. Ciò significa che quando il compilatore confronta due nomi che differiscono solo nelle maiuscole, li interpreta come lo stesso nome. Ad esempio, se si ha `ABC` e `abc` , il compilatore li interpreta come se facessero riferimento allo stesso elemento dichiarato.  
  
 Tuttavia, common language runtime (CLR) utilizza l'associazione tra maiuscole e minuscole. Perciò, quando si genera un assembly o una DLL e la si rende disponibile ad altri assembly, i nomi distinguono fra maiuscole e minuscole. Se ad esempio si definisce una classe con un elemento denominato `ABC`e altri assembly usano la classe mediante il Common Language Runtime, devono fare riferimento all'elemento come `ABC`. Se si successivamente ricompila la classe e modificare il nome dell'elemento a `abc`, gli altri assembly usano la classe non è più possano accedere all'elemento. Pertanto, quando si rilascia una versione aggiornata di un assembly, non si devono modificare le maiuscole e le minuscole degli elementi pubblici.  
  
## <a name="names-and-locales"></a>I nomi e le impostazioni locali  
 Confronto dei nomi è indipendente dalle impostazioni locali. Se due nomi corrispondano in una lingua, essi sono garantiti corrispondano in tutte le impostazioni locali.  
  
## <a name="see-also"></a>Vedere anche  
 [Elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md)  
 [Caratteristiche di elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)  
 [Riferimenti a elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [Istruzioni](../../../../visual-basic/language-reference/statements/index.md)
