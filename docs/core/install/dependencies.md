---
title: Dipendenze di runtime e sdiche di .NET Core - .NET Core
description: Vengono descritti in dettaglio i prerequisiti del sistema operativo e dell'architettura della CPU per installare .NET Core SDK e runtime in Windows, Linux e macOS.
author: leecow
ms.author: leecow
ms.date: 12/04/2019
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 023b8fdf029dd6b17fe2186296d87dd7507c60b5
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2020
ms.locfileid: "79546562"
---
# <a name="net-core-dependencies-and-requirements"></a>Dipendenze e requisiti di .NET Core

Questo articolo descrive in dettaglio quali sistemi operativi e architettura della CPU sono supportati da .NET Core.This article details which operating systems and CPU architecture are supported by .NET Core.

## <a name="supported-operating-systems"></a>Sistemi operativi supportati

::: zone pivot="os-windows"

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-core-31"></a>[.NET Core 3.1](#tab/netcore31)

Le seguenti versioni di Windows sono supportate con .NET Core 3.1:

> [!NOTE]
> Un `+` simbolo rappresenta la versione minima.

| OS                            | Versione                        | Architetture   |
| ----------------------------- | ------------------------------ | --------------- |
| Client Windows                | 7 SP1, 8,1                    | x64, x86        |
| Windows 10 Client             | Versione 1607                  | x64, x86        |
| Windows Server                | 2012 R2                       | x64, x86        |
| Nano Server                   | Versione 1803                  | x64, ARM32      |

Per ulteriori informazioni sui sistemi operativi supportati, distribuzioni e criteri del ciclo di vita supportati da .NET Core 3.1, vedere Versioni del sistema operativo supportate di [.NET Core 3.1.](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md)

# <a name="net-core-30"></a>[.NET Core 3.0](#tab/netcore30)

