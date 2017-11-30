---
title: 'Procedura: utilizzare le named pipe per la comunicazione interprocesso in rete'
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
- message-based communication [.NET Framework], named pipes
- named pipes [.NET Framework]
- pipes [.NET Framework]
- multiple connections via named pipes
- network communications [.NET Framework], named pipes
- impersonation [.NET Framework], named pipes
- full duplex communcation [.NET Framework], named pipes
ms.assetid: 4e4d7e64-9f1b-4026-98f7-20488ac7b42b
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 952600e71311184c4a4f906734addbf335d0358a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-named-pipes-for-network-interprocess-communication"></a>Procedura: utilizzare le named pipe per la comunicazione interprocesso in rete
Named pipe forniscono la comunicazione interprocesso tra un server di pipe e uno o più client pipe. Offrono maggiori funzionalità rispetto alle pipe anonime che forniscono la comunicazione interprocesso in un computer locale. Le named pipe supportano la comunicazione full duplex in una rete e in più istanze server, la comunicazione basata su messaggi e la rappresentazione client che consente ai processi di connessione di utilizzare il proprio set di autorizzazioni nei server remoti.  
  
 Per implementare le named pipe, utilizzare le classi <xref:System.IO.Pipes.NamedPipeServerStream> e <xref:System.IO.Pipes.NamedPipeClientStream>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come creare una named pipe mediante il <xref:System.IO.Pipes.NamedPipeServerStream> classe. In questo esempio, il processo server crea quattro thread. Ogni thread può accettare una connessione client. Il processo client connesso fornisce quindi il server con un nome di file. Se il client disponga di autorizzazioni sufficienti, il processo server apre il file e invia il contenuto al client.  
  
 [!code-cpp[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/vb/program.vb#01)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato il processo client, che usa la <xref:System.IO.Pipes.NamedPipeClientStream> classe. Il client si connette al processo del server e invia un nome di file al server. Nell'esempio viene utilizzata la rappresentazione, pertanto l'identità con cui è in esecuzione l'applicazione client deve disporre dell'autorizzazione per accedere al file. Il server invia quindi il contenuto del file al client. Il contenuto del file viene quindi visualizzato nella console.  
  
 [!code-csharp[System.IO.Pipes.NamedPipeClientStream_ImpersonationSample1#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeClientStream_ImpersonationSample1/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.NamedPipeClientStream_ImpersonationSample1#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeClientStream_ImpersonationSample1/vb/program.vb#01)]  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 I processi client e server in questo esempio siano in esecuzione nello stesso computer, pertanto il nome del server fornito per il <xref:System.IO.Pipes.NamedPipeClientStream> oggetto `"."`. Se i processi client e server in computer separati, `"."` verrà sostituito con il nome di rete del computer che esegue il processo server.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Security.Principal.TokenImpersonationLevel>  
 <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName%2A>  
 [Pipe](../../../docs/standard/io/pipe-operations.md)  
 [Procedura: Usare le unnamed pipe per la comunicazione interprocesso locale](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md)
