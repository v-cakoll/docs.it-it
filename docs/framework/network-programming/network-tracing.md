---
title: Tracciatura di rete in .NET Framework
ms.date: 03/30/2017
helpviewer_keywords:
- debugging [.NET Framework], network tracing
- methods, network tracing
- Networking
- trace enabled debugging
- network tracing, about network tracing
- network tracing
- network, network tracing
- traffic tracing
- tracing [.NET Framework], network
- deploying applications [.NET Framework], network traffic
- capturing network traffic
- Internet, network tracing
- Network Resources
- output, network tracing
- method invocations
ms.assetid: e993b7c3-087f-45d8-9c02-9dded936d804
ms.openlocfilehash: afb9c3a04258b543e373b6973e576f71f90d7003
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "71047585"
---
# <a name="network-tracing-in-the-net-framework"></a>Tracciatura di rete in .NET Framework
La funzionalità di traccia di rete in .NET Framework consente di accedere alle informazioni sulle chiamate ai metodi e sul traffico di rete generato da un'applicazione gestita. Questa funzionalità è utile per il debug delle applicazioni in fase di sviluppo, nonché per l'analisi delle applicazioni distribuite. È possibile personalizzare l'output generato dalla tracciatura della rete per supportare differenti scenari di utilizzo in fase di sviluppo e nell'ambiente di produzione.  
  
 Per abilitare la traccia di rete in .NET Framework, è necessario selezionare una destinazione per l'output della traccia e aggiungere impostazioni di configurazione della traccia di rete al file di configurazione dell'applicazione o del computer. Per informazioni sui file di configurazione e sul relativo uso, vedere [File di configurazione](../configure-apps/index.md). Per informazioni su come abilitare la traccia di rete, vedere [Abilitazione della traccia di rete](enabling-network-tracing.md). Per informazioni sulle impostazioni che è necessario aggiungere al file di configurazione, vedere [Procedura: Configurare la traccia di rete](how-to-configure-network-tracing.md).  
  
 Quando la funzionalità di traccia è abilitata, è possibile acquisire le informazioni di traccia che vengono restituite dalle classi **System.Net**. I membri delle classi della rete che generano le informazioni sulla traccia includono la nota riportata nella sezione relativa alle osservazioni della relativa documentazione della libreria di classi di .NET Framework:  
  
> [!NOTE]
> Questo membro genera informazioni di traccia quando viene abilitata la funzionalità di traccia di rete nell'applicazione in uso. Per ulteriori informazioni, vedere Traccia di rete.  
  
## <a name="see-also"></a>Vedere anche

- [Abilitazione della traccia di rete](enabling-network-tracing.md)
- [Procedura: Configurare la traccia di rete](how-to-configure-network-tracing.md)
- [Interpretazione della traccia di rete](interpreting-network-tracing.md)
- [Traccia e strumentazione di applicazioni](../debug-trace-profile/tracing-and-instrumenting-applications.md)
