---
title: Durata
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
ms.openlocfilehash: 377f0e0b5240c3da931dc4af5439aba8924f1e81
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84357141"
---
# <a name="lifetime-in-visual-basic"></a>Durata in Visual Basic
La *durata* di un elemento dichiarato è il periodo di tempo durante il quale è disponibile per l'utilizzo. Le variabili sono gli unici elementi con durata. A questo scopo, il compilatore considera i parametri della routine e la funzione restituisce come casi speciali di variabili. La durata di una variabile rappresenta il periodo di tempo durante il quale può conservare un valore. Il valore può variare nel corso della sua durata, ma include sempre un valore.  
  
## <a name="different-lifetimes"></a>Durate diverse  
 Una *variabile membro* (dichiarata a livello di modulo, all'esterno di qualsiasi routine) ha in genere la stessa durata dell'elemento in cui è dichiarata. Una variabile non condivisa dichiarata in una classe o struttura esiste come copia separata per ogni istanza della classe o della struttura in cui è dichiarata. Ogni variabile di questo tipo ha la stessa durata della relativa istanza. Tuttavia, una `Shared` variabile ha una sola durata, che dura per tutto il tempo in cui l'applicazione è in esecuzione.  
  
 Una *variabile locale* , dichiarata all'interno di una routine, esiste solo se è in esecuzione la procedura in cui è dichiarata. Questo vale anche per i parametri di tale procedura e per qualsiasi funzione restituita. Tuttavia, se tale procedura chiama altre routine, le variabili locali manterranno i valori mentre le stored procedure chiamate sono in esecuzione.  
  
## <a name="beginning-of-lifetime"></a>Inizio della durata  
 La durata di una variabile locale inizia quando il controllo immette la routine in cui è dichiarata. Ogni variabile locale viene inizializzata sul valore predefinito per il tipo di dati non appena viene avviata l'esecuzione della stored procedure. Quando la procedura rileva un' `Dim` istruzione che specifica i valori iniziali, imposta tali variabili su tali valori, anche se al codice sono già stati assegnati altri valori.  
  
 Ogni membro di una variabile di struttura viene inizializzato come se fosse una variabile separata. Analogamente, ogni elemento di una variabile di matrice viene inizializzato singolarmente.  
  
 Le variabili dichiarate all'interno di un blocco all'interno di una routine, ad esempio un `For` ciclo, vengono inizializzate alla voce della routine. Queste inizializzazioni hanno effetto indipendentemente dall'esecuzione del blocco da parte del codice.  
  
## <a name="end-of-lifetime"></a>Fine della durata  
 Quando una stored procedure viene terminata, i valori delle relative variabili locali non vengono mantenuti e Visual Basic recupera la memoria. Alla successiva chiamata della stored procedure, tutte le relative variabili locali vengono create di nuovo e reinizializzate.  
  
 Quando un'istanza di una classe o di una struttura termina, le variabili non condivise perdono la memoria e i relativi valori. Ogni nuova istanza della classe o della struttura crea e reinizializza le variabili non condivise. Tuttavia, `Shared` le variabili vengono mantenute finché l'esecuzione dell'applicazione non viene arrestata.  
  
## <a name="extension-of-lifetime"></a>Estensione della durata  
 Se si dichiara una variabile locale con la `Static` parola chiave, la durata è maggiore del tempo di esecuzione della relativa procedura. Nella tabella seguente viene illustrato come la dichiarazione di routine determini per quanto tempo una `Static` variabile esiste.  
  
|Percorso e condivisione delle procedure|Inizio durata variabile statica|Fine della durata variabile statica|  
|------------------------------------|-------------------------------------|-----------------------------------|  
|In un modulo (condiviso per impostazione predefinita)|La prima volta che viene chiamata la stored procedure|Quando l'esecuzione dell'applicazione viene arrestata|  
|In una classe, `Shared` (la routine non è un membro di istanza)|La prima volta che la stored procedure viene chiamata su un'istanza specifica o sul nome della classe o della struttura stessa|Quando l'esecuzione dell'applicazione viene arrestata|  
|In un'istanza di una classe, Not `Shared` (la procedura è un membro di istanza)|La prima volta che la stored procedure viene chiamata sull'istanza specifica|Quando l'istanza viene rilasciata per Garbage Collection (GC)|  
  
## <a name="static-variables-of-the-same-name"></a>Variabili statiche con lo stesso nome  
 È possibile dichiarare variabili statiche con lo stesso nome in più di una procedura. In tal caso, il compilatore Visual Basic considera ciascuna variabile come un elemento separato. L'inizializzazione di una di queste variabili non influisce sui valori degli altri. Lo stesso vale se si definisce una routine con un set di overload e si dichiara una variabile statica con lo stesso nome in ogni overload.  
  
## <a name="containing-elements-for-static-variables"></a>Contenitore di elementi per variabili statiche  
 È possibile dichiarare una variabile locale statica all'interno di una classe, ovvero all'interno di una routine di tale classe. Tuttavia, non è possibile dichiarare una variabile locale statica all'interno di una struttura, come membro della struttura o come variabile locale di una routine all'interno di tale struttura.  
  
## <a name="example"></a>Esempio  
  
### <a name="description"></a>Descrizione  
 Nell'esempio seguente viene dichiarata una variabile con la parola chiave [static](../../../language-reference/modifiers/static.md) . Si noti che non è necessaria la `Dim` parola chiave quando l' [istruzione Dim](../../../language-reference/statements/dim-statement.md) usa un modificatore, ad esempio `Static` .  
  
### <a name="code"></a>Codice  
 [!code-vb[VbVbalrKeywords#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class7.vb#13)]  
  
### <a name="comments"></a>Commenti  
 Nell'esempio precedente, la variabile `applesSold` continua a esistere dopo che la procedura viene `runningTotal` restituita al codice chiamante. La volta successiva che `runningTotal` viene chiamato, `applesSold` mantiene il valore calcolato in precedenza.  
  
 Se `applesSold` è stata dichiarata senza usare `Static` , i valori accumulati precedenti non verrebbero conservati tra le chiamate a `runningTotal` . La volta successiva che `runningTotal` è stata chiamata, `applesSold` verrebbe ricreata e inizializzata su 0 e `runningTotal` avrebbe restituito semplicemente lo stesso valore con cui è stato chiamato.  
  
### <a name="compile-the-code"></a>Compilare il codice  
 È possibile inizializzare il valore di una variabile locale statica come parte della relativa dichiarazione. Se si dichiara una matrice come `Static` , è possibile inizializzare il relativo rango (numero di dimensioni), la lunghezza di ogni dimensione e i valori dei singoli elementi.  
  
### <a name="security"></a>Sicurezza  
 Nell'esempio precedente, è possibile produrre la stessa durata dichiarando `applesSold` a livello di modulo. Se l'ambito di una variabile è stato modificato in questo modo, tuttavia, la procedura non avrà più accesso esclusivo. Poiché altre procedure possono accedere `applesSold` e modificare il valore, il totale parziale potrebbe essere inaffidabile e il codice potrebbe essere più difficile da gestire.  
  
## <a name="see-also"></a>Vedere anche

- [Condivisa](../../../language-reference/modifiers/shared.md)
- [Nothing](../../../language-reference/nothing.md)
- [Declared Element Names](declared-element-names.md)
- [References to Declared Elements](references-to-declared-elements.md)
- [Ambito in Visual Basic](scope.md)
- [Livelli di accesso in Visual Basic](access-levels.md)
- [Variabili](../variables/index.md)
- [Dichiarazione di variabile](../variables/variable-declaration.md)
- [Risoluzione dei problemi relativi ai tipi di dati](../data-types/troubleshooting-data-types.md)
- [Statico](../../../language-reference/modifiers/static.md)
