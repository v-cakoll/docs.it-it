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
# <a name="synclock-statement"></a><span data-ttu-id="04e59-102">Istruzione SyncLock</span><span class="sxs-lookup"><span data-stu-id="04e59-102">SyncLock Statement</span></span>
<span data-ttu-id="04e59-103">Acquisisce un blocco esclusivo per un blocco di istruzioni prima di eseguire il blocco.</span><span class="sxs-lookup"><span data-stu-id="04e59-103">Acquires an exclusive lock for a statement block before executing the block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04e59-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="04e59-104">Syntax</span></span>  
  
```vb  
SyncLock lockobject  
    [ block ]  
End SyncLock  
```  
  
## <a name="parts"></a><span data-ttu-id="04e59-105">Parti</span><span class="sxs-lookup"><span data-stu-id="04e59-105">Parts</span></span>  
 `lockobject`  
 <span data-ttu-id="04e59-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="04e59-106">Required.</span></span> <span data-ttu-id="04e59-107">Espressione che restituisce un riferimento a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="04e59-107">Expression that evaluates to an object reference.</span></span>  
  
 `block`  
 <span data-ttu-id="04e59-108">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="04e59-108">Optional.</span></span> <span data-ttu-id="04e59-109">Blocco di istruzioni da eseguire quando viene acquisito il blocco.</span><span class="sxs-lookup"><span data-stu-id="04e59-109">Block of statements that are to execute when the lock is acquired.</span></span>  
  
 `End SyncLock`  
 <span data-ttu-id="04e59-110">Termina un `SyncLock` blocco.</span><span class="sxs-lookup"><span data-stu-id="04e59-110">Terminates a `SyncLock` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04e59-111">Commenti</span><span class="sxs-lookup"><span data-stu-id="04e59-111">Remarks</span></span>  
 <span data-ttu-id="04e59-112">L' `SyncLock` istruzione garantisce che più thread non eseguano contemporaneamente il blocco di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="04e59-112">The `SyncLock` statement ensures that multiple threads do not execute the statement block at the same time.</span></span> <span data-ttu-id="04e59-113">`SyncLock`impedisce l'immissione del blocco da parte di ogni thread finché nessun altro thread lo esegue.</span><span class="sxs-lookup"><span data-stu-id="04e59-113">`SyncLock` prevents each thread from entering the block until no other thread is executing it.</span></span>  
  
 <span data-ttu-id="04e59-114">L'uso più comune di `SyncLock` è quello di proteggere i dati dall'aggiornamento simultaneo di più di un thread.</span><span class="sxs-lookup"><span data-stu-id="04e59-114">The most common use of `SyncLock` is to protect data from being updated by more than one thread simultaneously.</span></span> <span data-ttu-id="04e59-115">Se le istruzioni che modificano i dati devono andare al completamento senza interruzioni, inserirle all'interno di un `SyncLock` blocco.</span><span class="sxs-lookup"><span data-stu-id="04e59-115">If the statements that manipulate the data must go to completion without interruption, put them inside a `SyncLock` block.</span></span>  
  
 <span data-ttu-id="04e59-116">Un blocco di istruzioni protetto da un blocco esclusivo viene talvolta definito *sezione critica*.</span><span class="sxs-lookup"><span data-stu-id="04e59-116">A statement block protected by an exclusive lock is sometimes called a *critical section*.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="04e59-117">Regole</span><span class="sxs-lookup"><span data-stu-id="04e59-117">Rules</span></span>  
  
- <span data-ttu-id="04e59-118">Diramazione.</span><span class="sxs-lookup"><span data-stu-id="04e59-118">Branching.</span></span> <span data-ttu-id="04e59-119">Non è possibile eseguire il branching in un `SyncLock` blocco dall'esterno del blocco.</span><span class="sxs-lookup"><span data-stu-id="04e59-119">You cannot branch into a `SyncLock` block from outside the block.</span></span>  
  
- <span data-ttu-id="04e59-120">Valore dell'oggetto Lock.</span><span class="sxs-lookup"><span data-stu-id="04e59-120">Lock Object Value.</span></span> <span data-ttu-id="04e59-121">Il valore di `lockobject` non può essere `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="04e59-121">The value of `lockobject` cannot be `Nothing`.</span></span> <span data-ttu-id="04e59-122">È necessario creare l'oggetto Lock prima di utilizzarlo in un' `SyncLock` istruzione.</span><span class="sxs-lookup"><span data-stu-id="04e59-122">You must create the lock object before you use it in a `SyncLock` statement.</span></span>  
  
     <span data-ttu-id="04e59-123">Non è possibile modificare il valore di `lockobject` durante l'esecuzione di un `SyncLock` blocco.</span><span class="sxs-lookup"><span data-stu-id="04e59-123">You cannot change the value of `lockobject` while executing a `SyncLock` block.</span></span> <span data-ttu-id="04e59-124">Il meccanismo richiede che l'oggetto Lock rimanga invariato.</span><span class="sxs-lookup"><span data-stu-id="04e59-124">The mechanism requires that the lock object remain unchanged.</span></span>  
  
