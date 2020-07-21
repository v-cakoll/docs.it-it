---
title: .NET Framework & versioni del sistema operativo Windows
description: Informazioni sulle funzionalità principali di ogni versione di .NET Framework, incluse le versioni e le versioni CLR sottostanti installate dal sistema operativo Windows.
ms.custom: updateeachrelease
ms.date: 01/17/2020
helpviewer_keywords:
- versions, .NET Framework
ms.assetid: f75a72de-e2f2-4a7a-9574-3f278684ea90
ms.openlocfilehash: df44786dfd0a384ae2498a94d14b029612450fee
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475476"
---
# <a name="net-framework-versions-and-dependencies"></a>Versioni e dipendenze di .NET Framework

Ogni versione di .NET Framework contiene le Common Language Runtime (CLR), le librerie di classi base e altre librerie gestite. In questo articolo vengono descritte le funzionalità principali di .NET Framework per versione, vengono fornite informazioni sulle versioni CLR sottostanti e sugli ambienti di sviluppo associati e vengono identificate le versioni installate dal sistema operativo Windows.

Ogni nuova versione di .NET Framework aggiunge nuove funzionalità, ma mantiene le funzionalità delle versioni precedenti.

CLR viene identificato dal relativo numero di versione. Il numero di versione del .NET Framework viene incrementato a ogni rilascio, ma la versione CLR non è sempre incrementata. Ad esempio, .NET Framework 4, 4,5 e versioni successive includono CLR 4, ma .NET Framework 2,0, 3,0 e 3,5 includono CLR 2,0. (non c'è nessuna versione 3 di CLR).

> [!TIP]
>
> - Per un elenco completo dei sistemi operativi supportati, vedere [requisiti di sistema](../get-started/system-requirements.md).
> - Per i download, vedere [Install the .NET Framework for developers](../install/guide-for-developers.md) (Installare .NET Framework per sviluppatori).
> - Per informazioni sulla determinazione delle versioni di .NET Framework installate in un computer, vedere [come determinare quali versioni di .NET Framework sono installate](how-to-determine-which-versions-are-installed.md).

## <a name="version-information"></a>Informazioni sulla versione

Le tabelle che seguono riepilogano .NET Framework cronologia delle versioni e mettono in correlazione ogni versione con Visual Studio, Windows e Windows Server. Visual Studio supporta la funzionalità multitargeting, quindi non si è limitati alla versione di .NET Framework elencata.

- L'icona del segno di spunta ✔️ indica le versioni del sistema operativo in cui è installato .NET Framework, ma deve essere abilitato [nel pannello di controllo](../install/dotnet-35-windows-10.md) (per Windows) o tramite la Server Manager (per Windows Server).
- L'icona del segno più ➕ indica le versioni del sistema operativo in cui non viene installato .NET Framework ma che è possibile installare.

| | |
| - | - |
| [.NET Framework 4,8](#net-framework-48) | [.NET Framework 4.7.2](#net-framework-472) | [.NET Framework 4.7.1](#net-framework-471) | [.NET Framework 4,7](#net-framework-47) |
| [.NET Framework 4.6.2](#net-framework-462) | [.NET Framework 4.6.1](#net-framework-461) | [.NET framework 4.6](#net-framework-46) | [.NET Framework 4.5.2](#net-framework-452) |
| [.NET Framework 4.5.1](#net-framework-451) | [.NET Framework 4.5](#net-framework-45) | [.NET Framework 4](#net-framework-4) | [.NET Framework 3.5](#net-framework-35) |
| [.NET Framework 3.0](#net-framework-30) | [.NET Framework 2.0](#net-framework-20) | [.NET Framework 1.1](#net-framework-11) | [.NET Framework 1.0](#net-framework-10) |

### <a name="net-framework-48"></a>.NET Framework 4.8

- [Nuove funzionalità](../whats-new/index.md#whats-new-in-net-framework-48)
- [Nuove funzionalità di accessibilità](../whats-new/whats-new-in-accessibility.md#whats-new-in-accessibility-in-net-framework-48)
- [Note sulla versione](https://github.com/Microsoft/dotnet/tree/master/releases/net48/README.md)

|||
|-|-|
|**Versione CLR**|4|
|**Versioni di Windows**|✔️ 10 maggio 2019 aggiornamento<br/>➕ 10 ottobre 2018 aggiornamento (versione 1809)<br/>➕ 10 aprile 2018 aggiornamento (versione 1803)<br/>➕ 10 Fall Creators Update (versione 1709)<br/>➕ 10 Creators Update (versione 1703)<br/>Aggiornamento dell'anniversario di ➕ 10 (versione 1607)<br/>➕ 8,1<br/>➕ 7|
|**Versioni di Windows Server**|➕ Windows Server 2019<br/>➕ Windows Server, versione 1809<br/>➕ Windows Server, versione 1803<br/>➕ 2016<br/>➕ 2012 R2<br/>➕ 2012<br/>➕ 2008 R2 SP1|
|**Per determinare la versione di .NET installata**|Usare `Release` DWORD:<br/>-528040 (aggiornamento di Windows 10 maggio 2019)<br/>- 528049 (tutte le altre versioni del sistema operativo)<br/>(Vedere [le istruzioni](how-to-determine-which-versions-are-installed.md))|

### <a name="net-framework-472"></a>.NET Framework 4.7.2

- [Nuove funzionalità](../whats-new/index.md#whats-new-in-net-framework-472)
- [Nuove funzionalità di accessibilità](../whats-new/whats-new-in-accessibility.md#whats-new-in-accessibility-in-net-framework-472)
- [Note sulla versione](https://github.com/Microsoft/dotnet/tree/master/releases/net472/README.md)

|||
|-|-|
|**Versione CLR**|4|
|**Inclusa nella versione di Visual Studio**|2019<sup>1</sup>|
|**Versioni di Windows**|✔️ 10 ottobre 2018 aggiornamento (versione 1809)<br/>✔️ 10 aprile 2018 aggiornamento (versione 1803)<br/>➕ 10 Fall Creators Update (versione 1709)<br/>➕ 10 Creators Update (versione 1703)<br/>Aggiornamento dell'anniversario di ➕ 10 (versione 1607)<br/>➕ 8,1<br/>➕ 7|
|**Versioni di Windows Server**|✔️ Windows Server 2019<br/>✔️ Windows Server, versione 1809<br/>✔️ Windows Server, versione 1803<br/>➕ Windows Server, versione 1709<br/>➕ 2016<br/>➕ 2012 R2<br/>➕ 2012<br/>➕ 2008 R2 SP1|
|**Per determinare la versione di .NET installata**|Usare `Release` DWORD:<br/>- 461814 (Aggiornamento di Windows 10 (ottobre 2018))<br/>- 461808 (Windows 10 aggiornamento di aprile 2018 e Windows Server, versione 1803)<br/>- 461814 (tutte le altre versioni del sistema operativo)<br/>(Vedere [le istruzioni](how-to-determine-which-versions-are-installed.md))|

<sup>1</sup> richiede l'installazione dello sviluppo per **desktop .NET**, **ASP.NET e sviluppo Web**, lo sviluppo di **Azure**, **lo sviluppo per Office/SharePoint**, lo sviluppo **per dispositivi mobili con .NET**o i carichi **di lavoro di sviluppo multipiattaforma .NET Core** .

### <a name="net-framework-471"></a>.NET Framework 4.7.1

- [Nuove funzionalità](../whats-new/index.md#whats-new-in-net-framework-471)
- [Nuove funzionalità di accessibilità](../whats-new/whats-new-in-accessibility.md#whats-new-in-accessibility-in-net-framework-471)
- [Note sulla versione](https://github.com/Microsoft/dotnet/tree/master/releases/net471/README.md)

|||
|-|-|
|**Versione CLR**|4|
|**Versioni di Windows**|✔️ 10 Fall Creators Update (versione 1709)<br/>➕ 10 Creators Update (versione 1703)<br/>Aggiornamento dell'anniversario di ➕ 10 (versione 1607)<br/>➕ 8,1<br/>➕ 7|
|**Versioni di Windows Server**|➕ Windows Server, versione 1803<br/>✔️ Windows Server, versione 1709<br/>➕ 2016<br/>➕ 2012 R2<br/>➕ 2012<br/>➕ 2008 R2 SP1|
|**Per determinare la versione di .NET installata**|Usare `Release` DWORD:<br/>- 461308 (Windows 10 Creators Update e Windows Server, versione 1709)<br/>- 461310 (tutte le altre versioni del sistema operativo)<br/>(Vedere [le istruzioni](how-to-determine-which-versions-are-installed.md))|

### <a name="net-framework-47"></a>.NET Framework 4.7

- [Nuove funzionalità](../whats-new/index.md#whats-new-in-net-framework-47)
- [Note sulla versione](https://github.com/Microsoft/dotnet/tree/master/releases/net47/README.md)

|||
|-|-|
|**Versione CLR**|4|
|**Versioni di Windows**|✔️ 10 Creators Update (versione 1703)<br/>Aggiornamento dell'anniversario di ➕ 10 (versione 1607)<br/>➕ 8,1<br/>➕ 7|
|**Versioni di Windows Server**|➕ 2016<br/>➕ 2012 R2<br/>➕ 2012<br/>➕ 2008 R2 SP1|
|**Per determinare la versione di .NET installata**|Usare `Release` DWORD:<br/>- 460798 (Windows 10 Creators Update)<br/>- 460805 (tutte le altre versioni del sistema operativo)<br/>(Vedere [le istruzioni](how-to-determine-which-versions-are-installed.md))|

### <a name="net-framework-462"></a>.NET Framework 4.6.2

- [Nuove funzionalità](../whats-new/index.md#whats-new-in-net-framework-462)
- [Note sulla versione](https://github.com/Microsoft/dotnet/tree/master/releases/net462/README.md)

|||
|-|-|
|**Versione CLR**|4|
|**Versioni di Windows**|Aggiornamento dell'anniversario di ✔️ 10 (versione 1607)<br/>➕ 10 aggiornamento di novembre (versione 1511)<br/>➕ 10<br/>➕ 8,1<br />➕ 7|
|**Versioni di Windows Server**|✔️ 2016<br /><br/>➕ 2012 R2<br />➕ 2012<br />➕ 2008 R2 SP1|
|**Per determinare la versione di .NET installata**|Usare `Release` DWORD:<br /><br/>- 394802 (Aggiornamento dell'anniversario di Windows 10 e Windows Server 2016)<br/>- 394806 (tutte le altre versioni del sistema operativo)<br /><br/>(Vedere [le istruzioni](how-to-determine-which-versions-are-installed.md))|

### <a name="net-framework-461"></a>.NET Framework 4.6.1

- [Nuove funzionalità](../whats-new/index.md#whats-new-in-net-framework-461)
- [Note sulla versione](https://github.com/Microsoft/dotnet/tree/master/releases/net461/README.md)

|||
|-|-|
|**Versione CLR**|4|
|**Inclusa nella versione di Visual Studio**|2017<sup>1</sup>|
|**Versioni di Windows**|✔️ 10 aggiornamento di novembre (versione 1511)<br/>➕ 10<br />➕ 8,1<br />➕ 8<br />➕ 7|
|**Versioni di Windows Server**|➕ 2012 R2<br />➕ 2012<br />➕ 2008 R2 SP1|
|**Per determinare la versione di .NET installata**|Usare `Release` DWORD:<br /><br/>- 394254 (Aggiornamento di novembre di Windows 10)<br />- 394271 (tutte le altre versioni del sistema operativo)<br /><br/>(Vedere [le istruzioni](how-to-determine-which-versions-are-installed.md))|

<sup>1</sup> richiede l'installazione dello sviluppo per **desktop .NET**, **ASP.NET e sviluppo Web**, lo sviluppo di **Azure**, **lo sviluppo per Office/SharePoint**, lo sviluppo **per dispositivi mobili con .NET**o i carichi **di lavoro di sviluppo multipiattaforma .NET Core** .

### <a name="net-framework-46"></a>.NET framework 4.6

- [Nuove funzionalità](../whats-new/index.md#whats-new-in-net-2015)
- [Note sulla versione](https://github.com/Microsoft/dotnet/tree/master/releases/net46/README.md)

|||
|-|-|
|**Versione CLR**|4|
|**Inclusa nella versione di Visual Studio**|2015|
|**Versioni di Windows**|✔️ 10<br /><br />➕ 8,1<br />➕ 8<br />➕ 7<br />➕ Vista|
|**Versioni di Windows Server**|➕ 2012 R2<br />➕ 2012<br />➕ 2008 R2 SP1<br />➕ 2008 SP2|
|**Per determinare la versione di .NET installata**|Usare `Release` DWORD:<br /><br />- 393295 (Windows 10)<br />- 393297 (tutte le altre versioni del sistema operativo)<br /><br />(Vedere [le istruzioni](how-to-determine-which-versions-are-installed.md))|

### <a name="net-framework-452"></a>.NET Framework 4.5.2

- [Nuove funzionalità](../whats-new/index.md#whats-new-in-net-framework-452)
- [Note sulla versione](https://github.com/Microsoft/dotnet/tree/master/releases/net452/README.md)

|||
|-|-|
|**Versione CLR**|4|
|**Versioni di Windows**|➕ 8,1<br />➕ 8<br />➕ 7<br />➕ Vista|
|**Versioni di Windows Server**|➕ 2012 R2<br />➕ 2012<br />➕ 2008 R2 SP1<br />➕ 2008 SP2|
|**Per determinare la versione di .NET installata**|Usare `Release` DWORD 379893<br /><br />(Vedere [le istruzioni](how-to-determine-which-versions-are-installed.md))|

### <a name="net-framework-451"></a>.NET Framework 4.5.1

- [Nuove funzionalità](../whats-new/index.md#whats-new-in-net-framework-451)
- [Note sulla versione](https://github.com/Microsoft/dotnet/tree/master/releases/net451/README.md)

|||
|-|-|
|**Versione CLR**|4|
|**Inclusa nella versione di Visual Studio**|2013|
|**Versioni di Windows**|✔️ 8,1<br /><br />➕ 8<br />➕ 7<br />➕ Vista|
|**Versioni di Windows Server**|✔️ 2012 R2<br /><br />➕ 2012<br />➕ 2008 R2 SP1<br />➕ 2008 SP2|
|**Per determinare la versione di .NET installata**|Usare `Release` DWORD:<br /><br />- 378675 (Windows 8.1)<br />- 378758 (tutte le altre versioni)<br /><br />(Vedere [le istruzioni](how-to-determine-which-versions-are-installed.md))|

### <a name="net-framework-45"></a>.NET Framework 4.5

- [Nuove funzionalità](../whats-new/index.md#whats-new-in-net-framework-45)
- [Note sulla versione](https://github.com/Microsoft/dotnet/tree/master/releases/net45/README.md)

|||
|-|-|
|**Versione CLR**|4|
|**Inclusa nella versione di Visual Studio**|2012|
|**Versioni di Windows**|✔️ 8<br />➕ 7<br />➕ Vista|
|**Versioni di Windows Server**|✔️ 2012<br />➕ 2008 R2 SP1<br />➕ 2008 SP2|
|**Per determinare la versione di .NET installata**|Usare `Release` DWORD 378389<br /><br />(Vedere [le istruzioni](how-to-determine-which-versions-are-installed.md))|

### <a name="net-framework-4"></a>.NET Framework 4

[Nuove funzionalità](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms171868(v=vs.100))

|||
|-|-|
|**Versione CLR**|4|
|**Inclusa nella versione di Visual Studio**|2010|
|**Versioni di Windows**|➕ 7<br />➕ Vista|
|**Versioni di Windows Server**|➕ 2008 R2 SP1<br />➕ 2008 SP2<br />➕ 2003|
|**Per determinare la versione di .NET installata**|Vedere [le istruzioni](how-to-determine-which-versions-are-installed.md)|

### <a name="net-framework-35"></a>.NET Framework 3.5

[Nuove funzionalità](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ms171868\(v=vs.90\)):

- LINQ
- Alberi delle espressioni
- Supporto ASP.NET migliorato per lo sviluppo AJAX
- HashSet (raccolte)
- DateTimeOffset
- Integrazione di WCF e WF
- Rete peer-to-peer
- Componenti aggiuntivi per l'estendibilità

|||
|-|-|
|**Versione CLR**|2.0|
|**Inclusa nella versione di Visual Studio**|2008|
|**Versioni di Windows**|✔️ 10\*<br/>✔️ 8,1\*<br />✔️ 8\*<br />✔️ 7<br /><br />➕ Vista|
|**Versioni di Windows Server**|➕ Windows Server, versione 1803\*<br/>➕ Windows Server, versione 1709\*<br/>➕ 2016\*<br/>➕ 2012 R2\*<br />➕ 2012\*<br /><br />✔️ 2008 R2 SP1\*<br /><br/>➕ 2008 SP2<br />➕ 2003|
|**Per determinare la versione di .NET installata**|Vedere [le istruzioni](how-to-determine-which-versions-are-installed.md)|

### <a name="net-framework-30"></a>.NET Framework 3.0

[Nuove funzionalità](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bb822048(v=vs.90)):

- Windows Presentation Foundation
- Windows Communication Foundation
- Windows Workflow Foundation
- Windows CardSpace

|||
|-|-|
|**Versione CLR**|2.0|
|**Versioni di Windows**|✔️ Vista|
|**Versioni di Windows Server**|✔️ 2008 R2 SP1 *<br />✔️ 2008 SP2\*<br /><br />➕ 2003|
|**Per determinare la versione di .NET installata**|Vedere [le istruzioni](how-to-determine-which-versions-are-installed.md).|

### <a name="net-framework-20"></a>.NET Framework 2.0

[Nuove funzionalità](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/t357fb32%28v%3dvs.90%29):

- Generics
- Modifica e continuazione del debugger
- Scalabilità e prestazioni migliorate
- distribuzione ClickOnce
- In ASP.NET 2,0, nuovi controlli e supporto per un'ampia gamma di browser
- supporto 64 bit

|||
|-|-|
|**Versione CLR**|2.0|
|**Inclusa nella versione di Visual Studio**|2005|
|**Versioni di Windows**|N/D|
|**Versioni di Windows Server**|✔️ 2008 R2 SP1<br />✔️ 2008 SP2<br />✔️ 2003|
|**Per determinare la versione di .NET installata**|Vedere [le istruzioni](how-to-determine-which-versions-are-installed.md)|

### <a name="net-framework-11"></a>.NET Framework 1.1

[Nuove funzionalità](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/h88tthh0%28v%3dvs.90%29):

- Controlli per dispositivi mobili ASP.NET
- Esecuzione side-by-side
- Supporto per IPv6

|||
|-|-|
|**Versione CLR**|1.1|
|**Inclusa nella versione di Visual Studio**|2003|
|**Versioni di Windows**|N/D|
|**Versioni di Windows Server**|✔️ 2003|
|**Per determinare la versione di .NET installata**|Vedere [le istruzioni](how-to-determine-which-versions-are-installed.md)|

### <a name="net-framework-10"></a>.NET Framework 1.0

|||
|-|-|
|**Versione CLR**|1.0|
|**Inclusa nella versione di Visual Studio**|Visual Studio .NET|
|**Versioni di Windows**|N/D|
|**Versioni di Windows Server**|N/D|
|**Per determinare la versione di .NET installata**|Vedere [le istruzioni](how-to-determine-which-versions-are-installed.md)|

> [!NOTE]
>
> - .NET Framework deve essere abilitato in questo sistema operativo tramite [il pannello di controllo (per Windows) o il server Manager (per Windows Server)](../install/dotnet-35-windows-10.md#enable-the-net-framework-35-in-control-panel).
> - In generale, non è consigliabile disinstallare alcuna versione di .NET Framework installata nel computer, perché un'applicazione in uso potrebbe dipendere da una versione specifica e potrebbe interrompersi se la versione viene rimossa. È possibile caricare più versioni di .NET Framework in un singolo computer nello stesso momento. Ciò significa che è possibile installare .NET Framework senza dover disinstallare le versioni precedenti. Per ulteriori informazioni, vedere [Introduzione](../get-started/index.md).

## <a name="remarks-for-version-45-and-later"></a>Osservazioni per la versione 4,5 e successive

.NET Framework 4,5 è un aggiornamento sul posto che sostituisce .NET Framework 4 nel computer e, analogamente, .NET Framework 4.5.1, 4.5.2, 4,6, 4.6.1, 4.6.2, 4,7, 4.7.1, 4.7.2 e 4,8 sono aggiornamenti sul posto di .NET Framework 4,5. L'aggiornamento sul posto significa che usano la stessa versione di runtime, ma le versioni degli assembly vengono aggiornate e includono nuovi tipi e membri. Dopo aver installato uno di questi aggiornamenti, le app .NET Framework 4, .NET Framework 4.5, .NET Framework 4.6 o .NET Framework 4.7 dovrebbero continuare a funzionare senza richiedere la ricompilazione. Non è tuttavia consentito il contrario. Non è consigliabile eseguire app destinate a una versione più recente di .NET Framework su una versione precedente. Ad esempio, non è consigliabile eseguire un'app destinata a .NET Framework 4.6 in .NET Framework 4.5.

Vengono applicate le linee guida riportate di seguito:

- In Visual Studio è possibile scegliere .NET Framework 4.5 come framework di destinazione per un progetto (viene impostata la proprietà <xref:Microsoft.Build.Tasks.GetReferenceAssemblyPaths.TargetFrameworkMoniker%2A?displayProperty=nameWithType>) per compilare il progetto come assembly o file eseguibile di .NET Framework 4.5. Questo assembly o file eseguibile puoi poi essere usato in qualsiasi computer in cui è installato .NET Framework 4.5, 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7, 4.7.1, 4.7.2 o 4.8.

- In Visual Studio è possibile scegliere .NET Framework 4.5.1 come Framework di destinazione per un progetto per compilarlo come un assembly .NET Framework 4.5.1 o un eseguibile. Eseguire questo assembly o eseguibile solo nei computer in cui è installato .NET Framework 4.5.1 o versione successiva. Un file eseguibile destinato a .NET Framework 4.5.1 verrà bloccato in un computer in cui è installata solo una versione precedente di .NET Framework, ad esempio .NET Framework 4,5. All'utente verrà richiesto di installare .NET Framework 4.5.1. Inoltre, gli assembly .NET Framework 4.5.1 non devono essere chiamati da un'app destinata a una versione precedente di .NET Framework, ad esempio .NET Framework 4,5.

  > [!NOTE]
  > .NET framework 4.5.1 e .NET Framework 4.5 vengono usati qui solo come esempi. Il principio descritto si applica a qualsiasi app destinata a una versione successiva di .NET Framework rispetto a quella installata nel sistema in cui è in esecuzione.

Alcune modifiche in .NET Framework possono richiedere modifiche al codice dell'app; vedere [compatibilità delle applicazioni](application-compatibility.md) prima di eseguire le app esistenti con .NET Framework 4,5 o versioni successive. Per altre informazioni sull'installazione della versione corrente, vedere [Install the .NET Framework for developers](../install/guide-for-developers.md) (Installare .NET Framework per sviluppatori). Per informazioni sul supporto per la .NET Framework, vedere [.NET Framework i criteri di supporto ufficiale](https://dotnet.microsoft.com/platform/support/policy/dotnet-framework) nel sito Web .NET.

## <a name="remarks-for-older-versions"></a>Osservazioni per le versioni precedenti

Le versioni 2.0, 3.0 e 3.5 di .NET Framework sono compilate con la stessa versione di CLR (CLR 2.0). Queste versioni rappresentano i livelli successivi di una singola installazione. Ogni versione viene compilata in modo incrementale sulle versioni precedenti. Non è possibile eseguire le versioni 2,0, 3,0 e 3,5 side-by-side in un computer. Se si installa la versione 3.5, si ottengono automaticamente i livelli 2.0 e 3.0 e le app create per le versioni 2.0, 3.0 e 3.5 possono essere eseguite sulla versione 3.5. Tuttavia, .NET Framework 4 interrompe questo approccio su più livelli e le versioni successive (.NET Framework 4.5, 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7, 4.7.1, 4.7.2 e 4.8) rappresentano anche i livelli successivi di una singola installazione. A partire da .NET Framework 4, è possibile usare l'hosting affiancato in-process per eseguire più versioni di CLR in un singolo processo. Per altre informazioni, vedere [Assembly ed esecuzione side-by-side](../../standard/assembly/side-by-side-execution.md).

Inoltre, se l'app è destinata alla versione 2,0, 3,0 o 3,5, è possibile che agli utenti venga richiesto di abilitare .NET Framework 3,5 in un computer Windows 8, Windows 8.1 o Windows 10 prima di poter eseguire l'app. Per altre informazioni, vedere [Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8](../install/dotnet-35-windows-10.md) (Installare .NET Framework 3.5 in Windows 10, Windows 8.1 e Windows 8).

## <a name="next-steps"></a>Passaggi successivi

- Se non si ha familiarità con .NET Framework, vedere la [panoramica](../get-started/overview.md) per un'introduzione ai concetti e alle funzionalità chiave.

- Per le nuove funzionalità e i miglioramenti apportati all'.NET Framework 4,5 e alle relative versioni intermedie, vedere Novità del [.NET Framework](../whats-new/index.md).

- Per informazioni sulla migrazione dell'app a una versione più recente del .NET Framework, vedere la [Guida alla migrazione](index.md).

- Per informazioni su come determinare le versioni o gli aggiornamenti installati in un computer, vedere [Procedura: determinare le versioni di .NET Framework installate](how-to-determine-which-versions-are-installed.md) e [Procedura: determinare gli aggiornamenti di .NET Framework installati](how-to-determine-which-net-framework-updates-are-installed.md).

## <a name="see-also"></a>Vedere anche

- [Compatibilità](version-compatibility.md) 
|  tra versioni [.NET Framework criteri di supporto ufficiale](https://dotnet.microsoft.com/platform/support/policy/dotnet-framework)
- [Risolvere i problemi relativi alle installazioni e alle disinstallazioni bloccate di .NET Framework](../install/troubleshoot-blocked-installations-and-uninstallations.md)
