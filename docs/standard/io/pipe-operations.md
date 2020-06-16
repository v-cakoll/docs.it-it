---
title: Operazioni pipe in .NET
description: 'Informazioni sulle operazioni di pipe in .NET. Le pipe rappresentano un mezzo che consente la comunicazione interprocesso. Esistono due tipi di pipe: le pipe anonime e le named pipe.'
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- pipes [.NET Framework]
- pipe operations [.NET Framework]
- interprocess communication [.NET Framework], pipes
- I/O [.NET Framework], pipes
ms.assetid: 7b964ebd-7a4f-4d28-8194-7841f9e4c702
ms.openlocfilehash: 35a3910bbab1b34f085a55524be0b18b3fa81958
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768885"
---
# <a name="pipe-operations-in-net"></a><span data-ttu-id="824dc-105">Operazioni pipe in .NET</span><span class="sxs-lookup"><span data-stu-id="824dc-105">Pipe Operations in .NET</span></span>
<span data-ttu-id="824dc-106">Le pipe rappresentano un mezzo che consente la comunicazione interprocesso.</span><span class="sxs-lookup"><span data-stu-id="824dc-106">Pipes provide a means for interprocess communication.</span></span> <span data-ttu-id="824dc-107">Sono disponibili due tipi di pipe:</span><span class="sxs-lookup"><span data-stu-id="824dc-107">There are two types of pipes:</span></span>  
  
- <span data-ttu-id="824dc-108">Unnamed pipe.</span><span class="sxs-lookup"><span data-stu-id="824dc-108">Anonymous pipes.</span></span>  
  
     <span data-ttu-id="824dc-109">Le unnamed pipe consentono la comunicazione interprocesso in un computer locale.</span><span class="sxs-lookup"><span data-stu-id="824dc-109">Anonymous pipes provide interprocess communication on a local computer.</span></span> <span data-ttu-id="824dc-110">Le unnamed pipe comportano un sovraccarico minore rispetto alle named pipe, ma offrono servizi limitati.</span><span class="sxs-lookup"><span data-stu-id="824dc-110">Anonymous pipes require less overhead than named pipes but offer limited services.</span></span> <span data-ttu-id="824dc-111">Le unnamed pipe sono unidirezionali e non possono essere usate in una rete.</span><span class="sxs-lookup"><span data-stu-id="824dc-111">Anonymous pipes are one-way and cannot be used over a network.</span></span> <span data-ttu-id="824dc-112">Supportano solo una singola istanza del server.</span><span class="sxs-lookup"><span data-stu-id="824dc-112">They support only a single server instance.</span></span> <span data-ttu-id="824dc-113">Le unnamed pipe sono utili per la comunicazione tra thread o tra processi padre e figlio in cui gli handle di pipe possono essere facilmente passati al processo figlio quando viene creato.</span><span class="sxs-lookup"><span data-stu-id="824dc-113">Anonymous pipes are useful for communication between threads, or between parent and child processes where the pipe handles can be easily passed to the child process when it is created.</span></span>  
  
     <span data-ttu-id="824dc-114">In .NET, le unnamed pipe vengono implementate tramite le classi <xref:System.IO.Pipes.AnonymousPipeServerStream> e <xref:System.IO.Pipes.AnonymousPipeClientStream>.</span><span class="sxs-lookup"><span data-stu-id="824dc-114">In .NET, you implement anonymous pipes by using the <xref:System.IO.Pipes.AnonymousPipeServerStream> and <xref:System.IO.Pipes.AnonymousPipeClientStream> classes.</span></span>  
  
     <span data-ttu-id="824dc-115">Vedere [Procedura: Usare le unnamed pipe per la comunicazione interprocesso locale](how-to-use-anonymous-pipes-for-local-interprocess-communication.md).</span><span class="sxs-lookup"><span data-stu-id="824dc-115">See [How to: Use Anonymous Pipes for Local Interprocess Communication](how-to-use-anonymous-pipes-for-local-interprocess-communication.md).</span></span>  
  
- <span data-ttu-id="824dc-116">Named pipe.</span><span class="sxs-lookup"><span data-stu-id="824dc-116">Named pipes.</span></span>  
  
     <span data-ttu-id="824dc-117">Le named pipe forniscono la comunicazione interprocesso tra un server pipe e uno o più client pipe.</span><span class="sxs-lookup"><span data-stu-id="824dc-117">Named pipes provide interprocess communication between a pipe server and one or more pipe clients.</span></span> <span data-ttu-id="824dc-118">Le named pipe possono essere unidirezionale o duplex.</span><span class="sxs-lookup"><span data-stu-id="824dc-118">Named pipes can be one-way or duplex.</span></span> <span data-ttu-id="824dc-119">Supportano la comunicazione basata su messaggi e consentono a più client di connettersi contemporaneamente al processo server tramite lo stesso nome di pipe.</span><span class="sxs-lookup"><span data-stu-id="824dc-119">They support message-based communication and allow multiple clients to connect simultaneously to the server process using the same pipe name.</span></span> <span data-ttu-id="824dc-120">Le named pipe supportano inoltre la rappresentazione, che consente ai processi di connessione di usare le proprie autorizzazioni nei server remoti.</span><span class="sxs-lookup"><span data-stu-id="824dc-120">Named pipes also support impersonation, which enables connecting processes to use their own permissions on remote servers.</span></span>  
  
     <span data-ttu-id="824dc-121">In .NET, le named pipe vengono implementate tramite le classi <xref:System.IO.Pipes.NamedPipeServerStream> e <xref:System.IO.Pipes.NamedPipeClientStream>.</span><span class="sxs-lookup"><span data-stu-id="824dc-121">In .NET, you implement named pipes by using the <xref:System.IO.Pipes.NamedPipeServerStream> and <xref:System.IO.Pipes.NamedPipeClientStream> classes.</span></span>  
  
     <span data-ttu-id="824dc-122">Vedere [Procedura: Usare le named pipe per la comunicazione interprocesso in rete](how-to-use-named-pipes-for-network-interprocess-communication.md).</span><span class="sxs-lookup"><span data-stu-id="824dc-122">See [How to: Use Named Pipes for Network Interprocess Communication](how-to-use-named-pipes-for-network-interprocess-communication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="824dc-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="824dc-123">See also</span></span>

- [<span data-ttu-id="824dc-124">I/O di file e di flussi</span><span class="sxs-lookup"><span data-stu-id="824dc-124">File and Stream I/O</span></span>](index.md)
- [<span data-ttu-id="824dc-125">Procedura: Usare le unnamed pipe per la comunicazione interprocesso locale</span><span class="sxs-lookup"><span data-stu-id="824dc-125">How to: Use Anonymous Pipes for Local Interprocess Communication</span></span>](how-to-use-anonymous-pipes-for-local-interprocess-communication.md)
- [<span data-ttu-id="824dc-126">Procedura: Usare le named pipe per la comunicazione interprocesso in rete</span><span class="sxs-lookup"><span data-stu-id="824dc-126">How to: Use Named Pipes for Network Interprocess Communication</span></span>](how-to-use-named-pipes-for-network-interprocess-communication.md)
