---
title: 'Procedura: Eliminare gli archivi nello spazio di memorizzazione isolato'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- stores, deleting
- data stores, deleting
- deleting stores
- removing stores
- isolated storage, deleting stores
- storing data using isolated storage, deleting stores
- data storage using isolated storage, deleting stores
ms.assetid: 3947e333-5af6-4601-b2f1-24d4d6129cf3
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 776984cf1cc17d5c1becc91d4491fa6dbc9e2c17
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33572327"
---
# <a name="how-to-delete-stores-in-isolated-storage"></a>Procedura: Eliminare gli archivi nello spazio di memorizzazione isolato
La classe <xref:System.IO.IsolatedStorage.IsolatedStorageFile> fornisce due metodi per eliminare i file dello spazio di memorizzazione isolato:  
  
-   Il metodo di istanza <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove> non accetta argomenti ed elimina l'archivio che lo chiama. Non sono necessarie autorizzazioni per questa operazione. Il codice che può accedere all'archivio può eliminare alcuni o tutti i dati in esso contenuti.  
  
-   Il metodo statico <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove%28System.IO.IsolatedStorage.IsolatedStorageScope%29> accetta il valore di enumerazione <xref:System.IO.IsolatedStorage.IsolatedStorageScope.User> ed elimina tutti gli archivi per l'utente che esegue il codice. Questa operazione richiede l'autorizzazione <xref:System.Security.Permissions.IsolatedStorageFilePermission> per il valore <xref:System.Security.Permissions.IsolatedStorageContainment.AdministerIsolatedStorageByUser> .  
  
## <a name="example"></a>Esempio  
 L'esempio di codice seguente illustra l'uso dei metodi <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove%2A> statici e di istanza. La classe ottiene due archivi, uno isolato per utente e assembly e l'altro isolato per utente, dominio e assembly. L'archivio utente, di dominio e di assembly viene quindi eliminato chiamando il metodo <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove> del file dello spazio di memorizzazione isolato  `isoStore1`. Tutti gli archivi rimanenti per l'utente vengono quindi eliminati chiamando il metodo statico <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove%28System.IO.IsolatedStorage.IsolatedStorageScope%29>.  
  
 [!code-cpp[Conceptual.IsolatedStorage#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source3.cpp#3)]
 [!code-csharp[Conceptual.IsolatedStorage#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source3.cs#3)]
 [!code-vb[Conceptual.IsolatedStorage#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source3.vb#3)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 [Spazio di memorizzazione isolato](../../../docs/standard/io/isolated-storage.md)
