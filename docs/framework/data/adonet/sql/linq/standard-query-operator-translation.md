---
title: Conversione dell'operatore query standard
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: a60c30fa-1e68-45fe-b984-f6abb9ede40e
caps.latest.revision: ''
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: fc99fea9b722f6c3395f6bade625a09c6e97eb08
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2018
---
# <a name="standard-query-operator-translation"></a><span data-ttu-id="ca6f2-102">Conversione dell'operatore query standard</span><span class="sxs-lookup"><span data-stu-id="ca6f2-102">Standard Query Operator Translation</span></span>
<span data-ttu-id="ca6f2-103">Gli operatori di query standard vengono convertiti in comandi SQL in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ca6f2-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translates Standard Query Operators to SQL commands.</span></span> <span data-ttu-id="ca6f2-104">Il processore di query del database determina la semantica di esecuzione della conversione SQL.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-104">The query processor of the database determines the execution semantics of SQL translation.</span></span>  
  
 <span data-ttu-id="ca6f2-105">Gli operatori Query standard definiti in *sequenze*.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-105">Standard Query Operators are defined against *sequences*.</span></span> <span data-ttu-id="ca6f2-106">È una sequenza *ordinati* e si basa sull'identità del riferimento per ogni elemento della sequenza.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-106">A sequence is *ordered* and relies on reference identity for each element of the sequence.</span></span> <span data-ttu-id="ca6f2-107">Per ulteriori informazioni, vedere [Cenni preliminari sugli operatori di Query Standard](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).</span><span class="sxs-lookup"><span data-stu-id="ca6f2-107">For more information, see [Standard Query Operators Overview](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).</span></span>  
  
 <span data-ttu-id="ca6f2-108">SQL vengono principalmente gestiti *insiemi di valori non ordinati*.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-108">SQL deals primarily with *unordered sets of values*.</span></span> <span data-ttu-id="ca6f2-109">L'ordinamento è in genere un'operazione di post-elaborazione specificata in modo esplicito, che viene applicata al risultato finale di una query piuttosto che ai risultati intermedi.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-109">Ordering is typically an explicitly stated, post-processing operation that is applied to the final result of a query rather than to intermediate results.</span></span> <span data-ttu-id="ca6f2-110">L'identità viene definita dai valori.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-110">Identity is defined by values.</span></span> <span data-ttu-id="ca6f2-111">Per questo motivo, le query SQL vengono riconosciute come multiset (*sacchetti*) anziché *imposta*.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-111">For this reason, SQL queries are understood to deal with multisets (*bags*) instead of *sets*.</span></span>  
  
 <span data-ttu-id="ca6f2-112">Nei paragrafi seguenti vengono descritte le differenze tra gli operatori di query standard e la relativa conversione SQL per il provider SQL Server per [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ca6f2-112">The following paragraphs describe the differences between the Standard Query Operators and their SQL translation for the SQL Server provider for [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
## <a name="operator-support"></a><span data-ttu-id="ca6f2-113">Supporto degli operatori</span><span class="sxs-lookup"><span data-stu-id="ca6f2-113">Operator Support</span></span>  
  
### <a name="concat"></a><span data-ttu-id="ca6f2-114">Concat</span><span class="sxs-lookup"><span data-stu-id="ca6f2-114">Concat</span></span>  
 <span data-ttu-id="ca6f2-115">Il metodo <xref:System.Linq.Enumerable.Concat%2A> viene definito per multiset ordinati in cui l'ordine del ricevente e l'ordine dell'argomento sono uguali.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-115">The <xref:System.Linq.Enumerable.Concat%2A> method is defined for ordered multisets where the order of the receiver and the order of the argument are the same.</span></span> <span data-ttu-id="ca6f2-116">Il funzionamento di <xref:System.Linq.Enumerable.Concat%2A> sui multiset seguiti dall'ordine comune è analogo a quello di `UNION ALL`.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-116"><xref:System.Linq.Enumerable.Concat%2A> works as `UNION ALL` over the multisets followed by the common order.</span></span>  
  
 <span data-ttu-id="ca6f2-117">Il passaggio finale in SQL consiste nell'ordinamento prima che vengano generati i risultati.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-117">The final step is ordering in SQL before results are produced.</span></span> <span data-ttu-id="ca6f2-118"><xref:System.Linq.Enumerable.Concat%2A> non mantiene l'ordine degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-118"><xref:System.Linq.Enumerable.Concat%2A> does not preserve the order of its arguments.</span></span> <span data-ttu-id="ca6f2-119">Per assicurare che l'ordine sia appropriato, è necessario ordinare i risultati di <xref:System.Linq.Enumerable.Concat%2A> in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-119">To ensure appropriate ordering, you must explicitly order the results of <xref:System.Linq.Enumerable.Concat%2A>.</span></span>  
  
### <a name="intersect-except-union"></a><span data-ttu-id="ca6f2-120">Metodi Intersect, Except, Union</span><span class="sxs-lookup"><span data-stu-id="ca6f2-120">Intersect, Except, Union</span></span>  
 <span data-ttu-id="ca6f2-121">I metodi <xref:System.Linq.Enumerable.Intersect%2A> e <xref:System.Linq.Enumerable.Except%2A> sono definiti correttamente solo sui set,</span><span class="sxs-lookup"><span data-stu-id="ca6f2-121">The <xref:System.Linq.Enumerable.Intersect%2A> and <xref:System.Linq.Enumerable.Except%2A> methods are well defined only on sets.</span></span> <span data-ttu-id="ca6f2-122">mentre la semantica per i tipi multiset non è definita.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-122">The semantics for multisets is undefined.</span></span>  
  
 <span data-ttu-id="ca6f2-123">Il metodo <xref:System.Linq.Enumerable.Union%2A> viene definito per i tipi multiset come concatenazione non ordinata di multiset, che corrisponde in effetti al risultato della clausola UNION ALL in SQL.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-123">The <xref:System.Linq.Enumerable.Union%2A> method is defined for multisets as the unordered concatenation of the multisets (effectively the result of the UNION ALL clause in SQL).</span></span>  
  
### <a name="take-skip"></a><span data-ttu-id="ca6f2-124">Metodi Take, Skip</span><span class="sxs-lookup"><span data-stu-id="ca6f2-124">Take, Skip</span></span>  
 <span data-ttu-id="ca6f2-125"><xref:System.Linq.Enumerable.Take%2A> e <xref:System.Linq.Enumerable.Skip%2A> metodi sono definiti correttamente solo sugli *set ordinati*.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-125"><xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> methods are well defined only against *ordered sets*.</span></span> <span data-ttu-id="ca6f2-126">mentre la semantica per i set non ordinati o i tipi multiset non è definita.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-126">The semantics for unordered sets or multisets are undefined.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ca6f2-127"><xref:System.Linq.Enumerable.Take%2A> e <xref:System.Linq.Enumerable.Skip%2A> presentano alcune limitazioni quando vengono usati nelle query su SQL Server 2000.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-127"><xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> have certain limitations when they are used in queries against SQL Server 2000.</span></span> <span data-ttu-id="ca6f2-128">Per ulteriori informazioni, vedere la voce "Skip e Take eccezioni in SQL Server 2000" in [risoluzione dei problemi](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="ca6f2-128">For more information, see the "Skip and Take Exceptions in SQL Server 2000" entry in [Troubleshooting](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md).</span></span>  
  
 <span data-ttu-id="ca6f2-129">A causa delle limitazioni relative all'ordinamento in SQL, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tenta di spostare l'ordinamento dell'argomento di questi metodi per il risultato del metodo.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-129">Because of limitations on ordering in SQL, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tries to move the ordering of the argument of these methods to the result of the method.</span></span> <span data-ttu-id="ca6f2-130">Si consideri ad esempio la seguente query [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="ca6f2-130">For example, consider the following [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] query:</span></span>  
  
 [!code-csharp[DLinqSQOTranslation#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSQOTranslation/cs/Program.cs#1)]
 [!code-vb[DLinqSQOTranslation#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSQOTranslation/vb/Module1.vb#1)]  
  
 <span data-ttu-id="ca6f2-131">L'SQL generato per questo codice sposta l'ordinamento alla fine, come segue:</span><span class="sxs-lookup"><span data-stu-id="ca6f2-131">The generated SQL for this code moves the ordering to the end, as follows:</span></span>  
  
```  
SELECT TOP 1 [t0].[CustomerID], [t0].[CompanyName],  
FROM [Customers] AS [t0]  
WHERE (NOT (EXISTS(  
    SELECT NULL AS [EMPTY]  
    FROM (  
        SELECT TOP 1 [t1].[CustomerID]  
        FROM [Customers] AS [t1]  
        WHERE [t1].[City] = @p0  
        ORDER BY [t1].[CustomerID]  
        ) AS [t2]  
    WHERE [t0].[CustomerID] = [t2].[CustomerID]  
    ))) AND ([t0].[City] = @p1)  
ORDER BY [t0].[CustomerID]  
```  
  
 <span data-ttu-id="ca6f2-132">È quindi evidente che quando <xref:System.Linq.Enumerable.Take%2A> e <xref:System.Linq.Enumerable.Skip%2A> vengono concatenati, tutto l'ordinamento specificato deve essere coerente.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-132">It becomes obvious that all the specified ordering must be consistent when <xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> are chained together.</span></span> <span data-ttu-id="ca6f2-133">In caso contrario i risultati non saranno definiti.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-133">Otherwise, the results are undefined.</span></span>  
  
 <span data-ttu-id="ca6f2-134">Sia <xref:System.Linq.Enumerable.Take%2A> che <xref:System.Linq.Enumerable.Skip%2A> sono definiti correttamente per gli argomenti di tipo integrale costante non negativi basati sulla specifica dell'operatore di query standard.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-134">Both <xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> are well-defined for non-negative, constant integral arguments based on the Standard Query Operator specification.</span></span>  
  
### <a name="operators-with-no-translation"></a><span data-ttu-id="ca6f2-135">Operatori senza conversione</span><span class="sxs-lookup"><span data-stu-id="ca6f2-135">Operators with No Translation</span></span>  
 <span data-ttu-id="ca6f2-136">I metodi seguenti non vengono convertiti da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ca6f2-136">The following methods are not translated by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="ca6f2-137">Il motivo più comune è la differenza tra i multiset non ordinati e le sequenze.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-137">The most common reason is the difference between unordered multisets and sequences.</span></span>  
  
|<span data-ttu-id="ca6f2-138">Operatori</span><span class="sxs-lookup"><span data-stu-id="ca6f2-138">Operators</span></span>|<span data-ttu-id="ca6f2-139">Spiegazione logica:</span><span class="sxs-lookup"><span data-stu-id="ca6f2-139">Rationale</span></span>|  
|---------------|---------------|  
|<span data-ttu-id="ca6f2-140"><xref:System.Linq.Enumerable.TakeWhile%2A>, <xref:System.Linq.Enumerable.SkipWhile%2A></span><span class="sxs-lookup"><span data-stu-id="ca6f2-140"><xref:System.Linq.Enumerable.TakeWhile%2A>, <xref:System.Linq.Enumerable.SkipWhile%2A></span></span>|<span data-ttu-id="ca6f2-141">Le query SQL vengono eseguite su multiset, non su sequenze.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-141">SQL queries operate on multisets, not on sequences.</span></span> <span data-ttu-id="ca6f2-142">`ORDER BY` deve essere l'ultima clausola applicata ai risultati.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-142">`ORDER BY` must be the last clause applied to the results.</span></span> <span data-ttu-id="ca6f2-143">Per questo motivo non esiste una conversione di tipo generico per questi due metodi.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-143">For this reason, there is no general-purpose translation for these two methods.</span></span>|  
|<xref:System.Linq.Enumerable.Reverse%2A>|<span data-ttu-id="ca6f2-144">La conversione di questo metodo è possibile per un set ordinato, ma attualmente non viene eseguita da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ca6f2-144">Translation of this method is possible for an ordered set but is not currently translated by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>|  
|<span data-ttu-id="ca6f2-145"><xref:System.Linq.Enumerable.Last%2A>, <xref:System.Linq.Enumerable.LastOrDefault%2A></span><span class="sxs-lookup"><span data-stu-id="ca6f2-145"><xref:System.Linq.Enumerable.Last%2A>, <xref:System.Linq.Enumerable.LastOrDefault%2A></span></span>|<span data-ttu-id="ca6f2-146">La conversione di questi metodi è possibile per un set ordinato, ma attualmente non viene eseguita da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ca6f2-146">Translation of these methods is possible for an ordered set but is not currently translated by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>|  
|<span data-ttu-id="ca6f2-147"><xref:System.Linq.Enumerable.ElementAt%2A>, <xref:System.Linq.Enumerable.ElementAtOrDefault%2A></span><span class="sxs-lookup"><span data-stu-id="ca6f2-147"><xref:System.Linq.Enumerable.ElementAt%2A>, <xref:System.Linq.Enumerable.ElementAtOrDefault%2A></span></span>|<span data-ttu-id="ca6f2-148">Le query SQL vengono eseguite su multiset, non sulle sequenze indicizzabili.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-148">SQL queries operate on multisets, not on indexable sequences.</span></span>|  
|<span data-ttu-id="ca6f2-149"><xref:System.Linq.Enumerable.DefaultIfEmpty%2A> (overload con argomento predefinito)</span><span class="sxs-lookup"><span data-stu-id="ca6f2-149"><xref:System.Linq.Enumerable.DefaultIfEmpty%2A> (overload with default arg)</span></span>|<span data-ttu-id="ca6f2-150">In generale non è possibile specificare un valore predefinito per una tupla arbitraria.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-150">In general, a default value cannot be specified for an arbitrary tuple.</span></span> <span data-ttu-id="ca6f2-151">In alcuni casi i valori null per le tuple sono consentiti tramite outer join.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-151">Null values for tuples are possible in some cases through outer joins.</span></span>|  
  
## <a name="expression-translation"></a><span data-ttu-id="ca6f2-152">Conversione di espressione</span><span class="sxs-lookup"><span data-stu-id="ca6f2-152">Expression Translation</span></span>  
  
### <a name="null-semantics"></a><span data-ttu-id="ca6f2-153">Semantica null</span><span class="sxs-lookup"><span data-stu-id="ca6f2-153">Null semantics</span></span>  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="ca6f2-154"> non impone la semantica di confronto in SQL.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-154"> does not impose null comparison semantics on SQL.</span></span> <span data-ttu-id="ca6f2-155">Gli operatori di confronto vengono sintatticamente convertiti negli equivalenti SQL.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-155">Comparison operators are syntactically translated to their SQL equivalents.</span></span> <span data-ttu-id="ca6f2-156">Per questo motivo la semantica riflette la semantica SQL definita nelle impostazioni di connessione o del server.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-156">For this reason, the semantics reflect SQL semantics that are defined by server or connection settings.</span></span> <span data-ttu-id="ca6f2-157">Ad esempio, due valori null sono considerati non uguali nelle impostazioni predefinite di SQL Server, ma è possibile modificare le impostazioni per modificare la semantica.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-157">For example, two null values are considered unequal under default SQL Server settings, but you can change the settings to change the semantics.</span></span> <span data-ttu-id="ca6f2-158">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] non vengono considerate le impostazioni del server durante la conversione delle query.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-158">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] does not consider server settings when it translates queries.</span></span>  
  
 <span data-ttu-id="ca6f2-159">Un confronto con il valore letterale null viene convertito nella versione SQL appropriata (`is null` o `is not null`).</span><span class="sxs-lookup"><span data-stu-id="ca6f2-159">A comparison with the literal null is translated to the appropriate SQL version (`is null` or `is not null`).</span></span>  
  
 <span data-ttu-id="ca6f2-160">Il valore `null` nelle regole di confronto viene definito da SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-160">The value of `null` in collation is defined by SQL Server.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="ca6f2-161"> non modifica le regole di confronto.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-161"> does not change the collation.</span></span>  
  
### <a name="aggregates"></a><span data-ttu-id="ca6f2-162">Aggregati</span><span class="sxs-lookup"><span data-stu-id="ca6f2-162">Aggregates</span></span>  
 <span data-ttu-id="ca6f2-163">Il metodo di aggregazione dell'operatore di query standard <xref:System.Linq.Enumerable.Sum%2A> restituisce valori zero per tutte le sequenze vuote o che contengono solo valori null.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-163">The Standard Query Operator aggregate method <xref:System.Linq.Enumerable.Sum%2A> evaluates to zero for an empty sequence or for a sequence that contains only nulls.</span></span> <span data-ttu-id="ca6f2-164">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], la semantica di SQL rimane invariata, e <xref:System.Linq.Enumerable.Sum%2A> restituisce `null` anziché zero per una sequenza vuota o una sequenza che contiene solo valori null.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-164">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the semantics of SQL are left unchanged, and <xref:System.Linq.Enumerable.Sum%2A> evaluates to `null` instead of zero for an empty sequence or for a sequence that contains only nulls.</span></span>  
  
 <span data-ttu-id="ca6f2-165">Le limitazioni di SQL sui risultati intermedi vengono applicate agli aggregati in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ca6f2-165">SQL limitations on intermediate results apply to aggregates in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="ca6f2-166">La somma, <xref:System.Linq.Enumerable.Sum%2A>, delle quantità di valori integer a 32 bit non viene calcolata utilizzando risultati a 64 bit</span><span class="sxs-lookup"><span data-stu-id="ca6f2-166">The <xref:System.Linq.Enumerable.Sum%2A> of 32-bit integer quantities is not computed by using 64-bit results.</span></span> <span data-ttu-id="ca6f2-167">ed è possibile che si verifichi un overflow per una conversione [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] di <xref:System.Linq.Enumerable.Sum%2A>, anche se l'implementazione dell'operatore di query standard non provoca un overflow per la corrispondente sequenza in memoria.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-167">Overflow might occur for a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translation of <xref:System.Linq.Enumerable.Sum%2A>, even if the Standard Query Operator implementation does not cause an overflow for the corresponding in-memory sequence.</span></span>  
  
 <span data-ttu-id="ca6f2-168">In modo analogo la conversione [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] di <xref:System.Linq.Enumerable.Average%2A> di valori integer viene calcolata come un valore `integer`, non come un valore `double`.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-168">Likewise, the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translation of <xref:System.Linq.Enumerable.Average%2A> of integer values is computed as an `integer`, not as a `double`.</span></span>  
  
### <a name="entity-arguments"></a><span data-ttu-id="ca6f2-169">Argomenti di entità</span><span class="sxs-lookup"><span data-stu-id="ca6f2-169">Entity Arguments</span></span>  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="ca6f2-170"> consente ai tipi di entità da utilizzare nel <xref:System.Linq.Enumerable.GroupBy%2A> e <xref:System.Linq.Enumerable.OrderBy%2A> metodi.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-170"> enables entity types to be used in the <xref:System.Linq.Enumerable.GroupBy%2A> and <xref:System.Linq.Enumerable.OrderBy%2A> methods.</span></span> <span data-ttu-id="ca6f2-171">Nella conversione di tali operatori l'uso di un argomento di un tipo viene considerato equivalente della specifica di tutti i membri di quel tipo.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-171">In the translation of these operators, the use of an argument of a type is considered to be the equivalent to specifying all members of that type.</span></span> <span data-ttu-id="ca6f2-172">Ad esempio, il codice seguente è equivalente.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-172">For example, the following code is equivalent:</span></span>  
  
 [!code-csharp[DLinqSQOTranslation#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSQOTranslation/cs/Program.cs#2)]
 [!code-vb[DLinqSQOTranslation#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSQOTranslation/vb/Module1.vb#2)]  
  
### <a name="equatable--comparable-arguments"></a><span data-ttu-id="ca6f2-173">Argomenti di uguaglianza/confronto</span><span class="sxs-lookup"><span data-stu-id="ca6f2-173">Equatable / Comparable Arguments</span></span>  
 <span data-ttu-id="ca6f2-174">Nell'implementazione dei metodi elencati di seguito è richiesta l'uguaglianza di argomenti:</span><span class="sxs-lookup"><span data-stu-id="ca6f2-174">Equality of arguments is required in the implementation of the following methods:</span></span>  
  
 <xref:System.Linq.Enumerable.Contains%2A>  
  
 <xref:System.Linq.Enumerable.Skip%2A>  
  
 <xref:System.Linq.Enumerable.Union%2A>  
  
 <xref:System.Linq.Enumerable.Intersect%2A>  
  
 <xref:System.Linq.Enumerable.Except%2A>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="ca6f2-175"> supporta uguaglianza e confronto per *flat* argomenti, ma non per gli argomenti sono o che contengono le sequenze.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-175"> supports equality and comparison for *flat* arguments, but not for arguments that are or contain sequences.</span></span> <span data-ttu-id="ca6f2-176">Un argomento non strutturato è un tipo di cui è possibile eseguire il mapping a una riga SQL.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-176">A flat argument is a type that can be mapped to a SQL row.</span></span> <span data-ttu-id="ca6f2-177">Una proiezione di uno o più tipi di entità, per cui è possibile determinare staticamente che non è presente una sequenza, viene considerata un argomento non strutturato.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-177">A projection of one or more entity types that can be statically determined not to contain a sequence is considered a flat argument.</span></span>  
  
 <span data-ttu-id="ca6f2-178">Di seguito sono riportati esempi di argomenti non strutturati:</span><span class="sxs-lookup"><span data-stu-id="ca6f2-178">Following are examples of flat arguments:</span></span>  
  
 [!code-csharp[DLinqSQOTranslation#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSQOTranslation/cs/Program.cs#3)]
 [!code-vb[DLinqSQOTranslation#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSQOTranslation/vb/Module1.vb#3)]  
  
 <span data-ttu-id="ca6f2-179">Gli esempi seguenti si riferiscono ad argomenti strutturati (gerarchici).</span><span class="sxs-lookup"><span data-stu-id="ca6f2-179">The following are examples of non-flat (hierarchical) arguments.</span></span>  
  
 [!code-csharp[DLinqSQOTranslation#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSQOTranslation/cs/Program.cs#4)]
 [!code-vb[DLinqSQOTranslation#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSQOTranslation/vb/Module1.vb#4)]  
  
### <a name="visual-basic-function-translation"></a><span data-ttu-id="ca6f2-180">Conversione di funzioni Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ca6f2-180">Visual Basic Function Translation</span></span>  
 <span data-ttu-id="ca6f2-181">Le seguenti funzioni di supporto usate dal compilatore Visual Basic vengono convertite nei corrispondenti operatori e funzioni SQL:</span><span class="sxs-lookup"><span data-stu-id="ca6f2-181">The following helper functions that are used by the Visual Basic compiler are translated to corresponding SQL operators and functions:</span></span>  
  
 `CompareString`  
  
 `DateTime.Compare`  
  
 `Decimal.Compare`  
  
 `IIf (in Microsoft.VisualBasic.Interaction)`  
  
 <span data-ttu-id="ca6f2-182">Metodi di conversione:</span><span class="sxs-lookup"><span data-stu-id="ca6f2-182">Conversion methods:</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="ca6f2-183">ToBoolean</span><span class="sxs-lookup"><span data-stu-id="ca6f2-183">ToBoolean</span></span>|<span data-ttu-id="ca6f2-184">ToSByte</span><span class="sxs-lookup"><span data-stu-id="ca6f2-184">ToSByte</span></span>|<span data-ttu-id="ca6f2-185">ToByte</span><span class="sxs-lookup"><span data-stu-id="ca6f2-185">ToByte</span></span>|<span data-ttu-id="ca6f2-186">ToChar</span><span class="sxs-lookup"><span data-stu-id="ca6f2-186">ToChar</span></span>|  
|<span data-ttu-id="ca6f2-187">ToCharArrayRankOne</span><span class="sxs-lookup"><span data-stu-id="ca6f2-187">ToCharArrayRankOne</span></span>|<span data-ttu-id="ca6f2-188">ToDate</span><span class="sxs-lookup"><span data-stu-id="ca6f2-188">ToDate</span></span>|<span data-ttu-id="ca6f2-189">ToDecimal</span><span class="sxs-lookup"><span data-stu-id="ca6f2-189">ToDecimal</span></span>|<span data-ttu-id="ca6f2-190">ToDouble</span><span class="sxs-lookup"><span data-stu-id="ca6f2-190">ToDouble</span></span>|  
|<span data-ttu-id="ca6f2-191">ToInteger</span><span class="sxs-lookup"><span data-stu-id="ca6f2-191">ToInteger</span></span>|<span data-ttu-id="ca6f2-192">ToUInteger</span><span class="sxs-lookup"><span data-stu-id="ca6f2-192">ToUInteger</span></span>|<span data-ttu-id="ca6f2-193">ToLong</span><span class="sxs-lookup"><span data-stu-id="ca6f2-193">ToLong</span></span>|<span data-ttu-id="ca6f2-194">ToULong</span><span class="sxs-lookup"><span data-stu-id="ca6f2-194">ToULong</span></span>|  
|<span data-ttu-id="ca6f2-195">ToShort</span><span class="sxs-lookup"><span data-stu-id="ca6f2-195">ToShort</span></span>|<span data-ttu-id="ca6f2-196">ToUShort</span><span class="sxs-lookup"><span data-stu-id="ca6f2-196">ToUShort</span></span>|<span data-ttu-id="ca6f2-197">ToSingle</span><span class="sxs-lookup"><span data-stu-id="ca6f2-197">ToSingle</span></span>|<span data-ttu-id="ca6f2-198">ToString</span><span class="sxs-lookup"><span data-stu-id="ca6f2-198">ToString</span></span>|  
  
## <a name="inheritance-support"></a><span data-ttu-id="ca6f2-199">Supporto dell'ereditarietà</span><span class="sxs-lookup"><span data-stu-id="ca6f2-199">Inheritance Support</span></span>  
  
### <a name="inheritance-mapping-restrictions"></a><span data-ttu-id="ca6f2-200">Limitazioni relative al mapping di ereditarietà</span><span class="sxs-lookup"><span data-stu-id="ca6f2-200">Inheritance Mapping Restrictions</span></span>  
 <span data-ttu-id="ca6f2-201">Per ulteriori informazioni, vedere [come: mappa di gerarchie di ereditarietà](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-inheritance-hierarchies.md).</span><span class="sxs-lookup"><span data-stu-id="ca6f2-201">For more information, see [How to: Map Inheritance Hierarchies](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-inheritance-hierarchies.md).</span></span>  
  
### <a name="inheritance-in-queries"></a><span data-ttu-id="ca6f2-202">Ereditarietà nelle query</span><span class="sxs-lookup"><span data-stu-id="ca6f2-202">Inheritance in Queries</span></span>  
 <span data-ttu-id="ca6f2-203">I cast C# sono supportati solo nella proiezione.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-203">C# casts are supported only in projection.</span></span> <span data-ttu-id="ca6f2-204">I cast usati in altri contesti non vengono convertiti e sono ignorati.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-204">Casts that are used elsewhere are not translated and are ignored.</span></span> <span data-ttu-id="ca6f2-205">A parte i nomi delle funzioni SQL, in SQL viene in effetti eseguito solo l'equivalente dell'operazione <xref:System.Convert> di Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="ca6f2-205">Aside from SQL function names, SQL really only performs the equivalent of the common language runtime (CLR) <xref:System.Convert>.</span></span> <span data-ttu-id="ca6f2-206">In altre parole SQL è in grado di modificare il valore di un tipo in un altro.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-206">That is, SQL can change the value of one type to another.</span></span> <span data-ttu-id="ca6f2-207">Non è disponibile un cast CLR equivalente, in quanto non esiste un concetto che consenta di reinterpretare gli stessi bit di un altro tipo.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-207">There is no equivalent of CLR cast because there is no concept of reinterpreting the same bits as those of another type.</span></span> <span data-ttu-id="ca6f2-208">Per questo motivo un cast C# funziona solo localmente</span><span class="sxs-lookup"><span data-stu-id="ca6f2-208">That is why a C# cast works only locally.</span></span> <span data-ttu-id="ca6f2-209">e non viene usato in modalità remota.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-209">It is not remoted.</span></span>  
  
 <span data-ttu-id="ca6f2-210">Gli operatori `is` e `as` e il metodo `GetType` non sono limitati all'operatore `Select`,</span><span class="sxs-lookup"><span data-stu-id="ca6f2-210">The operators, `is` and `as`, and the `GetType` method are not restricted to the `Select` operator.</span></span> <span data-ttu-id="ca6f2-211">pertanto possono essere usati anche in altri operatori di query.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-211">They can be used in other query operators also.</span></span>  
  
## <a name="sql-server-2008-support"></a><span data-ttu-id="ca6f2-212">Supporto di SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="ca6f2-212">SQL Server 2008 Support</span></span>  
 <span data-ttu-id="ca6f2-213">A partire da .NET Framework versione 3.5 SP1, LINQ to SQL supporta il mapping ai nuovi tipi di data e ora introdotti con SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-213">Starting with the .NET Framework 3.5 SP1, LINQ to SQL supports mapping to new date and time types introduced with SQL Server 2008.</span></span> <span data-ttu-id="ca6f2-214">Vi sono tuttavia alcune limitazioni relative agli operatori di query LINQ to SQL che è possibile usare quando si lavora con valori mappati a questi nuovi tipi.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-214">But, there are some limitations to the LINQ to SQL query operators that you can use when operating against values mapped to these new types.</span></span>  
  
### <a name="unsupported-query-operators"></a><span data-ttu-id="ca6f2-215">Operatori di query non supportati</span><span class="sxs-lookup"><span data-stu-id="ca6f2-215">Unsupported Query Operators</span></span>  
 <span data-ttu-id="ca6f2-216">Gli operatori di query seguenti non sono supportati per i valori mappati ai nuovi tipi di data e ora SQL Server: `DATETIME2`, `DATE`, `TIME` e `DATETIMEOFFSET`.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-216">The following query operators are not supported on values mapped to the new SQL Server date and time types: `DATETIME2`, `DATE`, `TIME`, and `DATETIMEOFFSET`.</span></span>  
  
-   `Aggregate`  
  
-   `Average`  
  
-   `LastOrDefault`  
  
-   `OfType`  
  
-   `Sum`  
  
 <span data-ttu-id="ca6f2-217">Per ulteriori informazioni sul mapping di questi tipi di data e ora di SQL Server, vedere [Mapping dei tipi CLR SQL](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="ca6f2-217">For more information about mapping to these SQL Server date and time types, see [SQL-CLR Type Mapping](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).</span></span>  
  
## <a name="sql-server-2005-support"></a><span data-ttu-id="ca6f2-218">Supporto di SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="ca6f2-218">SQL Server 2005 Support</span></span>  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="ca6f2-219"> non supporta le seguenti funzionalità di SQL Server 2005:</span><span class="sxs-lookup"><span data-stu-id="ca6f2-219"> does not support the following SQL Server 2005 features:</span></span>  
  
-   <span data-ttu-id="ca6f2-220">Stored procedure scritte per CLR SQL.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-220">Stored procedures written for SQL CLR.</span></span>  
  
-   <span data-ttu-id="ca6f2-221">Tipo definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-221">User-defined type.</span></span>  
  
-   <span data-ttu-id="ca6f2-222">Funzionalità di query XML.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-222">XML query features.</span></span>  
  
## <a name="sql-server-2000-support"></a><span data-ttu-id="ca6f2-223">Supporto di SQL Server 2000</span><span class="sxs-lookup"><span data-stu-id="ca6f2-223">SQL Server 2000 Support</span></span>  
 <span data-ttu-id="ca6f2-224">Le seguenti limitazioni di [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)], rispetto a [!INCLUDE[sqprsqext](../../../../../../includes/sqprsqext-md.md)], influiscono sul supporto di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ca6f2-224">The following [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)] limitations (compared to [!INCLUDE[sqprsqext](../../../../../../includes/sqprsqext-md.md)]) affect [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] support.</span></span>  
  
### <a name="cross-apply-and-outer-apply-operators"></a><span data-ttu-id="ca6f2-225">Operatori Cross Apply e Outer Apply</span><span class="sxs-lookup"><span data-stu-id="ca6f2-225">Cross Apply and Outer Apply Operators</span></span>  
 <span data-ttu-id="ca6f2-226">Questi operatori non sono disponibili in [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ca6f2-226">These operators are not available in [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)].</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="ca6f2-227"> tenta una serie di operazioni di riscrittura per sostituirli con join appropriati.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-227"> tries a series of rewrites to replace them with appropriate joins.</span></span>  
  
 <span data-ttu-id="ca6f2-228">`Cross Apply` e `Outer Apply` vengono generati per la navigazione tra relazioni.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-228">`Cross Apply` and `Outer Apply` are generated for relationship navigations.</span></span> <span data-ttu-id="ca6f2-229">Il set di query per cui tali riscritture sono possibili non è esattamente definito.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-229">The set of queries for which such rewrites are possible is not well defined.</span></span> <span data-ttu-id="ca6f2-230">Per questo motivo il set minimo di query supportato per [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)] è quello che non comporta la navigazione tra relazioni.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-230">For this reason, the minimal set of queries that is supported for [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)] is the set that does not involve relationship navigation.</span></span>  
  
### <a name="text--ntext"></a><span data-ttu-id="ca6f2-231">text/ntext</span><span class="sxs-lookup"><span data-stu-id="ca6f2-231">text / ntext</span></span>  
 <span data-ttu-id="ca6f2-232">Tipi di dati `text`  /  `ntext` non può essere utilizzato in determinate operazioni di query su `varchar(max)`  /  `nvarchar(max)`, che sono supportate da [!INCLUDE[sqprsqext](../../../../../../includes/sqprsqext-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ca6f2-232">Data types `text` / `ntext` cannot be used in certain query operations against `varchar(max)` / `nvarchar(max)`, which are supported by [!INCLUDE[sqprsqext](../../../../../../includes/sqprsqext-md.md)].</span></span>  
  
 <span data-ttu-id="ca6f2-233">Non sono disponibili risoluzioni per questa limitazione.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-233">No resolution is available for this limitation.</span></span> <span data-ttu-id="ca6f2-234">In particolare, non è possibile usare `Distinct()` su qualsiasi risultato contenente membri di cui è stato eseguito il mapping a colonne `text` o `ntext`.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-234">Specifically, you cannot use `Distinct()` on any result that contains members that are mapped to `text` or `ntext` columns.</span></span>  
  
### <a name="behavior-triggered-by-nested-queries"></a><span data-ttu-id="ca6f2-235">Comportamento attivato dalle query annidate</span><span class="sxs-lookup"><span data-stu-id="ca6f2-235">Behavior Triggered by Nested Queries</span></span>  
 [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)]<span data-ttu-id="ca6f2-236"> (tramite SP4) dello strumento di associazione presenta alcune peculiarità attivate dalle query annidate.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-236"> (through SP4) binder has some idiosyncrasies that are triggered by nested queries.</span></span> <span data-ttu-id="ca6f2-237">Il set di query SQL che attiva queste peculiarità non è esattamente definito.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-237">The set of SQL queries that triggers these idiosyncrasies is not well defined.</span></span> <span data-ttu-id="ca6f2-238">Per questo motivo, è possibile definire il set di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] query che potrebbero provocare eccezioni di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-238">For this reason, you cannot define the set of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries that might cause SQL Server exceptions.</span></span>  
  
### <a name="skip-and-take-operators"></a><span data-ttu-id="ca6f2-239">Operatori Skip e Take</span><span class="sxs-lookup"><span data-stu-id="ca6f2-239">Skip and Take Operators</span></span>  
 <span data-ttu-id="ca6f2-240"><xref:System.Linq.Enumerable.Take%2A> e <xref:System.Linq.Enumerable.Skip%2A> presentano determinate limitazioni quando vengono usati nelle query su [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ca6f2-240"><xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> have certain limitations when they are used in queries against [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)].</span></span> <span data-ttu-id="ca6f2-241">Per ulteriori informazioni, vedere la voce "Skip e Take eccezioni in SQL Server 2000" in [risoluzione dei problemi](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="ca6f2-241">For more information, see the "Skip and Take Exceptions in SQL Server 2000" entry in [Troubleshooting](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md).</span></span>  
  
## <a name="object-materialization"></a><span data-ttu-id="ca6f2-242">Materializzazione di oggetti</span><span class="sxs-lookup"><span data-stu-id="ca6f2-242">Object Materialization</span></span>  
 <span data-ttu-id="ca6f2-243">La materializzazione crea oggetti CLR da righe restituite da una o più query SQL.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-243">Materialization creates CLR objects from rows that are returned by one or more SQL queries.</span></span>  
  
-   <span data-ttu-id="ca6f2-244">Le chiamate seguenti vengono *eseguite localmente* come parte dell'operazione di materializzazione:</span><span class="sxs-lookup"><span data-stu-id="ca6f2-244">The following calls are *executed locally* as a part of materialization:</span></span>  
  
    -   <span data-ttu-id="ca6f2-245">Costruttori</span><span class="sxs-lookup"><span data-stu-id="ca6f2-245">Constructors</span></span>  
  
    -   <span data-ttu-id="ca6f2-246">Metodi `ToString` nelle proiezioni</span><span class="sxs-lookup"><span data-stu-id="ca6f2-246">`ToString` methods in projections</span></span>  
  
    -   <span data-ttu-id="ca6f2-247">Cast dei tipi nelle proiezioni</span><span class="sxs-lookup"><span data-stu-id="ca6f2-247">Type casts in projections</span></span>  
  
-   <span data-ttu-id="ca6f2-248">I metodi che seguono il <xref:System.Linq.Enumerable.AsEnumerable%2A> metodo *eseguite localmente*.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-248">Methods that follow the <xref:System.Linq.Enumerable.AsEnumerable%2A> method are *executed locally*.</span></span> <span data-ttu-id="ca6f2-249">Questo metodo non provoca l'esecuzione immediata.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-249">This method does not cause immediate execution.</span></span>  
  
-   <span data-ttu-id="ca6f2-250">È possibile usare `struct` come tipo restituito del risultato di una query o come un membro del tipo di risultato.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-250">You can use a `struct` as the return type of a query result or as a member of the result type.</span></span> <span data-ttu-id="ca6f2-251">Le entità devono essere classi.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-251">Entities are required to be classes.</span></span> <span data-ttu-id="ca6f2-252">I tipi anonimi vengono materializzati come istanze della classe, tuttavia gli struct denominati, non le entità, possono essere usati nella proiezione.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-252">Anonymous types are materialized as class instances, but named structs (non-entities) can be used in projection.</span></span>  
  
-   <span data-ttu-id="ca6f2-253">Un membro del tipo restituito del risultato di una query può essere di tipo <xref:System.Linq.IQueryable%601></span><span class="sxs-lookup"><span data-stu-id="ca6f2-253">A member of the return type of a query result can be of type <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="ca6f2-254">e viene materializzato come una raccolta locale.</span><span class="sxs-lookup"><span data-stu-id="ca6f2-254">It is materialized as a local collection.</span></span>  
  
-   <span data-ttu-id="ca6f2-255">I metodi seguenti provocano la *materializzazione immediata* della sequenza che i metodi vengono applicati a:</span><span class="sxs-lookup"><span data-stu-id="ca6f2-255">The following methods cause the *immediate materialization* of the sequence that the methods are applied to:</span></span>  
  
    -   <xref:System.Linq.Enumerable.ToList%2A>  
  
    -   <xref:System.Linq.Enumerable.ToDictionary%2A>  
  
    -   <xref:System.Linq.Enumerable.ToArray%2A>  
  
## <a name="see-also"></a><span data-ttu-id="ca6f2-256">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ca6f2-256">See Also</span></span>  
 [<span data-ttu-id="ca6f2-257">Riferimento</span><span class="sxs-lookup"><span data-stu-id="ca6f2-257">Reference</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)  
 [<span data-ttu-id="ca6f2-258">Restituire o ignorare elementi in una sequenza</span><span class="sxs-lookup"><span data-stu-id="ca6f2-258">Return Or Skip Elements in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-or-skip-elements-in-a-sequence.md)  
 [<span data-ttu-id="ca6f2-259">Concatenare due sequenze</span><span class="sxs-lookup"><span data-stu-id="ca6f2-259">Concatenate Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/concatenate-two-sequences.md)  
 [<span data-ttu-id="ca6f2-260">Restituire la differenza dei set tra due sequenze</span><span class="sxs-lookup"><span data-stu-id="ca6f2-260">Return the Set Difference Between Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-difference-between-two-sequences.md)  
 [<span data-ttu-id="ca6f2-261">Restituire l'intersezione tra set di due sequenze</span><span class="sxs-lookup"><span data-stu-id="ca6f2-261">Return the Set Intersection of Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-intersection-of-two-sequences.md)  
 [<span data-ttu-id="ca6f2-262">Restituire l'unione di set di due sequenze</span><span class="sxs-lookup"><span data-stu-id="ca6f2-262">Return the Set Union of Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-union-of-two-sequences.md)
