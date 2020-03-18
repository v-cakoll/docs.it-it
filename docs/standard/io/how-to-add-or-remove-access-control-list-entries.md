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
# <a name="how-to-add-or-remove-access-control-list-entries-net-framework-only"></a>Procedura: aggiungere o rimuovere voci dell'elenco di controllo di accesso (solo .NET Framework)
Per aggiungere o rimuovere voci dell'elenco di controllo di accesso (ACL) in o da un file o una directory, ottenere l'oggetto <xref:System.Security.AccessControl.FileSecurity> o <xref:System.Security.AccessControl.DirectorySecurity> dal file o dalla directory. Modificare l'oggetto e quindi applicarlo nuovamente al file o alla directory.  
  
## <a name="add-or-remove-an-acl-entry-from-a-file"></a>Aggiungere o rimuovere una voce ACL da un file  
  
1. Chiamare il metodo <xref:System.IO.File.GetAccessControl%2A?displayProperty=nameWithType> per ottenere un oggetto <xref:System.Security.AccessControl.FileSecurity> che contiene le voci ACL correnti di un file.  
  
2. Aggiungere o rimuovere voci ACL dall'oggetto <xref:System.Security.AccessControl.FileSecurity> restituito dal passaggio 1.  
  
3. Per applicare le modifiche, passare l'oggetto <xref:System.Security.AccessControl.FileSecurity> al metodo <xref:System.IO.File.SetAccessControl%2A?displayProperty=nameWithType>.  
  
## <a name="add-or-remove-an-acl-entry-from-a-directory"></a>Aggiungere o rimuovere una voce ACL da una directory  
  
1. Chiamare il metodo <xref:System.IO.Directory.GetAccessControl%2A?displayProperty=nameWithType> per ottenere un oggetto <xref:System.Security.AccessControl.DirectorySecurity> che contiene le voci ACL correnti di una directory.  
  
2. Aggiungere o rimuovere voci ACL dall'oggetto <xref:System.Security.AccessControl.DirectorySecurity> restituito dal passaggio 1.  
  
3. Per applicare le modifiche, passare l'oggetto <xref:System.Security.AccessControl.DirectorySecurity> al metodo <xref:System.IO.Directory.SetAccessControl%2A?displayProperty=nameWithType>.  
  
## <a name="example"></a>Esempio  
 È necessario usare un utente o un account di gruppo valido per eseguire questo esempio. L'esempio usa un oggetto <xref:System.IO.File>. Usare la stessa procedura per le classi <xref:System.IO.FileInfo>, <xref:System.IO.Directory> e <xref:System.IO.DirectoryInfo>.

 [!code-csharp[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/CS/sample.cs#1)]
 [!code-vb[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/VB/sample.vb#1)]  
