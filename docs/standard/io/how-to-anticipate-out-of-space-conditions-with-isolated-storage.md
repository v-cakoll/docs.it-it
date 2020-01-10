---
title: 'Procedura: Anticipare le condizioni di spazio insufficiente con lo spazio di memorizzazione isolato'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data stores, quotas
- isolated storage, quotas
- quantity of isolated storage used
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
ms.openlocfilehash: 5666019e1a65880221261ef5ad704f82c37263b2
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708115"
---
# <a name="how-to-anticipate-out-of-space-conditions-with-isolated-storage"></a><span data-ttu-id="aae55-102">Procedura: Anticipare le condizioni di spazio insufficiente con lo spazio di memorizzazione isolato</span><span class="sxs-lookup"><span data-stu-id="aae55-102">How to: Anticipate Out-of-Space Conditions with Isolated Storage</span></span>

<span data-ttu-id="aae55-103">Il codice che usa lo spazio di memorizzazione isolato è vincolato da una [quota](../../../docs/standard/io/isolated-storage.md#quotas) che specifica la dimensione massima per il raggruppamento dati in cui si trovano file e directory dello spazio di memorizzazione isolato.</span><span class="sxs-lookup"><span data-stu-id="aae55-103">Code that uses isolated storage is constrained by a [quota](../../../docs/standard/io/isolated-storage.md#quotas) that specifies the maximum size for the data compartment in which isolated storage files and directories exist.</span></span> <span data-ttu-id="aae55-104">La quota è definita da criteri di sicurezza e può essere configurata dagli amministratori.</span><span class="sxs-lookup"><span data-stu-id="aae55-104">The quota is defined by security policy and is configurable by administrators.</span></span> <span data-ttu-id="aae55-105">Se la dimensione massima consentita viene superata quando si prova a scrivere dati, viene generata un'eccezione <xref:System.IO.IsolatedStorage.IsolatedStorageException> e l'operazione non riesce.</span><span class="sxs-lookup"><span data-stu-id="aae55-105">If the maximum allowed size is exceeded when you try to write data, an <xref:System.IO.IsolatedStorage.IsolatedStorageException> exception is thrown and the operation fails.</span></span> <span data-ttu-id="aae55-106">In questo modo, è possibile impedire attacchi Denial of Service dannosi che possono causare il rifiuto delle richieste da parte dell'applicazione perché l'archivio dati è pieno.</span><span class="sxs-lookup"><span data-stu-id="aae55-106">This helps prevent malicious denial-of-service attacks that could cause the application to refuse requests because data storage is filled.</span></span>

<span data-ttu-id="aae55-107">Per determinare se un tentativo di scrittura specifico rischia di non riuscire per questo motivo, la classe <xref:System.IO.IsolatedStorage.IsolatedStorage> fornisce tre proprietà di sola lettura: <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorage.UsedSize%2A> e <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A>.</span><span class="sxs-lookup"><span data-stu-id="aae55-107">To help you determine whether a given write attempt is likely to fail for this reason, the <xref:System.IO.IsolatedStorage.IsolatedStorage> class provides three read-only properties: <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorage.UsedSize%2A>, and <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A>.</span></span> <span data-ttu-id="aae55-108">È possibile usare queste proprietà per determinare se la scrittura nell'archivio provocherà il superamento della dimensione massima consentita.</span><span class="sxs-lookup"><span data-stu-id="aae55-108">You can use these properties to determine whether writing to the store will cause the maximum allowed size of the store to be exceeded.</span></span> <span data-ttu-id="aae55-109">Tenere presente che lo spazio di memorizzazione isolato è accessibile simultaneamente. Di conseguenza, quando si calcola la quantità di archiviazione rimanente, lo spazio di memorizzazione potrebbe essere già completamente utilizzato quando si tenta di scrivere nell'archivio.</span><span class="sxs-lookup"><span data-stu-id="aae55-109">Keep in mind that isolated storage can be accessed concurrently; therefore, when you compute the amount of remaining storage, the storage space could be consumed by the time you try to write to the store.</span></span> <span data-ttu-id="aae55-110">Tuttavia, è possibile usare la dimensione massima dell'archivio per determinare se sta per essere raggiunto il limite superiore di archiviazione disponibile.</span><span class="sxs-lookup"><span data-stu-id="aae55-110">However, you can use the maximum size of the store to help determine whether the upper limit on available storage is about to be reached.</span></span>

<span data-ttu-id="aae55-111">La proprietà <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A> dipende dall'evidenza dall'assembly per il corretto funzionamento.</span><span class="sxs-lookup"><span data-stu-id="aae55-111">The <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A> property depends on evidence from the assembly to work properly.</span></span> <span data-ttu-id="aae55-112">Per questo motivo, è necessario recuperare questa proprietà solo in oggetti <xref:System.IO.IsolatedStorage.IsolatedStorageFile> creati usando il metodo <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A> o <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>.</span><span class="sxs-lookup"><span data-stu-id="aae55-112">For this reason, you should retrieve this property only on <xref:System.IO.IsolatedStorage.IsolatedStorageFile> objects that were created by using the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>, or <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> method.</span></span> <span data-ttu-id="aae55-113">Gli oggetti <xref:System.IO.IsolatedStorage.IsolatedStorageFile> creati in un altro modo, ad esempio gli oggetti restituiti dal metodo <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A>, non restituiscono una dimensione massima precisa.</span><span class="sxs-lookup"><span data-stu-id="aae55-113"><xref:System.IO.IsolatedStorage.IsolatedStorageFile> objects that were created in any other way (for example, objects that were returned from the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> method) will not return an accurate maximum size.</span></span>

## <a name="example"></a><span data-ttu-id="aae55-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="aae55-114">Example</span></span>

<span data-ttu-id="aae55-115">L'esempio di codice seguente ottiene uno spazio di memorizzazione isolato, crea nuovi file e recupera la proprietà <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A>.</span><span class="sxs-lookup"><span data-stu-id="aae55-115">The following code example obtains an isolated store, creates a few files, and retrieves the <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A> property.</span></span> <span data-ttu-id="aae55-116">Lo spazio rimanente viene indicato in byte.</span><span class="sxs-lookup"><span data-stu-id="aae55-116">The remaining space is reported in bytes.</span></span>

[!code-cpp[Conceptual.IsolatedStorage#8](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source7.cpp#8)]
[!code-csharp[Conceptual.IsolatedStorage#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source7.cs#8)]
[!code-vb[Conceptual.IsolatedStorage#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source7.vb#8)]

## <a name="see-also"></a><span data-ttu-id="aae55-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aae55-117">See also</span></span>

- <xref:System.IO.IsolatedStorage.IsolatedStorageFile>
- [<span data-ttu-id="aae55-118">Spazio di memorizzazione isolato</span><span class="sxs-lookup"><span data-stu-id="aae55-118">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)
- [<span data-ttu-id="aae55-119">Procedura: Recuperare archivi per lo spazio di memorizzazione isolato</span><span class="sxs-lookup"><span data-stu-id="aae55-119">How to: Obtain Stores for Isolated Storage</span></span>](../../../docs/standard/io/how-to-obtain-stores-for-isolated-storage.md)
