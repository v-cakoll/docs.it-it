---
title: Operazioni pipe in .NET Framework
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- pipes [.NET Framework]
- pipe operations [.NET Framework]
- interprocess communication [.NET Framework], pipes
- I/O [.NET Framework], pipes
ms.assetid: 7b964ebd-7a4f-4d28-8194-7841f9e4c702
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1e0d2747abbacf766ddeda6f41404d8701cbc273
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33574366"
---
# <a name="pipe-operations-in-the-net-framework"></a><span data-ttu-id="66ef7-102">Operazioni pipe in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="66ef7-102">Pipe Operations in the .NET Framework</span></span>
<span data-ttu-id="66ef7-103">Le pipe rappresentano un mezzo che consente la comunicazione interprocesso.</span><span class="sxs-lookup"><span data-stu-id="66ef7-103">Pipes provide a means for interprocess communication.</span></span> <span data-ttu-id="66ef7-104">Sono disponibili due tipi di pipe:</span><span class="sxs-lookup"><span data-stu-id="66ef7-104">There are two types of pipes:</span></span>  
  
-   <span data-ttu-id="66ef7-105">Unnamed pipe.</span><span class="sxs-lookup"><span data-stu-id="66ef7-105">Anonymous pipes.</span></span>  
  
     <span data-ttu-id="66ef7-106">Le unnamed pipe consentono la comunicazione interprocesso in un computer locale.</span><span class="sxs-lookup"><span data-stu-id="66ef7-106">Anonymous pipes provide interprocess communication on a local computer.</span></span> <span data-ttu-id="66ef7-107">Le unnamed pipe comportano un sovraccarico minore rispetto alle named pipe, ma offrono servizi limitati.</span><span class="sxs-lookup"><span data-stu-id="66ef7-107">Anonymous pipes require less overhead than named pipes but offer limited services.</span></span> <span data-ttu-id="66ef7-108">Le unnamed pipe sono unidirezionali e non possono essere usate in una rete.</span><span class="sxs-lookup"><span data-stu-id="66ef7-108">Anonymous pipes are one-way and cannot be used over a network.</span></span> <span data-ttu-id="66ef7-109">Supportano solo una singola istanza del server.</span><span class="sxs-lookup"><span data-stu-id="66ef7-109">They support only a single server instance.</span></span> <span data-ttu-id="66ef7-110">Le unnamed pipe sono utili per la comunicazione tra thread o tra processi padre e figlio in cui gli handle di pipe possono essere facilmente passati al processo figlio quando viene creato.</span><span class="sxs-lookup"><span data-stu-id="66ef7-110">Anonymous pipes are useful for communication between threads, or between parent and child processes where the pipe handles can be easily passed to the child process when it is created.</span></span>  
  
     <span data-ttu-id="66ef7-111">In .NET Framework, le unnamed pipe vengono implementate mediante le classi <xref:System.IO.Pipes.AnonymousPipeServerStream> e <xref:System.IO.Pipes.AnonymousPipeClientStream>.</span><span class="sxs-lookup"><span data-stu-id="66ef7-111">In the .NET Framework, you implement anonymous pipes by using the <xref:System.IO.Pipes.AnonymousPipeServerStream> and <xref:System.IO.Pipes.AnonymousPipeClientStream> classes.</span></span>  
  
     <span data-ttu-id="66ef7-112">Vedere [Procedura: Usare le unnamed pipe per la comunicazione interprocesso locale](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md).</span><span class="sxs-lookup"><span data-stu-id="66ef7-112">See [How to: Use Anonymous Pipes for Local Interprocess Communication](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md).</span></span>  
  
-   <span data-ttu-id="66ef7-113">Named pipe.</span><span class="sxs-lookup"><span data-stu-id="66ef7-113">Named pipes.</span></span>  
  
     <span data-ttu-id="66ef7-114">Le named pipe forniscono la comunicazione interprocesso tra un server pipe e uno o più client pipe.</span><span class="sxs-lookup"><span data-stu-id="66ef7-114">Named pipes provide interprocess communication between a pipe server and one or more pipe clients.</span></span> <span data-ttu-id="66ef7-115">Le named pipe possono essere unidirezionale o duplex.</span><span class="sxs-lookup"><span data-stu-id="66ef7-115">Named pipes can be one-way or duplex.</span></span> <span data-ttu-id="66ef7-116">Supportano la comunicazione basata su messaggi e consentono a più client di connettersi contemporaneamente al processo server tramite lo stesso nome di pipe.</span><span class="sxs-lookup"><span data-stu-id="66ef7-116">They support message-based communication and allow multiple clients to connect simultaneously to the server process using the same pipe name.</span></span> <span data-ttu-id="66ef7-117">Le named pipe supportano inoltre la rappresentazione, che consente ai processi di connessione di usare le proprie autorizzazioni nei server remoti.</span><span class="sxs-lookup"><span data-stu-id="66ef7-117">Named pipes also support impersonation, which enables connecting processes to use their own permissions on remote servers.</span></span>  
  
     <span data-ttu-id="66ef7-118">In .NET Framework, le named pipe vengono implementate mediante le classi <xref:System.IO.Pipes.NamedPipeServerStream> e <xref:System.IO.Pipes.NamedPipeClientStream>.</span><span class="sxs-lookup"><span data-stu-id="66ef7-118">In the .NET Framework, you implement named pipes by using the <xref:System.IO.Pipes.NamedPipeServerStream> and <xref:System.IO.Pipes.NamedPipeClientStream> classes.</span></span>  
  
     <span data-ttu-id="66ef7-119">Vedere [Procedura: Usare le named pipe per la comunicazione interprocesso in rete](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md).</span><span class="sxs-lookup"><span data-stu-id="66ef7-119">See [How to: Use Named Pipes for Network Interprocess Communication](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66ef7-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66ef7-120">See Also</span></span>  
 [<span data-ttu-id="66ef7-121">I/O di file e di flussi</span><span class="sxs-lookup"><span data-stu-id="66ef7-121">File and Stream I/O</span></span>](../../../docs/standard/io/index.md)  
 [<span data-ttu-id="66ef7-122">Procedura: Usare le unnamed pipe per la comunicazione interprocesso locale</span><span class="sxs-lookup"><span data-stu-id="66ef7-122">How to: Use Anonymous Pipes for Local Interprocess Communication</span></span>](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md)  
 [<span data-ttu-id="66ef7-123">Procedura: Usare le named pipe per la comunicazione interprocesso in rete</span><span class="sxs-lookup"><span data-stu-id="66ef7-123">How to: Use Named Pipes for Network Interprocess Communication</span></span>](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md)
