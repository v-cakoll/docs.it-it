---
title: Come scegliere il sistema operativo per i contenitori .NET
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Come scegliere il sistema operativo per i contenitori .NET
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 01/07/2019
ms.openlocfilehash: bef268a180584c47486a16960ca13fd63201fbe2
ms.sourcegitcommit: dcc8feeff4718664087747529638ec9b47e65234
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/31/2019
ms.locfileid: "55479867"
---
# <a name="what-os-to-target-with-net-containers"></a>Come scegliere il sistema operativo per i contenitori .NET

Considerata la varietà di sistemi operativi supportati da Docker e le differenze tra .NET Framework e .NET Core, è necessario scegliere un sistema operativo e le versioni specifiche a seconda del framework in uso.

Per Windows, è possibile usare Windows Server Core o Windows Nano Server. Queste versioni di Windows offrono caratteristiche diverse (IIS in Windows Server Core rispetto a un server Web self-hosted come Kestrel in Windows Nano Server) che potrebbero essere richieste rispettivamente da .NET Framework o .NET Core.

Per Linux, sono disponibili più distribuzioni supportate in immagini Docker. NET ufficiali, ad esempio Debian.

Nella figura 3-1 sono mostrate le versioni possibili del sistema operativo a seconda del framework .NET usato.

![Quando si distribuiscono applicazioni .NET Framework legacy, è necessario usare come destinazione Windows Server Core, che è compatibile con le app legacy e IIS e ha un'immagine di dimensioni maggiori. Quando si distribuiscono applicazioni .NET Core, è possibile usare come destinazione Windows Nano Server, che è ottimizzato per il cloud, usa Kestrel, è di dimensioni inferiori e viene avviato più rapidamente. È anche possibile usare come destinazione Linux, che supporta Debian, Alpine e altri sistemi. Anche Linux usa Kestrel, è di dimensioni inferiori e viene avviato più rapidamente.](./media/image1.png)

**Figura 3-1.** Sistemi operativi possibili a seconda delle versioni del framework .NET

È anche possibile creare un'immagine Docker personalizzata, se si vuole usare una distribuzione Linux diversa o un'immagine con versioni non fornite da Microsoft. Si può ad esempio creare un'immagine con ASP.NET Core in esecuzione in .NET Framework tradizionale e in Windows Server Core, che non rappresenta uno scenario così comune per Docker.

Quando si aggiunge il nome dell'immagine al file Dockerfile, è possibile selezionare il sistema operativo e la versione a seconda del tag usato, come negli esempi seguenti:

<table>
<thead>
<tr class="header">
<th>Image</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr>
<td>microsoft/dotnet:2.2-runtime</td>
<td>Multiarchitettura .NET Core 2.2: supporta Linux e Windows Nano Server a seconda dell'host Docker.</td>
</tr>
<tr class="odd">
<td>microsoft/dotnet:2.2-aspnetcore-runtime</td>
<td><p>Multiarchitettura ASP .NET Core 2.2: supporta Linux e Windows Nano Server a seconda dell'host Docker.</p>
<p>L'immagine aspnetcore ha poche ottimizzazioni per ASP.NET Core.</p></td>
</tr>
<tr class="even">
<td>microsoft/dotnet:2.2-aspnetcore-runtime-alpine</td>
<td>Solo runtime .NET Core 2.2 in distribuzioni Linux Alpine</td>
</tr>
<tr class="odd">
<td>microsoft/dotnet:2.2-aspnetcore-runtime-nanoserver-1803</td>
<td>Solo runtime .NET Core 2.2 in Windows Nano Server (Windows Server versione 1803)</td>
</tr>
</tbody>
</table>

>[!div class="step-by-step"]
>[Precedente](container-framework-choice-factors.md)
>[Successivo](official-net-docker-images.md)