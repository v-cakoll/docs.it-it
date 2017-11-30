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
# <a name="how-to-obtain-stores-for-isolated-storage"></a><span data-ttu-id="0bbb2-102">Procedura: Recuperare archivi per lo spazio di memorizzazione isolato</span><span class="sxs-lookup"><span data-stu-id="0bbb2-102">How to: Obtain Stores for Isolated Storage</span></span>
<span data-ttu-id="0bbb2-103">Un archivio isolato espone un file system virtuale all'interno di un raggruppamento di dati.</span><span class="sxs-lookup"><span data-stu-id="0bbb2-103">An isolated store exposes a virtual file system within a data compartment.</span></span> <span data-ttu-id="0bbb2-104">La <xref:System.IO.IsolatedStorage.IsolatedStorageFile> classe fornisce numerosi metodi per interagire con un archivio isolato.</span><span class="sxs-lookup"><span data-stu-id="0bbb2-104">The <xref:System.IO.IsolatedStorage.IsolatedStorageFile> class supplies a number of methods for interacting with an isolated store.</span></span> <span data-ttu-id="0bbb2-105">Per creare e recuperare archivi, <xref:System.IO.IsolatedStorage.IsolatedStorageFile> fornisce tre metodi statici:</span><span class="sxs-lookup"><span data-stu-id="0bbb2-105">To create and retrieve stores, <xref:System.IO.IsolatedStorage.IsolatedStorageFile> provides three static methods:</span></span>  
  
-   <span data-ttu-id="0bbb2-106"><xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>Restituisce lo spazio di archiviazione è isolata dall'utente e all'assembly.</span><span class="sxs-lookup"><span data-stu-id="0bbb2-106"><xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A> returns storage that is isolated by user and assembly.</span></span>  
  
-   <span data-ttu-id="0bbb2-107"><xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>Restituisce spazio di archiviazione è isolato dal dominio e assembly.</span><span class="sxs-lookup"><span data-stu-id="0bbb2-107"><xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A> returns storage that is isolated by domain and assembly.</span></span>  
  
     <span data-ttu-id="0bbb2-108">Entrambi i metodi di recuperano un archivio a cui appartiene il codice da cui vengono chiamati.</span><span class="sxs-lookup"><span data-stu-id="0bbb2-108">Both methods retrieve a store that belongs to the code from which they are called.</span></span>  
  
