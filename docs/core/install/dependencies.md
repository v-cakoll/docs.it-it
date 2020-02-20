---
title: Dipendenze di .NET Core SDK e Runtime-.NET Core
description: Informazioni dettagliate sui prerequisiti per l'architettura del sistema operativo e della CPU per installare il .NET Core SDK e il runtime in Windows, Linux e macOS.
author: leecow
ms.author: leecow
ms.date: 12/04/2019
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 4164ea5a04d80ab20109168a225b793b02ee616a
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77448893"
---
# <a name="net-core-dependencies-and-requirements"></a>Dipendenze e requisiti di .NET Core

In questo articolo vengono illustrati i sistemi operativi e l'architettura della CPU supportati da .NET Core.

## <a name="supported-operating-systems"></a>Sistemi operativi supportati

::: zone pivot="os-windows"

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-core-31"></a>[.NET Core 3,1](#tab/netcore31)

Con .NET Core 3,1 sono supportate le seguenti versioni di Windows:

> [!NOTE]
> Un simbolo di `+` rappresenta la versione minima.

| Sistema operativo                            | Versione                        | Architetture   |
| ----------------------------- | ------------------------------ | --------------- |
| Client Windows                | 7 SP1 +, 8,1                    | x64, x86        |
| Client Windows 10             | Versione 1607 +                  | x64, x86        |
| Windows Server                | 2012 R2 +                       | x64, x86        |
| Nano Server                   | Versione 1803 +                  | x64, ARM32      |

Per altre informazioni sui sistemi operativi, le distribuzioni e i criteri del ciclo di vita supportati di .NET Core 3,1, vedere [versioni del sistema operativo supportate da .net core 3,1](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).

# <a name="net-core-30"></a>[.NET Core 3.0](#tab/netcore30)

Con .NET Core 3,0 sono supportate le seguenti versioni di Windows:

> [!NOTE]
> Un simbolo di `+` rappresenta la versione minima.

| Sistema operativo                            | Versione                        | Architetture   |
| ----------------------------- | ------------------------------ | --------------- |
| Client Windows                | 7 SP1 +, 8,1                    | x64, x86        |
| Client Windows 10             | Versione 1607 +                  | x64, x86        |
| Windows Server                | 2012 R2 +                       | x64, x86        |
| Nano Server                   | Versione 1803 +                  | x64, ARM32      |

Per altre informazioni sui sistemi operativi, le distribuzioni e i criteri del ciclo di vita supportati di .NET Core 3,0, vedere [versioni del sistema operativo supportate da .net core 3,0](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).

# <a name="net-core-22"></a>[.NET Core 2.2](#tab/netcore22)

Con .NET Core 2,2 sono supportate le seguenti versioni di Windows:

> [!NOTE]
> Un simbolo di `+` rappresenta la versione minima.

| Sistema operativo                            | Versione                        | Architetture   |
| ----------------------------- | ------------------------------ | --------------- |
| Client Windows                | 7 SP1 +, 8,1                    | x64, x86        |
| Client Windows 10             | Versione 1607 +                  | x64, x86        |
| Windows Server                | 2008 R2 SP1 +                   | x64, x86        |
| Nano Server                   | Versione 1803 +                   | x64, ARM32      |

Per altre informazioni sui sistemi operativi, le distribuzioni e i criteri del ciclo di vita supportati di .NET Core 2,2, vedere [versioni del sistema operativo supportate da .net core 2,2](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).

# <a name="net-core-21"></a>[.NET Core 2.1](#tab/netcore21)

Con .NET Core 2,1 sono supportate le seguenti versioni di Windows:

> [!NOTE]
> Un simbolo di `+` rappresenta la versione minima.

| Sistema operativo                            | Versione                        | Architetture   |
| ----------------------------- | ------------------------------ | --------------- |
| Client Windows                | 7 SP1 +, 8,1                    | x64, x86        |
| Client Windows 10             | Versione 1607 +                  | x64, x86        |
| Windows Server                | 2008 R2 SP1 +                   | x64, x86        |
| Nano Server                   | Versione 1803 +                  | x64            |

Per altre informazioni sui sistemi operativi, le distribuzioni e i criteri del ciclo di vita supportati di .NET Core 2,1, vedere [versioni del sistema operativo supportate da .net core 2,1](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).

---

<!-- markdownlint-disable MD001 -->

### <a name="windows-7--vista--81--server-2008-r2"></a>Windows 7/Vista/8,1/Server 2008 R2

Sono necessarie dipendenze aggiuntive se si sta installando .NET SDK o Runtime nelle versioni di Windows seguenti:

- Windows 7 SP1
- Windows Vista SP 2
- Windows 8.1
- Windows Server 2008 R2
- Windows Server 2012 R2

Installare gli elementi seguenti:

- [Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).
- [KB2533623](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)

I requisiti indicati sopra sono necessari anche se si verifica uno degli errori seguenti:

