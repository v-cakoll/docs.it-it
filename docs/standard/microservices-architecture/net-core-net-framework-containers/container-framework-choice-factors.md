---
title: Tabella decisioni. Framework .NET da usare per Docker
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Tabella decisioni, framework .NET da usare per Docker
ms.date: 09/11/2018
ms.openlocfilehash: 96b2750e52d64b06444b7f87dea624879f37d3d7
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65639173"
---
# <a name="decision-table-net-frameworks-to-use-for-docker"></a>Tabella decisioni: framework .NET da usare per Docker

La tabella decisioni seguente indica se usare .NET Framework o .NET Core. Tenere presente che per i contenitori Linux sono necessari host Docker (macchine virtuali o server) basati su Linux e che per i contenitori Windows sono necessari host Docker (macchine virtuali o server) basati su Windows Server.

> [!IMPORTANT]
> I computer di sviluppo eseguiranno un host Docker, Linux o Windows. I servizi correlati da eseguire e testare insieme in un'unica soluzione dovranno essere eseguiti sulla stessa piattaforma di contenitori.

<table>
<thead>
<tr class="header">
<th><strong>Architettura/Tipo di app</strong></th>
<th><strong>Contenitori Linux</strong></th>
<th><strong>Contenitori Windows</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Microservizi in contenitori</td>
<td>.NET Core</td>
<td>.NET Core</td>
</tr>
<tr class="even">
<td>App monolitica</td>
<td>.NET Core</td>
<td><p>.NET Framework</p>
<p>.NET Core</p></td>
</tr>
<tr class="odd">
<td>Prestazioni e scalabilità migliori del settore</td>
<td>.NET Core</td>
<td>.NET Core</td>
</tr>
<tr class="even">
<td>Migrazione di un'app legacy (brown field) Windows Server ai contenitori</td>
<td>--</td>
<td>.NET Framework</td>
</tr>
<tr class="odd">
<td>Nuovo sviluppo basato su contenitori (green field)</td>
<td>.NET Core</td>
<td>.NET Core</td>
</tr>
<tr class="even">
<td>ASP.NET Core</td>
<td>.NET Core</td>
<td><p>.NET Core (consigliato)</p>
<p>.NET Framework</p></td>
</tr>
<tr class="odd">
<td>ASP.NET 4 (MVC 5, Web API 2 e Web Form)</td>
<td>--</td>
<td>.NET Framework</td>
</tr>
<tr class="even">
<td>Servizi SignalR</td>
<td>.NET Core 2.1 o versioni successive</td>
<td><p>.NET Framework</p>
<p>.NET Core 2.1 o versioni successive</p></td>
</tr>
<tr class="odd">
<td>WCF, WF e altri framework legacy</td>
<td>WCF in .NET Core (solo la libreria client WCF)</td>
<td><p>.NET Framework</p>
<p>WCF in .NET Core (solo la libreria client WCF)</p></td>
</tr>
<tr class="even">
<td>Utilizzo di servizi di Azure</td>
<td><p>.NET Core</p>
<p>(prossimamente tutti i servizi di Azure forniranno SDK client per .NET Core)</p></td>
<td><p>.NET Framework</p>
<p>.NET Core</p>
<p>(prossimamente tutti i servizi di Azure forniranno SDK client per .NET Core)</p></td>
</tr>
</tbody>
</table>

>[!div class="step-by-step"]
>[Precedente](net-framework-container-scenarios.md)
>[Successivo](net-container-os-targets.md)