-   <span data-ttu-id="0bbb2-109">Il metodo statico <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> restituisce un archivio isolato che viene specificato tramite il passaggio di una combinazione di parametri di ambito.</span><span class="sxs-lookup"><span data-stu-id="0bbb2-109">The static method <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> returns an isolated store that is specified by passing in a combination of scope parameters.</span></span>  
  
 <span data-ttu-id="0bbb2-110">Il codice seguente restituisce un archivio isolato in base a utente, l'assembly e dominio.</span><span class="sxs-lookup"><span data-stu-id="0bbb2-110">The following code returns a store that is isolated by user, assembly, and domain.</span></span>  
  
 [!code-cpp[Conceptual.IsolatedStorage#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source6.cpp#6)]
 [!code-csharp[Conceptual.IsolatedStorage#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source6.cs#6)]
 [!code-vb[Conceptual.IsolatedStorage#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source6.vb#6)]  
  
 <span data-ttu-id="0bbb2-111">È possibile utilizzare il <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> per specificare che un archivio deve effettuare il roaming con un profilo utente mobile.</span><span class="sxs-lookup"><span data-stu-id="0bbb2-111">You can use the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> method to specify that a store should roam with a roaming user profile.</span></span> <span data-ttu-id="0bbb2-112">Per informazioni dettagliate su come specificare questa impostazione, vedere [tipi di isolamento](../../../docs/standard/io/types-of-isolation.md).</span><span class="sxs-lookup"><span data-stu-id="0bbb2-112">For details on how to set this up, see [Types of Isolation](../../../docs/standard/io/types-of-isolation.md).</span></span>  
  
 <span data-ttu-id="0bbb2-113">Archivi isolati ottenuti da assembly diversi sono, per impostazione predefinita, archivi diversi.</span><span class="sxs-lookup"><span data-stu-id="0bbb2-113">Isolated stores obtained from within different assemblies are, by default, different stores.</span></span> <span data-ttu-id="0bbb2-114">È possibile accedere all'archivio di un dominio o un assembly diverso passando l'evidenza del dominio o di assembly nei parametri del <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="0bbb2-114">You can access the store of a different assembly or domain by passing in the assembly or domain evidence in the parameters of the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> method.</span></span> <span data-ttu-id="0bbb2-115">È necessaria l'autorizzazione per accedere all'archiviazione isolata dall'identità del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="0bbb2-115">This requires permission to access isolated storage by application domain identity.</span></span> <span data-ttu-id="0bbb2-116">Per ulteriori informazioni, vedere il <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> overload del metodo.</span><span class="sxs-lookup"><span data-stu-id="0bbb2-116">For more information, see the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> method overloads.</span></span>  
  
 <span data-ttu-id="0bbb2-117">Il <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>, e <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> i metodi restituiscono un <xref:System.IO.IsolatedStorage.IsolatedStorageFile> oggetto.</span><span class="sxs-lookup"><span data-stu-id="0bbb2-117">The <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>, and <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> methods return an <xref:System.IO.IsolatedStorage.IsolatedStorageFile> object.</span></span> <span data-ttu-id="0bbb2-118">Per decidere quale tipo di isolamento è più adatto alle proprie esigenze, vedere [tipi di isolamento](../../../docs/standard/io/types-of-isolation.md).</span><span class="sxs-lookup"><span data-stu-id="0bbb2-118">To help you decide which isolation type is most appropriate for your situation, see [Types of Isolation](../../../docs/standard/io/types-of-isolation.md).</span></span> <span data-ttu-id="0bbb2-119">Quando si dispone di un oggetto di file di memorizzazione isolato, è possibile utilizzare i metodi di memorizzazione isolato per lettura, scrittura, creare ed eliminare file e directory.</span><span class="sxs-lookup"><span data-stu-id="0bbb2-119">When you have an isolated storage file object, you can use the isolated storage methods to read, write, create, and delete files and directories.</span></span>  
  
 <span data-ttu-id="0bbb2-120">Non è disponibile alcun meccanismo che impedisce il passaggio di codice un <xref:System.IO.IsolatedStorage.IsolatedStorageFile> oggetto a codice che non dispone di accesso sufficienti per ottenere l'archivio.</span><span class="sxs-lookup"><span data-stu-id="0bbb2-120">There is no mechanism that prevents code from passing an <xref:System.IO.IsolatedStorage.IsolatedStorageFile> object to code that does not have sufficient access to get the store itself.</span></span> <span data-ttu-id="0bbb2-121">Le identità di dominio e assembly e le autorizzazioni di memorizzazione isolato vengono controllate solo quando un riferimento a un <xref:System.IO.IsolatedStorage.IsolatedStorage> viene ottenuto l'oggetto, in genere nel <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>, o <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="0bbb2-121">Domain and assembly identities and isolated storage permissions are checked only when a reference to an <xref:System.IO.IsolatedStorage.IsolatedStorage> object is obtained, typically in the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>, or <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> method.</span></span> <span data-ttu-id="0bbb2-122">La protezione dei riferimenti a <xref:System.IO.IsolatedStorage.IsolatedStorageFile> oggetti consiste, pertanto, la responsabilità del codice che utilizza tali riferimenti.</span><span class="sxs-lookup"><span data-stu-id="0bbb2-122">Protecting references to <xref:System.IO.IsolatedStorage.IsolatedStorageFile> objects is, therefore, the responsibility of the code that uses these references.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0bbb2-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="0bbb2-123">Example</span></span>  
 <span data-ttu-id="0bbb2-124">Il codice seguente fornisce un esempio semplice di una classe di ottenere un archivio isolato in base a utente e all'assembly.</span><span class="sxs-lookup"><span data-stu-id="0bbb2-124">The following code provides a simple example of a class obtaining a store that is isolated by user and assembly.</span></span> <span data-ttu-id="0bbb2-125">Possibile modificare il codice per recuperare un archivio isolato dall'utente, dominio e assembly aggiungendo <xref:System.IO.IsolatedStorage.IsolatedStorageScope.Domain?displayProperty=nameWithType> agli argomenti che la <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> metodo passate.</span><span class="sxs-lookup"><span data-stu-id="0bbb2-125">The code can be changed to retrieve a store that is isolated by user, domain, and assembly by adding <xref:System.IO.IsolatedStorage.IsolatedStorageScope.Domain?displayProperty=nameWithType> to the arguments that the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> method passes.</span></span>  
  
 <span data-ttu-id="0bbb2-126">Dopo aver eseguito il codice, è possibile verificare che l'archivio è stato creato digitando **StoreAdm /LIST** nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="0bbb2-126">After you run the code, you can confirm that a store was created by typing **StoreAdm /LIST** at the command line.</span></span> <span data-ttu-id="0bbb2-127">Viene eseguita la [strumento spazio di memorizzazione isolato (Storeadm.exe)](../../../docs/framework/tools/storeadm-exe-isolated-storage-tool.md) e vengono elencati tutti gli archivi isolati correnti per l'utente.</span><span class="sxs-lookup"><span data-stu-id="0bbb2-127">This runs the [Isolated Storage tool (Storeadm.exe)](../../../docs/framework/tools/storeadm-exe-isolated-storage-tool.md) and lists all the current isolated stores for the user.</span></span>  
  
 [!code-cpp[Conceptual.IsolatedStorage#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source6.cpp#7)]
 [!code-csharp[Conceptual.IsolatedStorage#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source6.cs#7)]
 [!code-vb[Conceptual.IsolatedStorage#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source6.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="0bbb2-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0bbb2-128">See Also</span></span>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageScope>  
 [<span data-ttu-id="0bbb2-129">Spazio di memorizzazione isolato</span><span class="sxs-lookup"><span data-stu-id="0bbb2-129">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)  
 [<span data-ttu-id="0bbb2-130">Tipi di isolamento</span><span class="sxs-lookup"><span data-stu-id="0bbb2-130">Types of Isolation</span></span>](../../../docs/standard/io/types-of-isolation.md)  
 [<span data-ttu-id="0bbb2-131">Assembly in Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="0bbb2-131">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
