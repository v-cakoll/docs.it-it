---
title: Istruzione SyncLock
ms.date: 07/20/2015
f1_keywords:
- vb.SyncLock
- SyncLock
helpviewer_keywords:
- threading [Visual Basic], locks
- SyncLock statement [Visual Basic]
- locks, threads
ms.assetid: 14501703-298f-4d43-b139-c4b6366af176
ms.openlocfilehash: fd932a20af274faf2b56136a94675b28399989b8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404161"
---
# <a name="synclock-statement"></a>Istruzione SyncLock
Acquisisce un blocco esclusivo per un blocco di istruzioni prima di eseguire il blocco.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
SyncLock lockobject  
    [ block ]  
End SyncLock  
```  
  
## <a name="parts"></a>Parti  
 `lockobject`  
 Obbligatorio. Espressione che restituisce un riferimento a un oggetto.  
  
 `block`  
 Facoltativa. Blocco di istruzioni da eseguire quando viene acquisito il blocco.  
  
 `End SyncLock`  
 Termina un `SyncLock` blocco.  
  
## <a name="remarks"></a>Commenti  
 L' `SyncLock` istruzione garantisce che più thread non eseguano contemporaneamente il blocco di istruzioni. `SyncLock`impedisce l'immissione del blocco da parte di ogni thread finché nessun altro thread lo esegue.  
  
 L'uso più comune di `SyncLock` è quello di proteggere i dati dall'aggiornamento simultaneo di più di un thread. Se le istruzioni che modificano i dati devono andare al completamento senza interruzioni, inserirle all'interno di un `SyncLock` blocco.  
  
 Un blocco di istruzioni protetto da un blocco esclusivo viene talvolta definito *sezione critica*.  
  
## <a name="rules"></a>Regole  
  
- Diramazione. Non è possibile eseguire il branching in un `SyncLock` blocco dall'esterno del blocco.  
  
- Valore dell'oggetto Lock. Il valore di `lockobject` non può essere `Nothing` . È necessario creare l'oggetto Lock prima di utilizzarlo in un' `SyncLock` istruzione.  
  
     Non è possibile modificare il valore di `lockobject` durante l'esecuzione di un `SyncLock` blocco. Il meccanismo richiede che l'oggetto Lock rimanga invariato.  
  
- Non è possibile usare l'operatore [await](../operators/await-operator.md) in un `SyncLock` blocco.  
  
## <a name="behavior"></a>Comportamento  
  
- Meccanismo. Quando un thread raggiunge l' `SyncLock` istruzione, valuta l' `lockobject` espressione e sospende l'esecuzione fino a quando non acquisisce un blocco esclusivo sull'oggetto restituito dall'espressione. Quando un altro thread raggiunge l' `SyncLock` istruzione, non acquisisce un blocco fino a quando il primo thread non esegue l' `End SyncLock` istruzione.  
  
- Dati protetti. Se `lockobject` è una `Shared` variabile, il blocco esclusivo impedisce a un thread in qualsiasi istanza della classe di eseguire il `SyncLock` blocco mentre un altro thread lo esegue. Questa operazione protegge i dati condivisi tra tutte le istanze.  
  
     Se `lockobject` è una variabile di istanza (non `Shared` ), il blocco impedisce a un thread in esecuzione nell'istanza corrente di eseguire il `SyncLock` blocco contemporaneamente a un altro thread nella stessa istanza. Ciò consente di proteggere i dati gestiti dalla singola istanza.  
  
- Acquisizione e rilascio. Un `SyncLock` blocco si comporta come una `Try...Finally` costruzione in cui il `Try` blocco acquisisce un blocco esclusivo su `lockobject` e il blocco lo `Finally` rilascia. Per questo motivo, il `SyncLock` blocco garantisce il rilascio del blocco, indipendentemente dal modo in cui si esce dal blocco. Questo vale anche nel caso di un'eccezione non gestita.  
  
- Chiamate del Framework. Il `SyncLock` blocco acquisisce e rilascia il blocco esclusivo chiamando i `Enter` metodi e `Exit` della `Monitor` classe nello <xref:System.Threading> spazio dei nomi.  
  
## <a name="programming-practices"></a>Procedure di programmazione  
 L' `lockobject` espressione deve sempre restituire un oggetto che appartiene esclusivamente alla classe. È necessario dichiarare una `Private` variabile oggetto per proteggere i dati appartenenti all'istanza corrente o una `Private Shared` variabile oggetto per proteggere i dati comuni a tutte le istanze.  
  
 Non utilizzare la `Me` parola chiave per fornire un oggetto Lock per i dati dell'istanza. Se il codice esterno alla classe dispone di un riferimento a un'istanza della classe, può utilizzare tale riferimento come oggetto Lock per un `SyncLock` blocco completamente diverso da quello dell'utente, proteggendo i dati diversi. In questo modo, la classe e l'altra classe potrebbero bloccarsi reciprocamente dall'esecuzione dei blocchi non correlati `SyncLock` . Analogamente, il blocco su una stringa può essere problematico perché qualsiasi altro codice nel processo che utilizza la stessa stringa condividerà lo stesso blocco.  
  
 Non è inoltre consigliabile utilizzare il `Me.GetType` metodo per fornire un oggetto Lock per i dati condivisi. Questo perché `GetType` restituisce sempre lo stesso `Type` oggetto per un nome di classe specificato. Il codice esterno può chiamare `GetType` sulla classe e ottenere lo stesso oggetto di blocco in uso. In questo modo le due classi si bloccano tra loro i `SyncLock` blocchi.  
  
## <a name="examples"></a>Esempi  
  
### <a name="description"></a>Descrizione  
 Nell'esempio seguente viene illustrata una classe che gestisce un semplice elenco di messaggi. Include i messaggi in una matrice e l'ultimo elemento usato della matrice in una variabile. La `addAnotherMessage` procedura incrementa l'ultimo elemento e archivia il nuovo messaggio. Queste due operazioni sono protette dalle `SyncLock` istruzioni e `End SyncLock` , perché una volta che l'ultimo elemento è stato incrementato, il nuovo messaggio deve essere archiviato prima che qualsiasi altro thread possa incrementare nuovamente l'ultimo elemento.  
  
 Se la `simpleMessageList` classe condivide un elenco di messaggi tra tutte le relative istanze, le variabili `messagesList` e `messagesLast` verrebbero dichiarate come `Shared` . In questo caso, la variabile `messagesLock` deve anche essere `Shared` , in modo che sia presente un singolo oggetto Lock usato da ogni istanza.  
  
### <a name="code"></a>Codice  
 [!code-vb[VbVbalrThreading#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrThreading/VB/Class1.vb#1)]  
  
### <a name="description"></a>Descrizione  
 Nell'esempio seguente vengono usati i thread e `SyncLock` . Finché l' `SyncLock` istruzione è presente, il blocco di istruzioni è una sezione critica e `balance` mai diventa un numero negativo. È possibile impostare come commento `SyncLock` le `End SyncLock` istruzioni e per vedere l'effetto dell'uscita dalla `SyncLock` parola chiave.  
  
### <a name="code"></a>Codice  
 [!code-vb[VbVbalrThreading#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrThreading/VB/class2.vb#21)]  
  
### <a name="comments"></a>Commenti  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.Interlocked?displayProperty=nameWithType>
- [Panoramica delle primitive di sincronizzazione](../../../standard/threading/overview-of-synchronization-primitives.md)
