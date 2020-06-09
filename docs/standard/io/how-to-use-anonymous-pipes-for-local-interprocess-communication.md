---
title: 'Procedura: Usare le unnamed pipe per la comunicazione interprocesso locale'
description: Informazioni su come usare le pipe anonime per la comunicazione interprocesso locale in un computer locale in .NET. Le pipe anonime richiedono un sovraccarico minore rispetto alle named pipe.
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
ms.openlocfilehash: 090a25aea4f280fc2ad00cf7777a501c475dfc66
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594803"
---
# <a name="how-to-use-anonymous-pipes-for-local-interprocess-communication"></a><span data-ttu-id="26b82-104">Procedura: Usare le unnamed pipe per la comunicazione interprocesso locale</span><span class="sxs-lookup"><span data-stu-id="26b82-104">How to: Use Anonymous Pipes for Local Interprocess Communication</span></span>
<span data-ttu-id="26b82-105">Le unnamed pipe consentono la comunicazione interprocesso in un computer locale.</span><span class="sxs-lookup"><span data-stu-id="26b82-105">Anonymous pipes provide interprocess communication on a local computer.</span></span> <span data-ttu-id="26b82-106">Offrono meno funzionalità rispetto alle named pipe, ma richiedono anche meno overhead.</span><span class="sxs-lookup"><span data-stu-id="26b82-106">They offer less functionality than named pipes, but also require less overhead.</span></span> <span data-ttu-id="26b82-107">È possibile usare le unnamed pipe per semplificare la comunicazione interprocesso in un computer locale.</span><span class="sxs-lookup"><span data-stu-id="26b82-107">You can use anonymous pipes to make interprocess communication on a local computer easier.</span></span> <span data-ttu-id="26b82-108">Non è possibile usare le unnamed pipe per la comunicazione in rete.</span><span class="sxs-lookup"><span data-stu-id="26b82-108">You cannot use anonymous pipes for communication over a network.</span></span>  
  
 <span data-ttu-id="26b82-109">Per implementare le pipe anonime, utilizzare le classi <xref:System.IO.Pipes.AnonymousPipeServerStream> e <xref:System.IO.Pipes.AnonymousPipeClientStream>.</span><span class="sxs-lookup"><span data-stu-id="26b82-109">To implement anonymous pipes, use the <xref:System.IO.Pipes.AnonymousPipeServerStream> and <xref:System.IO.Pipes.AnonymousPipeClientStream> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="26b82-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="26b82-110">Example</span></span>  
 <span data-ttu-id="26b82-111">L'esempio seguente illustra come inviare una stringa da un processo padre a un processo figlio usando unnamed pipe.</span><span class="sxs-lookup"><span data-stu-id="26b82-111">The following example demonstrates a way to send a string from a parent process to a child process using anonymous pipes.</span></span> <span data-ttu-id="26b82-112">Questo esempio crea un oggetto <xref:System.IO.Pipes.AnonymousPipeServerStream> in un processo padre con un valore di <xref:System.IO.Pipes.PipeDirection> equivalente a <xref:System.IO.Pipes.PipeDirection.Out>.</span><span class="sxs-lookup"><span data-stu-id="26b82-112">This example creates an <xref:System.IO.Pipes.AnonymousPipeServerStream> object in a parent process with a <xref:System.IO.Pipes.PipeDirection> value of <xref:System.IO.Pipes.PipeDirection.Out>.</span></span> <span data-ttu-id="26b82-113">Il processo padre crea quindi un processo figlio usando un handle client per creare un oggetto <xref:System.IO.Pipes.AnonymousPipeClientStream>.</span><span class="sxs-lookup"><span data-stu-id="26b82-113">The parent process then creates a child process by using a client handle to create an <xref:System.IO.Pipes.AnonymousPipeClientStream> object.</span></span> <span data-ttu-id="26b82-114">Il processo figlio ha un valore di <xref:System.IO.Pipes.PipeDirection> equivalente a <xref:System.IO.Pipes.PipeDirection.In>.</span><span class="sxs-lookup"><span data-stu-id="26b82-114">The child process has a <xref:System.IO.Pipes.PipeDirection> value of <xref:System.IO.Pipes.PipeDirection.In>.</span></span>  
  
 <span data-ttu-id="26b82-115">Il processo padre invia quindi una stringa fornita dall'utente al processo figlio.</span><span class="sxs-lookup"><span data-stu-id="26b82-115">The parent process then sends a user-supplied string to the child process.</span></span> <span data-ttu-id="26b82-116">La stringa viene visualizzata nella console del processo figlio.</span><span class="sxs-lookup"><span data-stu-id="26b82-116">The string is displayed to the console in the child process.</span></span>  
  
 <span data-ttu-id="26b82-117">L'esempio seguente mostra il processo server.</span><span class="sxs-lookup"><span data-stu-id="26b82-117">The following example shows the server process.</span></span>  
  
 [!code-cpp[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/vb/program.vb#01)]  

[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]
  
## <a name="example"></a><span data-ttu-id="26b82-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="26b82-118">Example</span></span>  
 <span data-ttu-id="26b82-119">L'esempio seguente mostra il processo client.</span><span class="sxs-lookup"><span data-stu-id="26b82-119">The following example shows the client process.</span></span> <span data-ttu-id="26b82-120">Il processo server avvia il processo client e fornisce al processo un handle client.</span><span class="sxs-lookup"><span data-stu-id="26b82-120">The server process starts the client process and gives that process a client handle.</span></span> <span data-ttu-id="26b82-121">Il file eseguibile risultante dal codice client deve essere denominato `pipeClient.exe` e copiato nella stessa directory del file eseguibile server prima di eseguire il processo server.</span><span class="sxs-lookup"><span data-stu-id="26b82-121">The resulting executable from the client code should be named `pipeClient.exe` and be copied to the same directory as the server executable before running the server process.</span></span>  
  
 [!code-cpp[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/vb/program.vb#01)]  
  
## <a name="see-also"></a><span data-ttu-id="26b82-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="26b82-122">See also</span></span>

- [<span data-ttu-id="26b82-123">Pipe</span><span class="sxs-lookup"><span data-stu-id="26b82-123">Pipes</span></span>](pipe-operations.md)
- [<span data-ttu-id="26b82-124">Procedura: Usare le named pipe per la comunicazione interprocesso in rete</span><span class="sxs-lookup"><span data-stu-id="26b82-124">How to: Use Named Pipes for Network Interprocess Communication</span></span>](how-to-use-named-pipes-for-network-interprocess-communication.md)
