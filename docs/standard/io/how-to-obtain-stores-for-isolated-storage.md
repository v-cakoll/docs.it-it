---
title: 'Procedura: Recuperare archivi per lo spazio di memorizzazione isolato'
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
- stores, obtaining
- storing data using isolated storage, obtaining stores
- isolated storage, obtaining stores
- data stores, obtaining
- data storage using isolated storage, obtaining stores
ms.assetid: fcb6b178-d526-47c4-b029-e946f880f9db
caps.latest.revision: "19"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bb0b877aa0f4cee36bd1f8c1cea624cf9368fbaa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-obtain-stores-for-isolated-storage"></a>Procedura: Recuperare archivi per lo spazio di memorizzazione isolato
Un archivio isolato espone un file system virtuale all'interno di un raggruppamento di dati. La <xref:System.IO.IsolatedStorage.IsolatedStorageFile> classe fornisce numerosi metodi per interagire con un archivio isolato. Per creare e recuperare archivi, <xref:System.IO.IsolatedStorage.IsolatedStorageFile> fornisce tre metodi statici:  
  
-   <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>Restituisce lo spazio di archiviazione è isolata dall'utente e all'assembly.  
  
-   <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>Restituisce spazio di archiviazione è isolato dal dominio e assembly.  
  
     Entrambi i metodi di recuperano un archivio a cui appartiene il codice da cui vengono chiamati.  
  
-   Il metodo statico <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> restituisce un archivio isolato che viene specificato tramite il passaggio di una combinazione di parametri di ambito.  
  
 Il codice seguente restituisce un archivio isolato in base a utente, l'assembly e dominio.  
  
 [!code-cpp[Conceptual.IsolatedStorage#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source6.cpp#6)]
 [!code-csharp[Conceptual.IsolatedStorage#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source6.cs#6)]
 [!code-vb[Conceptual.IsolatedStorage#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source6.vb#6)]  
  
 È possibile utilizzare il <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> per specificare che un archivio deve effettuare il roaming con un profilo utente mobile. Per informazioni dettagliate su come specificare questa impostazione, vedere [tipi di isolamento](../../../docs/standard/io/types-of-isolation.md).  
  
 Archivi isolati ottenuti da assembly diversi sono, per impostazione predefinita, archivi diversi. È possibile accedere all'archivio di un dominio o un assembly diverso passando l'evidenza del dominio o di assembly nei parametri del <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> metodo. È necessaria l'autorizzazione per accedere all'archiviazione isolata dall'identità del dominio applicazione. Per ulteriori informazioni, vedere il <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> overload del metodo.  
  
 Il <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>, e <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> i metodi restituiscono un <xref:System.IO.IsolatedStorage.IsolatedStorageFile> oggetto. Per decidere quale tipo di isolamento è più adatto alle proprie esigenze, vedere [tipi di isolamento](../../../docs/standard/io/types-of-isolation.md). Quando si dispone di un oggetto di file di memorizzazione isolato, è possibile utilizzare i metodi di memorizzazione isolato per lettura, scrittura, creare ed eliminare file e directory.  
  
 Non è disponibile alcun meccanismo che impedisce il passaggio di codice un <xref:System.IO.IsolatedStorage.IsolatedStorageFile> oggetto a codice che non dispone di accesso sufficienti per ottenere l'archivio. Le identità di dominio e assembly e le autorizzazioni di memorizzazione isolato vengono controllate solo quando un riferimento a un <xref:System.IO.IsolatedStorage.IsolatedStorage> viene ottenuto l'oggetto, in genere nel <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>, o <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> metodo. La protezione dei riferimenti a <xref:System.IO.IsolatedStorage.IsolatedStorageFile> oggetti consiste, pertanto, la responsabilità del codice che utilizza tali riferimenti.  
  
## <a name="example"></a>Esempio  
 Il codice seguente fornisce un esempio semplice di una classe di ottenere un archivio isolato in base a utente e all'assembly. Possibile modificare il codice per recuperare un archivio isolato dall'utente, dominio e assembly aggiungendo <xref:System.IO.IsolatedStorage.IsolatedStorageScope.Domain?displayProperty=nameWithType> agli argomenti che la <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> metodo passate.  
  
 Dopo aver eseguito il codice, è possibile verificare che l'archivio è stato creato digitando **StoreAdm /LIST** nella riga di comando. Viene eseguita la [strumento spazio di memorizzazione isolato (Storeadm.exe)](../../../docs/framework/tools/storeadm-exe-isolated-storage-tool.md) e vengono elencati tutti gli archivi isolati correnti per l'utente.  
  
 [!code-cpp[Conceptual.IsolatedStorage#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source6.cpp#7)]
 [!code-csharp[Conceptual.IsolatedStorage#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source6.cs#7)]
 [!code-vb[Conceptual.IsolatedStorage#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source6.vb#7)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageScope>  
 [Spazio di memorizzazione isolato](../../../docs/standard/io/isolated-storage.md)  
 [Tipi di isolamento](../../../docs/standard/io/types-of-isolation.md)  
 [Assembly in Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
