---
title: Requisiti di sistema di .NET Framework
description: Informazioni sui requisiti hardware, software e del sistema operativo per installare .NET Framework 4.5 e versioni successive.
ms.custom: updateeachrelease
ms.date: 02/02/2018
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
helpviewer_keywords:
- software requirements
- .NET Framework, system requirements
- system requirements
- operating systems supported
- hardware requirements
ms.assetid: 298275e2-da1d-4618-9f74-6a3567832350
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a0cfbcbc4c2c0857c1fe4163484a43f4521444a3
ms.sourcegitcommit: be1fb5d9447ad459bef22b91a91c72e3e0b2d916
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2018
---
# <a name="net-framework-system-requirements"></a>Requisiti di sistema di .NET Framework

Nelle tabelle presenti in questo argomento sono indicati i requisiti hardware, software e del sistema operativo per le versioni di .NET Framework seguenti:

* .NET framework 4.5 e relative versioni intermedie (4.5.1 e 4.5.2).
* .NET framework 4.6 e relative versioni intermedie (4.6.1 e 4.6.2).
* .NET framework 4.7 e relative versioni intermedie (4.7.1).

Gli ambienti di sviluppo che consentono di sviluppare app per .NET Framework dispongono di un set di requisiti separato.

> [!IMPORTANT]
> Tutte le versioni di .NET Framework successive a .NET Framework 4 sono aggiornamenti sul posto, quindi in un sistema può essere presente una singola versione 4.x.
> Inoltre, specifiche versioni di .NET Framework sono preinstallate in alcune versioni del sistema operativo Windows. Vale a dire che:
>
> * Se nel computer è già installata una versione successiva, non è possibile installare una versione 4.x precedente.
> * Se nel sistema operativo è preinstallata una versione particolare di .NET, non è possibile installare una versione 4.x precedente nello stesso computer.
> * Se si installa una versione successiva, non è necessario disinstallare prima la versione precedente.

Per informazioni su download e collegamenti, vedere [Install the .NET Framework for developers](../../../docs/framework/install/guide-for-developers.md) (Installazione di .NET Framework per sviluppatori).

