---
title: 'Procedura: utilizzare le named pipe per la comunicazione interprocesso in rete'
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
- full duplex communication [.NET Framework], named pipes
ms.assetid: 4e4d7e64-9f1b-4026-98f7-20488ac7b42b
ms.openlocfilehash: 71f3a8d38b46993762b2673ea5fe735d8d54d351
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706634"
---
# <a name="how-to-use-named-pipes-for-network-interprocess-communication"></a>Procedura: utilizzare le named pipe per la comunicazione interprocesso in rete
Le named pipe forniscono la comunicazione interprocesso tra un server pipe e uno o più client pipe. Offrono maggiori funzionalità rispetto alle pipe anonime che forniscono la comunicazione interprocesso in un computer locale. Le named pipe supportano la comunicazione full duplex in una rete e in più istanze server, la comunicazione basata su messaggi e la rappresentazione client che consente ai processi di connessione di utilizzare il proprio set di autorizzazioni nei server remoti.  
  
 Per implementare le named pipe, utilizzare le classi <xref:System.IO.Pipes.NamedPipeServerStream> e <xref:System.IO.Pipes.NamedPipeClientStream>.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra come creare una named pipe usando la classe <xref:System.IO.Pipes.NamedPipeServerStream>. In questo esempio il processo server crea quattro thread. Ogni thread può accettare una connessione client. Il processo client connesso fornisce quindi al server un nome file. Se il client ha autorizzazioni sufficienti, il processo server apre il file e invia il contenuto al client.  
  
 [!code-cpp[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/vb/program.vb#01)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra il processo client, che usa la classe <xref:System.IO.Pipes.NamedPipeClientStream>. Il client si connette al processo server e invia un nome file al server. L'esempio usa la rappresentazione, quindi l'identità che esegue l'applicazione client deve avere l'autorizzazione per accedere al file. Il server invia quindi il contenuto del file al client. Il contenuto del file viene quindi visualizzato nella console.  
  
 [!code-csharp[System.IO.Pipes.NamedPipeClientStream_ImpersonationSample1#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeClientStream_ImpersonationSample1/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.NamedPipeClientStream_ImpersonationSample1#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeClientStream_ImpersonationSample1/vb/program.vb#01)]  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 I processi client e server in questo esempio sono in esecuzione nello stesso computer, quindi il nome del server fornito all'oggetto <xref:System.IO.Pipes.NamedPipeClientStream> è `"."`. Se i processi client e server fossero in computer distinti, `"."` verrebbe sostituito dal nome di rete del computer che esegue il processo server.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Security.Principal.TokenImpersonationLevel>
- <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName%2A>
- [Pipe](../../../docs/standard/io/pipe-operations.md)
- [Procedura: Usare le unnamed pipe per la comunicazione interprocesso locale](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md)
