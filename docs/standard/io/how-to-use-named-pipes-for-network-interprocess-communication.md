---
title: 'Procedura: Usare le named pipe per la comunicazione interprocesso in rete'
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
ms.openlocfilehash: bebfd136245fd7b577ffcd71954f46ca82bfc72d
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291747"
---
# <a name="how-to-use-named-pipes-for-network-interprocess-communication"></a><span data-ttu-id="49da8-102">Procedura: Usare le named pipe per la comunicazione interprocesso in rete</span><span class="sxs-lookup"><span data-stu-id="49da8-102">How to: Use Named Pipes for Network Interprocess Communication</span></span>
<span data-ttu-id="49da8-103">Le named pipe forniscono la comunicazione interprocesso tra un server pipe e uno o più client pipe.</span><span class="sxs-lookup"><span data-stu-id="49da8-103">Named pipes provide interprocess communication between a pipe server and one or more pipe clients.</span></span> <span data-ttu-id="49da8-104">Offrono maggiori funzionalità rispetto alle pipe anonime che forniscono la comunicazione interprocesso in un computer locale.</span><span class="sxs-lookup"><span data-stu-id="49da8-104">They offer more functionality than anonymous pipes, which provide interprocess communication on a local computer.</span></span> <span data-ttu-id="49da8-105">Le named pipe supportano la comunicazione full duplex in una rete e in più istanze server, la comunicazione basata su messaggi e la rappresentazione client che consente ai processi di connessione di utilizzare il proprio set di autorizzazioni nei server remoti.</span><span class="sxs-lookup"><span data-stu-id="49da8-105">Named pipes support full duplex communication over a network and multiple server instances, message-based communication, and client impersonation, which enables connecting processes to use their own set of permissions on remote servers.</span></span>  
  
 <span data-ttu-id="49da8-106">Per implementare le named pipe, utilizzare le classi <xref:System.IO.Pipes.NamedPipeServerStream> e <xref:System.IO.Pipes.NamedPipeClientStream>.</span><span class="sxs-lookup"><span data-stu-id="49da8-106">To implement name pipes, use the <xref:System.IO.Pipes.NamedPipeServerStream> and <xref:System.IO.Pipes.NamedPipeClientStream> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="49da8-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="49da8-107">Example</span></span>  
 <span data-ttu-id="49da8-108">L'esempio seguente illustra come creare una named pipe usando la classe <xref:System.IO.Pipes.NamedPipeServerStream>.</span><span class="sxs-lookup"><span data-stu-id="49da8-108">The following example demonstrates how to create a named pipe by using the <xref:System.IO.Pipes.NamedPipeServerStream> class.</span></span> <span data-ttu-id="49da8-109">In questo esempio il processo server crea quattro thread.</span><span class="sxs-lookup"><span data-stu-id="49da8-109">In this example, the server process creates four threads.</span></span> <span data-ttu-id="49da8-110">Ogni thread può accettare una connessione client.</span><span class="sxs-lookup"><span data-stu-id="49da8-110">Each thread can accept a client connection.</span></span> <span data-ttu-id="49da8-111">Il processo client connesso fornisce quindi al server un nome file.</span><span class="sxs-lookup"><span data-stu-id="49da8-111">The connected client process then supplies the server with a file name.</span></span> <span data-ttu-id="49da8-112">Se il client ha autorizzazioni sufficienti, il processo server apre il file e invia il contenuto al client.</span><span class="sxs-lookup"><span data-stu-id="49da8-112">If the client has sufficient permissions, the server process opens the file and sends its contents back to the client.</span></span>  
  
 [!code-cpp[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/vb/program.vb#01)]  
  
## <a name="example"></a><span data-ttu-id="49da8-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="49da8-113">Example</span></span>  
 <span data-ttu-id="49da8-114">L'esempio seguente mostra il processo client, che usa la classe <xref:System.IO.Pipes.NamedPipeClientStream>.</span><span class="sxs-lookup"><span data-stu-id="49da8-114">The following example shows the client process, which uses the <xref:System.IO.Pipes.NamedPipeClientStream> class.</span></span> <span data-ttu-id="49da8-115">Il client si connette al processo server e invia un nome file al server.</span><span class="sxs-lookup"><span data-stu-id="49da8-115">The client connects to the server process and sends a file name to the server.</span></span> <span data-ttu-id="49da8-116">L'esempio usa la rappresentazione, quindi l'identità che esegue l'applicazione client deve avere l'autorizzazione per accedere al file.</span><span class="sxs-lookup"><span data-stu-id="49da8-116">The example uses impersonation, so the identity that is running the client application must have permission to access the file.</span></span> <span data-ttu-id="49da8-117">Il server invia quindi il contenuto del file al client.</span><span class="sxs-lookup"><span data-stu-id="49da8-117">The server then sends the contents of the file back to the client.</span></span> <span data-ttu-id="49da8-118">Il contenuto del file viene quindi visualizzato nella console.</span><span class="sxs-lookup"><span data-stu-id="49da8-118">The file contents are then displayed to the console.</span></span>  
  
 [!code-csharp[System.IO.Pipes.NamedPipeClientStream_ImpersonationSample1#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeClientStream_ImpersonationSample1/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.NamedPipeClientStream_ImpersonationSample1#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeClientStream_ImpersonationSample1/vb/program.vb#01)]  
  
## <a name="robust-programming"></a><span data-ttu-id="49da8-119">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="49da8-119">Robust Programming</span></span>  
 <span data-ttu-id="49da8-120">I processi client e server in questo esempio sono in esecuzione nello stesso computer, quindi il nome del server fornito all'oggetto <xref:System.IO.Pipes.NamedPipeClientStream> è `"."`.</span><span class="sxs-lookup"><span data-stu-id="49da8-120">The client and server processes in this example are intended to run on the same computer, so the server name provided to the <xref:System.IO.Pipes.NamedPipeClientStream> object is `"."`.</span></span> <span data-ttu-id="49da8-121">Se i processi client e server fossero in computer distinti, `"."` verrebbe sostituito dal nome di rete del computer che esegue il processo server.</span><span class="sxs-lookup"><span data-stu-id="49da8-121">If the client and server processes were on separate computers, `"."` would be replaced with the network name of the computer that runs the server process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49da8-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49da8-122">See also</span></span>

- <xref:System.Security.Principal.TokenImpersonationLevel>
- <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName%2A>
- [<span data-ttu-id="49da8-123">Pipe</span><span class="sxs-lookup"><span data-stu-id="49da8-123">Pipes</span></span>](pipe-operations.md)
- [<span data-ttu-id="49da8-124">Procedura: Usare le unnamed pipe per la comunicazione interprocesso locale</span><span class="sxs-lookup"><span data-stu-id="49da8-124">How to: Use Anonymous Pipes for Local Interprocess Communication</span></span>](how-to-use-anonymous-pipes-for-local-interprocess-communication.md)
