---
title: 'Procedura: aggiungere o rimuovere voci dell''elenco di controllo di accesso (ACL)'
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
- ACEs [.NET Framework]
- ACLs [.NET Framework]
- access control entries [.NET Framework]
- I/O [.NET Framework], access control list entries
- access control lists [.NET Framework]
ms.assetid: 53758b39-bd9b-4640-bb04-cad5ed8d0abf
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 988fd354caa5fcc716107087242ead113c9a9939
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-add-or-remove-access-control-list-entries"></a><span data-ttu-id="f1b86-102">Procedura: aggiungere o rimuovere voci dell'elenco di controllo di accesso (ACL)</span><span class="sxs-lookup"><span data-stu-id="f1b86-102">How to: Add or Remove Access Control List Entries</span></span>
<span data-ttu-id="f1b86-103">Per aggiungere o rimuovere le voci dell'elenco di controllo di accesso (ACL) a o da un file, l'oggetto <xref:System.Security.AccessControl.FileSecurity> o <xref:System.Security.AccessControl.DirectorySecurity> deve essere recuperato dal file o dalla directory, modificato e quindi riapplicato al file o alla directory.</span><span class="sxs-lookup"><span data-stu-id="f1b86-103">To add or remove Access Control List (ACL) entries to or from a file, the <xref:System.Security.AccessControl.FileSecurity> or <xref:System.Security.AccessControl.DirectorySecurity> object must be obtained from the file or directory, modified, and then applied back to the file or directory.</span></span>  
  
### <a name="to-add-or-remove-an-acl-entry-from-a-file"></a><span data-ttu-id="f1b86-104">Per aggiungere o rimuovere una voce ACL da un file</span><span class="sxs-lookup"><span data-stu-id="f1b86-104">To add or remove an ACL entry from a File</span></span>  
  
1.  <span data-ttu-id="f1b86-105">Chiamare il metodo <xref:System.IO.File.GetAccessControl%2A> per ottenere un oggetto <xref:System.Security.AccessControl.FileSecurity> che contiene le voci ACL correnti di un file.</span><span class="sxs-lookup"><span data-stu-id="f1b86-105">Call the <xref:System.IO.File.GetAccessControl%2A> method to get a <xref:System.Security.AccessControl.FileSecurity> object that contains the current ACL entries of a file.</span></span>  
  
2.  <span data-ttu-id="f1b86-106">Aggiungere o rimuovere voci ACL dall'oggetto <xref:System.Security.AccessControl.FileSecurity> restituito dal passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="f1b86-106">Add or remove ACL entries from the <xref:System.Security.AccessControl.FileSecurity> object returned from step 1.</span></span>  
  
3.  <span data-ttu-id="f1b86-107">Passare l'oggetto <xref:System.Security.AccessControl.FileSecurity> al metodo <xref:System.IO.File.SetAccessControl%2A> per applicare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="f1b86-107">Pass the <xref:System.Security.AccessControl.FileSecurity> object to the <xref:System.IO.File.SetAccessControl%2A> method to apply the changes.</span></span>  
  
### <a name="to-add-or-remove-an-acl-entry-from-a-directory"></a><span data-ttu-id="f1b86-108">Per aggiungere o rimuovere una voce ACL da una directory</span><span class="sxs-lookup"><span data-stu-id="f1b86-108">To add or remove an ACL entry from a Directory</span></span>  
  
1.  <span data-ttu-id="f1b86-109">Chiamare il metodo <xref:System.IO.Directory.GetAccessControl%2A> per ottenere un oggetto <xref:System.Security.AccessControl.DirectorySecurity> che contiene le voci ACL correnti di una directory.</span><span class="sxs-lookup"><span data-stu-id="f1b86-109">Call the <xref:System.IO.Directory.GetAccessControl%2A> method to get a <xref:System.Security.AccessControl.DirectorySecurity> object that contains the current ACL entries of a directory.</span></span>  
  
2.  <span data-ttu-id="f1b86-110">Aggiungere o rimuovere voci ACL dall'oggetto <xref:System.Security.AccessControl.DirectorySecurity> restituito dal passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="f1b86-110">Add or remove ACL entries from the <xref:System.Security.AccessControl.DirectorySecurity> object returned from step 1.</span></span>  
  
3.  <span data-ttu-id="f1b86-111">Passare l'oggetto <xref:System.Security.AccessControl.DirectorySecurity> al metodo <xref:System.IO.Directory.SetAccessControl%2A> per applicare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="f1b86-111">Pass the <xref:System.Security.AccessControl.DirectorySecurity> object to the <xref:System.IO.Directory.SetAccessControl%2A> method to apply the changes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1b86-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="f1b86-112">Example</span></span>  
 [!code-cpp[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/cpp/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/cpp/sample.cpp#1)]
 [!code-csharp[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/CS/sample.cs#1)]
 [!code-vb[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/VB/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f1b86-113">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="f1b86-113">Compiling the Code</span></span>  
 <span data-ttu-id="f1b86-114">È necessario specificare un utente valido o un account di gruppo per eseguire questo esempio.</span><span class="sxs-lookup"><span data-stu-id="f1b86-114">You must supply a valid user or group account to run this example.</span></span> <span data-ttu-id="f1b86-115">Questo esempio usa un oggetto <xref:System.IO.File>; tuttavia, la stessa procedura viene usata anche per le classi <xref:System.IO.FileInfo>, <xref:System.IO.Directory> e <xref:System.IO.DirectoryInfo>.</span><span class="sxs-lookup"><span data-stu-id="f1b86-115">This example uses a <xref:System.IO.File> object; however, the same procedure is used for the <xref:System.IO.FileInfo>, <xref:System.IO.Directory>, and <xref:System.IO.DirectoryInfo> classes.</span></span>
