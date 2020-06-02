---
title: 'Procedura: Usare le unnamed pipe per la comunicazione interprocesso locale'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- anonymous pipes [.NET Framework]
- parent-child communication [.NET Framework]
- pipes [.NET Framework]
- one-way communication [.NET Framework]
- local computer communication [.NET Framework], pipes
ms.assetid: e7773c77-c646-4a01-8a96-a003d59fc4c9
ms.openlocfilehash: 9962471697888041e98e38dd5f7feaecc306894d
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291786"
---
# <a name="how-to-use-anonymous-pipes-for-local-interprocess-communication"></a><span data-ttu-id="8369b-102">Procedura: Usare le unnamed pipe per la comunicazione interprocesso locale</span><span class="sxs-lookup"><span data-stu-id="8369b-102">How to: Use Anonymous Pipes for Local Interprocess Communication</span></span>
<span data-ttu-id="8369b-103">Le unnamed pipe consentono la comunicazione interprocesso in un computer locale.</span><span class="sxs-lookup"><span data-stu-id="8369b-103">Anonymous pipes provide interprocess communication on a local computer.</span></span> <span data-ttu-id="8369b-104">Offrono meno funzionalità rispetto alle named pipe, ma richiedono anche meno overhead.</span><span class="sxs-lookup"><span data-stu-id="8369b-104">They offer less functionality than named pipes, but also require less overhead.</span></span> <span data-ttu-id="8369b-105">È possibile usare le unnamed pipe per semplificare la comunicazione interprocesso in un computer locale.</span><span class="sxs-lookup"><span data-stu-id="8369b-105">You can use anonymous pipes to make interprocess communication on a local computer easier.</span></span> <span data-ttu-id="8369b-106">Non è possibile usare le unnamed pipe per la comunicazione in rete.</span><span class="sxs-lookup"><span data-stu-id="8369b-106">You cannot use anonymous pipes for communication over a network.</span></span>  
  
 <span data-ttu-id="8369b-107">Per implementare le pipe anonime, utilizzare le classi <xref:System.IO.Pipes.AnonymousPipeServerStream> e <xref:System.IO.Pipes.AnonymousPipeClientStream>.</span><span class="sxs-lookup"><span data-stu-id="8369b-107">To implement anonymous pipes, use the <xref:System.IO.Pipes.AnonymousPipeServerStream> and <xref:System.IO.Pipes.AnonymousPipeClientStream> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8369b-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="8369b-108">Example</span></span>  
 <span data-ttu-id="8369b-109">L'esempio seguente illustra come inviare una stringa da un processo padre a un processo figlio usando unnamed pipe.</span><span class="sxs-lookup"><span data-stu-id="8369b-109">The following example demonstrates a way to send a string from a parent process to a child process using anonymous pipes.</span></span> <span data-ttu-id="8369b-110">Questo esempio crea un oggetto <xref:System.IO.Pipes.AnonymousPipeServerStream> in un processo padre con un valore di <xref:System.IO.Pipes.PipeDirection> equivalente a <xref:System.IO.Pipes.PipeDirection.Out>.</span><span class="sxs-lookup"><span data-stu-id="8369b-110">This example creates an <xref:System.IO.Pipes.AnonymousPipeServerStream> object in a parent process with a <xref:System.IO.Pipes.PipeDirection> value of <xref:System.IO.Pipes.PipeDirection.Out>.</span></span> <span data-ttu-id="8369b-111">Il processo padre crea quindi un processo figlio usando un handle client per creare un oggetto <xref:System.IO.Pipes.AnonymousPipeClientStream>.</span><span class="sxs-lookup"><span data-stu-id="8369b-111">The parent process then creates a child process by using a client handle to create an <xref:System.IO.Pipes.AnonymousPipeClientStream> object.</span></span> <span data-ttu-id="8369b-112">Il processo figlio ha un valore di <xref:System.IO.Pipes.PipeDirection> equivalente a <xref:System.IO.Pipes.PipeDirection.In>.</span><span class="sxs-lookup"><span data-stu-id="8369b-112">The child process has a <xref:System.IO.Pipes.PipeDirection> value of <xref:System.IO.Pipes.PipeDirection.In>.</span></span>  
  
 <span data-ttu-id="8369b-113">Il processo padre invia quindi una stringa fornita dall'utente al processo figlio.</span><span class="sxs-lookup"><span data-stu-id="8369b-113">The parent process then sends a user-supplied string to the child process.</span></span> <span data-ttu-id="8369b-114">La stringa viene visualizzata nella console del processo figlio.</span><span class="sxs-lookup"><span data-stu-id="8369b-114">The string is displayed to the console in the child process.</span></span>  
  
 <span data-ttu-id="8369b-115">L'esempio seguente mostra il processo server.</span><span class="sxs-lookup"><span data-stu-id="8369b-115">The following example shows the server process.</span></span>  
  
 [!code-cpp[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/vb/program.vb#01)]  

[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]
  
## <a name="example"></a><span data-ttu-id="8369b-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="8369b-116">Example</span></span>  
 <span data-ttu-id="8369b-117">L'esempio seguente mostra il processo client.</span><span class="sxs-lookup"><span data-stu-id="8369b-117">The following example shows the client process.</span></span> <span data-ttu-id="8369b-118">Il processo server avvia il processo client e fornisce al processo un handle client.</span><span class="sxs-lookup"><span data-stu-id="8369b-118">The server process starts the client process and gives that process a client handle.</span></span> <span data-ttu-id="8369b-119">Il file eseguibile risultante dal codice client deve essere denominato `pipeClient.exe` e copiato nella stessa directory del file eseguibile server prima di eseguire il processo server.</span><span class="sxs-lookup"><span data-stu-id="8369b-119">The resulting executable from the client code should be named `pipeClient.exe` and be copied to the same directory as the server executable before running the server process.</span></span>  
  
 [!code-cpp[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/vb/program.vb#01)]  
  
## <a name="see-also"></a><span data-ttu-id="8369b-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8369b-120">See also</span></span>

- [<span data-ttu-id="8369b-121">Pipe</span><span class="sxs-lookup"><span data-stu-id="8369b-121">Pipes</span></span>](pipe-operations.md)
- [<span data-ttu-id="8369b-122">Procedura: Usare le named pipe per la comunicazione interprocesso in rete</span><span class="sxs-lookup"><span data-stu-id="8369b-122">How to: Use Named Pipes for Network Interprocess Communication</span></span>](how-to-use-named-pipes-for-network-interprocess-communication.md)
