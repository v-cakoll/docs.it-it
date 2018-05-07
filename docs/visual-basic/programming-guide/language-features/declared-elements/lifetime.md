---
title: Durata in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- static variables [Visual Basic], lifetime
- static variables [Visual Basic], Visual Basic
- declared elements [Visual Basic], lifetime
- Shared variable lifetime [Visual Basic]
- lifetime [Visual Basic], declared elements
- lifetime [Visual Basic], Visual Basic
- lifetime [Visual Basic]
ms.assetid: bd91e390-690a-469a-9946-8dca70bc14e7
ms.openlocfilehash: d32639f1c392d53a7e9f6258440b6c0925d27a5d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="lifetime-in-visual-basic"></a>Durata in Visual Basic
Il *durata* di un elemento dichiarato è il periodo di tempo durante il quale essa è disponibile per l'utilizzo. Le variabili sono gli unici elementi che hanno una durata. A tale scopo, il compilatore considera i parametri di routine e funzione restituisce come case speciale di variabili. La durata di una variabile rappresenta il periodo di tempo durante i quali può contenere un valore. Il valore può cambiare nel corso della sua durata, ma contiene sempre un valore.  
  
## <a name="different-lifetimes"></a>Durata diversa  
 Oggetto *variabile membro* (dichiarato a livello di modulo, all'esterno di qualsiasi routine) è in genere uguale alla durata dell'elemento in cui è dichiarata. Una variabile non condivisa dichiarata in una classe o struttura esiste come una copia separata per ogni istanza della classe o struttura in cui viene dichiarato. Ognuna di queste variabili è uguale alla durata della relativa istanza. Tuttavia, un `Shared` variabile ha un'unica durata, rimane attiva per il tempo di esecuzione dell'applicazione.  
  
 Oggetto *variabile locale* (dichiarata all'interno di una stored procedure) esiste solo durante l'esecuzione della routine in cui viene dichiarato. Questo vale anche per i parametri della routine e per qualsiasi funzione. Tuttavia, se tale routine chiama altre procedure, le variabili locali mantengono i relativi valori durante l'esecuzione delle routine chiamate.  
  
## <a name="beginning-of-lifetime"></a>Inizio della durata  
 La durata di una variabile locale inizia quando il controllo passa la routine in cui è dichiarata. Ogni variabile locale viene inizializzata sul valore predefinito per il tipo di dati non appena inizia la procedura in esecuzione. Quando la stored procedure rileva un `Dim` istruzione che specifica i valori iniziali, imposta le variabili a tali valori, anche se il codice aveva già assegnato altri valori.  
  
 Ogni membro di una variabile di struttura viene inizializzato come se fosse una variabile separata. Analogamente, ogni elemento di una variabile di matrice viene inizializzato singolarmente.  
  
 Le variabili dichiarate all'interno di un blocco all'interno di una stored procedure (ad esempio un `For` ciclo) vengono inizializzati su una voce con la procedura. Queste inizializzazioni effettive verrà mai eseguito il blocco o meno.  
  
## <a name="end-of-lifetime"></a>Fine della durata  
 Al termine di una stored procedure, i valori delle variabili locali non vengono mantenuti e Visual Basic recupera la memoria. Alla successiva che si chiama la routine, tutte le variabili locali vengono ricreate e reinizializzate.  
  
 Al termine di un'istanza di una classe o struttura, delle sue variabili perdono la memoria e i relativi valori. Ogni nuova istanza della classe o struttura crea e reinizializza delle sue variabili. Tuttavia, `Shared` le variabili vengono mantenute fino a quando l'esecuzione dell'applicazione.  
  
## <a name="extension-of-lifetime"></a>Estensione della durata  
 Se si dichiara una variabile locale con il `Static` (parola chiave), la relativa durata è maggiore rispetto al tempo di esecuzione della relativa routine. Nella tabella seguente viene illustrato come la dichiarazione di routine determina per quanto tempo un `Static` variabile esiste.  
  
|Posizione della routine e condivisione|Inizia la durata delle variabili statica|Termina la durata delle variabili statiche|  
|------------------------------------|-------------------------------------|-----------------------------------|  
|In un modulo (condiviso per impostazione predefinita)|La prima volta che viene chiamata la procedura|Al termine dell'esecuzione dell'applicazione|  
|In una classe, `Shared` (procedura non è un membro di istanza)|La prima volta la procedura viene chiamata su un'istanza specifica o sul nome della classe o struttura stessa|Al termine dell'esecuzione dell'applicazione|  
|In un'istanza di una classe, non `Shared` (stored procedure è un membro di istanza)|La prima volta che la routine viene chiamata sull'istanza specifica|Quando l'istanza viene rilasciata per l'operazione di garbage collection (GC)|  
  
## <a name="static-variables-of-the-same-name"></a>Variabili statiche con lo stesso nome  
 È possibile dichiarare le variabili statiche con lo stesso nome in più di una stored procedure. In questo caso, il compilatore Visual Basic considera ognuna di queste variabili per un elemento distinto. L'inizializzazione di una di queste variabili non influenza i valori delle altre. Lo stesso vale se si definisce una routine con un set di overload e dichiara una variabile statica con lo stesso nome in ogni overload.  
  
## <a name="containing-elements-for-static-variables"></a>Contenente gli elementi per le variabili statiche  
 È possibile dichiarare una variabile locale statica all'interno di una classe, vale a dire, all'interno di una routine in tale classe. Tuttavia, è possibile dichiarare una variabile locale statica all'interno di una struttura, come un membro di struttura o come una variabile locale di una stored procedure all'interno della struttura.  
  
## <a name="example"></a>Esempio  
  
### <a name="description"></a>Descrizione  
 Nell'esempio seguente viene dichiarata una variabile con il [statico](../../../../visual-basic/language-reference/modifiers/static.md) (parola chiave). (Si noti che non è necessario il `Dim` (parola chiave) quando il [Dim (istruzione)](../../../../visual-basic/language-reference/statements/dim-statement.md) Usa un modificatore, ad esempio `Static`.)  
  
### <a name="code"></a>Codice  
 [!code-vb[VbVbalrKeywords#13](../../../../visual-basic/language-reference/codesnippet/VisualBasic/lifetime_1.vb)]  
  
### <a name="comments"></a>Commenti  
 Nell'esempio precedente, la variabile `applesSold` continua a esistere dopo la procedura `runningTotal` restituisce al codice chiamante. Alla successiva `runningTotal` viene chiamato, `applesSold` mantiene il relativo valore calcolato in precedenza.  
  
 Se `applesSold` è stata dichiarata senza utilizzando `Static`, i valori precedentemente accumulati non verranno conservati per chiamate a `runningTotal`. Alla successiva `runningTotal` è stato chiamato, `applesSold` verrà ricreata e inizializzata su 0, e `runningTotal` restituirà semplicemente lo stesso valore con cui è stato chiamato.  
  
### <a name="compiling-the-code"></a>Compilazione del codice  
 È possibile inizializzare il valore di una variabile locale statica come parte della relativa dichiarazione. Se si dichiara una matrice come `Static`, è possibile inizializzare il rango (numero di dimensioni), la lunghezza di ogni dimensione e i valori dei singoli elementi.  
  
### <a name="security"></a>Sicurezza  
 Nell'esempio precedente, è possibile ottenere la stessa durata dichiarando `applesSold` a livello di modulo. Se è stato modificato l'ambito di una variabile in questo modo, tuttavia, la procedura non avrebbe accesso esclusivo a essa. Perché è in grado di accedere ad altre procedure `applesSold` e modificarne il valore, il totale parziale potrebbe non essere affidabile e il codice potrebbe essere più difficile da gestire.  
  
## <a name="see-also"></a>Vedere anche  
 [Shared](../../../../visual-basic/language-reference/modifiers/shared.md)  
 [Nothing](../../../../visual-basic/language-reference/nothing.md)  
 [Nomi di elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [Riferimenti a elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [Ambito in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)  
 [Livelli di accesso in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [Variabili](../../../../visual-basic/programming-guide/language-features/variables/index.md)  
 [Dichiarazione di variabile](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [Risoluzione dei problemi relativi ai tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Static](../../../../visual-basic/language-reference/modifiers/static.md)
