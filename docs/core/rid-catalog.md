---
title: Catalogo dei RID (Runtime IDentifier) di .NET Core
description: Informazioni sull'identificatore di runtime (RID) e su come vengono usati i RID in .NET Core.
author: mairaw
ms.author: mairaw
ms.date: 09/07/2017
ms.topic: article
ms.prod: .net-core
ms.workload: dotnetcore
ms.openlocfilehash: 180aac7635746f9ede146c3e561deb9bba9a61ab
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="net-core-rid-catalog"></a>Catalogo RID di .NET Core

RID è l'acronimo di *Runtime IDentifier*. I valori RID vengono usati per identificare le piattaforme di destinazione in cui viene eseguita l'applicazione
e vengono usati dai pacchetti .NET per rappresentare risorse specifiche della piattaforma in pacchetti NuGet. I valori seguenti sono esempi di RID: `linux-x64`, `ubuntu.14.04-x64`, `win7-x64` o `osx.10.12-x64`.
Per i pacchetti con dipendenze native, il RID specifica le piattaforme su cui può essere ripristinato il pacchetto.

I RID possono essere impostati nell'elemento `<RuntimeIdentifier>` del file di progetto. Vengono usati anche tramite l'opzione `--runtime` con i [comandi CLI di .NET Core](./tools/index.md) seguenti:

- [dotnet build](./tools/dotnet-build.md)
- [dotnet clean](./tools/dotnet-clean.md)
- [dotnet pack](./tools/dotnet-pack.md)
- [dotnet publish](./tools/dotnet-publish.md)
- [dotnet restore](./tools/dotnet-restore.md)
- [dotnet run](./tools/dotnet-run.md)
- [dotnet store](./tools/dotnet-store.md)

I RID che rappresentano un sistema operativo reale seguono in genere il modello seguente: `[os].[version]-[architecture]-[additional qualifiers]` dove:

- `[os]` è il moniker di sistema operativo/piattaforma. Ad esempio `ubuntu`.

- `[version]` è il numero di versione del sistema operativo nel formato separato da punti (`.`). Ad esempio `15.10`.

  - **Non deve** trattarsi di versioni marketing, poiché tali versioni rappresentano spesso più versioni discrete del sistema operativo con una superficie delle API della piattaforma variabile.

- `[architecture]` indica l'architettura del processore, ad esempio `x86`, `x64`, `arm` o `arm64`.

- `[additional qualifiers]` differenziano ulteriormente piattaforme diverse. Ad esempio: `aot` o `corert`.

## <a name="rid-graph"></a>Grafico RID

