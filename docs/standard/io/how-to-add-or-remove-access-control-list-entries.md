---
title: "Procedura: aggiungere o rimuovere voci dell'elenco di controllo di accesso (solo .NET Framework)"
ms.date: 01/14/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ACEs [.NET Framework]
- ACLs [.NET Framework]
- access control entries [.NET Framework]
- I/O [.NET Framework], access control list entries
- access control lists [.NET Framework]
ms.assetid: 53758b39-bd9b-4640-bb04-cad5ed8d0abf
ms.openlocfilehash: 5f41c518b8732adff95593cab29d7085adcc9ab3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "75708128"
---
# <a name="how-to-add-or-remove-access-control-list-entries-net-framework-only"></a><span data-ttu-id="af3ee-102">Procedura: aggiungere o rimuovere voci dell'elenco di controllo di accesso (solo .NET Framework)</span><span class="sxs-lookup"><span data-stu-id="af3ee-102">How to: Add or remove Access Control List entries (.NET Framework only)</span></span>
<span data-ttu-id="af3ee-103">Per aggiungere o rimuovere voci dell'elenco di controllo di accesso (ACL) in o da un file o una directory, ottenere l'oggetto <xref:System.Security.AccessControl.FileSecurity> o <xref:System.Security.AccessControl.DirectorySecurity> dal file o dalla directory.</span><span class="sxs-lookup"><span data-stu-id="af3ee-103">To add or remove Access Control List (ACL) entries to or from a file or directory, get the <xref:System.Security.AccessControl.FileSecurity> or <xref:System.Security.AccessControl.DirectorySecurity> object from the file or directory.</span></span> <span data-ttu-id="af3ee-104">Modificare l'oggetto e quindi applicarlo nuovamente al file o alla directory.</span><span class="sxs-lookup"><span data-stu-id="af3ee-104">Modify the object, and then apply it back to the file or directory.</span></span>  
  
## <a name="add-or-remove-an-acl-entry-from-a-file"></a><span data-ttu-id="af3ee-105">Aggiungere o rimuovere una voce ACL da un file</span><span class="sxs-lookup"><span data-stu-id="af3ee-105">Add or remove an ACL entry from a file</span></span>  
  
1. <span data-ttu-id="af3ee-106">Chiamare il metodo <xref:System.IO.File.GetAccessControl%2A?displayProperty=nameWithType> per ottenere un oggetto <xref:System.Security.AccessControl.FileSecurity> che contiene le voci ACL correnti di un file.</span><span class="sxs-lookup"><span data-stu-id="af3ee-106">Call the <xref:System.IO.File.GetAccessControl%2A?displayProperty=nameWithType> method to get a <xref:System.Security.AccessControl.FileSecurity> object that contains the current ACL entries of a file.</span></span>  
  
2. <span data-ttu-id="af3ee-107">Aggiungere o rimuovere voci ACL dall'oggetto <xref:System.Security.AccessControl.FileSecurity> restituito dal passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="af3ee-107">Add or remove ACL entries from the <xref:System.Security.AccessControl.FileSecurity> object returned from step 1.</span></span>  
  
3. <span data-ttu-id="af3ee-108">Per applicare le modifiche, passare l'oggetto <xref:System.Security.AccessControl.FileSecurity> al metodo <xref:System.IO.File.SetAccessControl%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="af3ee-108">To apply the changes, pass the <xref:System.Security.AccessControl.FileSecurity> object to the <xref:System.IO.File.SetAccessControl%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="add-or-remove-an-acl-entry-from-a-directory"></a><span data-ttu-id="af3ee-109">Aggiungere o rimuovere una voce ACL da una directory</span><span class="sxs-lookup"><span data-stu-id="af3ee-109">Add or remove an ACL entry from a directory</span></span>  
  
1. <span data-ttu-id="af3ee-110">Chiamare il metodo <xref:System.IO.Directory.GetAccessControl%2A?displayProperty=nameWithType> per ottenere un oggetto <xref:System.Security.AccessControl.DirectorySecurity> che contiene le voci ACL correnti di una directory.</span><span class="sxs-lookup"><span data-stu-id="af3ee-110">Call the <xref:System.IO.Directory.GetAccessControl%2A?displayProperty=nameWithType> method to get a <xref:System.Security.AccessControl.DirectorySecurity> object that contains the current ACL entries of a directory.</span></span>  
  
2. <span data-ttu-id="af3ee-111">Aggiungere o rimuovere voci ACL dall'oggetto <xref:System.Security.AccessControl.DirectorySecurity> restituito dal passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="af3ee-111">Add or remove ACL entries from the <xref:System.Security.AccessControl.DirectorySecurity> object returned from step 1.</span></span>  
  
3. <span data-ttu-id="af3ee-112">Per applicare le modifiche, passare l'oggetto <xref:System.Security.AccessControl.DirectorySecurity> al metodo <xref:System.IO.Directory.SetAccessControl%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="af3ee-112">To apply the changes, pass the <xref:System.Security.AccessControl.DirectorySecurity> object to the <xref:System.IO.Directory.SetAccessControl%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af3ee-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="af3ee-113">Example</span></span>  
 <span data-ttu-id="af3ee-114">È necessario usare un utente o un account di gruppo valido per eseguire questo esempio.</span><span class="sxs-lookup"><span data-stu-id="af3ee-114">You must use a valid user or group account to run this example.</span></span> <span data-ttu-id="af3ee-115">L'esempio usa un oggetto <xref:System.IO.File>.</span><span class="sxs-lookup"><span data-stu-id="af3ee-115">The example uses a <xref:System.IO.File> object.</span></span> <span data-ttu-id="af3ee-116">Usare la stessa procedura per le classi <xref:System.IO.FileInfo>, <xref:System.IO.Directory> e <xref:System.IO.DirectoryInfo>.</span><span class="sxs-lookup"><span data-stu-id="af3ee-116">Use the same procedure for the <xref:System.IO.FileInfo>, <xref:System.IO.Directory>, and <xref:System.IO.DirectoryInfo> classes.</span></span>

 [!code-csharp[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/CS/sample.cs#1)]
 [!code-vb[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/VB/sample.vb#1)]  
