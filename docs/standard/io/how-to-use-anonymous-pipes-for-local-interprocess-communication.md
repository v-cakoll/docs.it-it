---
title: 'Procedura: utilizzare le unnamed pipe per la comunicazione interprocesso locale'
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
- anonymous pipes [.NET Framework]
- parent-child communication [.NET Framework]
- pipes [.NET Framework]
- one-way communication [.NET Framework]
- local computer communication [.NET Framework], pipes
ms.assetid: e7773c77-c646-4a01-8a96-a003d59fc4c9
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f457cc91e6fbfc118e5363d1b0a8e8c2ad800748
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-anonymous-pipes-for-local-interprocess-communication"></a>Procedura: utilizzare le unnamed pipe per la comunicazione interprocesso locale
Le unnamed pipe forniscono la comunicazione interprocesso in un computer locale. Offrono meno funzionalità rispetto alle named pipe, ma richiedono anche meno overhead. È possibile utilizzare le unnamed pipe per semplificare la comunicazione interprocesso in un computer locale. Non è possibile utilizzare le unnamed pipe per la comunicazione in rete.  
  
 Per implementare le pipe anonime, utilizzare le classi <xref:System.IO.Pipes.AnonymousPipeServerStream> e <xref:System.IO.Pipes.AnonymousPipeClientStream>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato un modo per inviare una stringa da un processo padre a un processo figlio utilizzando le unnamed pipe. Questo esempio viene creato un <xref:System.IO.Pipes.AnonymousPipeServerStream> oggetto in un processo padre con un <xref:System.IO.Pipes.PipeDirection> valore <xref:System.IO.Pipes.PipeDirection.Out>. Il processo padre crea quindi un processo figlio tramite un handle del client per creare un <xref:System.IO.Pipes.AnonymousPipeClientStream> oggetto. Il processo figlio ha un <xref:System.IO.Pipes.PipeDirection> valore <xref:System.IO.Pipes.PipeDirection.In>.  
  
 Il processo padre invia quindi una stringa fornita dall'utente per il processo figlio. La stringa viene visualizzata nella console del processo figlio.  
  
 Nell'esempio seguente viene illustrato il processo server.  
  
 [!code-cpp[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/vb/program.vb#01)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato il processo client. Il processo server avvia il processo client e fornisce un handle del client di tale processo. Il file eseguibile risultante dal codice client deve essere denominato `pipeClient.exe` e copiato alla stessa directory del file eseguibile prima di eseguire il processo del server del server.  
  
 [!code-cpp[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/vb/program.vb#01)]  
  
## <a name="see-also"></a>Vedere anche  
 [Pipe](../../../docs/standard/io/pipe-operations.md)  
 [Procedura: Usare le named pipe per la comunicazione interprocesso in rete](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md)
