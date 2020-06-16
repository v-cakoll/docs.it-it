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
# <a name="pipe-operations-in-net"></a>Operazioni pipe in .NET
Le pipe rappresentano un mezzo che consente la comunicazione interprocesso. Sono disponibili due tipi di pipe:  
  
- Unnamed pipe.  
  
     Le unnamed pipe consentono la comunicazione interprocesso in un computer locale. Le unnamed pipe comportano un sovraccarico minore rispetto alle named pipe, ma offrono servizi limitati. Le unnamed pipe sono unidirezionali e non possono essere usate in una rete. Supportano solo una singola istanza del server. Le unnamed pipe sono utili per la comunicazione tra thread o tra processi padre e figlio in cui gli handle di pipe possono essere facilmente passati al processo figlio quando viene creato.  
  
     In .NET, le unnamed pipe vengono implementate tramite le classi <xref:System.IO.Pipes.AnonymousPipeServerStream> e <xref:System.IO.Pipes.AnonymousPipeClientStream>.  
  
     Vedere [Procedura: Usare le unnamed pipe per la comunicazione interprocesso locale](how-to-use-anonymous-pipes-for-local-interprocess-communication.md).  
  
- Named pipe.  
  
     Le named pipe forniscono la comunicazione interprocesso tra un server pipe e uno o più client pipe. Le named pipe possono essere unidirezionale o duplex. Supportano la comunicazione basata su messaggi e consentono a più client di connettersi contemporaneamente al processo server tramite lo stesso nome di pipe. Le named pipe supportano inoltre la rappresentazione, che consente ai processi di connessione di usare le proprie autorizzazioni nei server remoti.  
  
     In .NET, le named pipe vengono implementate tramite le classi <xref:System.IO.Pipes.NamedPipeServerStream> e <xref:System.IO.Pipes.NamedPipeClientStream>.  
  
     Vedere [Procedura: Usare le named pipe per la comunicazione interprocesso in rete](how-to-use-named-pipes-for-network-interprocess-communication.md).  
  
## <a name="see-also"></a>Vedere anche

- [I/O di file e di flussi](index.md)
- [Procedura: Usare le unnamed pipe per la comunicazione interprocesso locale](how-to-use-anonymous-pipes-for-local-interprocess-communication.md)
- [Procedura: Usare le named pipe per la comunicazione interprocesso in rete](how-to-use-named-pipes-for-network-interprocess-communication.md)
