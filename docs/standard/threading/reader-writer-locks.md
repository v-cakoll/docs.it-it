---
title: Blocchi in lettura/scrittura
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ReaderWriterLock class, about ReaderWriterLock class
- threading [.NET Framework], ReaderWriterLock class
ms.assetid: 8c71acf2-2c18-4f4d-8cdb-0728639265fd
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: df06e83165906199774f99de4140ace9b7396cbb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="reader-writer-locks"></a><span data-ttu-id="96b28-102">Blocchi in lettura/scrittura</span><span class="sxs-lookup"><span data-stu-id="96b28-102">Reader-Writer Locks</span></span>
<span data-ttu-id="96b28-103">La <xref:System.Threading.ReaderWriterLockSlim> classe consente la lettura di una risorsa contemporaneamente più thread, ma richiede un thread rimanga in attesa di un blocco esclusivo per scrivere la risorsa.</span><span class="sxs-lookup"><span data-stu-id="96b28-103">The <xref:System.Threading.ReaderWriterLockSlim> class enables multiple threads to read a resource concurrently, but requires a thread to wait for an exclusive lock in order to write to the resource.</span></span>  
  
 <span data-ttu-id="96b28-104">È possibile utilizzare un <xref:System.Threading.ReaderWriterLockSlim> nell'applicazione per la sincronizzazione cooperativa tra i thread che accedono a una risorsa condivisa.</span><span class="sxs-lookup"><span data-stu-id="96b28-104">You might use a <xref:System.Threading.ReaderWriterLockSlim> in your application to provide cooperative synchronization among threads that access a shared resource.</span></span> <span data-ttu-id="96b28-105">Cui vengono acquisiti blocchi di <xref:System.Threading.ReaderWriterLockSlim> stesso.</span><span class="sxs-lookup"><span data-stu-id="96b28-105">Locks are taken on the <xref:System.Threading.ReaderWriterLockSlim> itself.</span></span>  
  
 <span data-ttu-id="96b28-106">Come con qualsiasi meccanismo di sincronizzazione di thread, è necessario assicurarsi che nessun thread ignori il blocco causato da <xref:System.Threading.ReaderWriterLockSlim>.</span><span class="sxs-lookup"><span data-stu-id="96b28-106">As with any thread synchronization mechanism, you must ensure that no threads bypass the locking that is provided by <xref:System.Threading.ReaderWriterLockSlim>.</span></span> <span data-ttu-id="96b28-107">Un modo per assicurare ciò consiste nel progettare una classe che incapsula la risorsa condivisa.</span><span class="sxs-lookup"><span data-stu-id="96b28-107">One way to ensure this is to design a class that encapsulates the shared resource.</span></span> <span data-ttu-id="96b28-108">Questa classe fornisce membri che accedono alla risorsa condivisa privata e che utilizzano un oggetto privato <xref:System.Threading.ReaderWriterLockSlim> per la sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="96b28-108">This class would provide members that access the private shared resource and that use a private <xref:System.Threading.ReaderWriterLockSlim> for synchronization.</span></span> <span data-ttu-id="96b28-109">Per un esempio, vedere l'esempio di codice per la <xref:System.Threading.ReaderWriterLockSlim> classe.</span><span class="sxs-lookup"><span data-stu-id="96b28-109">For an example, see the code example for the <xref:System.Threading.ReaderWriterLockSlim> class.</span></span> <span data-ttu-id="96b28-110"><xref:System.Threading.ReaderWriterLockSlim>è abbastanza efficace da utilizzare per sincronizzare i singoli oggetti.</span><span class="sxs-lookup"><span data-stu-id="96b28-110"><xref:System.Threading.ReaderWriterLockSlim> is efficient enough to be used to synchronize individual objects.</span></span>  
  
 <span data-ttu-id="96b28-111">Strutturare l'applicazione per ridurre al minimo la durata di lettura e operazioni di scrittura.</span><span class="sxs-lookup"><span data-stu-id="96b28-111">Structure your application to minimize the duration of read and write operations.</span></span> <span data-ttu-id="96b28-112">Le operazioni di scrittura lungo influiscono sulla velocità effettiva direttamente perché il blocco di scrittura è esclusivo.</span><span class="sxs-lookup"><span data-stu-id="96b28-112">Long write operations affect throughput directly because the write lock is exclusive.</span></span> <span data-ttu-id="96b28-113">Writer in attesa di blocco operazioni di lettura lunghe e almeno un thread è in attesa per l'accesso in scrittura, verranno bloccati anche i thread che richiedono l'accesso in lettura.</span><span class="sxs-lookup"><span data-stu-id="96b28-113">Long read operations block waiting writers, and if at least one thread is waiting for write access, threads that request read access will be blocked as well.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="96b28-114">Il [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] presenta due blocchi di lettura / scrittura, <xref:System.Threading.ReaderWriterLockSlim> e <xref:System.Threading.ReaderWriterLock>.</span><span class="sxs-lookup"><span data-stu-id="96b28-114">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] has two reader-writer locks, <xref:System.Threading.ReaderWriterLockSlim> and <xref:System.Threading.ReaderWriterLock>.</span></span> <span data-ttu-id="96b28-115"><xref:System.Threading.ReaderWriterLockSlim>è consigliato per lo sviluppo di nuovo.</span><span class="sxs-lookup"><span data-stu-id="96b28-115"><xref:System.Threading.ReaderWriterLockSlim> is recommended for all new development.</span></span> <span data-ttu-id="96b28-116"><xref:System.Threading.ReaderWriterLockSlim>è simile a <xref:System.Threading.ReaderWriterLock>, ma ha regole per la ricorsione e per l'aggiornamento e il downgrade dello stato del blocco semplificate.</span><span class="sxs-lookup"><span data-stu-id="96b28-116"><xref:System.Threading.ReaderWriterLockSlim> is similar to <xref:System.Threading.ReaderWriterLock>, but it has simplified rules for recursion and for upgrading and downgrading lock state.</span></span> <span data-ttu-id="96b28-117"><xref:System.Threading.ReaderWriterLockSlim>evita molti casi di potenziale deadlock.</span><span class="sxs-lookup"><span data-stu-id="96b28-117"><xref:System.Threading.ReaderWriterLockSlim> avoids many cases of potential deadlock.</span></span> <span data-ttu-id="96b28-118">Inoltre, le prestazioni di <xref:System.Threading.ReaderWriterLockSlim> è significativamente migliore di <xref:System.Threading.ReaderWriterLock>.</span><span class="sxs-lookup"><span data-stu-id="96b28-118">In addition, the performance of <xref:System.Threading.ReaderWriterLockSlim> is significantly better than <xref:System.Threading.ReaderWriterLock>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96b28-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="96b28-119">See Also</span></span>  
 <xref:System.Threading.ReaderWriterLockSlim>  
 <xref:System.Threading.ReaderWriterLock>  
 [<span data-ttu-id="96b28-120">Threading</span><span class="sxs-lookup"><span data-stu-id="96b28-120">Threading</span></span>](../../../docs/standard/threading/index.md)  
 <span data-ttu-id="96b28-121">[Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md) (Oggetti e funzionalità del threading)</span><span class="sxs-lookup"><span data-stu-id="96b28-121">[Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)</span></span>
