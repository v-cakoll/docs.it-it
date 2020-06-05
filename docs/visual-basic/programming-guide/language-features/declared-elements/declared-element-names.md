---
title: Declared Element Names
ms.date: 07/20/2015
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
ms.openlocfilehash: cdba2b5f3e17fc6666ca653abd7f4bd7dfb31c4a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392922"
---
# <a name="declared-element-names-visual-basic"></a>Nomi di elementi dichiarati (Visual Basic)
Ogni elemento dichiarato ha un nome, detto anche *identificatore*, che è quello usato dal codice per farvi riferimento.  
  
## <a name="rules"></a>Regole  
 Il nome di un elemento in Visual Basic deve rispettare le regole seguenti:  
  
- Deve iniziare con un carattere alfabetico o un carattere di sottolineatura ( `_` ).  
  
- Deve contenere solo caratteri alfabetici, cifre decimali e caratteri di sottolineatura.  
  
- Deve contenere almeno un carattere alfabetico o una cifra decimale se inizia con un carattere di sottolineatura.  
  
- La lunghezza non deve superare i 1023 caratteri.  
  
 Il limite di lunghezza di 1023 caratteri si applica anche all'intera stringa di un nome completo, ad esempio `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement` .  
  
 Nell'esempio seguente vengono illustrati alcuni nomi di elementi validi.  
  
 `aB123__45`  
  
 `_567`  
  
 Nell'esempio seguente vengono illustrati alcuni nomi di elemento non validi. Il primo contiene solo un carattere di sottolineatura, il secondo inizia con una cifra decimale e il terzo contiene un carattere non valido ($).  
  
 `' Three INVALID element names`  
  
 `_`  
  
 `12ABC`  
  
 `xyz$wv`  
  
> [!CAUTION]
> I nomi di elemento che iniziano con un carattere di sottolineatura ( `_` ) non fanno parte dell' [indipendenza del linguaggio e dei componenti indipendenti dal linguaggio](../../../../standard/language-independence-and-language-independent-components.md) , quindi il codice conforme a CLS non può usare un componente che definisce tali nomi. Tuttavia, un carattere di sottolineatura in qualsiasi altra posizione nel nome di un elemento è conforme a CLS.  
  
### <a name="name-length-guidelines"></a>Linee guida per la lunghezza del nome  
 In pratica, il nome deve essere il più breve possibile, pur identificando chiaramente la natura dell'elemento. In questo modo è possibile migliorare la leggibilità del codice e ridurre la lunghezza delle righe e le dimensioni del file di origine.  
  
 D'altra parte, il nome non dovrebbe essere così breve che non descriva in modo adeguato ciò che l'elemento rappresenta e come viene usato dal codice. Questo è importante per la leggibilità del codice. Se un altro utente sta provando a comprenderlo o se si sta esaminando molto tempo dopo averlo scritto, i nomi degli elementi appropriati possono risparmiare una notevole quantità di tempo.  
  
## <a name="escaped-names"></a>Nomi preceduti da un carattere di escape  
 In genere, il nome di un elemento non deve corrispondere a nessuna delle parole chiave riservate da Visual Basic, ad esempio `Case` o `Friend` . Tuttavia, è possibile definire un *nome*preceduto da un carattere di escape, racchiuso tra parentesi quadre ( `[ ]` ). Un nome preceduto da un carattere di escape può corrispondere a qualsiasi parola chiave Visual Basic, poiché le parentesi quadre rimuovono qualsiasi ambiguità. Si usano anche le parentesi quadre quando si fa riferimento al nome in un secondo momento nel codice.  
  
 In generale, è consigliabile usare i nomi con caratteri di escape solo nei casi seguenti:  
  
- È stata eseguita la migrazione del codice da una versione precedente di Visual Basic che non ha riservato la parola chiave usata come nome; o  
  
- Si sta lavorando con il codice scritto in un altro linguaggio in cui la parola chiave specificata non è riservata.  
  
 In caso contrario, è consigliabile rinominare l'elemento se il nome è in conflitto con una parola chiave. Il Integrated Development Environment (IDE) fornisce un modo semplice per eseguire questa operazione. Per altre informazioni, vedere [refactoring](/visualstudio/ide/refactoring-in-visual-studio).  
  
## <a name="case-sensitivity-in-names"></a>Distinzione maiuscole/minuscole nei nomi  
 I nomi degli elementi in Visual Basic non fanno distinzione tra maiuscole e minuscole. Ciò significa che quando il compilatore confronta due nomi che differiscono solo per i casi alfabetici, li interpreta come lo stesso nome. Ad esempio, se si ha `ABC` e `abc` , il compilatore li interpreta come se facessero riferimento allo stesso elemento dichiarato.  
  
 Il Common Language Runtime (CLR) usa invece l'associazione che distingue fra maiuscole e minuscole. Perciò, quando si genera un assembly o una DLL e la si rende disponibile ad altri assembly, i nomi distinguono fra maiuscole e minuscole. Se ad esempio si definisce una classe con un elemento denominato `ABC`e altri assembly usano la classe mediante il Common Language Runtime, devono fare riferimento all'elemento come `ABC`. Se successivamente si ricompila la classe e si modifica il nome dell'elemento in `abc` , gli altri assembly che usano la classe non possono più accedere a tale elemento. Pertanto, quando si rilascia una versione aggiornata di un assembly, non si devono modificare le maiuscole e le minuscole degli elementi pubblici.  
  
## <a name="names-and-locales"></a>Nomi e impostazioni locali  
 Il confronto dei nomi è indipendente dalle impostazioni locali. Se due nomi corrispondono in un'unica impostazione locale, viene garantita la corrispondenza con tutte le impostazioni locali.  
  
## <a name="see-also"></a>Vedere anche

- [Elementi dichiarati](index.md)
- [Caratteristiche di elementi dichiarati](declared-element-characteristics.md)
- [References to Declared Elements](references-to-declared-elements.md)
- [Istruzioni](../../../language-reference/statements/index.md)
