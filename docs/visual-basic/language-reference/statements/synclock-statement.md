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
ms.openlocfilehash: 0f430edce99513b0de9ef437d70648a128b336b8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352812"
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
 Obbligatoria. Espressione che restituisce un riferimento a un oggetto.  
  
 `block`  
 Facoltativa. Blocco di istruzioni da eseguire quando viene acquisito il blocco.  
  
 `End SyncLock`  
 Termina un blocco di `SyncLock`.  
  
## <a name="remarks"></a>Osservazioni  
 L'istruzione `SyncLock` garantisce che più thread non eseguano contemporaneamente il blocco di istruzioni. `SyncLock` impedisce l'immissione del blocco da parte di ogni thread finché nessun altro thread lo esegue.  
  
 L'uso più comune di `SyncLock` consiste nel proteggere i dati dall'aggiornamento simultaneo di più di un thread. Se le istruzioni che modificano i dati devono andare al completamento senza interruzioni, inserirle all'interno di un blocco di `SyncLock`.  
  
 Un blocco di istruzioni protetto da un blocco esclusivo viene talvolta definito *sezione critica*.  
  
## <a name="rules"></a>Regole  
  
- Diramazione. Non è possibile creare un ramo in un blocco `SyncLock` dall'esterno del blocco.  
  
- Valore dell'oggetto Lock. Il valore di `lockobject` non può essere `Nothing`. È necessario creare l'oggetto Lock prima di utilizzarlo in un'istruzione `SyncLock`.  
  
     Non è possibile modificare il valore di `lockobject` durante l'esecuzione di un blocco di `SyncLock`. Il meccanismo richiede che l'oggetto Lock rimanga invariato.  
  
- Non è possibile usare l'operatore [await](../../../visual-basic/language-reference/operators/await-operator.md) in un blocco `SyncLock`.  
  
## <a name="behavior"></a>Comportamento  
  
- Meccanismo. Quando un thread raggiunge l'istruzione `SyncLock`, valuta l'espressione `lockobject` e sospende l'esecuzione fino a quando non acquisisce un blocco esclusivo sull'oggetto restituito dall'espressione. Quando un altro thread raggiunge l'istruzione `SyncLock`, non acquisisce un blocco fino a quando il primo thread non esegue l'istruzione `End SyncLock`.  
  
- Dati protetti. Se `lockobject` è una variabile `Shared`, il blocco esclusivo impedisce a un thread in qualsiasi istanza della classe di eseguire il blocco `SyncLock` mentre un altro thread lo esegue. Questa operazione protegge i dati condivisi tra tutte le istanze.  
  
     Se `lockobject` è una variabile di istanza (non `Shared`), il blocco impedisce a un thread in esecuzione nell'istanza corrente di eseguire il blocco `SyncLock` nello stesso momento in cui si trova un altro thread nella stessa istanza. Ciò consente di proteggere i dati gestiti dalla singola istanza.  
  
- Acquisizione e rilascio. Un blocco di `SyncLock` si comporta come una costruzione di `Try...Finally` in cui il blocco `Try` acquisisce un blocco esclusivo su `lockobject` e il blocco di `Finally` lo rilascia. Per questo motivo, il blocco `SyncLock` garantisce il rilascio del blocco, indipendentemente dal modo in cui si esce dal blocco. Questo vale anche nel caso di un'eccezione non gestita.  
  
- Chiamate del Framework. Il blocco `SyncLock` acquisisce e rilascia il blocco esclusivo chiamando i metodi `Enter` e `Exit` della classe `Monitor` nello spazio dei nomi <xref:System.Threading>.  
  
## <a name="programming-practices"></a>Procedure di programmazione  
 L'espressione `lockobject` deve sempre restituire un oggetto che appartiene esclusivamente alla classe. È necessario dichiarare un `Private` variabile oggetto per proteggere i dati appartenenti all'istanza corrente o una variabile oggetto `Private Shared` per proteggere i dati comuni a tutte le istanze.  
  
 Non utilizzare la parola chiave `Me` per fornire un oggetto Lock per i dati dell'istanza. Se il codice esterno alla classe dispone di un riferimento a un'istanza della classe, può utilizzare tale riferimento come oggetto Lock per un blocco di `SyncLock` completamente diverso da quello dell'utente, proteggendo i dati diversi. In questo modo, la classe e l'altra classe potrebbero bloccarsi reciprocamente eseguendo i blocchi di `SyncLock` non correlati. Analogamente, il blocco su una stringa può essere problematico perché qualsiasi altro codice nel processo che utilizza la stessa stringa condividerà lo stesso blocco.  
  
 È inoltre consigliabile non utilizzare il metodo `Me.GetType` per fornire un oggetto Lock per i dati condivisi. Questo perché `GetType` restituisce sempre lo stesso oggetto `Type` per un nome di classe specificato. Il codice esterno può chiamare `GetType` sulla classe e ottenere lo stesso oggetto di blocco in uso. In questo modo le due classi si bloccano tra loro `SyncLock` blocchi.  
  
## <a name="examples"></a>Esempi  
  
### <a name="description"></a>Descrizione  
 Nell'esempio seguente viene illustrata una classe che gestisce un semplice elenco di messaggi. Include i messaggi in una matrice e l'ultimo elemento usato della matrice in una variabile. Con la procedura `addAnotherMessage` viene incrementato l'ultimo elemento e viene archiviato il nuovo messaggio. Queste due operazioni sono protette dalle istruzioni `SyncLock` e `End SyncLock`, perché una volta che l'ultimo elemento è stato incrementato, il nuovo messaggio deve essere archiviato prima che qualsiasi altro thread possa incrementare nuovamente l'ultimo elemento.  
  
 Se la classe `simpleMessageList` condivide un elenco di messaggi tra tutte le relative istanze, le variabili `messagesList` e `messagesLast` verrebbero dichiarate come `Shared`. In questo caso, la variabile `messagesLock` deve anche essere `Shared`, in modo che sia presente un singolo oggetto Lock usato da ogni istanza.  
  
### <a name="code"></a>Codice  
 [!code-vb[VbVbalrThreading#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrThreading/VB/Class1.vb#1)]  
  
### <a name="description"></a>Descrizione  
 Nell'esempio seguente vengono usati i thread e `SyncLock`. Fino a quando l'istruzione `SyncLock` è presente, il blocco di istruzioni è una sezione critica e `balance` non diventa mai un numero negativo. È possibile impostare come commento le istruzioni `SyncLock` e `End SyncLock` per vedere l'effetto di uscire dalla parola chiave `SyncLock`.  
  
### <a name="code"></a>Codice  
 [!code-vb[VbVbalrThreading#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrThreading/VB/class2.vb#21)]  
  
### <a name="comments"></a>Commenti  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.Interlocked?displayProperty=nameWithType>
- [Cenni preliminari sulle primitive di sincronizzazione](../../../standard/threading/overview-of-synchronization-primitives.md)
