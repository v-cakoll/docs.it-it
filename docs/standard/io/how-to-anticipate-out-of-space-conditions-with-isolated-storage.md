---
title: 'Procedura: Anticipare le condizioni di spazio insufficiente con lo spazio di memorizzazione isolato'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data stores, quotas
- isolated storage, quotas
- quanitity of isolated storage used
- limit on isolated storage used
- stores, quotas
- stores, out of space conditions
- data storage using isolated storage, quotas
- storing data using isolated storage, quotas
- space remaining in isolated storage
- data stores, out of space conditions
- storing data using isolated storage, out of space conditions
- quotas for isolated storage
- isolated storage, out of space conditions
- data storage using isolated storage, out of space conditions
ms.assetid: e35d4535-3732-421e-b1a3-37412e036145
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d813522d0aeb9bf37582c167760d44268df27039
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-anticipate-out-of-space-conditions-with-isolated-storage"></a><span data-ttu-id="7033d-102">Procedura: Anticipare le condizioni di spazio insufficiente con lo spazio di memorizzazione isolato</span><span class="sxs-lookup"><span data-stu-id="7033d-102">How to: Anticipate Out-of-Space Conditions with Isolated Storage</span></span>
<span data-ttu-id="7033d-103">Il codice che utilizza l'archiviazione isolata è vincolato da un [quota](../../../docs/standard/io/isolated-storage.md#quotas) che specifica la dimensione massima per il raggruppamento di dati in cui è isolata file di archiviazione e le directory esistano.</span><span class="sxs-lookup"><span data-stu-id="7033d-103">Code that uses isolated storage is constrained by a [quota](../../../docs/standard/io/isolated-storage.md#quotas) that specifies the maximum size for the data compartment in which isolated storage files and directories exist.</span></span> <span data-ttu-id="7033d-104">La quota è definita dai criteri di sicurezza e può essere configurato dagli amministratori.</span><span class="sxs-lookup"><span data-stu-id="7033d-104">The quota is defined by security policy and is configurable by administrators.</span></span> <span data-ttu-id="7033d-105">Se il valore massimo consentito viene superata la dimensione quando si tenta di scrivere i dati, un <xref:System.IO.IsolatedStorage.IsolatedStorageException> viene generata un'eccezione e l'operazione non riesce.</span><span class="sxs-lookup"><span data-stu-id="7033d-105">If the maximum allowed size is exceeded when you try to write data, an <xref:System.IO.IsolatedStorage.IsolatedStorageException> exception is thrown and the operation fails.</span></span> <span data-ttu-id="7033d-106">Ciò aiuta a evitare attacchi di tipo denial of service che potrebbe causare l'applicazione per rifiutare le richieste perché l'archiviazione dei dati viene compilato.</span><span class="sxs-lookup"><span data-stu-id="7033d-106">This helps prevent malicious denial-of-service attacks that could cause the application to refuse requests because data storage is filled.</span></span>  
  
 <span data-ttu-id="7033d-107">Per determinare se un determinato tentativo di scrittura è probabilmente esito negativo per questo motivo, il <xref:System.IO.IsolatedStorage.IsolatedStorage> classe fornisce tre proprietà di sola lettura: <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorage.UsedSize%2A>, e <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A>.</span><span class="sxs-lookup"><span data-stu-id="7033d-107">To help you determine whether a given write attempt is likely to fail for this reason, the <xref:System.IO.IsolatedStorage.IsolatedStorage> class provides three read-only properties: <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorage.UsedSize%2A>, and <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A>.</span></span> <span data-ttu-id="7033d-108">È possibile utilizzare queste proprietà per determinare se la scrittura nell'archivio sarà la dimensione massima consentita dell'archivio devono essere superati.</span><span class="sxs-lookup"><span data-stu-id="7033d-108">You can use these properties to determine whether writing to the store will cause the maximum allowed size of the store to be exceeded.</span></span> <span data-ttu-id="7033d-109">Tenere presente che lo spazio di memorizzazione isolato è possibile accedere contemporaneamente; Pertanto, quando si calcola la quantità di memoria rimanente, lo spazio di archiviazione poteva essere usato quando che si tenta di scrivere nell'archivio.</span><span class="sxs-lookup"><span data-stu-id="7033d-109">Keep in mind that isolated storage can be accessed concurrently; therefore, when you compute the amount of remaining storage, the storage space could be consumed by the time you try to write to the store.</span></span> <span data-ttu-id="7033d-110">Tuttavia, è possibile utilizzare le dimensioni massime dell'archivio per informazioni su come determinare se sta per raggiungere il limite di archiviazione disponibile.</span><span class="sxs-lookup"><span data-stu-id="7033d-110">However, you can use the maximum size of the store to help determine whether the upper limit on available storage is about to be reached.</span></span>  
  
 <span data-ttu-id="7033d-111">Il <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A> proprietà dipende dall'evidenza dell'assembly per il corretto funzionamento.</span><span class="sxs-lookup"><span data-stu-id="7033d-111">The <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A> property depends on evidence from the assembly to work properly.</span></span> <span data-ttu-id="7033d-112">Per questo motivo, è necessario recuperare questa proprietà solo in <xref:System.IO.IsolatedStorage.IsolatedStorageFile> gli oggetti creati tramite il <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>, o <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="7033d-112">For this reason, you should retrieve this property only on <xref:System.IO.IsolatedStorage.IsolatedStorageFile> objects that were created by using the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>, or <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> method.</span></span> <span data-ttu-id="7033d-113"><xref:System.IO.IsolatedStorage.IsolatedStorageFile>gli oggetti creati in altro modo (ad esempio, gli oggetti restituiti dal <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> metodo) non restituirà una dimensione massima precisa.</span><span class="sxs-lookup"><span data-stu-id="7033d-113"><xref:System.IO.IsolatedStorage.IsolatedStorageFile> objects that were created in any other way (for example, objects that were returned from the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> method) will not return an accurate maximum size.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7033d-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="7033d-114">Example</span></span>  
 <span data-ttu-id="7033d-115">Esempio di codice seguente ottiene un archivio isolato, vengono creati alcuni file e recupera il <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="7033d-115">The following code example obtains an isolated store, creates a few files, and retrieves the <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A> property.</span></span> <span data-ttu-id="7033d-116">Lo spazio rimanente viene indicato in byte.</span><span class="sxs-lookup"><span data-stu-id="7033d-116">The remaining space is reported in bytes.</span></span>  
  
 [!code-cpp[Conceptual.IsolatedStorage#8](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source7.cpp#8)]
 [!code-csharp[Conceptual.IsolatedStorage#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source7.cs#8)]
 [!code-vb[Conceptual.IsolatedStorage#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source7.vb#8)]  
  
## <a name="see-also"></a><span data-ttu-id="7033d-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7033d-117">See Also</span></span>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 [<span data-ttu-id="7033d-118">Spazio di memorizzazione isolato</span><span class="sxs-lookup"><span data-stu-id="7033d-118">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)  
 [<span data-ttu-id="7033d-119">Procedura: Recuperare archivi per lo spazio di memorizzazione isolato</span><span class="sxs-lookup"><span data-stu-id="7033d-119">How to: Obtain Stores for Isolated Storage</span></span>](../../../docs/standard/io/how-to-obtain-stores-for-isolated-storage.md)