Per informazioni sul ciclo di vita del supporto delle versioni di .NET Framework, vedere [Ciclo di vita del supporto Microsoft](https://support.microsoft.com/en-us/lifecycle/search?sort=PN&alpha=Microsoft%20.NET%20Framework&Filter=FilterNO).

## <a name="hardware-requirements"></a>Requisiti hardware

|                          |        |
| ------------------------ | ------ |
| **Processore**            | 1 GHz  |
| **RAM**                  | 512 MB |
| **Spazio su disco (minimo)** |        |
| 32 bit                   | 4,5 GB |
| 64 bit                   | 4,5 GB |

## <a name="installation-requirements"></a>Requisiti di installazione

Per l'installazione di .NET Framework è necessario avere privilegi di amministratore. Se non si hanno diritti di amministratore nel computer in cui si vuole installare .NET Framework, contattare l'amministratore di rete.

## <a name="supported-client-operating-systems"></a>Sistemi operativi client supportati

| Sistema operativo | Edizioni supportate | Preinstallato con il sistema operativo | Installabile separatamente |
| ---------------- | ------------------ | ------------------------ | ---------------------- |
| Windows 10 Fall Creators Update | 32 e 64 bit | .NET Framework 4.7.1 | |
| Windows 10 Creators Update | 32 e 64 bit | .NET Framework 4.7 | .NET Framework 4.7.1 | 
| Aggiornamento dell'anniversario di Windows 10 | 32 e 64 bit | [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]|.NET Framework 4.7<br/><br/>.NET Framework 4.7.1 |
| Aggiornamento di novembre di Windows 10 | 32 e 64 bit | .NET Framework 4.6.1 | .NET Framework 4.6.2 |
| Windows 10 | 32 e 64 bit | .NET Framework 4.6 | .NET Framework 4.6.1 <br/><br/> .NET Framework 4.6.2 |
| [!INCLUDE[win81](../../../includes/win81-md.md)] | 32 bit, 64 bit e ARM | [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] | [!INCLUDE[net_v452](../../../includes/net-v452-md.md)]<br /><br /> [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]<br /><br /> [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]<br /><br /> [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]<br /><br />.NET Framework 4.7<br/><br/>.NET Framework 4.7.1 |
| [!INCLUDE[win8](../../../includes/win8-md.md)] | 32 bit, 64 bit e ARM | [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] | [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]<br /><br /> [!INCLUDE[net_v452](../../../includes/net-v452-md.md)]<br /><br /> [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]<br /><br /> [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] |
| Windows 7 SP1|32 e 64 bit | -- | .NET Framework 4<br /><br /> [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]<br /><br /> [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]<br /><br /> [!INCLUDE[net_v452](../../../includes/net-v452-md.md)]<br /><br /> [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]<br /><br /> [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]<br /><br /> [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]<br /><br />.NET Framework 4.7<br/><br/>.NET Framework 4.7.1|
| Windows Vista SP2|32 e 64 bit | -- | .NET Framework 4<br /><br /> [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]<br /><br /> [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]<br /><br /> [!INCLUDE[net_v452](../../../includes/net-v452-md.md)]<br /><br /> [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] |
| Windows XP |32 e 64 bit | -- | .NET Framework 4 |

 **Note:**

- Nei sistemi Windows 7, .NET Framework richiede Windows 7 SP1. Se si ha Windows 7 ma non è ancora stato installato Service Pack 1, è necessario farlo prima di installare .NET Framework.

- [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] è supportato nell'Ambiente preinstallazione di Windows (Windows PE). Non tutte le funzionalità sono supportate in Windows PE.

- .NET Framework 4 supporta inoltre la piattaforma IA64.

- Per tutte le piattaforme, si consiglia di eseguire l'aggiornamento al Service Pack di Windows più recente e di installare gli aggiornamenti critici disponibili nel [sito Web Windows Update](http://go.microsoft.com/fwlink/?LinkId=168461) per garantire la massima compatibilità e sicurezza.

- Nei sistemi operativi a 64 bit, .NET Framework supporta sia WOW64 (elaborazione a 32 bit su un computer a 64 bit) che l'elaborazione nativa a 64 bit.

## <a name="supported-server-operating-systems"></a>Sistemi operativi server supportati

| Sistema operativo | Edizioni supportate | Preinstallato con il sistema operativo | Installabile separatamente |
| ---------------- | ------------------ | ------------------------ | ---------------------- |
| Windows Server, versione 1709 | 64 bit | .NET Framework 4.7.1 | -- |
| Windows Server 2016 | 64 bit | [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] | .NET Framework 4.7<br/><br/> .NET Framework 4.7.1 |
| Windows Server 2012 R2 | 64 bit | [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] | [!INCLUDE[net_v452](../../../includes/net-v452-md.md)]<br /><br /> [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]<br /><br /> [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]<br /><br /> [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]<br /><br />.NET Framework 4.7<br/><br/> .NET Framework 4.7.1 |
| Windows Server 2012 (edizione a 64 bit) | 64 bit| [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] | [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]<br /><br /> [!INCLUDE[net_v452](../../../includes/net-v452-md.md)]<br /><br /> [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]<br /><br /> [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]<br /><br /> [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]<br /><br />.NET Framework 4.7<br/><br/>.NET Framework 4.7.1 |
| Windows Server 2008 R2 SP1|64 bit | -- | .NET Framework 4<br /><br /> [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]<br /><br /> [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]<br /><br /> [!INCLUDE[net_v452](../../../includes/net-v452-md.md)]<br /><br /> [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]<br /><br /> [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]<br /><br /> [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]<br /><br />.NET Framework 4.7<br/><br/>.NET Framework 4.7.1 |
| Windows Server 2008 SP2|32 e 64 bit | -- | .NET Framework 4<br /><br /> [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]<br /><br /> [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]<br /><br /> [!INCLUDE[net_v452](../../../includes/net-v452-md.md)]<br /><br /> [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] |

 **Note:**

- [!INCLUDE[winserver8](../../../includes/winserver8-md.md)] include [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], pertanto non è necessario installarlo separatamente. Analogamente, in [!INCLUDE[winblue_server_2](../../../includes/winblue-server-2-md.md)] è incluso [!INCLUDE[net_v451](../../../includes/net-v451-md.md)].

- .NET Framework ha supporto limitato per il ruolo Server Core con Windows Server 2008 R2 SP1 o versioni successive. Per un elenco di API non supportate, vedere [Server Core .NET Functionality](https://msdn.microsoft.com/library/ee391632.aspx) (Funzionalità .NET di Server Core).

- .NET Framework non è supportato in Windows Server 2008 R2 per sistemi basati su Itanium.

- .NET Framework non è supportato nel ruolo Server Core in Windows Server 2008 SP2.

- Per tutte le piattaforme, si consiglia di eseguire l'aggiornamento al Service Pack di Windows più recente e installare gli aggiornamenti critici disponibili nel [sito Web Windows Update](http://go.microsoft.com/fwlink/?LinkId=168461) per garantire la massima compatibilità e sicurezza. Su alcuni sistemi operativi potrebbe essere necessaria l'installazione dell'ultimo Windows Service Pack.

- Nei sistemi operativi a 64 bit, .NET Framework supporta sia WOW64 (elaborazione a 32 bit su un computer a 64 bit) che l'elaborazione nativa a 64 bit.

## <a name="see-also"></a>Vedere anche

[Guida all'installazione](../../../docs/framework/install/index.md)   
[Introduzione](../../../docs/framework/get-started/index.md)   
[Risolvere i problemi relativi alle installazioni e alle disinstallazioni bloccate di .NET Framework](../../../docs/framework/install/troubleshoot-blocked-installations-and-uninstallations.md)
