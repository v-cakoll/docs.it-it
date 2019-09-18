---
title: moduloObjectHashcode (MDA)
ms.date: 03/30/2017
helpviewer_keywords:
- managed debugging assistants (MDAs), hashcode modulus
- Modulo object hash code
- moduloObjectHashcode MDA
- hashcode modulus
- MDAs (managed debugging assistants), hashcode modulus
- GetHashCode method
- modulus of hashcodes
ms.assetid: b45366ff-2a7a-4b8e-ab01-537b72e9de68
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1679e283a801044ad5a0baed89f17e6acc74259c
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71052450"
---
# <a name="moduloobjecthashcode-mda"></a><span data-ttu-id="f24b7-102">moduloObjectHashcode (MDA)</span><span class="sxs-lookup"><span data-stu-id="f24b7-102">moduloObjectHashcode MDA</span></span>
<span data-ttu-id="f24b7-103">L'assistente al debug gestito `moduloObjectHashcode` modifica il comportamento della classe <xref:System.Object> per eseguire un'operazione modulo sul codice hash restituito dal metodo <xref:System.Object.GetHashCode%2A>.</span><span class="sxs-lookup"><span data-stu-id="f24b7-103">The `moduloObjectHashcode` managed debugging assistant (MDA) changes the behavior of the <xref:System.Object> class to perform a modulo operation on the hash code returned by the <xref:System.Object.GetHashCode%2A> method.</span></span> <span data-ttu-id="f24b7-104">Il modulo predefinito per questo assistente al debug gestito è 1, che fa sì che <xref:System.Object.GetHashCode%2A> restituisca 0 per tutti gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="f24b7-104">The default modulus for this MDA is 1, which causes <xref:System.Object.GetHashCode%2A> to return 0 for all objects.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="f24b7-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="f24b7-105">Symptoms</span></span>  
 <span data-ttu-id="f24b7-106">Dopo la migrazione a una nuova versione di Common Language Runtime (CLR), un programma non viene più eseguito correttamente:</span><span class="sxs-lookup"><span data-stu-id="f24b7-106">After moving to a new version of the common language runtime (CLR), a program no longer executes properly:</span></span>  
  
- <span data-ttu-id="f24b7-107">Il programma ottiene un oggetto non corretto da una <xref:System.Collections.Hashtable>.</span><span class="sxs-lookup"><span data-stu-id="f24b7-107">The program is getting the wrong object from a <xref:System.Collections.Hashtable>.</span></span>  
  
- <span data-ttu-id="f24b7-108">L'ordine di enumerazione da una <xref:System.Collections.Hashtable> include una modifica che compromette il funzionamento del programma.</span><span class="sxs-lookup"><span data-stu-id="f24b7-108">The order of enumeration from a <xref:System.Collections.Hashtable> has a change that breaks the program.</span></span>  
  
- <span data-ttu-id="f24b7-109">Due oggetti che erano uguali non sono più uguali.</span><span class="sxs-lookup"><span data-stu-id="f24b7-109">Two objects that used to be equal are no longer equal.</span></span>  
  