- <span data-ttu-id="04e59-125">Non è possibile usare l'operatore [await](../operators/await-operator.md) in un `SyncLock` blocco.</span><span class="sxs-lookup"><span data-stu-id="04e59-125">You can't use the [Await](../operators/await-operator.md) operator in a `SyncLock` block.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="04e59-126">Comportamento</span><span class="sxs-lookup"><span data-stu-id="04e59-126">Behavior</span></span>  
  
- <span data-ttu-id="04e59-127">Meccanismo.</span><span class="sxs-lookup"><span data-stu-id="04e59-127">Mechanism.</span></span> <span data-ttu-id="04e59-128">Quando un thread raggiunge l' `SyncLock` istruzione, valuta l' `lockobject` espressione e sospende l'esecuzione fino a quando non acquisisce un blocco esclusivo sull'oggetto restituito dall'espressione.</span><span class="sxs-lookup"><span data-stu-id="04e59-128">When a thread reaches the `SyncLock` statement, it evaluates the `lockobject` expression and suspends execution until it acquires an exclusive lock on the object returned by the expression.</span></span> <span data-ttu-id="04e59-129">Quando un altro thread raggiunge l' `SyncLock` istruzione, non acquisisce un blocco fino a quando il primo thread non esegue l' `End SyncLock` istruzione.</span><span class="sxs-lookup"><span data-stu-id="04e59-129">When another thread reaches the `SyncLock` statement, it does not acquire a lock until the first thread executes the `End SyncLock` statement.</span></span>  
  
- <span data-ttu-id="04e59-130">Dati protetti.</span><span class="sxs-lookup"><span data-stu-id="04e59-130">Protected Data.</span></span> <span data-ttu-id="04e59-131">Se `lockobject` è una `Shared` variabile, il blocco esclusivo impedisce a un thread in qualsiasi istanza della classe di eseguire il `SyncLock` blocco mentre un altro thread lo esegue.</span><span class="sxs-lookup"><span data-stu-id="04e59-131">If `lockobject` is a `Shared` variable, the exclusive lock prevents a thread in any instance of the class from executing the `SyncLock` block while any other thread is executing it.</span></span> <span data-ttu-id="04e59-132">Questa operazione protegge i dati condivisi tra tutte le istanze.</span><span class="sxs-lookup"><span data-stu-id="04e59-132">This protects data that is shared among all the instances.</span></span>  
  
     <span data-ttu-id="04e59-133">Se `lockobject` è una variabile di istanza (non `Shared` ), il blocco impedisce a un thread in esecuzione nell'istanza corrente di eseguire il `SyncLock` blocco contemporaneamente a un altro thread nella stessa istanza.</span><span class="sxs-lookup"><span data-stu-id="04e59-133">If `lockobject` is an instance variable (not `Shared`), the lock prevents a thread running in the current instance from executing the `SyncLock` block at the same time as another thread in the same instance.</span></span> <span data-ttu-id="04e59-134">Ciò consente di proteggere i dati gestiti dalla singola istanza.</span><span class="sxs-lookup"><span data-stu-id="04e59-134">This protects data maintained by the individual instance.</span></span>  
  
- <span data-ttu-id="04e59-135">Acquisizione e rilascio.</span><span class="sxs-lookup"><span data-stu-id="04e59-135">Acquisition and Release.</span></span> <span data-ttu-id="04e59-136">Un `SyncLock` blocco si comporta come una `Try...Finally` costruzione in cui il `Try` blocco acquisisce un blocco esclusivo su `lockobject` e il blocco lo `Finally` rilascia.</span><span class="sxs-lookup"><span data-stu-id="04e59-136">A `SyncLock` block behaves like a `Try...Finally` construction in which the `Try` block acquires an exclusive lock on `lockobject` and the `Finally` block releases it.</span></span> <span data-ttu-id="04e59-137">Per questo motivo, il `SyncLock` blocco garantisce il rilascio del blocco, indipendentemente dal modo in cui si esce dal blocco.</span><span class="sxs-lookup"><span data-stu-id="04e59-137">Because of this, the `SyncLock` block guarantees release of the lock, no matter how you exit the block.</span></span> <span data-ttu-id="04e59-138">Questo vale anche nel caso di un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="04e59-138">This is true even in the case of an unhandled exception.</span></span>  
  
