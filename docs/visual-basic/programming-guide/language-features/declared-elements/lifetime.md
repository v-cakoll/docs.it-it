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
ms.openlocfilehash: 4c52d426fe5194a6eb61b232b8f17669b4477f16
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54667388"
---
# <a name="lifetime-in-visual-basic"></a>Durata in Visual Basic
Il *durata* di un elemento dichiarato è il periodo di tempo durante cui si è disponibile per l'uso. Le variabili sono gli unici elementi che hanno una durata. A tale scopo, il compilatore considera i parametri di routine e funzione restituisce come case speciale delle variabili. La durata di una variabile rappresenta il periodo di tempo durante i quali può contenere un valore. Tale valore può cambiare nel corso del tempo, ma mantiene sempre un valore.  
  
## <a name="different-lifetimes"></a>Durate diverse  
 Oggetto *variabile membro* (dichiarato a livello di modulo, all'esterno di qualsiasi routine) è in genere uguale alla durata dell'elemento in cui è dichiarata. Una variabile non condivisa in una classe o struttura dichiarata esiste una copia separata per ogni istanza della classe o struttura in cui è dichiarata. Ognuna di queste variabili hanno la stessa durata della relativa istanza. Tuttavia, un `Shared` variabile ha un'unica durata, che dura tutto il tempo applicazione è in esecuzione.  
  
 Oggetto *variabile locale* (dichiarato all'interno di una procedura) esiste solo durante l'esecuzione della routine in cui è dichiarata. Questo vale anche per i parametri della routine e per qualsiasi restituito dalla funzione. Tuttavia, se tale procedura chiama altre procedure, le variabili locali conservano i relativi valori mentre sono in esecuzione le procedure chiamate.  
  
## <a name="beginning-of-lifetime"></a>Inizio del ciclo di vita  
 La durata della variabile locale inizia quando il controllo entra la procedura in cui è dichiarata. Ogni variabile locale viene inizializzato sul valore predefinito per il tipo di dati, non appena viene avviata la procedura in esecuzione. Quando la procedura rileva un `Dim` istruzione che specifica i valori iniziali, imposta le variabili per tali valori, anche se il codice aveva già assegnato gli altri valori.  
  
 Ogni membro di una variabile di struttura viene inizializzata come se fosse una variabile separata. Analogamente, ogni elemento di una variabile di matrice viene inizializzata separatamente.  
  
 Le variabili dichiarate all'interno di un blocco all'interno di una routine (ad esempio un `For` ciclo) vengono inizializzati su voce per la procedura. Queste inizializzazioni effettive verrà mai eseguito il blocco o meno.  
  
## <a name="end-of-lifetime"></a>Fine della durata  
 Al termine di una routine, i valori delle variabili locali non vengono mantenuti e Visual Basic recupera la memoria. La volta successiva che si chiama la routine, tutte le variabili locali vengono ricreate e reinizializzate.  
  
 Quando termina un'istanza di una classe o struttura, le variabili non perdono memoria e i relativi valori. Ogni nuova istanza della classe o struttura consente di creare e reinizializza delle sue variabili. Tuttavia, `Shared` le variabili vengono mantenute fino a quando non si arresta l'applicazione.  
  
## <a name="extension-of-lifetime"></a>Estensione della durata  
 Se si dichiara una variabile locale con il `Static` parola chiave, la sua durata è supera al tempo di esecuzione della relativa routine. La tabella seguente illustra come la dichiarazione di routine determina per quanto tempo un `Static` variabile esiste.  
  
|Posizione della routine e condivisione|Inizia la durata delle variabili statica|Termina la durata delle variabili statiche|  
|------------------------------------|-------------------------------------|-----------------------------------|  
|In un modulo (condiviso per impostazione predefinita)|La prima volta che viene chiamata la procedura|Al termine dell'esecuzione dell'applicazione|  
|In una classe, `Shared` (procedura non è un membro di istanza)|La prima volta la procedura viene chiamata su un'istanza specifica oppure sul nome della classe o struttura stessa|Al termine dell'esecuzione dell'applicazione|  
|In un'istanza di una classe, non `Shared` (procedure è un membro di istanza)|La prima volta la procedura viene chiamata sull'istanza specifica|Quando l'istanza viene rilasciata per la garbage collection (GC)|  
  
## <a name="static-variables-of-the-same-name"></a>Variabili statiche lo stesso nome  
 È possibile dichiarare le variabili statiche con lo stesso nome in più di una procedura. In questo caso, il compilatore Visual Basic ritiene ognuna di queste variabili per un elemento distinto. L'inizializzazione di una di queste variabili non interessa i valori degli altri. Lo stesso vale se si definisce una routine con un set di overload e dichiara una variabile statica con lo stesso nome in ogni overload.  
  
## <a name="containing-elements-for-static-variables"></a>Contenente gli elementi per le variabili statiche  
 È possibile dichiarare una variabile locale statica all'interno di una classe, vale a dire, all'interno di una procedura in tale classe. Tuttavia, è possibile dichiarare una variabile locale statica all'interno di una struttura, come un membro della struttura o come una variabile locale di una stored procedure all'interno di tale struttura.  
  
## <a name="example"></a>Esempio  
  
### <a name="description"></a>Descrizione  
 Nell'esempio seguente viene dichiarata una variabile con il [statici](../../../../visual-basic/language-reference/modifiers/static.md) (parola chiave). (Si noti che non è necessario il `Dim` parola chiave quando il [istruzione Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) Usa un modificatore, ad esempio `Static`.)  
  
### <a name="code"></a>Codice  
 [!code-vb[VbVbalrKeywords#13](../../../../visual-basic/language-reference/codesnippet/VisualBasic/lifetime_1.vb)]  
  
### <a name="comments"></a>Commenti  
 Nell'esempio precedente, la variabile `applesSold` continua a esistere dopo la procedura `runningTotal` restituisce al codice chiamante. La volta successiva `runningTotal` viene chiamato, `applesSold` mantiene il valore calcolato in precedenza.  
  
 Se `applesSold` fosse stato dichiarato senza l'uso `Static`, non verranno conservati i valori precedentemente accumulati durante le chiamate a `runningTotal`. La volta successiva `runningTotal` è stato chiamato `applesSold` verrà ricreata e inizializzata su 0, e `runningTotal` restituirà semplicemente lo stesso valore con cui è stato chiamato.  
  
### <a name="compiling-the-code"></a>Compilazione del codice  
 È possibile inizializzare il valore di una variabile locale statica come parte della relativa dichiarazione. Se si dichiara una matrice come `Static`, è possibile inizializzare la classificazione (numero di dimensioni), la lunghezza di ogni dimensione e i valori dei singoli elementi.  
  
### <a name="security"></a>Sicurezza  
 Nell'esempio precedente, è possibile ottenere la stessa durata dichiarando `applesSold` a livello di modulo. Se è stato modificato l'ambito di una variabile in questo modo, tuttavia, la procedura non è più avrebbe accesso esclusivo a esso. Poiché è stato possibile accedere ad altre procedure `applesSold` e modificarne il valore, il totale parziale potrebbe non essere affidabile e il codice potrebbe risultare più difficile da gestire.  
  
## <a name="see-also"></a>Vedere anche
- [Shared](../../../../visual-basic/language-reference/modifiers/shared.md)
- [Nothing](../../../../visual-basic/language-reference/nothing.md)
- [Nomi di elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [Riferimenti a elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [Livelli di accesso in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Variabili](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [Dichiarazione di variabile](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Risoluzione dei problemi relativi ai tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Static](../../../../visual-basic/language-reference/modifiers/static.md)
