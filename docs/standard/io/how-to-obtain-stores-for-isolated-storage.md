---
title: 'Procedura: Recuperare archivi per lo spazio di memorizzazione isolato'
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
ms.openlocfilehash: 7104ba665f60c2d55217a2d8628c85f6e469ad6f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "75706931"
---
# <a name="how-to-obtain-stores-for-isolated-storage"></a>Procedura: Recuperare archivi per lo spazio di memorizzazione isolato
Un archivio isolato espone un file system virtuale all'interno di un raggruppamento dati. La classe <xref:System.IO.IsolatedStorage.IsolatedStorageFile> fornisce numerosi metodi per l'interazione con un archivio isolato. Per creare e recuperare archivi, <xref:System.IO.IsolatedStorage.IsolatedStorageFile> fornisce tre metodi statici:  
  
- <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A> restituisce lo spazio di archiviazione isolato in base a utente e assembly.  
  
- <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A> restituisce lo spazio di archiviazione isolato in base a dominio e assembly.  
  
     Entrambi i metodi di recuperano un archivio che appartiene al codice da cui vengono chiamati.  
  
- Il metodo statico <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> restituisce un archivio isolato specificato passando una combinazione di parametri di ambito.  
  
 Il codice seguente restituisce un archivio isolato in base a utente, assembly e dominio.  
  
 [!code-cpp[Conceptual.IsolatedStorage#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source6.cpp#6)]
 [!code-csharp[Conceptual.IsolatedStorage#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source6.cs#6)]
 [!code-vb[Conceptual.IsolatedStorage#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source6.vb#6)]  
  
 È possibile usare il metodo <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> per specificare che un archivio deve effettuare il roaming con un profilo utente mobile. Per informazioni dettagliate su come specificare questa configurazione, vedere [Tipi di isolamento](../../../docs/standard/io/types-of-isolation.md).  
  
 Gli archivi isolati ottenuti da assembly diversi sono, per impostazione predefinita, archivi diversi. È possibile accedere all'archivio di un dominio o un assembly diverso passando l'evidenza del dominio o dell'assembly nei parametri del metodo <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>. È necessaria l'autorizzazione per accedere allo spazio di memorizzazione isolato tramite l'identità del dominio dell'applicazione. Per altre informazioni, vedere gli overload del metodo <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>.  
  
 I metodi <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A> e <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> restituiscono un oggetto <xref:System.IO.IsolatedStorage.IsolatedStorageFile>. Per scegliere il tipo di isolamento più adatto alle proprie esigenze, vedere [Tipi di isolamento](../../../docs/standard/io/types-of-isolation.md). Quando si ha un oggetto file dello spazio di memorizzazione isolato, è possibile usare i metodi dello spazio di memorizzazione isolato per leggere, scrivere, creare ed eliminare file e directory.  
  
 Non c'è un meccanismo che impedisce di passare un oggetto <xref:System.IO.IsolatedStorage.IsolatedStorageFile> a codice che non ha autorizzazioni di accesso sufficienti per ottenere l'archivio. Le identità di dominio e assembly e le autorizzazioni dello spazio di memorizzazione isolato vengono controllate solo quando viene ottenuto un riferimento a un oggetto <xref:System.IO.IsolatedStorage.IsolatedStorage>, in genere nel metodo <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A> o <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>. Proteggere i riferimenti agli oggetti <xref:System.IO.IsolatedStorage.IsolatedStorageFile> è quindi responsabilità del codice che usa tali riferimenti.  
  
## <a name="example"></a>Esempio  
 Il codice seguente fornisce un semplice esempio di classe che ottiene un archivio isolato in base a utente e assembly. È possibile modificare il codice per recuperare un archivio isolato in base a utente, dominio e assembly aggiungendo <xref:System.IO.IsolatedStorage.IsolatedStorageScope.Domain?displayProperty=nameWithType> agli argomenti passati dal metodo <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>.  
  
 Dopo avere eseguito il codice, è possibile verificare che l'archivio sia stato creato digitando **StoreAdm /LIST** nella riga di comando. In questo modo, viene eseguito lo strumento [Storeadm.exe (strumento per lo spazio di memorizzazione isolato)](../../../docs/framework/tools/storeadm-exe-isolated-storage-tool.md) e vengono elencati tutti gli archivi isolati correnti per l'utente.  
  
 [!code-cpp[Conceptual.IsolatedStorage#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source6.cpp#7)]
 [!code-csharp[Conceptual.IsolatedStorage#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source6.cs#7)]
 [!code-vb[Conceptual.IsolatedStorage#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source6.vb#7)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IO.IsolatedStorage.IsolatedStorageFile>
- <xref:System.IO.IsolatedStorage.IsolatedStorageScope>
- [Archiviazione isolata](../../../docs/standard/io/isolated-storage.md)
- [Tipi di isolamento](../../../docs/standard/io/types-of-isolation.md)
- [Assembly in .NET](../assembly/index.md)
