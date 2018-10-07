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
ms.openlocfilehash: 5a931199ff8d09412d536a173f3cd12e451def64
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2018
ms.locfileid: "48845980"
---
# <a name="synclock-statement"></a><span data-ttu-id="f4546-102">Istruzione SyncLock</span><span class="sxs-lookup"><span data-stu-id="f4546-102">SyncLock Statement</span></span>
<span data-ttu-id="f4546-103">Acquisisce un blocco esclusivo per un blocco di istruzioni prima di eseguire il blocco.</span><span class="sxs-lookup"><span data-stu-id="f4546-103">Acquires an exclusive lock for a statement block before executing the block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4546-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f4546-104">Syntax</span></span>  
  
```  
SyncLock lockobject  
    [ block ]  
End SyncLock  
```  
  
## <a name="parts"></a><span data-ttu-id="f4546-105">Parti</span><span class="sxs-lookup"><span data-stu-id="f4546-105">Parts</span></span>  
 `lockobject`  
 <span data-ttu-id="f4546-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="f4546-106">Required.</span></span> <span data-ttu-id="f4546-107">Espressione che restituisce un riferimento all'oggetto.</span><span class="sxs-lookup"><span data-stu-id="f4546-107">Expression that evaluates to an object reference.</span></span>  
  
 `block`  
 <span data-ttu-id="f4546-108">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="f4546-108">Optional.</span></span> <span data-ttu-id="f4546-109">Blocco di istruzioni da eseguire quando viene acquisito il blocco.</span><span class="sxs-lookup"><span data-stu-id="f4546-109">Block of statements that are to execute when the lock is acquired.</span></span>  
  
 `End SyncLock`  
 <span data-ttu-id="f4546-110">Termina un `SyncLock` blocco.</span><span class="sxs-lookup"><span data-stu-id="f4546-110">Terminates a `SyncLock` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f4546-111">Note</span><span class="sxs-lookup"><span data-stu-id="f4546-111">Remarks</span></span>  
 <span data-ttu-id="f4546-112">Il `SyncLock` istruzione garantisce che più thread non eseguano il blocco di istruzioni nello stesso momento.</span><span class="sxs-lookup"><span data-stu-id="f4546-112">The `SyncLock` statement ensures that multiple threads do not execute the statement block at the same time.</span></span> <span data-ttu-id="f4546-113">`SyncLock` impedisce ogni thread di immettere il blocco fino a quando non viene eseguito alcun altro thread.</span><span class="sxs-lookup"><span data-stu-id="f4546-113">`SyncLock` prevents each thread from entering the block until no other thread is executing it.</span></span>  
  
 <span data-ttu-id="f4546-114">L'uso più comune di `SyncLock` consiste nel proteggere i dati vengano aggiornati da più thread contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="f4546-114">The most common use of `SyncLock` is to protect data from being updated by more than one thread simultaneously.</span></span> <span data-ttu-id="f4546-115">Se le istruzioni che modificano i dati devono andare fino al completamento senza interruzioni, inserirli all'interno di un `SyncLock` blocco.</span><span class="sxs-lookup"><span data-stu-id="f4546-115">If the statements that manipulate the data must go to completion without interruption, put them inside a `SyncLock` block.</span></span>  
  
 <span data-ttu-id="f4546-116">Un blocco di istruzioni protetto da un blocco esclusivo viene a volte chiamato un *sezione critica*.</span><span class="sxs-lookup"><span data-stu-id="f4546-116">A statement block protected by an exclusive lock is sometimes called a *critical section*.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="f4546-117">Regole</span><span class="sxs-lookup"><span data-stu-id="f4546-117">Rules</span></span>  
  
-   <span data-ttu-id="f4546-118">Creazione di rami.</span><span class="sxs-lookup"><span data-stu-id="f4546-118">Branching.</span></span> <span data-ttu-id="f4546-119">È possibile creare rami in un `SyncLock` impedisce all'esterno del blocco.</span><span class="sxs-lookup"><span data-stu-id="f4546-119">You cannot branch into a `SyncLock` block from outside the block.</span></span>  
  
