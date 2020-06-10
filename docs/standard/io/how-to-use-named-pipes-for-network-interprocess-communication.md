---
title: 'Procedura: Usare le named pipe per la comunicazione interprocesso in rete'
description: Vedere due esempi di utilizzo di named pipe per la comunicazione interprocesso tra un server pipe e uno o più client pipe in una rete.
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
ms.openlocfilehash: a529d1d44a903df36099a59e07f4582554d230f2
ms.sourcegitcommit: 7137e12f54c4e83a94ae43ec320f8cf59c1772ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2020
ms.locfileid: "84662563"
---
# <a name="how-to-use-named-pipes-for-network-interprocess-communication"></a><span data-ttu-id="bdb5e-103">Procedura: Usare le named pipe per la comunicazione interprocesso in rete</span><span class="sxs-lookup"><span data-stu-id="bdb5e-103">How to: Use Named Pipes for Network Interprocess Communication</span></span>
<span data-ttu-id="bdb5e-104">Le named pipe forniscono la comunicazione interprocesso tra un server pipe e uno o più client pipe.</span><span class="sxs-lookup"><span data-stu-id="bdb5e-104">Named pipes provide interprocess communication between a pipe server and one or more pipe clients.</span></span> <span data-ttu-id="bdb5e-105">Offrono maggiori funzionalità rispetto alle pipe anonime che forniscono la comunicazione interprocesso in un computer locale.</span><span class="sxs-lookup"><span data-stu-id="bdb5e-105">They offer more functionality than anonymous pipes, which provide interprocess communication on a local computer.</span></span> <span data-ttu-id="bdb5e-106">Le named pipe supportano la comunicazione full duplex in una rete e in più istanze server, la comunicazione basata su messaggi e la rappresentazione client che consente ai processi di connessione di utilizzare il proprio set di autorizzazioni nei server remoti.</span><span class="sxs-lookup"><span data-stu-id="bdb5e-106">Named pipes support full duplex communication over a network and multiple server instances, message-based communication, and client impersonation, which enables connecting processes to use their own set of permissions on remote servers.</span></span>  
  
 <span data-ttu-id="bdb5e-107">Per implementare le named pipe, utilizzare le classi <xref:System.IO.Pipes.NamedPipeServerStream> e <xref:System.IO.Pipes.NamedPipeClientStream>.</span><span class="sxs-lookup"><span data-stu-id="bdb5e-107">To implement name pipes, use the <xref:System.IO.Pipes.NamedPipeServerStream> and <xref:System.IO.Pipes.NamedPipeClientStream> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bdb5e-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="bdb5e-108">Example</span></span>  
 <span data-ttu-id="bdb5e-109">L'esempio seguente illustra come creare una named pipe usando la classe <xref:System.IO.Pipes.NamedPipeServerStream>.</span><span class="sxs-lookup"><span data-stu-id="bdb5e-109">The following example demonstrates how to create a named pipe by using the <xref:System.IO.Pipes.NamedPipeServerStream> class.</span></span> <span data-ttu-id="bdb5e-110">In questo esempio il processo server crea quattro thread.</span><span class="sxs-lookup"><span data-stu-id="bdb5e-110">In this example, the server process creates four threads.</span></span> <span data-ttu-id="bdb5e-111">Ogni thread può accettare una connessione client.</span><span class="sxs-lookup"><span data-stu-id="bdb5e-111">Each thread can accept a client connection.</span></span> <span data-ttu-id="bdb5e-112">Il processo client connesso fornisce quindi al server un nome file.</span><span class="sxs-lookup"><span data-stu-id="bdb5e-112">The connected client process then supplies the server with a file name.</span></span> <span data-ttu-id="bdb5e-113">Se il client ha autorizzazioni sufficienti, il processo server apre il file e invia il contenuto al client.</span><span class="sxs-lookup"><span data-stu-id="bdb5e-113">If the client has sufficient permissions, the server process opens the file and sends its contents back to the client.</span></span>  
  
 [!code-cpp[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/vb/program.vb#01)]  
  
## <a name="example"></a><span data-ttu-id="bdb5e-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="bdb5e-114">Example</span></span>  
 <span data-ttu-id="bdb5e-115">L'esempio seguente mostra il processo client, che usa la classe <xref:System.IO.Pipes.NamedPipeClientStream>.</span><span class="sxs-lookup"><span data-stu-id="bdb5e-115">The following example shows the client process, which uses the <xref:System.IO.Pipes.NamedPipeClientStream> class.</span></span> <span data-ttu-id="bdb5e-116">Il client si connette al processo server e invia un nome file al server.</span><span class="sxs-lookup"><span data-stu-id="bdb5e-116">The client connects to the server process and sends a file name to the server.</span></span> <span data-ttu-id="bdb5e-117">L'esempio usa la rappresentazione, quindi l'identità che esegue l'applicazione client deve avere l'autorizzazione per accedere al file.</span><span class="sxs-lookup"><span data-stu-id="bdb5e-117">The example uses impersonation, so the identity that is running the client application must have permission to access the file.</span></span> <span data-ttu-id="bdb5e-118">Il server invia quindi il contenuto del file al client.</span><span class="sxs-lookup"><span data-stu-id="bdb5e-118">The server then sends the contents of the file back to the client.</span></span> <span data-ttu-id="bdb5e-119">Il contenuto del file viene quindi visualizzato nella console.</span><span class="sxs-lookup"><span data-stu-id="bdb5e-119">The file contents are then displayed to the console.</span></span>  
  
 [!code-csharp[System.IO.Pipes.NamedPipeClientStream_ImpersonationSample1#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeClientStream_ImpersonationSample1/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.NamedPipeClientStream_ImpersonationSample1#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeClientStream_ImpersonationSample1/vb/program.vb#01)]  
  
## <a name="robust-programming"></a><span data-ttu-id="bdb5e-120">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="bdb5e-120">Robust Programming</span></span>  
 <span data-ttu-id="bdb5e-121">I processi client e server in questo esempio sono in esecuzione nello stesso computer, quindi il nome del server fornito all'oggetto <xref:System.IO.Pipes.NamedPipeClientStream> è `"."`.</span><span class="sxs-lookup"><span data-stu-id="bdb5e-121">The client and server processes in this example are intended to run on the same computer, so the server name provided to the <xref:System.IO.Pipes.NamedPipeClientStream> object is `"."`.</span></span> <span data-ttu-id="bdb5e-122">Se i processi client e server fossero in computer distinti, `"."` verrebbe sostituito dal nome di rete del computer che esegue il processo server.</span><span class="sxs-lookup"><span data-stu-id="bdb5e-122">If the client and server processes were on separate computers, `"."` would be replaced with the network name of the computer that runs the server process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdb5e-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bdb5e-123">See also</span></span>

- <xref:System.Security.Principal.TokenImpersonationLevel>
- <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName%2A>
- [<span data-ttu-id="bdb5e-124">Pipe</span><span class="sxs-lookup"><span data-stu-id="bdb5e-124">Pipes</span></span>](pipe-operations.md)
- [<span data-ttu-id="bdb5e-125">Procedura: Usare le unnamed pipe per la comunicazione interprocesso locale</span><span class="sxs-lookup"><span data-stu-id="bdb5e-125">How to: Use Anonymous Pipes for Local Interprocess Communication</span></span>](how-to-use-anonymous-pipes-for-local-interprocess-communication.md)
