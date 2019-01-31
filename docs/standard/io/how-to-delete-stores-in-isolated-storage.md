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
ms.openlocfilehash: 19a671cac609e79088956ecb4324ebb0a25fb941
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54547399"
---
# <a name="how-to-delete-stores-in-isolated-storage"></a><span data-ttu-id="1b52a-102">Procedura: Eliminare gli archivi nello spazio di memorizzazione isolato</span><span class="sxs-lookup"><span data-stu-id="1b52a-102">How to: Delete Stores in Isolated Storage</span></span>
<span data-ttu-id="1b52a-103">La classe <xref:System.IO.IsolatedStorage.IsolatedStorageFile> fornisce due metodi per eliminare i file dello spazio di memorizzazione isolato:</span><span class="sxs-lookup"><span data-stu-id="1b52a-103">The <xref:System.IO.IsolatedStorage.IsolatedStorageFile> class supplies two methods for deleting isolated storage files:</span></span>  
  
-   <span data-ttu-id="1b52a-104">Il metodo di istanza <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove> non accetta argomenti ed elimina l'archivio che lo chiama.</span><span class="sxs-lookup"><span data-stu-id="1b52a-104">The instance method <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove> does not take any arguments and deletes the store that calls it.</span></span> <span data-ttu-id="1b52a-105">Non sono necessarie autorizzazioni per questa operazione.</span><span class="sxs-lookup"><span data-stu-id="1b52a-105">No permissions are required for this operation.</span></span> <span data-ttu-id="1b52a-106">Il codice che può accedere all'archivio può eliminare alcuni o tutti i dati in esso contenuti.</span><span class="sxs-lookup"><span data-stu-id="1b52a-106">Any code that can access the store can delete any or all the data inside it.</span></span>  
  
-   <span data-ttu-id="1b52a-107">Il metodo statico <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove%28System.IO.IsolatedStorage.IsolatedStorageScope%29> accetta il valore di enumerazione <xref:System.IO.IsolatedStorage.IsolatedStorageScope.User> ed elimina tutti gli archivi per l'utente che esegue il codice.</span><span class="sxs-lookup"><span data-stu-id="1b52a-107">The static method <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove%28System.IO.IsolatedStorage.IsolatedStorageScope%29> takes the <xref:System.IO.IsolatedStorage.IsolatedStorageScope.User> enumeration value, and deletes all the stores for the user who is running the code.</span></span> <span data-ttu-id="1b52a-108">Questa operazione richiede l'autorizzazione <xref:System.Security.Permissions.IsolatedStorageFilePermission> per il valore <xref:System.Security.Permissions.IsolatedStorageContainment.AdministerIsolatedStorageByUser> .</span><span class="sxs-lookup"><span data-stu-id="1b52a-108">This operation requires <xref:System.Security.Permissions.IsolatedStorageFilePermission> permission for the <xref:System.Security.Permissions.IsolatedStorageContainment.AdministerIsolatedStorageByUser> value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b52a-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="1b52a-109">Example</span></span>  
 <span data-ttu-id="1b52a-110">L'esempio di codice seguente illustra l'uso dei metodi <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove%2A> statici e di istanza.</span><span class="sxs-lookup"><span data-stu-id="1b52a-110">The following code example demonstrates the use of the static and instance <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove%2A> methods.</span></span> <span data-ttu-id="1b52a-111">La classe ottiene due archivi, uno isolato per utente e assembly e l'altro isolato per utente, dominio e assembly.</span><span class="sxs-lookup"><span data-stu-id="1b52a-111">The class obtains two stores; one is isolated for user and assembly and the other is isolated for user, domain, and assembly.</span></span> <span data-ttu-id="1b52a-112">L'archivio utente, di dominio e di assembly viene quindi eliminato chiamando il metodo <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove> del file dello spazio di memorizzazione isolato  `isoStore1`.</span><span class="sxs-lookup"><span data-stu-id="1b52a-112">The user, domain, and assembly store is then deleted by calling the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove> method of the isolated storage file  `isoStore1`.</span></span> <span data-ttu-id="1b52a-113">Tutti gli archivi rimanenti per l'utente vengono quindi eliminati chiamando il metodo statico <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove%28System.IO.IsolatedStorage.IsolatedStorageScope%29>.</span><span class="sxs-lookup"><span data-stu-id="1b52a-113">Then, all remaining stores for the user are deleted by calling the static method <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove%28System.IO.IsolatedStorage.IsolatedStorageScope%29>.</span></span>  
  
 [!code-cpp[Conceptual.IsolatedStorage#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source3.cpp#3)]
 [!code-csharp[Conceptual.IsolatedStorage#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source3.cs#3)]
 [!code-vb[Conceptual.IsolatedStorage#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source3.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="1b52a-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b52a-114">See also</span></span>

- <xref:System.IO.IsolatedStorage.IsolatedStorageFile>
- [<span data-ttu-id="1b52a-115">Spazio di memorizzazione isolato</span><span class="sxs-lookup"><span data-stu-id="1b52a-115">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)