- <span data-ttu-id="f24b7-110">Due oggetti che erano diversi sono ora uguali.</span><span class="sxs-lookup"><span data-stu-id="f24b7-110">Two objects that used to not be equal are now equal.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="f24b7-111">Causa</span><span class="sxs-lookup"><span data-stu-id="f24b7-111">Cause</span></span>  
 <span data-ttu-id="f24b7-112">È possibile che il programma ottenga l'oggetto non corretto da una <xref:System.Collections.Hashtable> perché l'implementazione del metodo <xref:System.Object.Equals%2A> nella classe per la chiave in <xref:System.Collections.Hashtable> verifica l'uguaglianza degli oggetti confrontando i risultati della chiamata al metodo <xref:System.Object.GetHashCode%2A>.</span><span class="sxs-lookup"><span data-stu-id="f24b7-112">Your program may be getting the wrong object from a <xref:System.Collections.Hashtable> because the implementation of the <xref:System.Object.Equals%2A> method on the class for the key into the <xref:System.Collections.Hashtable> tests for equality of objects by comparing the results of the call to the <xref:System.Object.GetHashCode%2A> method.</span></span> <span data-ttu-id="f24b7-113">Non è consigliabile usare i codici hash per verificare l'uguaglianza di oggetti perché due oggetti possono avere lo stesso codice hash, anche se i rispettivi campi hanno valori diversi.</span><span class="sxs-lookup"><span data-stu-id="f24b7-113">Hash codes should not be used to test for object equality because two objects may have the same hash code even if their respective fields have different values.</span></span> <span data-ttu-id="f24b7-114">Queste collisioni di codici hash, anche se nella pratica si tratta di eventi rari, possono verificarsi.</span><span class="sxs-lookup"><span data-stu-id="f24b7-114">These hash code collisions, although rare in practice, do occur.</span></span> <span data-ttu-id="f24b7-115">L'effetto su una ricerca <xref:System.Collections.Hashtable> è che due chiavi diverse risultano apparentemente uguali e <xref:System.Collections.Hashtable> restituisce un oggetto non corretto.</span><span class="sxs-lookup"><span data-stu-id="f24b7-115">The effect this has on a <xref:System.Collections.Hashtable> lookup is that two keys which are not equal appear to be equal, and the wrong object is returned from the <xref:System.Collections.Hashtable>.</span></span> <span data-ttu-id="f24b7-116">Per motivi di prestazioni, l'implementazione di <xref:System.Object.GetHashCode%2A> può cambiare tra versioni di runtime diverse, quindi potrebbero verificarsi collisioni in una versione e non nelle versioni successive.</span><span class="sxs-lookup"><span data-stu-id="f24b7-116">For performance reasons, the implementation of <xref:System.Object.GetHashCode%2A> can change between runtime versions, so collisions that might not occur on one version might occur on subsequent versions.</span></span> <span data-ttu-id="f24b7-117">Abilitare questo assistente al debug gestito per verificare se il codice include bug in caso di collisioni di codici hash.</span><span class="sxs-lookup"><span data-stu-id="f24b7-117">Enable this MDA to test whether your code has bugs when hash codes collide.</span></span> <span data-ttu-id="f24b7-118">Quando questo assistente al debug gestito viene abilitato, il metodo <xref:System.Object.GetHashCode%2A> restituisce 0, quindi tutti i codici hash risultano in collisione.</span><span class="sxs-lookup"><span data-stu-id="f24b7-118">When enabled, this MDA causes the <xref:System.Object.GetHashCode%2A> method to return 0, resulting in all hash codes colliding.</span></span> <span data-ttu-id="f24b7-119">L'unico effetto dell'abilitazione di questo assistente al debug gestito sul programma è un rallentamento dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f24b7-119">The only effect enabling this MDA should have on your program is that your program runs slower.</span></span>  
  
 <span data-ttu-id="f24b7-120">L'ordine di enumerazione da una <xref:System.Collections.Hashtable> può variare tra le diverse versioni di runtime se cambia l'algoritmo usato per calcolare i codici hash per la chiave.</span><span class="sxs-lookup"><span data-stu-id="f24b7-120">The order of enumeration from a <xref:System.Collections.Hashtable> may change from one version of the runtime to another if the algorithm used to compute the hash codes for the key change.</span></span> <span data-ttu-id="f24b7-121">Per verificare se il programma ha una dipendenza dall'ordine di enumerazione delle chiavi o dei valori da una tabella hash, è possibile abilitare questo assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="f24b7-121">To test whether your program has taken a dependency on the order of enumeration of keys or values out of a hash table, you can enable this MDA.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="f24b7-122">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="f24b7-122">Resolution</span></span>  
 <span data-ttu-id="f24b7-123">Non usare mai codici hash in sostituzione all'identità dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="f24b7-123">Never use hash codes as a substitute for object identity.</span></span> <span data-ttu-id="f24b7-124">Implementare l'override del metodo <xref:System.Object.Equals%2A?displayProperty=nameWithType> per non confrontare i codici hash.</span><span class="sxs-lookup"><span data-stu-id="f24b7-124">Implement the override of the <xref:System.Object.Equals%2A?displayProperty=nameWithType> method to not compare hash codes.</span></span>  
  
 <span data-ttu-id="f24b7-125">Non creare dipendenze dall'ordine di enumerazione delle chiavi o dei valori nelle tabelle hash.</span><span class="sxs-lookup"><span data-stu-id="f24b7-125">Do not create dependencies on the order of enumerations of keys or values in hash tables.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="f24b7-126">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="f24b7-126">Effect on the Runtime</span></span>  
 <span data-ttu-id="f24b7-127">Le applicazioni vengono eseguite più lentamente quando si abilita questo assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="f24b7-127">Applications run more slowly when this MDA is enabled.</span></span> <span data-ttu-id="f24b7-128">Questo assistente al debug gestito accetta semplicemente il codice hash che sarebbe stato restituito e restituisce invece il resto della divisione di un modulo.</span><span class="sxs-lookup"><span data-stu-id="f24b7-128">This MDA simply takes the hash code that would have been returned and instead returns the remainder when divided by a modulus.</span></span>  
  
## <a name="output"></a><span data-ttu-id="f24b7-129">Output</span><span class="sxs-lookup"><span data-stu-id="f24b7-129">Output</span></span>  
 <span data-ttu-id="f24b7-130">Non è previsto alcun output per questo assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="f24b7-130">There is no output for this MDA.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="f24b7-131">Configurazione</span><span class="sxs-lookup"><span data-stu-id="f24b7-131">Configuration</span></span>  
 <span data-ttu-id="f24b7-132">L'attributo `modulus` specifica il modulo usato sul codice hash.</span><span class="sxs-lookup"><span data-stu-id="f24b7-132">The `modulus` attribute specifies the modulus used on the hash code.</span></span> <span data-ttu-id="f24b7-133">Il valore predefinito è 1.</span><span class="sxs-lookup"><span data-stu-id="f24b7-133">The default value is 1.</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <moduloObjectHashcode modulus="1" />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f24b7-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f24b7-134">See also</span></span>

- <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.Object.Equals%2A?displayProperty=nameWithType>
- [<span data-ttu-id="f24b7-135">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="f24b7-135">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
