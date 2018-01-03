---
title: Istruzione SyncLock
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.SyncLock
- SyncLock
helpviewer_keywords:
- threading [Visual Basic], locks
- SyncLock statement [Visual Basic]
- locks, threads
ms.assetid: 14501703-298f-4d43-b139-c4b6366af176
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c363b41bb7a409c490a6e07d4a1a4f1bb44c1438
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
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
 Il `SyncLock` istruzione garantisce che più thread eseguano contemporaneamente il blocco di istruzioni. `SyncLock`impedisce l'immissione il blocco fino a quando nessun altro thread è in esecuzione, ogni thread.  
  
 L'utilizzo più comune di `SyncLock` consiste nel proteggere i dati vengano aggiornati da più thread contemporaneamente. Se le istruzioni che modificano i dati devono essere completate senza interruzioni, inserirli all'interno di un `SyncLock` blocco.  
  
 Un blocco di istruzioni protetto da un blocco esclusivo a volte viene chiamato un *sezione critica*.  
  
## <a name="rules"></a>Regole  
  
-   Creazione di rami. È possibile creare rami in un `SyncLock` impedire all'esterno del blocco.  
  
-   Valore dell'oggetto di blocco. Il valore di `lockobject` non può essere `Nothing`. È necessario creare l'oggetto di blocco prima di utilizzarlo in un `SyncLock` istruzione.  
  
     Non è possibile modificare il valore di `lockobject` durante l'esecuzione di un `SyncLock` blocco. Il meccanismo richiede che l'oggetto di blocco rimangono invariati.  
  
-   Non è possibile utilizzare il [Await](../../../visual-basic/language-reference/operators/await-operator.md) operatore in un `SyncLock` blocco.  
  
## <a name="behavior"></a>Comportamento  
  
-   Meccanismo. Quando un thread raggiunge il `SyncLock` istruzione, viene restituito il `lockobject` espressione e sospende l'esecuzione fino a quando non acquisisce un blocco esclusivo sull'oggetto restituito dall'espressione. Quando un altro thread raggiunge il `SyncLock` istruzione, non acquisisce un blocco finché non viene eseguito il primo thread di `End SyncLock` istruzione.  
  
-   I dati protetti. Se `lockobject` è un `Shared` variabile, il blocco esclusivo impedisce a un thread in qualsiasi istanza della classe dall'esecuzione di `SyncLock` blocco durante l'esecuzione di qualsiasi altro thread. Consente di proteggere i dati che viene condiviso tra tutte le istanze.  
  
     Se `lockobject` è una variabile di istanza (non `Shared`), il blocco impedisce a un thread in esecuzione nell'istanza corrente di eseguire il `SyncLock` blocco contemporaneamente nella stessa istanza di un altro thread. Consente di proteggere dati gestiti da una singola istanza.  
  
-   Acquisizione e il rilascio. A `SyncLock` blocco si comporta come un `Try...Finally` costruzione in cui il `Try` blocco acquisisce un blocco esclusivo su `lockobject` e `Finally` blocco lo rilascia. Per questo motivo, il `SyncLock` garantisce il rilascio del blocco, indipendentemente da come si esce dal blocco. Questo vale anche nel caso di un'eccezione non gestita.  
  
-   Chiamate di Framework. Il `SyncLock` blocco acquisisce e rilascia il blocco esclusivo chiamando il `Enter` e `Exit` metodi del `Monitor` classe il <xref:System.Threading> dello spazio dei nomi.  
  
## <a name="programming-practices"></a>Tecniche di programmazione  
 Il `lockobject` espressione deve restituire sempre un oggetto che appartiene esclusivamente alla classe. È necessario dichiarare un `Private` variabile oggetto per proteggere i dati appartenenti all'istanza corrente, o un `Private Shared` variabile oggetto per proteggere i dati comuni a tutte le istanze.  
  
 Non è consigliabile utilizzare il `Me` (parola chiave) per fornire un blocco per l'istanza dell'oggetto dati. Se il codice esterno alla classe ha un riferimento a un'istanza della classe, è possibile utilizzare il riferimento come oggetto di blocco per un `SyncLock` blocco completamente diversa da quelle in uso, protezione dei dati diversi. In questo modo, la classe e le altre possono bloccarsi reciprocamente l'esecuzione non loro correlati `SyncLock` blocchi. Analogamente, il blocco su una stringa può essere problematico perché qualsiasi altro codice nel processo che utilizza la stessa stringa condivideranno lo stesso blocco.  
  
 È inoltre consigliabile non utilizzare il `Me.GetType` metodo per fornire un oggetto di blocco per i dati condivisi. In questo modo `GetType` restituisce sempre lo stesso `Type` oggetto per un determinato nome di classe. Impossibile chiamare codice esterno `GetType` sulla classe e ottenere lo stesso oggetto di blocco in uso. In questo modo, le due classi di blocco tra loro da loro `SyncLock` blocchi.  
  
## <a name="examples"></a>Esempi  
  
### <a name="description"></a>Descrizione  
 Nell'esempio seguente viene illustrata una classe che gestisce un elenco semplice di messaggi. Contiene i messaggi in una matrice e l'ultimo elemento della matrice utilizzato in una variabile. Il `addAnotherMessage` procedure incrementa l'ultimo elemento e archivia il nuovo messaggio. Queste due operazioni sono protetti dal `SyncLock` e `End SyncLock` istruzioni, poiché dopo l'ultimo elemento è stato incrementato, deve essere archiviato nel nuovo messaggio prima di qualsiasi altro thread può incrementare l'ultimo elemento nuovo.  
  
 Se il `simpleMessageList` classe condivide un unico elenco di messaggi tra tutte le istanze, le variabili `messagesList` e `messagesLast` sarebbe dichiarata come `Shared`. In questo caso, la variabile `messagesLock` deve inoltre essere `Shared`, in modo che non vi sarà un unico oggetto blocco utilizzato da ogni istanza.  
  
### <a name="code"></a>Codice  
 [!code-vb[VbVbalrThreading#1](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/synclock-statement_1.vb)]  
  
### <a name="description"></a>Descrizione  
 Nell'esempio seguente vengono utilizzati thread e `SyncLock`. Purché il `SyncLock` istruzione è presente, il blocco di istruzioni è una sezione critica e `balance` non diventerà mai un numero negativo. È possibile impostare come commento il `SyncLock` e `End SyncLock` istruzioni per visualizzare l'effetto di escludendo il `SyncLock` (parola chiave).  
  
### <a name="code"></a>Codice  
 [!code-vb[VbVbalrThreading#21](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/synclock-statement_2.vb)]  
  
### <a name="comments"></a>Commenti  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Threading>  
 <xref:System.Threading.Monitor>  
 [Sincronizzazione di thread](../../programming-guide/concepts/threading/thread-synchronization.md)  
 [Threading](../../programming-guide/concepts/threading/index.md)