-   <span data-ttu-id="f4546-120">Valore dell'oggetto di blocco.</span><span class="sxs-lookup"><span data-stu-id="f4546-120">Lock Object Value.</span></span> <span data-ttu-id="f4546-121">Il valore di `lockobject` non può essere `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="f4546-121">The value of `lockobject` cannot be `Nothing`.</span></span> <span data-ttu-id="f4546-122">È necessario creare l'oggetto di blocco prima di usarla in un `SyncLock` istruzione.</span><span class="sxs-lookup"><span data-stu-id="f4546-122">You must create the lock object before you use it in a `SyncLock` statement.</span></span>  
  
     <span data-ttu-id="f4546-123">Non è possibile modificare il valore di `lockobject` durante l'esecuzione di un `SyncLock` blocco.</span><span class="sxs-lookup"><span data-stu-id="f4546-123">You cannot change the value of `lockobject` while executing a `SyncLock` block.</span></span> <span data-ttu-id="f4546-124">Il meccanismo di richiede che l'oggetto blocco rimangono invariati.</span><span class="sxs-lookup"><span data-stu-id="f4546-124">The mechanism requires that the lock object remain unchanged.</span></span>  
  
-   <span data-ttu-id="f4546-125">Non è possibile usare la [Await](../../../visual-basic/language-reference/operators/await-operator.md) operatore in un `SyncLock` blocco.</span><span class="sxs-lookup"><span data-stu-id="f4546-125">You can't use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in a `SyncLock` block.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="f4546-126">Comportamento</span><span class="sxs-lookup"><span data-stu-id="f4546-126">Behavior</span></span>  
  
-   <span data-ttu-id="f4546-127">Meccanismo.</span><span class="sxs-lookup"><span data-stu-id="f4546-127">Mechanism.</span></span> <span data-ttu-id="f4546-128">Quando un thread raggiunge la `SyncLock` istruzione, viene restituito il `lockobject` espressione e sospende l'esecuzione fino a quando non acquisisce un blocco esclusivo sull'oggetto restituito dall'espressione.</span><span class="sxs-lookup"><span data-stu-id="f4546-128">When a thread reaches the `SyncLock` statement, it evaluates the `lockobject` expression and suspends execution until it acquires an exclusive lock on the object returned by the expression.</span></span> <span data-ttu-id="f4546-129">Quando un altro thread raggiunge la `SyncLock` istruzione, non acquisisce un blocco fino a quando non viene eseguito il primo thread la `End SyncLock` istruzione.</span><span class="sxs-lookup"><span data-stu-id="f4546-129">When another thread reaches the `SyncLock` statement, it does not acquire a lock until the first thread executes the `End SyncLock` statement.</span></span>  
  
-   <span data-ttu-id="f4546-130">Dati protetti.</span><span class="sxs-lookup"><span data-stu-id="f4546-130">Protected Data.</span></span> <span data-ttu-id="f4546-131">Se `lockobject` è un `Shared` variabile, il blocco esclusivo impedisce a un thread in qualsiasi istanza della classe dall'esecuzione di `SyncLock` bloccarsi mentre viene eseguito un altro thread.</span><span class="sxs-lookup"><span data-stu-id="f4546-131">If `lockobject` is a `Shared` variable, the exclusive lock prevents a thread in any instance of the class from executing the `SyncLock` block while any other thread is executing it.</span></span> <span data-ttu-id="f4546-132">Consente di proteggere i dati condivisi fra tutte le istanze.</span><span class="sxs-lookup"><span data-stu-id="f4546-132">This protects data that is shared among all the instances.</span></span>  
  
     <span data-ttu-id="f4546-133">Se `lockobject` è una variabile di istanza (non `Shared`), il blocco impedisce a un thread in esecuzione nell'istanza corrente di eseguire il `SyncLock` blocco allo stesso tempo come un altro thread nella stessa istanza.</span><span class="sxs-lookup"><span data-stu-id="f4546-133">If `lockobject` is an instance variable (not `Shared`), the lock prevents a thread running in the current instance from executing the `SyncLock` block at the same time as another thread in the same instance.</span></span> <span data-ttu-id="f4546-134">Ciò consente di proteggere dati gestiti da istanza singola.</span><span class="sxs-lookup"><span data-stu-id="f4546-134">This protects data maintained by the individual instance.</span></span>  
  
-   <span data-ttu-id="f4546-135">Acquisizione e il rilascio.</span><span class="sxs-lookup"><span data-stu-id="f4546-135">Acquisition and Release.</span></span> <span data-ttu-id="f4546-136">Oggetto `SyncLock` blocco si comporta come un `Try...Finally` costruzione in cui le `Try` blocco acquisisce un blocco esclusivo sul `lockobject` e il `Finally` lo rilascia blocco.</span><span class="sxs-lookup"><span data-stu-id="f4546-136">A `SyncLock` block behaves like a `Try...Finally` construction in which the `Try` block acquires an exclusive lock on `lockobject` and the `Finally` block releases it.</span></span> <span data-ttu-id="f4546-137">Per questo motivo, il `SyncLock` garantisce il rilascio del blocco, indipendentemente dal modo in cui si esce dal blocco.</span><span class="sxs-lookup"><span data-stu-id="f4546-137">Because of this, the `SyncLock` block guarantees release of the lock, no matter how you exit the block.</span></span> <span data-ttu-id="f4546-138">Questo vale anche in caso di un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="f4546-138">This is true even in the case of an unhandled exception.</span></span>  
  
