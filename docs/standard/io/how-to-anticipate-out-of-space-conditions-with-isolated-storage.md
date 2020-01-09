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
# <a name="how-to-anticipate-out-of-space-conditions-with-isolated-storage"></a>Procedura: Anticipare le condizioni di spazio insufficiente con lo spazio di memorizzazione isolato

Il codice che usa lo spazio di memorizzazione isolato è vincolato da una [quota](../../../docs/standard/io/isolated-storage.md#quotas) che specifica la dimensione massima per il raggruppamento dati in cui si trovano file e directory dello spazio di memorizzazione isolato. La quota è definita da criteri di sicurezza e può essere configurata dagli amministratori. Se la dimensione massima consentita viene superata quando si prova a scrivere dati, viene generata un'eccezione <xref:System.IO.IsolatedStorage.IsolatedStorageException> e l'operazione non riesce. In questo modo, è possibile impedire attacchi Denial of Service dannosi che possono causare il rifiuto delle richieste da parte dell'applicazione perché l'archivio dati è pieno.

Per determinare se un tentativo di scrittura specifico rischia di non riuscire per questo motivo, la classe <xref:System.IO.IsolatedStorage.IsolatedStorage> fornisce tre proprietà di sola lettura: <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorage.UsedSize%2A> e <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A>. È possibile usare queste proprietà per determinare se la scrittura nell'archivio provocherà il superamento della dimensione massima consentita. Tenere presente che lo spazio di memorizzazione isolato è accessibile simultaneamente. Di conseguenza, quando si calcola la quantità di archiviazione rimanente, lo spazio di memorizzazione potrebbe essere già completamente utilizzato quando si tenta di scrivere nell'archivio. Tuttavia, è possibile usare la dimensione massima dell'archivio per determinare se sta per essere raggiunto il limite superiore di archiviazione disponibile.

La proprietà <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A> dipende dall'evidenza dall'assembly per il corretto funzionamento. Per questo motivo, è necessario recuperare questa proprietà solo in oggetti <xref:System.IO.IsolatedStorage.IsolatedStorageFile> creati usando il metodo <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A> o <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>. Gli oggetti <xref:System.IO.IsolatedStorage.IsolatedStorageFile> creati in un altro modo, ad esempio gli oggetti restituiti dal metodo <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A>, non restituiscono una dimensione massima precisa.

## <a name="example"></a>Esempio

L'esempio di codice seguente ottiene uno spazio di memorizzazione isolato, crea nuovi file e recupera la proprietà <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A>. Lo spazio rimanente viene indicato in byte.

[!code-cpp[Conceptual.IsolatedStorage#8](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source7.cpp#8)]
[!code-csharp[Conceptual.IsolatedStorage#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source7.cs#8)]
[!code-vb[Conceptual.IsolatedStorage#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source7.vb#8)]

## <a name="see-also"></a>Vedere anche

- <xref:System.IO.IsolatedStorage.IsolatedStorageFile>
- [Spazio di memorizzazione isolato](../../../docs/standard/io/isolated-storage.md)
- [Procedura: Recuperare archivi per lo spazio di memorizzazione isolato](../../../docs/standard/io/how-to-obtain-stores-for-isolated-storage.md)
