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
# <a name="how-to-add-or-remove-access-control-list-entries"></a>Procedura: aggiungere o rimuovere voci dell'elenco di controllo di accesso (ACL)
Per aggiungere o rimuovere le voci dell'elenco di controllo di accesso (ACL) a o da un file, l'oggetto <xref:System.Security.AccessControl.FileSecurity> o <xref:System.Security.AccessControl.DirectorySecurity> deve essere recuperato dal file o dalla directory, modificato e quindi riapplicato al file o alla directory.  
  
### <a name="to-add-or-remove-an-acl-entry-from-a-file"></a>Per aggiungere o rimuovere una voce ACL da un file  
  
1.  Chiamare il metodo <xref:System.IO.File.GetAccessControl%2A> per ottenere un oggetto <xref:System.Security.AccessControl.FileSecurity> che contiene le voci ACL correnti di un file.  
  
2.  Aggiungere o rimuovere voci ACL dall'oggetto <xref:System.Security.AccessControl.FileSecurity> restituito dal passaggio 1.  
  
3.  Passare l'oggetto <xref:System.Security.AccessControl.FileSecurity> al metodo <xref:System.IO.File.SetAccessControl%2A> per applicare le modifiche.  
  
### <a name="to-add-or-remove-an-acl-entry-from-a-directory"></a>Per aggiungere o rimuovere una voce ACL da una directory  
  
1.  Chiamare il metodo <xref:System.IO.Directory.GetAccessControl%2A> per ottenere un oggetto <xref:System.Security.AccessControl.DirectorySecurity> che contiene le voci ACL correnti di una directory.  
  
2.  Aggiungere o rimuovere voci ACL dall'oggetto <xref:System.Security.AccessControl.DirectorySecurity> restituito dal passaggio 1.  
  
3.  Passare l'oggetto <xref:System.Security.AccessControl.DirectorySecurity> al metodo <xref:System.IO.Directory.SetAccessControl%2A> per applicare le modifiche.  
  
## <a name="example"></a>Esempio  
 [!code-cpp[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/cpp/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/cpp/sample.cpp#1)]
 [!code-csharp[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/CS/sample.cs#1)]
 [!code-vb[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/VB/sample.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 È necessario specificare un utente valido o un account di gruppo per eseguire questo esempio. Questo esempio usa un oggetto <xref:System.IO.File>; tuttavia, la stessa procedura viene usata anche per le classi <xref:System.IO.FileInfo>, <xref:System.IO.Directory> e <xref:System.IO.DirectoryInfo>.
