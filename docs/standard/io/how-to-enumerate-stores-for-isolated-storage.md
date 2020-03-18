---
title: 'Procedura: Enumerare gli archivi per lo spazio di memorizzazione isolato'
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
ms.openlocfilehash: 3ba38093e9e978c89cdb2bb7a584ed9e04c1096d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "75707528"
---
# <a name="how-to-enumerate-stores-for-isolated-storage"></a>Procedura: Enumerare gli archivi per lo spazio di memorizzazione isolato
È possibile enumerare tutti gli archivi isolati dell'utente corrente utilizzando il metodo statico <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A?displayProperty=nameWithType>. Questo metodo accetta un valore <xref:System.IO.IsolatedStorage.IsolatedStorageScope> e restituisce un enumeratore <xref:System.IO.IsolatedStorage.IsolatedStorageFile>. Per enumerare gli archivi, è necessario avere l'autorizzazione <xref:System.Security.Permissions.IsolatedStorageFilePermission> con il valore <xref:System.Security.Permissions.IsolatedStorageContainment.AdministerIsolatedStorageByUser> specificato. Se si chiama il metodo <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> con il valore <xref:System.IO.IsolatedStorage.IsolatedStorageScope.User>, viene restituita una matrice di oggetti <xref:System.IO.IsolatedStorage.IsolatedStorageFile> definiti per l'utente corrente.  
  
## <a name="example"></a>Esempio  
 L'esempio di codice seguente ottiene uno spazio di memorizzazione isolato in base all'utente e all'assembly, crea alcuni file e recupera i file usando il metodo <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A>.  
  
 [!code-csharp[Conceptual.IsolatedStorage#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source2.cs#2)]
 [!code-vb[Conceptual.IsolatedStorage#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source2.vb#2)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IO.IsolatedStorage.IsolatedStorageFile>
- [Archiviazione isolata](../../../docs/standard/io/isolated-storage.md)