-   <span data-ttu-id="f4546-139">Chiamate di Framework.</span><span class="sxs-lookup"><span data-stu-id="f4546-139">Framework Calls.</span></span> <span data-ttu-id="f4546-140">Il `SyncLock` blocco acquisisce e rilascia il blocco esclusivo chiamando il `Enter` e `Exit` metodi del `Monitor` classe la <xref:System.Threading> dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="f4546-140">The `SyncLock` block acquires and releases the exclusive lock by calling the `Enter` and `Exit` methods of the `Monitor` class in the <xref:System.Threading> namespace.</span></span>  
  
## <a name="programming-practices"></a><span data-ttu-id="f4546-141">Procedure consigliate di programmazione</span><span class="sxs-lookup"><span data-stu-id="f4546-141">Programming Practices</span></span>  
 <span data-ttu-id="f4546-142">Il `lockobject` espressione deve sempre restituire un oggetto a cui appartiene esclusivamente alla classe.</span><span class="sxs-lookup"><span data-stu-id="f4546-142">The `lockobject` expression should always evaluate to an object that belongs exclusively to your class.</span></span> <span data-ttu-id="f4546-143">È necessario dichiarare un `Private` variabile di oggetto per proteggere i dati appartenenti all'istanza corrente, o un `Private Shared` variabile oggetto per proteggere i dati comuni a tutte le istanze.</span><span class="sxs-lookup"><span data-stu-id="f4546-143">You should declare a `Private` object variable to protect data belonging to the current instance, or a `Private Shared` object variable to protect data common to all instances.</span></span>  
  
 <span data-ttu-id="f4546-144">È consigliabile non usare il `Me` (parola chiave) per fornire un blocco di dati dell'oggetto, ad esempio.</span><span class="sxs-lookup"><span data-stu-id="f4546-144">You should not use the `Me` keyword to provide a lock object for instance data.</span></span> <span data-ttu-id="f4546-145">Se il codice esterno alla classe ha un riferimento a un'istanza della classe, è Impossibile utilizzare il riferimento come un oggetto di blocco per un `SyncLock` blocco completamente diversa da quelle in uso, protezione dei dati diversi.</span><span class="sxs-lookup"><span data-stu-id="f4546-145">If code external to your class has a reference to an instance of your class, it could use that reference as a lock object for a `SyncLock` block completely different from yours, protecting different data.</span></span> <span data-ttu-id="f4546-146">In questo modo, la classe e l'altra classe può bloccare loro l'esecuzione di loro non correlati `SyncLock` blocchi.</span><span class="sxs-lookup"><span data-stu-id="f4546-146">In this way, your class and the other class could block each other from executing their unrelated `SyncLock` blocks.</span></span> <span data-ttu-id="f4546-147">Analogamente, il blocco su una stringa può essere problematico perché qualsiasi altro codice nel processo che usa la stessa stringa condividerà lo stesso blocco.</span><span class="sxs-lookup"><span data-stu-id="f4546-147">Similarly locking on a string can be problematic since any other code in the process using the same string will share the same lock.</span></span>  
  
 <span data-ttu-id="f4546-148">È inoltre consigliabile non utilizzare il `Me.GetType` metodo per fornire un oggetto di blocco per i dati condivisi.</span><span class="sxs-lookup"><span data-stu-id="f4546-148">You should also not use the `Me.GetType` method to provide a lock object for shared data.</span></span> <span data-ttu-id="f4546-149">Infatti `GetType` restituisce sempre lo stesso `Type` oggetto per un determinato nome di classe.</span><span class="sxs-lookup"><span data-stu-id="f4546-149">This is because `GetType` always returns the same `Type` object for a given class name.</span></span> <span data-ttu-id="f4546-150">Impossibile chiamare codice esterno `GetType` nella classe e ottenere lo stesso oggetto di blocco in uso.</span><span class="sxs-lookup"><span data-stu-id="f4546-150">External code could call `GetType` on your class and obtain the same lock object you are using.</span></span> <span data-ttu-id="f4546-151">In questo modo, le due classi di blocco tra loro da loro `SyncLock` blocchi.</span><span class="sxs-lookup"><span data-stu-id="f4546-151">This would result in the two classes blocking each other from their `SyncLock` blocks.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="f4546-152">Esempi</span><span class="sxs-lookup"><span data-stu-id="f4546-152">Examples</span></span>  
  