> Non è possibile avviare il programma perché non è presente alcuna *API-MS-Win-CRT-Runtime-L1-1-0. dll* nel computer. Per risolvere il problema, provare a reinstallare il programma.
>
> \- oppure -
>
> La libreria *hostfxr. dll* è stata trovata, ma il caricamento da *C:\\\<path_to_app >\\hostfxr. dll* non è riuscita.

::: zone-end

::: zone pivot="os-linux"

# <a name="net-core-31"></a>[.NET Core 3,1](#tab/netcore31)

.NET Core 3,1 considera Linux come un singolo sistema operativo. È disponibile una singola Build Linux (per ogni architettura chip) per le distribuzioni di Linux supportate.

.NET Core 3,1 è supportato nelle seguenti distribuzioni/versioni di Linux:

> [!NOTE]
> Un simbolo di `+` rappresenta la versione minima.

| Sistema operativo                             | Versione               | Architetture    |
| ------------------------------ | --------------------- | ---------------- |
| Red Hat Enterprise Linux       | 6, 7, 8               | X64 |
| CentOS                         | 7+                    | X64 |
| Oracle Linux                   | 7+                    | X64 |
| Fedora                         | 29 +                   | X64 |
| Debian                         | 9+                    | x64, ARM32, ARM64 |
| Ubuntu                         | 16.04+                | x64, ARM32, ARM64 |
| Linux Mint                     | 18 +                   | X64 |
| openSUSE                       | 15 +                   | X64 |
| SUSE Enterprise Linux (SLES)   | 12 SP2+               | X64 |
| Alpine Linux                   | 3.10 +                 | x64, ARM64 |

Per altre informazioni sui sistemi operativi, le distribuzioni e i criteri del ciclo di vita supportati di .NET Core 3,1, vedere [versioni del sistema operativo supportate da .net core 3,1](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).

Per altre informazioni su come installare .NET Core 3,1 in ARM64 (kernel 4.14 +), vedere [installazione di .net core 3,0 in Linux arm64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).

> [!IMPORTANT]
> Il supporto di ARM64 richiede il kernel Linux 4,14 o versione successiva. Alcune distribuzioni Linux soddisfano questo requisito mentre altre no. Ubuntu 18,04, ad esempio, è supportato, ma Ubuntu 16,04 non lo è.

# <a name="net-core-30"></a>[.NET Core 3.0](#tab/netcore30)

.NET Core 3,0 considera Linux come un singolo sistema operativo. È disponibile una singola Build Linux (per ogni architettura chip) per le distribuzioni di Linux supportate.

.NET Core 3,0 è supportato nelle seguenti distribuzioni/versioni di Linux:

> [!NOTE]
> Un simbolo di `+` rappresenta la versione minima.

| Sistema operativo                             | Versione               | Architetture    |
| ------------------------------ | --------------------- | ---------------- |
| Red Hat Enterprise Linux       | 6, 7, 8               | X64 |
| CentOS                         | 7+                    | X64 |
| Oracle Linux                   | 7+                    | X64 |
| Fedora                         | 29 +                   | X64 |
| Debian                         | 9+                    | x64, ARM32, ARM64 |
| Ubuntu                         | 16.04+                | x64, ARM32, ARM64 |
| Linux Mint                     | 18 +                   | X64 |
| openSUSE                       | 15 +                   | X64 |
| SUSE Enterprise Linux (SLES)   | 12 SP2+               | X64 |
| Alpine Linux                   | 3.8+                  | x64, ARM64 |

Per altre informazioni sui sistemi operativi, le distribuzioni e i criteri del ciclo di vita supportati di .NET Core 3,0, vedere [versioni del sistema operativo supportate da .net core 3,0](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).

Per altre informazioni su come installare .NET Core 3.0 su ARM64, vedere [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213) (Installazione di .NET Core 3.0 su Linux ARM64).

# <a name="net-core-22"></a>[.NET Core 2.2](#tab/netcore22)

.NET Core 2,2 considera Linux come un singolo sistema operativo. È disponibile una singola Build Linux (per ogni architettura chip) per le distribuzioni di Linux supportate.

.NET Core 2,2 è supportato nelle seguenti distribuzioni/versioni di Linux:

> [!NOTE]
> Un simbolo di `+` rappresenta la versione minima.

| Sistema operativo                             |  Versione                |  Architetture   |
| ------------------------------ | ----------------------- | ---------------- |
| Red Hat Enterprise Linux       |  6, 7                   | X64 |
| CentOS                         |  7                      | X64 |
| Oracle Linux                   |  7                      | X64 |
| Fedora                         |  29, 30                 | X64 |
| Debian                         |  9                      | x64, ARM32 |
| Ubuntu                         |  16,04, 18,04, 18,10    | x64, ARM32 |
| Linux Mint                     |  17, 18                 | X64 |
| openSUSE                       |  15 +                    | X64 |
| SUSE Enterprise Linux (SLES)   |  12 SP2+                | X64 |
| Alpine Linux                   |  3.8+                   | X64 |

Per altre informazioni sui sistemi operativi, le distribuzioni e i criteri del ciclo di vita supportati di .NET Core 2,2, vedere [versioni del sistema operativo supportate da .net core 2,2](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).