*.NET Core 3.0 è attualmente fuori supporto. Per ulteriori informazioni, vedere Criteri di [supporto di .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*

Le seguenti versioni di Windows sono supportate con .NET Core 3.0:

> [!NOTE]
> Un `+` simbolo rappresenta la versione minima.

| OS                            | Versione                        | Architetture   |
| ----------------------------- | ------------------------------ | --------------- |
| Client Windows                | 7 SP1, 8,1                    | x64, x86        |
| Windows 10 Client             | Versione 1607                  | x64, x86        |
| Windows Server                | 2012 R2                       | x64, x86        |
| Nano Server                   | Versione 1803                  | x64, ARM32      |

Per ulteriori informazioni sui sistemi operativi supportati, distribuzioni e criteri del ciclo di vita supportati da .NET Core 3.0, vedere Versioni del sistema operativo supportate di [.NET Core 3.0](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).

# <a name="net-core-22"></a>[.NET Core 2.2](#tab/netcore22)

*.NET Core 2.2 è attualmente fuori supporto. Per ulteriori informazioni, vedere Criteri di [supporto di .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*

Le seguenti versioni di Windows sono supportate con .NET Core 2.2:

> [!NOTE]
> Un `+` simbolo rappresenta la versione minima.

| OS                            | Versione                        | Architetture   |
| ----------------------------- | ------------------------------ | --------------- |
| Client Windows                | 7 SP1, 8,1                    | x64, x86        |
| Windows 10 Client             | Versione 1607                  | x64, x86        |
| Windows Server                | 2008 R2 SP1                   | x64, x86        |
| Nano Server                   | Versione 1803                   | x64, ARM32      |

Per ulteriori informazioni sui sistemi operativi supportati, distribuzioni e criteri del ciclo di vita supportati da .NET Core 2.2, vedere Versioni del sistema operativo supportate di [.NET Core 2.2.](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)

# <a name="net-core-21"></a>[.NET Core 2.1](#tab/netcore21)

Le seguenti versioni di Windows sono supportate con .NET Core 2.1:

> [!NOTE]
> Un `+` simbolo rappresenta la versione minima.

| OS                            | Versione                        | Architetture   |
| ----------------------------- | ------------------------------ | --------------- |
| Client Windows                | 7 SP1, 8,1                    | x64, x86        |
| Windows 10 Client             | Versione 1607                  | x64, x86        |
| Windows Server                | 2008 R2 SP1                   | x64, x86        |
| Nano Server                   | Versione 1803                  | x64,            |

Per ulteriori informazioni sui sistemi operativi supportati, distribuzioni e criteri del ciclo di vita supportati da .NET Core 2.1, vedere Versioni del sistema operativo supportate di [.NET Core 2.1.](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)

---

<!-- markdownlint-disable MD001 -->

### <a name="windows-7--vista--81--server-2008-r2"></a>Windows 7 / Vista / 8.1 / Server 2008 R2

Ulteriori dipendenze sono necessarie se si installa .NET SDK o runtime nelle seguenti versioni di Windows:

- Windows 7 SP1
- Windows Vista SP 2
- Windows 8.1
- Windows Server 2008 R2
- Windows Server 2012 R2

Installare i componenti seguenti:

- [Aggiornamento ridistribuibile 3](https://www.microsoft.com/download/details.aspx?id=52685)di Microsoft Visual C
- [KB2533623](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)

I requisiti di cui sopra sono necessari anche se si verifica uno dei seguenti errori:

> Impossibile avviare il programma perché *api-ms-win-crt-runtime-l1-1-0.dll* non è presente nel computer. Provare a reinstallare il programma per risolvere il problema.
>
> \- - oppure -
>
> La libreria *hostfxr.dll* è stata trovata, ma il caricamento da *C:\\\<path_to_app>hostfxr.dll \\* non è riuscito.

::: zone-end

::: zone pivot="os-linux"

# <a name="net-core-31"></a>[.NET Core 3.1](#tab/netcore31)

.NET Core 3.1 considera Linux come un unico sistema operativo. Esiste una singola build Linux (per architettura per chip) per le distribuzioni Linux supportate.

.NET Core 3.1 è supportato nelle seguenti distribuzioni/versioni Linux:

> [!NOTE]
> Un `+` simbolo rappresenta la versione minima.

| OS                             | Versione               | Architetture    |
| ------------------------------ | --------------------- | ---------------- |
| Red Hat Enterprise Linux       | 6, 7, 8               | x64 |
| CentOS                         | 7+                    | x64 |
| Oracle Linux                   | 7+                    | x64 |
| Fedora                         | Più di 30 anni                   | x64 |
| Debian                         | 9+                    | x64, ARM32, ARM64 |
| Ubuntu                         | 16.04+                | x64, ARM32, ARM64 |
| Linux Mint                     | PIÙ di 18 anni                   | x64 |
| openSUSE                       | PIÙ di 15 anni                   | x64 |
| SUSE Enterprise Linux (SLES)   | 12 SP2+               | x64 |
| Alpine Linux                   | 3.10 o più                 | x64, ARM64 |

Per ulteriori informazioni sui sistemi operativi supportati, distribuzioni e criteri del ciclo di vita supportati da .NET Core 3.1, vedere Versioni del sistema operativo supportate di [.NET Core 3.1.](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md)

Per ulteriori informazioni su come installare .NET Core 3.1 in ARM64 (kernel 4.14), vedere Installazione di [.NET Core 3.0 su Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).

> [!IMPORTANT]
> Il supporto ARM64 richiede kernel Linux 4.14 o versione successiva. Alcune distribuzioni linux soddisfano questo requisito, mentre altre no. Ad esempio, Ubuntu 18.04 è supportato, ma Ubuntu 16.04 non lo è.

# <a name="net-core-30"></a>[.NET Core 3.0](#tab/netcore30)

*.NET Core 3.0 è attualmente fuori supporto. Per ulteriori informazioni, vedere Criteri di [supporto di .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*

.NET Core 3.0 considera Linux come un unico sistema operativo. Esiste una singola build Linux (per architettura per chip) per le distribuzioni Linux supportate.

.NET Core 3.0 è supportato nelle seguenti distribuzioni/versioni Linux:

> [!NOTE]
> Un `+` simbolo rappresenta la versione minima.

| OS                             | Versione               | Architetture    |
| ------------------------------ | --------------------- | ---------------- |
| Red Hat Enterprise Linux       | 6, 7, 8               | x64 |
| CentOS                         | 7+                    | x64 |
| Oracle Linux                   | 7+                    | x64 |
| Fedora                         | Più di 29 anni                   | x64 |
| Debian                         | 9+                    | x64, ARM32, ARM64 |
| Ubuntu                         | 16.04+                | x64, ARM32, ARM64 |
| Linux Mint                     | PIÙ di 18 anni                   | x64 |
| openSUSE                       | PIÙ di 15 anni                   | x64 |
| SUSE Enterprise Linux (SLES)   | 12 SP2+               | x64 |
| Alpine Linux                   | 3.8+                  | x64, ARM64 |

Per ulteriori informazioni sui sistemi operativi supportati, distribuzioni e criteri del ciclo di vita supportati da .NET Core 3.0, vedere Versioni del sistema operativo supportate di [.NET Core 3.0](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).

Per altre informazioni su come installare .NET Core 3.0 su ARM64, vedere [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213) (Installazione di .NET Core 3.0 su Linux ARM64).

# <a name="net-core-22"></a>[.NET Core 2.2](#tab/netcore22)

*.NET Core 2.2 è attualmente fuori supporto. Per ulteriori informazioni, vedere Criteri di [supporto di .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*

.NET Core 2.2 considera Linux come un unico sistema operativo. Esiste una singola build Linux (per architettura per chip) per le distribuzioni Linux supportate.

.NET Core 2.2 è supportato nelle seguenti distribuzioni/versioni Linux:

> [!NOTE]
> Un `+` simbolo rappresenta la versione minima.

| OS                             |  Versione                |  Architetture   |
| ------------------------------ | ----------------------- | ---------------- |
| Red Hat Enterprise Linux       |  6, 7                   | x64 |
| CentOS                         |  7                      | x64 |
| Oracle Linux                   |  7                      | x64 |
| Fedora                         |  29, 30                 | x64 |
| Debian                         |  9                      | x64, ARM32 |
| Ubuntu                         |  16.04, 18.04, 18.10    | x64, ARM32 |
| Linux Mint                     |  17, 18                 | x64 |
| openSUSE                       |  PIÙ di 15 anni                    | x64 |
| SUSE Enterprise Linux (SLES)   |  12 SP2+                | x64 |
| Alpine Linux                   |  3.8+                   | x64 |

Per ulteriori informazioni sui sistemi operativi supportati, distribuzioni e criteri del ciclo di vita supportati da .NET Core 2.2, vedere Versioni del sistema operativo supportate di [.NET Core 2.2.](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)

# <a name="net-core-21"></a>[.NET Core 2.1](#tab/netcore21)

.NET Core 2.1 considera Linux come un unico sistema operativo. Esiste una singola build Linux (per architettura per chip) per le distribuzioni Linux supportate.

.NET Core 2.1 è supportato nelle seguenti distribuzioni/versioni Linux:

> [!NOTE]
> Un `+` simbolo rappresenta la versione minima.

| OS                             |  Versione                |  Architetture   |
| ------------------------------ | ----------------------- | ---------------- |
| Red Hat Enterprise Linux       |  6, 7, 8                | x64 |
| CentOS                         |  7+                     | x64 |
| Oracle Linux                   |  7+                     | x64 |
| Fedora                         |  Più di 30 anni                    | x64 |
| Debian                         |  9                      | x64, ARM32 |
| Ubuntu                         |  16.04, 18.04, 19.04, 19.10    | x64, ARM32 |
| Linux Mint                     |  17+                    | x64 |
| openSUSE                       |  PIÙ di 15 anni                    | x64 |
| SUSE Enterprise Linux (SLES)   |  12 SP2+                | x64 |
| Alpine Linux                   |  3.8+                   | x64 |

Per ulteriori informazioni sui sistemi operativi supportati, distribuzioni e criteri del ciclo di vita supportati da .NET Core 2.1, vedere Versioni del sistema operativo supportate di [.NET Core 2.1.](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)

---

## <a name="linux-distribution-dependencies"></a>Dipendenze delle distribuzioni Linux

In base alla distribuzione linux, potrebbe essere necessario installare dipendenze aggiuntive.

> [!IMPORTANT]
> Le versioni e i nomi esatti possono variare leggermente nella distribuzione di Linux scelta.

### <a name="ubuntu"></a>Ubuntu

Le distribuzioni Di Ubuntu richiedono l'installazione delle seguenti librerie:

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

Per le app .NET Core che usano l'assembly *System.Drawing.Common,* è necessaria anche la dipendenza seguente:For .NET Core apps that use the System.Drawing.Common assembly, you also need the following dependency:

- libgdiplus (versione 6.0.1 o successiva)

> [!WARNING]
> La maggior parte delle versioni di Ubuntu includono una versione precedente di libgdiplus. È possibile installare una versione recente di libgdiplus aggiungendo il repository Mono al sistema. Per altre informazioni, vedere <https://www.mono-project.com/download/stable/>.

### <a name="centos-and-fedora"></a>CentOS e Fedora

Le distribuzioni CentOS richiedono che siano installate le librerie seguenti:

- lttng-ust
- libcurl
- openssl-libs
- krb5-libs
- libicu
- zlib

Utenti Fedora: se la versione di OpenSSL >1,1, dovrai installare **compat-openssl10**.

Per .NET Core 2.0, sono necessarie anche le dipendenze seguenti:For .NET Core 2.0, also the following dependencies are required:

- libunwind
- libuuid

Per altre informazioni sulle dipendenze, vedere [App Linux autonome](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).

Per le app .NET Core che usano l'assembly *System.Drawing.Common,* è inoltre necessaria la dipendenza seguente:For .NET Core apps that use the System.Drawing.Common assembly, you'll also need the following dependency:

- libgdiplus (versione 6.0.1 o successiva)

> [!WARNING]
> La maggior parte delle versioni di CentOS e Fedora includono una versione precedente di libgdiplus. È possibile installare una versione recente di libgdiplus aggiungendo il repository Mono al sistema. Per altre informazioni, vedere <https://www.mono-project.com/download/stable/>.

::: zone-end

::: zone pivot="os-macos"

.NET Core è supportato nelle seguenti versioni di macOS:

> [!NOTE]
> Un `+` simbolo rappresenta la versione minima.

| Versione .NET Core | macOS                 | Architetture |     |
| ----------------- | --------------------- | --------------| --- |
| 3.1               | Alta Sierra (10.13)  | x64 | [Ulteriori informazioni](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| 3.0               | Alta Sierra (10.13)  | x64 | [Ulteriori informazioni](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| 2.2               | Sierra (10.12)       | x64 | [Ulteriori informazioni](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| 2.1               | Sierra (10.12)       | x64 | [Ulteriori informazioni](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

A partire da macOS Catalina (versione 10.15), tutti i software creati dopo il 1 giugno 2019 distribuito con l'ID sviluppatore devono essere notarizzati. Questo requisito si applica al runtime .NET Core, a .NET Core SDK e al software creato con .NET Core.

I programmi di installazione per .NET Core (sia runtime che SDK) versioni 3.1, 3.0 e 2.1, sono stati notarizzati dal 18 febbraio 2020. Le versioni rilasciate precedenti non sono notificate. Se esegui un'app non notarizzata, verrà visualizzato un errore simile all'immagine seguente:

![avviso di notarizzazione catalina macOS](media/dependencies/macos-notarized-pkg-warning.png)

Per altre informazioni su come la notarizzazione applicata influisce su .NET Core (e sulle app .NET Core), vedere [Utilizzo della notarizzazione catalina di macOS](macos-notarization-issues.md).

## <a name="libgdiplus"></a>libgdiplus

Le applicazioni .NET Core che utilizzano l'assembly *System.Drawing.Common* richiedono l'installazione di libgdiplus.

Un modo semplice per ottenere libgdiplus consiste nell'utilizzare il gestore di pacchetti [Homebrew ("brew")](https://brew.sh/) per macOS. Dopo aver installato *brew*, installare libgdiplus eseguendo i seguenti comandi al prompt Terminal (comando):

```console
brew update
brew install mono-libgdiplus
```

::: zone-end

## <a name="next-steps"></a>Passaggi successivi

- Per sviluppare ed eseguire app, installare [.NET Core SDK](sdk.md) (include il runtime).
- Per eseguire le app create da altri, installare il [runtime di .NET Core.](runtime.md)