Il grafico RID o grafico di fallback di runtime è un elenco di RID compatibili tra loro. I RID sono definiti nel pacchetto [Microsoft.NETCore.Platforms](https://www.nuget.org/packages/Microsoft.NETCore.Platforms/). È possibile visualizzare l'elenco di RID supportati e il grafico RID nel file [*runtime.json* ](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json), disponibile nel repository CoreFX. In questo file, si noterà che tutti i RID, ad eccezione di quello di base, contengono un'istruzione `"#import"`. Queste istruzioni indicano RID compatibili.

Quando NuGet ripristina i pacchetti, tenta di trovare una corrispondenza esatta per il runtime specificato.
Se non trova una corrispondenza esatta, NuGet ripercorre il grafico a ritroso fino a individuare il sistema compatibile più simile in base al grafico RID.

L'esempio seguente è la voce effettiva per il RID `osx.10.12-x64`:

```json
"osx.10.12-x64": {
    "#import": [ "osx.10.12", "osx.10.11-x64" ]
}
```

Il RID sopra riportato specifica che `osx.10.12-x64` importa `osx.10.11-x64`. Quando NuGet ripristina i pacchetti, quindi, tenta di trovare una corrispondenza esatta per `osx.10.12-x64` nel pacchetto. Se NuGet non riesce a trovare il runtime specifico, può ripristinare i pacchetti che specificano i runtime `osx.10.11-x64`, ad esempio.

L'esempio seguente mostra un grafico RID leggermente più ampio, anch'esso definito nel file *runtime.json*:

```
    win7-x64    win7-x86
       |   \   /    |
       |   win7     |
       |     |      |
    win-x64  |  win-x86
          \  |  /
            win
             |
            any
```

Tutti i RID finiscono per mappare nuovamente al RID `any` radice.

Esistono alcune considerazioni che è necessario tenere presenti quando si lavora con i RID:

- I RID sono **stringhe opache** e devono essere trattati come black box.
- Non creare i RID a livello di codice.
- Usare i RID già definiti per la piattaforma.
- I RID devono essere specifici, quindi non desumere nulla dal valore RID effettivo.

## <a name="using-rids"></a>Uso dei RID

Per usare i RID, è necessario sapere quali sono quelli disponibili. Alla piattaforma vengono regolarmente aggiunti nuovi valori.
Per la versione più recente e completa, vedere il file [runtime.json](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) nel repository CoreFX.

.NET Core 2.0 SDK introduce il concetto di RID portabili. Si tratta di nuovi valori aggiunti al grafico RID che non sono associati a una versione specifica o a una distribuzione specifica del sistema operativo. Risultano particolarmente utili quando si lavora con più distribuzioni di Linux.

L'elenco seguente mostra i RID più comuni usati per ogni sistema operativo. Non sono inclusi valori `arm` o `corert`.

## <a name="windows-rids"></a>RID Windows

- Portabile
  - `win-x86`
  - `win-x64`
- Windows 7/Windows Server 2008 R2
  - `win7-x64`
  - `win7-x86`
- Windows 8/Windows Server 2012
  - `win8-x64`
  - `win8-x86`
  - `win8-arm`
- Windows 8.1/Windows Server 2012 R2
  - `win81-x64`
  - `win81-x86`
  - `win81-arm`
- Windows 10/Windows Server 2016
  - `win10-x64`
  - `win10-x86`
  - `win10-arm`
  - `win10-arm64`

Per altre informazioni, vedere [Prerequisiti per .NET Core in Windows](windows-prerequisites.md).

## <a name="linux-rids"></a>RID Linux

- Portabile
  - `linux-x64`
- CentOS
  - `centos-x64`
  - `centos.7-x64`
- Debian
  - `debian-x64`
  - `debian.8-x64`
- Fedora
  - `fedora-x64`
  - `fedora.24-x64`
  - `fedora.25-x64` (.NET Core 2.0 o versioni successive)
  - `fedora.26-x64` (.NET Core 2.0 o versioni successive)
- Gentoo (.NET Core 2.0 o versioni successive)
  - `gentoo-x64`
- openSUSE
  - `opensuse-x64`
  - `opensuse.42.1-x64`
- Oracle Linux
  - `ol-x64`
  - `ol.7-x64`
  - `ol.7.0-x64`
  - `ol.7.1-x64`
  - `ol.7.2-x64`
- Red Hat Enterprise Linux
  - `rhel-x64`
  - `rhel.6-x64` (.NET Core 2.0 o versioni successive)
  - `rhel.7-x64`
  - `rhel.7.1-x64`
  - `rhel.7.2-x64`
  - `rhel.7.3-x64` (.NET Core 2.0 o versioni successive)
  - `rhel.7.4-x64` (.NET Core 2.0 o versioni successive)
- Tizen (.NET Core 2.0 o versioni successive)
  - `tizen`
- Ubuntu
  - `ubuntu-x64`
  - `ubuntu.14.04-x64`
  - `ubuntu.14.10-x64`
  - `ubuntu.15.04-x64`
  - `ubuntu.15.10-x64`
  - `ubuntu.16.04-x64`
  - `ubuntu.16.10-x64`
- Derivati di Ubuntu
  - `linuxmint.17-x64`
  - `linuxmint.17.1-x64`
  - `linuxmint.17.2-x64`
  - `linuxmint.17.3-x64`
  - `linuxmint.18-x64`
  - `linuxmint.18.1-x64` (.NET Core 2.0 o versioni successive)

Per altre informazioni, vedere [Prerequisiti per .NET Core in Linux](linux-prerequisites.md).

## <a name="macos-rids"></a>RID macOS

I RID macOS usano la personalizzazione "OSX" precedente.

- `osx-x64` (.NET Core 2.0 o versioni successive, la versione minima è `osx.10.12-x64`)
- `osx.10.10-x64`
- `osx.10.11-x64`
- `osx.10.12-x64` (.NET Core 1.1 o versioni successive)
- `osx.10.13-x64`

Per altre informazioni, vedere [Prerequisiti per .NET Core in macOS](macos-prerequisites.md).

## <a name="android-rids-net-core-20-or-later-versions"></a>RID Android (.NET Core 2.0 o versioni successive)

- `android`
- `android.21`

## <a name="see-also"></a>Vedere anche

[ID di runtime](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/readme.md)
