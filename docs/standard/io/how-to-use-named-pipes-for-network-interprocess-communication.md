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
# <a name="how-to-use-named-pipes-for-network-interprocess-communication"></a><span data-ttu-id="4a77b-102">Procedura: utilizzare le named pipe per la comunicazione interprocesso in rete</span><span class="sxs-lookup"><span data-stu-id="4a77b-102">How to: Use Named Pipes for Network Interprocess Communication</span></span>
<span data-ttu-id="4a77b-103">Named pipe forniscono la comunicazione interprocesso tra un server di pipe e uno o più client pipe.</span><span class="sxs-lookup"><span data-stu-id="4a77b-103">Named pipes provide interprocess communication between a pipe server and one or more pipe clients.</span></span> <span data-ttu-id="4a77b-104">Offrono maggiori funzionalità rispetto alle pipe anonime che forniscono la comunicazione interprocesso in un computer locale.</span><span class="sxs-lookup"><span data-stu-id="4a77b-104">They offer more functionality than anonymous pipes, which provide interprocess communication on a local computer.</span></span> <span data-ttu-id="4a77b-105">Le named pipe supportano la comunicazione full duplex in una rete e in più istanze server, la comunicazione basata su messaggi e la rappresentazione client che consente ai processi di connessione di utilizzare il proprio set di autorizzazioni nei server remoti.</span><span class="sxs-lookup"><span data-stu-id="4a77b-105">Named pipes support full duplex communication over a network and multiple server instances, message-based communication, and client impersonation, which enables connecting processes to use their own set of permissions on remote servers.</span></span>  
  
 <span data-ttu-id="4a77b-106">Per implementare le named pipe, utilizzare le classi <xref:System.IO.Pipes.NamedPipeServerStream> e <xref:System.IO.Pipes.NamedPipeClientStream>.</span><span class="sxs-lookup"><span data-stu-id="4a77b-106">To implement name pipes, use the <xref:System.IO.Pipes.NamedPipeServerStream> and <xref:System.IO.Pipes.NamedPipeClientStream> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a77b-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="4a77b-107">Example</span></span>  
 <span data-ttu-id="4a77b-108">Nell'esempio seguente viene illustrato come creare una named pipe mediante il <xref:System.IO.Pipes.NamedPipeServerStream> classe.</span><span class="sxs-lookup"><span data-stu-id="4a77b-108">The following example demonstrates how to create a named pipe by using the <xref:System.IO.Pipes.NamedPipeServerStream> class.</span></span> <span data-ttu-id="4a77b-109">In questo esempio, il processo server crea quattro thread.</span><span class="sxs-lookup"><span data-stu-id="4a77b-109">In this example, the server process creates four threads.</span></span> <span data-ttu-id="4a77b-110">Ogni thread può accettare una connessione client.</span><span class="sxs-lookup"><span data-stu-id="4a77b-110">Each thread can accept a client connection.</span></span> <span data-ttu-id="4a77b-111">Il processo client connesso fornisce quindi il server con un nome di file.</span><span class="sxs-lookup"><span data-stu-id="4a77b-111">The connected client process then supplies the server with a file name.</span></span> <span data-ttu-id="4a77b-112">Se il client disponga di autorizzazioni sufficienti, il processo server apre il file e invia il contenuto al client.</span><span class="sxs-lookup"><span data-stu-id="4a77b-112">If the client has sufficient permissions, the server process opens the file and sends its contents back to the client.</span></span>  
  
 [!code-cpp[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/vb/program.vb#01)]  
  
## <a name="example"></a><span data-ttu-id="4a77b-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="4a77b-113">Example</span></span>  
 <span data-ttu-id="4a77b-114">Nell'esempio seguente viene illustrato il processo client, che usa la <xref:System.IO.Pipes.NamedPipeClientStream> classe.</span><span class="sxs-lookup"><span data-stu-id="4a77b-114">The following example shows the client process, which uses the <xref:System.IO.Pipes.NamedPipeClientStream> class.</span></span> <span data-ttu-id="4a77b-115">Il client si connette al processo del server e invia un nome di file al server.</span><span class="sxs-lookup"><span data-stu-id="4a77b-115">The client connects to the server process and sends a file name to the server.</span></span> <span data-ttu-id="4a77b-116">Nell'esempio viene utilizzata la rappresentazione, pertanto l'identità con cui è in esecuzione l'applicazione client deve disporre dell'autorizzazione per accedere al file.</span><span class="sxs-lookup"><span data-stu-id="4a77b-116">The example uses impersonation, so the identity that is running the client application must have permission to access the file.</span></span> <span data-ttu-id="4a77b-117">Il server invia quindi il contenuto del file al client.</span><span class="sxs-lookup"><span data-stu-id="4a77b-117">The server then sends the contents of the file back to the client.</span></span> <span data-ttu-id="4a77b-118">Il contenuto del file viene quindi visualizzato nella console.</span><span class="sxs-lookup"><span data-stu-id="4a77b-118">The file contents are then displayed to the console.</span></span>  
  
 [!code-csharp[System.IO.Pipes.NamedPipeClientStream_ImpersonationSample1#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeClientStream_ImpersonationSample1/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.NamedPipeClientStream_ImpersonationSample1#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeClientStream_ImpersonationSample1/vb/program.vb#01)]  
  
## <a name="robust-programming"></a><span data-ttu-id="4a77b-119">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="4a77b-119">Robust Programming</span></span>  
 <span data-ttu-id="4a77b-120">I processi client e server in questo esempio siano in esecuzione nello stesso computer, pertanto il nome del server fornito per il <xref:System.IO.Pipes.NamedPipeClientStream> oggetto `"."`.</span><span class="sxs-lookup"><span data-stu-id="4a77b-120">The client and server processes in this example are intended to run on the same computer, so the server name provided to the <xref:System.IO.Pipes.NamedPipeClientStream> object is `"."`.</span></span> <span data-ttu-id="4a77b-121">Se i processi client e server in computer separati, `"."` verrà sostituito con il nome di rete del computer che esegue il processo server.</span><span class="sxs-lookup"><span data-stu-id="4a77b-121">If the client and server processes were on separate computers, `"."` would be replaced with the network name of the computer that runs the server process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a77b-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a77b-122">See Also</span></span>  
 <xref:System.Security.Principal.TokenImpersonationLevel>  
 <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName%2A>  
 [<span data-ttu-id="4a77b-123">Pipe</span><span class="sxs-lookup"><span data-stu-id="4a77b-123">Pipes</span></span>](../../../docs/standard/io/pipe-operations.md)  
 [<span data-ttu-id="4a77b-124">Procedura: Usare le unnamed pipe per la comunicazione interprocesso locale</span><span class="sxs-lookup"><span data-stu-id="4a77b-124">How to: Use Anonymous Pipes for Local Interprocess Communication</span></span>](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md)