### <a name="description"></a><span data-ttu-id="f4546-153">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f4546-153">Description</span></span>  
 <span data-ttu-id="f4546-154">Nell'esempio seguente viene illustrata una classe che gestisce un elenco semplice di messaggi.</span><span class="sxs-lookup"><span data-stu-id="f4546-154">The following example shows a class that maintains a simple list of messages.</span></span> <span data-ttu-id="f4546-155">Contiene i messaggi in una matrice e l'ultimo elemento della matrice di utilizzato in una variabile.</span><span class="sxs-lookup"><span data-stu-id="f4546-155">It holds the messages in an array and the last used element of that array in a variable.</span></span> <span data-ttu-id="f4546-156">Il `addAnotherMessage` procedure incrementa l'ultimo elemento e archivia il nuovo messaggio.</span><span class="sxs-lookup"><span data-stu-id="f4546-156">The `addAnotherMessage` procedure increments the last element and stores the new message.</span></span> <span data-ttu-id="f4546-157">Queste due operazioni sono protetti dal `SyncLock` e `End SyncLock` (istruzioni), poiché dopo l'ultimo elemento è stato incrementato, il nuovo messaggio deve essere archiviato prima di qualsiasi altro thread può incrementare nuovamente l'ultimo elemento.</span><span class="sxs-lookup"><span data-stu-id="f4546-157">Those two operations are protected by the `SyncLock` and `End SyncLock` statements, because once the last element has been incremented, the new message must be stored before any other thread can increment the last element again.</span></span>  
  
 <span data-ttu-id="f4546-158">Se il `simpleMessageList` classe condivisa un elenco di messaggi tra tutte le istanze, le variabili `messagesList` e `messagesLast` sarebbe dichiarata come `Shared`.</span><span class="sxs-lookup"><span data-stu-id="f4546-158">If the `simpleMessageList` class shared one list of messages among all its instances, the variables `messagesList` and `messagesLast` would be declared as `Shared`.</span></span> <span data-ttu-id="f4546-159">In questo caso, la variabile `messagesLock` deve essere anche `Shared`, in modo che non vi sarà un unico oggetto blocco usato da ogni istanza.</span><span class="sxs-lookup"><span data-stu-id="f4546-159">In this case, the variable `messagesLock` should also be `Shared`, so that there would be a single lock object used by every instance.</span></span>  
  
### <a name="code"></a><span data-ttu-id="f4546-160">Codice</span><span class="sxs-lookup"><span data-stu-id="f4546-160">Code</span></span>  
 [!code-vb[VbVbalrThreading#1](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/synclock-statement_1.vb)]  
  
### <a name="description"></a><span data-ttu-id="f4546-161">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f4546-161">Description</span></span>  
 <span data-ttu-id="f4546-162">L'esempio seguente usa i thread e `SyncLock`.</span><span class="sxs-lookup"><span data-stu-id="f4546-162">The following example uses threads and `SyncLock`.</span></span> <span data-ttu-id="f4546-163">Fino a quando la `SyncLock` istruzione è presente, il blocco di istruzioni è una sezione critica e `balance` non diventerà mai un numero negativo.</span><span class="sxs-lookup"><span data-stu-id="f4546-163">As long as the `SyncLock` statement is present, the statement block is a critical section and `balance` never becomes a negative number.</span></span> <span data-ttu-id="f4546-164">È possibile impostare come commento il `SyncLock` e `End SyncLock` istruzioni per visualizzare l'effetto dell'omissione di `SyncLock` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="f4546-164">You can comment out the `SyncLock` and `End SyncLock` statements to see the effect of leaving out the `SyncLock` keyword.</span></span>  
  
### <a name="code"></a><span data-ttu-id="f4546-165">Codice</span><span class="sxs-lookup"><span data-stu-id="f4546-165">Code</span></span>  
 [!code-vb[VbVbalrThreading#21](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/synclock-statement_2.vb)]  
  
### <a name="comments"></a><span data-ttu-id="f4546-166">Commenti</span><span class="sxs-lookup"><span data-stu-id="f4546-166">Comments</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4546-167">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4546-167">See also</span></span>

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.Interlocked?displayProperty=nameWithType>
- [<span data-ttu-id="f4546-168">Cenni preliminari sulle primitive di sincronizzazione</span><span class="sxs-lookup"><span data-stu-id="f4546-168">Overview of synchronization primitives</span></span>](../../../standard/threading/overview-of-synchronization-primitives.md)
