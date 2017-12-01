---
title: Operazioni pipe in .NET Framework
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipes [.NET Framework]
- pipe operations [.NET Framework]
- interprocess communication [.NET Framework], pipes
- I/O [.NET Framework], pipes
ms.assetid: 7b964ebd-7a4f-4d28-8194-7841f9e4c702
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 879e5a73417f9347224bc22b397814b83972751c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="pipe-operations-in-the-net-framework"></a>Operazioni pipe in .NET Framework
Pipe forniscono un mezzo per la comunicazione interprocesso. Esistono due tipi di pipe:  
  
-   Unnamed pipe.  
  
     Le unnamed pipe forniscono la comunicazione interprocesso in un computer locale. Le unnamed pipe comportano un sovraccarico minore rispetto alle named pipe, ma offrono servizi limitati. Le unnamed pipe sono unidirezionali e non possono essere utilizzate in una rete. Supportano solo una singola istanza del server. Le unnamed pipe sono utili per la comunicazione tra thread o tra processi padre e figlio in cui gli handle di pipe possono essere facilmente passati al processo figlio quando viene creato.  
  
     In .NET Framework, si implementano le unnamed pipe mediante il <xref:System.IO.Pipes.AnonymousPipeServerStream> e <xref:System.IO.Pipes.AnonymousPipeClientStream> classi.  
  
     Vedere [procedura: utilizzare le unnamed pipe per la comunicazione interprocesso locale](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md).  
  
-   Named pipe.  
  
     Named pipe forniscono la comunicazione interprocesso tra un server di pipe e uno o più client pipe. Named pipe possono essere unidirezionale o duplex. Supportano la comunicazione basata su messaggi e consentire a più client di connettersi contemporaneamente al processo del server utilizzando lo stesso nome di pipe. Named pipe supportano inoltre la rappresentazione, che consente ai processi di connessione utilizzare le proprie autorizzazioni nei server remoti.  
  
     In .NET Framework, named pipe vengono implementate utilizzando il <xref:System.IO.Pipes.NamedPipeServerStream> e <xref:System.IO.Pipes.NamedPipeClientStream> classi.  
  
     Vedere [procedura: utilizzare le Named pipe per la comunicazione interprocesso rete](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md).  
  
## <a name="see-also"></a>Vedere anche  
 [I/O di file e di flussi](../../../docs/standard/io/index.md)  
 [Procedura: Usare le unnamed pipe per la comunicazione interprocesso locale](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md)  
 [Procedura: Usare le named pipe per la comunicazione interprocesso in rete](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md)
