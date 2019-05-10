---
title: Istruzione SyncLock (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.SyncLock
- SyncLock
helpviewer_keywords:
- threading [Visual Basic], locks
- SyncLock statement [Visual Basic]
- locks, threads
ms.assetid: 14501703-298f-4d43-b139-c4b6366af176
ms.openlocfilehash: a2bd6ca11072113d8acff78032c19d48c30933c3
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64615132"
---
# <a name="synclock-statement"></a>Istruzione SyncLock
Acquisisce un blocco esclusivo per un blocco di istruzioni prima di eseguire il blocco.  
  
## <a name="syntax"></a>Sintassi  
  
```  
SyncLock lockobject  
    [ block ]  
End SyncLock  
```  
  
## <a name="parts"></a>Parti  
 `lockobject`  
 Obbligatorio. Espressione che restituisce un riferimento all'oggetto.  
  
 `block`  
 Facoltativo. Blocco di istruzioni da eseguire quando viene acquisito il blocco.  
  
 `End SyncLock`  
 Termina un `SyncLock` blocco.  
  
## <a name="remarks"></a>Note  
 Il `SyncLock` istruzione garantisce che più thread non eseguano il blocco di istruzioni nello stesso momento. `SyncLock` impedisce ogni thread di immettere il blocco fino a quando non viene eseguito alcun altro thread.  
  
 L'uso più comune di `SyncLock` consiste nel proteggere i dati vengano aggiornati da più thread contemporaneamente. Se le istruzioni che modificano i dati devono andare fino al completamento senza interruzioni, inserirli all'interno di un `SyncLock` blocco.  
  
 Un blocco di istruzioni protetto da un blocco esclusivo viene a volte chiamato un *sezione critica*.  
  
## <a name="rules"></a>Regole  
  
- Creazione di rami. È possibile creare rami in un `SyncLock` impedisce all'esterno del blocco.  
  
- Valore dell'oggetto di blocco. Il valore di `lockobject` non può essere `Nothing`. È necessario creare l'oggetto di blocco prima di usarla in un `SyncLock` istruzione.  
  
     Non è possibile modificare il valore di `lockobject` durante l'esecuzione di un `SyncLock` blocco. Il meccanismo di richiede che l'oggetto blocco rimangono invariati.  
  
- Non è possibile usare la [Await](../../../visual-basic/language-reference/operators/await-operator.md) operatore in un `SyncLock` blocco.  
  
## <a name="behavior"></a>Comportamento  
  
- Meccanismo. Quando un thread raggiunge la `SyncLock` istruzione, viene restituito il `lockobject` espressione e sospende l'esecuzione fino a quando non acquisisce un blocco esclusivo sull'oggetto restituito dall'espressione. Quando un altro thread raggiunge la `SyncLock` istruzione, non acquisisce un blocco fino a quando non viene eseguito il primo thread la `End SyncLock` istruzione.  
  
- Dati protetti. Se `lockobject` è un `Shared` variabile, il blocco esclusivo impedisce a un thread in qualsiasi istanza della classe dall'esecuzione di `SyncLock` bloccarsi mentre viene eseguito un altro thread. Consente di proteggere i dati condivisi fra tutte le istanze.  
  
     Se `lockobject` è una variabile di istanza (non `Shared`), il blocco impedisce a un thread in esecuzione nell'istanza corrente di eseguire il `SyncLock` blocco allo stesso tempo come un altro thread nella stessa istanza. Ciò consente di proteggere dati gestiti da istanza singola.  
  
- Acquisizione e il rilascio. Oggetto `SyncLock` blocco si comporta come un `Try...Finally` costruzione in cui le `Try` blocco acquisisce un blocco esclusivo sul `lockobject` e il `Finally` lo rilascia blocco. Per questo motivo, il `SyncLock` garantisce il rilascio del blocco, indipendentemente dal modo in cui si esce dal blocco. Questo vale anche in caso di un'eccezione non gestita.  
  
- Chiamate di Framework. Il `SyncLock` blocco acquisisce e rilascia il blocco esclusivo chiamando il `Enter` e `Exit` metodi del `Monitor` classe la <xref:System.Threading> dello spazio dei nomi.  
  
## <a name="programming-practices"></a>Procedure consigliate di programmazione  
 Il `lockobject` espressione deve sempre restituire un oggetto a cui appartiene esclusivamente alla classe. È necessario dichiarare un `Private` variabile di oggetto per proteggere i dati appartenenti all'istanza corrente, o un `Private Shared` variabile oggetto per proteggere i dati comuni a tutte le istanze.  
  
 È consigliabile non usare il `Me` (parola chiave) per fornire un blocco di dati dell'oggetto, ad esempio. Se il codice esterno alla classe ha un riferimento a un'istanza della classe, è Impossibile utilizzare il riferimento come un oggetto di blocco per un `SyncLock` blocco completamente diversa da quelle in uso, protezione dei dati diversi. In questo modo, la classe e l'altra classe può bloccare loro l'esecuzione di loro non correlati `SyncLock` blocchi. Analogamente, il blocco su una stringa può essere problematico perché qualsiasi altro codice nel processo che usa la stessa stringa condividerà lo stesso blocco.  
  
 È inoltre consigliabile non utilizzare il `Me.GetType` metodo per fornire un oggetto di blocco per i dati condivisi. Infatti `GetType` restituisce sempre lo stesso `Type` oggetto per un determinato nome di classe. Impossibile chiamare codice esterno `GetType` nella classe e ottenere lo stesso oggetto di blocco in uso. In questo modo, le due classi di blocco tra loro da loro `SyncLock` blocchi.  
  
## <a name="examples"></a>Esempi  
  
### <a name="description"></a>Descrizione  
 Nell'esempio seguente viene illustrata una classe che gestisce un elenco semplice di messaggi. Contiene i messaggi in una matrice e l'ultimo elemento della matrice di utilizzato in una variabile. Il `addAnotherMessage` procedure incrementa l'ultimo elemento e archivia il nuovo messaggio. Queste due operazioni sono protetti dal `SyncLock` e `End SyncLock` (istruzioni), poiché dopo l'ultimo elemento è stato incrementato, il nuovo messaggio deve essere archiviato prima di qualsiasi altro thread può incrementare nuovamente l'ultimo elemento.  
  
 Se il `simpleMessageList` classe condivisa un elenco di messaggi tra tutte le istanze, le variabili `messagesList` e `messagesLast` sarebbe dichiarata come `Shared`. In questo caso, la variabile `messagesLock` deve essere anche `Shared`, in modo che non vi sarà un unico oggetto blocco usato da ogni istanza.  
  
### <a name="code"></a>Codice  
 [!code-vb[VbVbalrThreading#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrThreading/VB/Class1.vb#1)]  
  
### <a name="description"></a>Descrizione  
 L'esempio seguente usa i thread e `SyncLock`. Fino a quando la `SyncLock` istruzione è presente, il blocco di istruzioni è una sezione critica e `balance` non diventerà mai un numero negativo. È possibile impostare come commento il `SyncLock` e `End SyncLock` istruzioni per visualizzare l'effetto dell'omissione di `SyncLock` (parola chiave).  
  
### <a name="code"></a>Codice  
 [!code-vb[VbVbalrThreading#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrThreading/VB/class2.vb#21)]  
  
### <a name="comments"></a>Commenti  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.Interlocked?displayProperty=nameWithType>
- [Cenni preliminari sulle primitive di sincronizzazione](../../../standard/threading/overview-of-synchronization-primitives.md)
