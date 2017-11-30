---
title: 'Procedura: Enumerare gli archivi per lo spazio di memorizzazione isolato'
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
helpviewer_keywords:
- enumerating stores
- data storage using isolated storage, enumerating stores
- storing data using isolated storage, enumerating stores
- stores, enumerating
- isolated storage, enumerating stores
- data stores, enumerating
ms.assetid: 0fcf279a-f241-48f0-8034-2e3d331f1fcb
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8f8863f1d8b3c7f4ed8f65f8f8eb3e8af51b0405
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enumerate-stores-for-isolated-storage"></a>Procedura: Enumerare gli archivi per lo spazio di memorizzazione isolato
È possibile enumerare tutti gli archivi isolati dell'utente corrente utilizzando il metodo statico <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A?displayProperty=nameWithType>. Questo metodo accetta un valore <xref:System.IO.IsolatedStorage.IsolatedStorageScope> e restituisce un enumeratore <xref:System.IO.IsolatedStorage.IsolatedStorageFile>. Per enumerare gli archivi, è necessario disporre di <xref:System.Security.Permissions.IsolatedStorageFilePermission> autorizzazione che specifica il <xref:System.Security.Permissions.IsolatedStorageContainment.AdministerIsolatedStorageByUser> valore. Se si chiama il <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> metodo con il <xref:System.IO.IsolatedStorage.IsolatedStorageScope.User> valore, viene restituita una matrice di <xref:System.IO.IsolatedStorage.IsolatedStorageFile> gli oggetti definiti per l'utente corrente.  
  
## <a name="example"></a>Esempio  
 L'esempio di codice seguente viene ottenuto un archivio che è isolato dall'utente e all'assembly, vengono creati alcuni file e recupera i file utilizzando il <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> metodo.  
  
 [!code-csharp[Conceptual.IsolatedStorage#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source2.cs#2)]
 [!code-vb[Conceptual.IsolatedStorage#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source2.vb#2)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 [Spazio di memorizzazione isolato](../../../docs/standard/io/isolated-storage.md)
