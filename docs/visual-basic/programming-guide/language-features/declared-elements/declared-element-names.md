---
title: Nomi di elementi dichiarati (Visual Basic)
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
ms.openlocfilehash: 5311bba92043d3fded34a5d9337b6af13e213d4a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54573387"
---
# <a name="declared-element-names-visual-basic"></a>Nomi di elementi dichiarati (Visual Basic)
Ogni elemento dichiarato è un nome, detto anche un *identificatore*, che viene usato il codice per fare riferimento a esso.  
  
## <a name="rules"></a>Regole  
 Il nome di un elemento in Visual Basic è necessario rispettare le regole seguenti:  
  
-   Deve iniziare con un carattere alfabetico o un carattere di sottolineatura (`_`).  
  
-   Deve contenere solo caratteri alfabetici, cifre decimali e caratteri di sottolineatura.  
  
-   Deve contenere almeno un carattere alfabetico o una cifra decimale se inizia con un carattere di sottolineatura.  
  
-   Non deve essere lungo più di 1023 caratteri.  
  
 La lunghezza massima di 1023 caratteri inoltre valida per l'intera stringa di un nome completo, ad esempio `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`.  
  
 L'esempio seguente illustra alcuni nomi di elemento valido.  
  
 `aB123__45`  
  
 `_567`  
  
 L'esempio seguente illustra alcuni nomi di elemento non valido. Il primo contiene solo un carattere di sottolineatura, il secondo inizia con una cifra decimale e il terzo contiene un carattere non valido ($).  
  
 `' Three INVALID element names`  
  
 `_`  
  
 `12ABC`  
  
 `xyz$wv`  
  
> [!CAUTION]
>  Nomi di elementi a partire da un carattere di sottolineatura (`_`) non fanno parte delle [Language Independence and Language-Independent Components](../../../../standard/language-independence-and-language-independent-components.md) (CLS), in modo che il codice conforme a CLS non è possibile utilizzare un componente che definisce tali nomi. Tuttavia, un carattere di sottolineatura in qualsiasi altra posizione nel nome di un elemento è conforme a CLS.  
  
### <a name="name-length-guidelines"></a>Nome lunghezza orientamenti  
 Ai fini pratici, il nome deve essere più corte possibili durante identificare chiaramente la natura dell'elemento. Ciò migliora la leggibilità del codice e riduce le dimensioni di file di origine e lunghezza riga.  
  
 D'altra parte, il nome non deve essere così breve che non in modo adeguato descrive ciò che rappresenta l'elemento e modo in cui il codice lo usa. Questo è importante per la leggibilità del codice. Se qualcun altro tenta di comprenderne il concetto, o se ne sta analizzando, molto tempo dopo che è stato scritto, i nomi degli elementi adatto può risparmiare una notevole quantità di tempo.  
  
## <a name="escaped-names"></a>Nomi con caratteri di escape  
 In genere, un nome di elemento non deve corrispondere la parola chiave riservata, ad esempio da Visual Basic `Case` o `Friend`. Tuttavia, è possibile definire un' *nome forzato*, che è racchiuso tra parentesi quadre (`[ ]`). Un nome con caratteri di escape può corrispondere a qualsiasi parola chiave Visual Basic, poiché le parentesi quadre rimuovere qualsiasi ambiguità. È anche possibile usare le parentesi quadre quando si fa riferimento al nome in un secondo momento nel codice.  
  
 In generale, è consigliabile usare nomi con caratteri di escape solo se:  
  
-   Il codice è eseguita la migrazione da una versione precedente di Visual Basic che non era riservata la parola chiave viene usata come un nome. o  
  
-   Si lavora con il codice scritto in un altro linguaggio in cui la parola chiave specificata non è riservata.  
  
 In caso contrario, è consigliabile rinominare l'elemento se il nome è in conflitto con una parola chiave. L'ambiente di sviluppo integrato (IDE) fornisce un modo semplice per eseguire questa operazione. Per altre informazioni, vedere [Refactoring](/visualstudio/vb-ide/refactoring-vb).  
  
## <a name="case-sensitivity-in-names"></a>Distinzione maiuscole/minuscole nei nomi  
 I nomi degli elementi in Visual Basic sono tra maiuscole e minuscole. Ciò significa che quando il compilatore consente di confrontare due nomi che differiscono solo nelle maiuscole, li interpreta come lo stesso nome. Ad esempio, se si ha `ABC` e `abc` , il compilatore li interpreta come se facessero riferimento allo stesso elemento dichiarato.  
  
 Tuttavia, common language runtime (CLR) utilizza l'associazione tra maiuscole e minuscole. Perciò, quando si genera un assembly o una DLL e la si rende disponibile ad altri assembly, i nomi distinguono fra maiuscole e minuscole. Se ad esempio si definisce una classe con un elemento denominato `ABC`e altri assembly usano la classe mediante il Common Language Runtime, devono fare riferimento all'elemento come `ABC`. Se si successivamente ricompila la classe e modificare il nome dell'elemento a `abc`, gli altri assembly usano la classe non è più è stato possibile accedere a quell'elemento. Pertanto, quando si rilascia una versione aggiornata di un assembly, non si devono modificare le maiuscole e le minuscole degli elementi pubblici.  
  
## <a name="names-and-locales"></a>I nomi e le impostazioni locali  
 Confronto dei nomi è indipendente dalle impostazioni locali. Se due nomi corrisponde a una delle impostazioni locali, essi sono garantiti in modo che corrispondano in tutte le impostazioni locali.  
  
## <a name="see-also"></a>Vedere anche
- [Elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md)
- [Caratteristiche di elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [Riferimenti a elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Istruzioni](../../../../visual-basic/language-reference/statements/index.md)