- <span data-ttu-id="04e59-139">Chiamate del Framework.</span><span class="sxs-lookup"><span data-stu-id="04e59-139">Framework Calls.</span></span> <span data-ttu-id="04e59-140">Il `SyncLock` blocco acquisisce e rilascia il blocco esclusivo chiamando i `Enter` metodi e `Exit` della `Monitor` classe nello <xref:System.Threading> spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="04e59-140">The `SyncLock` block acquires and releases the exclusive lock by calling the `Enter` and `Exit` methods of the `Monitor` class in the <xref:System.Threading> namespace.</span></span>  
  
## <a name="programming-practices"></a><span data-ttu-id="04e59-141">Procedure di programmazione</span><span class="sxs-lookup"><span data-stu-id="04e59-141">Programming Practices</span></span>  
 <span data-ttu-id="04e59-142">L' `lockobject` espressione deve sempre restituire un oggetto che appartiene esclusivamente alla classe.</span><span class="sxs-lookup"><span data-stu-id="04e59-142">The `lockobject` expression should always evaluate to an object that belongs exclusively to your class.</span></span> <span data-ttu-id="04e59-143">È necessario dichiarare una `Private` variabile oggetto per proteggere i dati appartenenti all'istanza corrente o una `Private Shared` variabile oggetto per proteggere i dati comuni a tutte le istanze.</span><span class="sxs-lookup"><span data-stu-id="04e59-143">You should declare a `Private` object variable to protect data belonging to the current instance, or a `Private Shared` object variable to protect data common to all instances.</span></span>  
  
 <span data-ttu-id="04e59-144">Non utilizzare la `Me` parola chiave per fornire un oggetto Lock per i dati dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="04e59-144">You should not use the `Me` keyword to provide a lock object for instance data.</span></span> <span data-ttu-id="04e59-145">Se il codice esterno alla classe dispone di un riferimento a un'istanza della classe, può utilizzare tale riferimento come oggetto Lock per un `SyncLock` blocco completamente diverso da quello dell'utente, proteggendo i dati diversi.</span><span class="sxs-lookup"><span data-stu-id="04e59-145">If code external to your class has a reference to an instance of your class, it could use that reference as a lock object for a `SyncLock` block completely different from yours, protecting different data.</span></span> <span data-ttu-id="04e59-146">In questo modo, la classe e l'altra classe potrebbero bloccarsi reciprocamente dall'esecuzione dei blocchi non correlati `SyncLock` .</span><span class="sxs-lookup"><span data-stu-id="04e59-146">In this way, your class and the other class could block each other from executing their unrelated `SyncLock` blocks.</span></span> <span data-ttu-id="04e59-147">Analogamente, il blocco su una stringa può essere problematico perché qualsiasi altro codice nel processo che utilizza la stessa stringa condividerà lo stesso blocco.</span><span class="sxs-lookup"><span data-stu-id="04e59-147">Similarly locking on a string can be problematic since any other code in the process using the same string will share the same lock.</span></span>  
  
 <span data-ttu-id="04e59-148">Non è inoltre consigliabile utilizzare il `Me.GetType` metodo per fornire un oggetto Lock per i dati condivisi.</span><span class="sxs-lookup"><span data-stu-id="04e59-148">You should also not use the `Me.GetType` method to provide a lock object for shared data.</span></span> <span data-ttu-id="04e59-149">Questo perché `GetType` restituisce sempre lo stesso `Type` oggetto per un nome di classe specificato.</span><span class="sxs-lookup"><span data-stu-id="04e59-149">This is because `GetType` always returns the same `Type` object for a given class name.</span></span> <span data-ttu-id="04e59-150">Il codice esterno può chiamare `GetType` sulla classe e ottenere lo stesso oggetto di blocco in uso.</span><span class="sxs-lookup"><span data-stu-id="04e59-150">External code could call `GetType` on your class and obtain the same lock object you are using.</span></span> <span data-ttu-id="04e59-151">In questo modo le due classi si bloccano tra loro i `SyncLock` blocchi.</span><span class="sxs-lookup"><span data-stu-id="04e59-151">This would result in the two classes blocking each other from their `SyncLock` blocks.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="04e59-152">Esempi</span><span class="sxs-lookup"><span data-stu-id="04e59-152">Examples</span></span>  
  
