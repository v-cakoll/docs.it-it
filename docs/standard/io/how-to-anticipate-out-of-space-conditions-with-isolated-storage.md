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
# <a name="how-to-anticipate-out-of-space-conditions-with-isolated-storage"></a>Procedura: Anticipare le condizioni di spazio insufficiente con lo spazio di memorizzazione isolato
Il codice che utilizza l'archiviazione isolata è vincolato da un [quota](../../../docs/standard/io/isolated-storage.md#quotas) che specifica la dimensione massima per il raggruppamento di dati in cui è isolata file di archiviazione e le directory esistano. La quota è definita dai criteri di sicurezza e può essere configurato dagli amministratori. Se il valore massimo consentito viene superata la dimensione quando si tenta di scrivere i dati, un <xref:System.IO.IsolatedStorage.IsolatedStorageException> viene generata un'eccezione e l'operazione non riesce. Ciò aiuta a evitare attacchi di tipo denial of service che potrebbe causare l'applicazione per rifiutare le richieste perché l'archiviazione dei dati viene compilato.  
  
 Per determinare se un determinato tentativo di scrittura è probabilmente esito negativo per questo motivo, il <xref:System.IO.IsolatedStorage.IsolatedStorage> classe fornisce tre proprietà di sola lettura: <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorage.UsedSize%2A>, e <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A>. È possibile utilizzare queste proprietà per determinare se la scrittura nell'archivio sarà la dimensione massima consentita dell'archivio devono essere superati. Tenere presente che lo spazio di memorizzazione isolato è possibile accedere contemporaneamente; Pertanto, quando si calcola la quantità di memoria rimanente, lo spazio di archiviazione poteva essere usato quando che si tenta di scrivere nell'archivio. Tuttavia, è possibile utilizzare le dimensioni massime dell'archivio per informazioni su come determinare se sta per raggiungere il limite di archiviazione disponibile.  
  
 Il <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A> proprietà dipende dall'evidenza dell'assembly per il corretto funzionamento. Per questo motivo, è necessario recuperare questa proprietà solo in <xref:System.IO.IsolatedStorage.IsolatedStorageFile> gli oggetti creati tramite il <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>, o <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> metodo. <xref:System.IO.IsolatedStorage.IsolatedStorageFile>gli oggetti creati in altro modo (ad esempio, gli oggetti restituiti dal <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> metodo) non restituirà una dimensione massima precisa.  
  
## <a name="example"></a>Esempio  
 Esempio di codice seguente ottiene un archivio isolato, vengono creati alcuni file e recupera il <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A> proprietà. Lo spazio rimanente viene indicato in byte.  
  
 [!code-cpp[Conceptual.IsolatedStorage#8](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source7.cpp#8)]
 [!code-csharp[Conceptual.IsolatedStorage#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source7.cs#8)]
 [!code-vb[Conceptual.IsolatedStorage#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source7.vb#8)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 [Spazio di memorizzazione isolato](../../../docs/standard/io/isolated-storage.md)  
 [Procedura: Recuperare archivi per lo spazio di memorizzazione isolato](../../../docs/standard/io/how-to-obtain-stores-for-isolated-storage.md)