# <a name="net-core-21"></a>[.NET Core 2.1](#tab/netcore21)

.NET Core 2,1 considera Linux come un singolo sistema operativo. È disponibile una singola Build Linux (per ogni architettura chip) per le distribuzioni di Linux supportate.

.NET Core 2,1 è supportato nelle seguenti distribuzioni/versioni di Linux:

> [!NOTE]
> Un simbolo di `+` rappresenta la versione minima.

| Sistema operativo                             |  Versione                |  Architetture   |
| ------------------------------ | ----------------------- | ---------------- |
| Red Hat Enterprise Linux       |  6, 7, 8                | X64 |
| CentOS                         |  7+                     | X64 |
| Oracle Linux                   |  7+                     | X64 |
| Fedora                         |  29 +                    | X64 |
| Debian                         |  9                      | x64, ARM32 |
| Ubuntu                         |  16,04, 18,04, 19,04, 19,10    | x64, ARM32 |
| Linux Mint                     |  17 +                    | X64 |
| openSUSE                       |  15 +                    | X64 |
| SUSE Enterprise Linux (SLES)   |  12 SP2+                | X64 |
| Alpine Linux                   |  3.8+                   | X64 |

Per altre informazioni sui sistemi operativi, le distribuzioni e i criteri del ciclo di vita supportati di .NET Core 2,1, vedere [versioni del sistema operativo supportate da .net core 2,1](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).

---

## <a name="linux-distribution-dependencies"></a>Dipendenze delle distribuzioni Linux

In base alla distribuzione Linux, potrebbe essere necessario installare dipendenze aggiuntive.

> [!IMPORTANT]
> Le versioni e i nomi esatti possono variare leggermente nella distribuzione di Linux scelta.

### <a name="ubuntu"></a>Ubuntu

Per le distribuzioni di Ubuntu è necessario installare le librerie seguenti:

- liblttng-ust0
- libcurl3 (per 14.x e 16.x)
- libcurl4 (per 18.x)
- libssl1.0.0
- libkrb5-3
- zlib1g
- libicu52 (per 14.X)
- libicu55 (per 16.X)
- libicu57 (per 17.X)
- libicu60 (per 18.x)

Per le app .NET Core che usano l'assembly *System. Drawing. Common* , è necessaria anche la dipendenza seguente:

- libgdiplus (versione 6.0.1 o successiva)

> [!WARNING]
> La maggior parte delle versioni di Ubuntu include una versione precedente di libgdiplus. È possibile installare una versione recente di libgdiplus aggiungendo il repository mono al sistema. Per altre informazioni, vedere <https://www.mono-project.com/download/stable/>.

### <a name="centos-and-fedora"></a>CentOS e Fedora

Le distribuzioni CentOS richiedono che siano installate le librerie seguenti:

- lttng-ust
- libcurl
- openssl-libs
- krb5-libs
- libicu
- zlib

Utenti Fedora: se la versione di OpenSSL > = 1,1, è necessario installare **compat-openssl10**.

Per .NET Core 2,0, sono necessarie anche le dipendenze seguenti:

- libunwind
- libuuid

Per altre informazioni sulle dipendenze, vedere [app Linux](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)autosufficienti.

Per le app .NET Core che usano l'assembly *System. Drawing. Common* , è necessaria anche la dipendenza seguente:

- libgdiplus (versione 6.0.1 o successiva)

> [!WARNING]
> La maggior parte delle versioni di CentOS e Fedora include una versione precedente di libgdiplus. È possibile installare una versione recente di libgdiplus aggiungendo il repository mono al sistema. Per altre informazioni, vedere <https://www.mono-project.com/download/stable/>.

::: zone-end

::: zone pivot="os-macos"

.NET Core è supportato nelle versioni di macOS seguenti:

> [!NOTE]
> Un simbolo di `+` rappresenta la versione minima.

| Versione di .NET Core | macOS                 | Architetture |     |
| ----------------- | --------------------- | --------------| --- |
| 3.1               | Alta Sierra (10.13 +)  | X64 | [Altre informazioni](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| 3.0               | Alta Sierra (10.13 +)  | X64 | [Altre informazioni](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| 2.2               | Sierra (10.12 +)       | X64 | [Altre informazioni](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| 2.1               | Sierra (10.12 +)       | X64 | [Altre informazioni](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

## <a name="libgdiplus"></a>libgdiplus

Le applicazioni .NET Core che usano l'assembly *System. Drawing. Common* richiedono l'installazione di libgdiplus.

Un modo semplice per ottenere libgdiplus consiste nell'usare la gestione pacchetti [homebrew ("Brew")](https://brew.sh/) per MacOS. Dopo l'installazione di *Brew*, installare libgdiplus eseguendo i comandi seguenti in un prompt dei comandi (Command) terminale:

```console
brew update
brew install mono-libgdiplus
```

::: zone-end

## <a name="next-steps"></a>Passaggi successivi

- Per sviluppare ed eseguire app, installare il [.NET Core SDK](sdk.md) (include il Runtime).
- Per eseguire le app create da altri utenti, installare il [runtime di .NET Core](runtime.md).