### <a name="description"></a><span data-ttu-id="04e59-153">Descrizione</span><span class="sxs-lookup"><span data-stu-id="04e59-153">Description</span></span>  
 <span data-ttu-id="04e59-154">Nell'esempio seguente viene illustrata una classe che gestisce un semplice elenco di messaggi.</span><span class="sxs-lookup"><span data-stu-id="04e59-154">The following example shows a class that maintains a simple list of messages.</span></span> <span data-ttu-id="04e59-155">Include i messaggi in una matrice e l'ultimo elemento usato della matrice in una variabile.</span><span class="sxs-lookup"><span data-stu-id="04e59-155">It holds the messages in an array and the last used element of that array in a variable.</span></span> <span data-ttu-id="04e59-156">La `addAnotherMessage` procedura incrementa l'ultimo elemento e archivia il nuovo messaggio.</span><span class="sxs-lookup"><span data-stu-id="04e59-156">The `addAnotherMessage` procedure increments the last element and stores the new message.</span></span> <span data-ttu-id="04e59-157">Queste due operazioni sono protette dalle `SyncLock` istruzioni e `End SyncLock` , perché una volta che l'ultimo elemento è stato incrementato, il nuovo messaggio deve essere archiviato prima che qualsiasi altro thread possa incrementare nuovamente l'ultimo elemento.</span><span class="sxs-lookup"><span data-stu-id="04e59-157">Those two operations are protected by the `SyncLock` and `End SyncLock` statements, because once the last element has been incremented, the new message must be stored before any other thread can increment the last element again.</span></span>  
  
 <span data-ttu-id="04e59-158">Se la `simpleMessageList` classe condivide un elenco di messaggi tra tutte le relative istanze, le variabili `messagesList` e `messagesLast` verrebbero dichiarate come `Shared` .</span><span class="sxs-lookup"><span data-stu-id="04e59-158">If the `simpleMessageList` class shared one list of messages among all its instances, the variables `messagesList` and `messagesLast` would be declared as `Shared`.</span></span> <span data-ttu-id="04e59-159">In questo caso, la variabile `messagesLock` deve anche essere `Shared` , in modo che sia presente un singolo oggetto Lock usato da ogni istanza.</span><span class="sxs-lookup"><span data-stu-id="04e59-159">In this case, the variable `messagesLock` should also be `Shared`, so that there would be a single lock object used by every instance.</span></span>  
  
### <a name="code"></a><span data-ttu-id="04e59-160">Codice</span><span class="sxs-lookup"><span data-stu-id="04e59-160">Code</span></span>  
 [!code-vb[VbVbalrThreading#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrThreading/VB/Class1.vb#1)]  
  
### <a name="description"></a><span data-ttu-id="04e59-161">Descrizione</span><span class="sxs-lookup"><span data-stu-id="04e59-161">Description</span></span>  
 <span data-ttu-id="04e59-162">Nell'esempio seguente vengono usati i thread e `SyncLock` .</span><span class="sxs-lookup"><span data-stu-id="04e59-162">The following example uses threads and `SyncLock`.</span></span> <span data-ttu-id="04e59-163">Finché l' `SyncLock` istruzione è presente, il blocco di istruzioni è una sezione critica e `balance` mai diventa un numero negativo.</span><span class="sxs-lookup"><span data-stu-id="04e59-163">As long as the `SyncLock` statement is present, the statement block is a critical section and `balance` never becomes a negative number.</span></span> <span data-ttu-id="04e59-164">È possibile impostare come commento `SyncLock` le `End SyncLock` istruzioni e per vedere l'effetto dell'uscita dalla `SyncLock` parola chiave.</span><span class="sxs-lookup"><span data-stu-id="04e59-164">You can comment out the `SyncLock` and `End SyncLock` statements to see the effect of leaving out the `SyncLock` keyword.</span></span>  
  
### <a name="code"></a><span data-ttu-id="04e59-165">Codice</span><span class="sxs-lookup"><span data-stu-id="04e59-165">Code</span></span>  
 [!code-vb[VbVbalrThreading#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrThreading/VB/class2.vb#21)]  
  
### <a name="comments"></a><span data-ttu-id="04e59-166">Commenti</span><span class="sxs-lookup"><span data-stu-id="04e59-166">Comments</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04e59-167">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04e59-167">See also</span></span>

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.Interlocked?displayProperty=nameWithType>
- [<span data-ttu-id="04e59-168">Panoramica delle primitive di sincronizzazione</span><span class="sxs-lookup"><span data-stu-id="04e59-168">Overview of synchronization primitives</span></span>](../../../standard/threading/overview-of-synchronization-primitives.md)
