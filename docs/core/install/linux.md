---
title: Installare le distribuzioni di .NET Core e Linux
description: Informazioni sulle distribuzioni di Linux che supportano l'installazione di .NET Core in Linux.
author: thraka
ms.author: adegeo
ms.date: 06/01/2020
ms.openlocfilehash: fec3cf9e99c2db5d7312280f676bc2a3344f1ae1
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602894"
---
# <a name="install-net-core-on-linux"></a>Installare .NET Core in Linux

.NET Core è disponibile in diverse distribuzioni di Linux. La maggior parte delle piattaforme e distribuzioni Linux hanno una versione principale ogni anno e la maggior parte forniscono un gestore di pacchetti usato per installare .NET Core. Questo articolo descrive gli elementi attualmente supportati e la gestione pacchetti usata.

Il resto di questo articolo è una suddivisione di ogni principale distribuzione Linux supportata da .NET Core. Tutte le versioni di .NET Core rimangono supportate fino a quando la versione di [.NET Core non raggiunge la fine del supporto](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la distribuzione di Linux raggiunge la fine del ciclo di vita.

Per una migliore compatibilità, scegliere una versione di Long-Term Release (LTS).

## <a name="unsupported-releases"></a>Versioni non supportate

Le versioni seguenti di .NET Core ❌ non sono più supportate. I download per questi ancora rimangono pubblicati:

- 3.0
- 2.2
- 2.0

Queste versioni non supportate non sono descritte in dettaglio nelle sezioni seguenti e il chilometraggio può variare se si tenta di installarli.

## <a name="centos"></a>CentOS

CentOS 7 USA yum come gestione pacchetti e CentOS 8 USA DNF.

La tabella seguente è un elenco delle versioni di .NET Core attualmente supportate in CentOS 7 e CentOS 8. Queste versioni rimangono supportate fino a quando la versione di [.NET Core raggiunge la fine del supporto](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la versione di CentOS non è più supportata.

| CentOS                   | .NET Core 2.1 | .NET Core 3.1 | .NET 5 Preview (solo installazione manuale) |
|--------------------------|---------------|---------------|----------------|
| ✔️ [8](linux-centos.md#centos-8-) | ✔️ 2,1        | ✔️ 3,1        | Anteprima di ✔️ 5,0 |
| ✔️ [7](linux-centos.md#centos-7-) | ✔️ 2,1        | ✔️ 3,1        | Anteprima di ✔️ 5,0 |

Per altre informazioni, vedere [installare .NET Core su CentOS](linux-centos.md).

## <a name="debian"></a>Debian

Debian usa APT (Advanced Package Tool) come strumento di gestione pacchetti.

La tabella seguente è un elenco delle versioni di .NET Core attualmente supportate e delle versioni di Debian su cui sono supportate. Queste versioni rimangono supportate fino a quando la versione di [.NET Core raggiunge la fine del supporto](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la versione di [Debian raggiunge la fine del ciclo di vita](https://wiki.debian.org/DebianReleases).

- Un ✔️ indica che la versione di Debian o .NET Core è ancora supportata.
- ❌Indica che la versione di Debian o .NET Core non è supportata in questa versione Debian.
- Quando una versione di Debian e una versione di .NET Core sono ✔️, sono supportate le combinazioni di sistema operativo e .NET.

| Debian                   | .NET Core 2.1 | .NET Core 3.1 | .NET 5 Preview (solo installazione manuale) |
|--------------------------|---------------|---------------|----------------|
| ✔️ [10](linux-debian.md#debian-10-)     | ✔️ 2,1        | ✔️ 3,1        | Anteprima di ✔️ 5,0 |
| ✔️ [9](linux-debian.md#debian-9-)       | ✔️ 2,1        | ✔️ 3,1        | Anteprima di ✔️ 5,0 |
| ❌[8](linux-debian.md#debian-8-)       | ✔️ 2,1        | ❌3,1        | ❌Anteprima 5,0 |

## <a name="fedora"></a>Fedora

Fedora usa DNF come gestione pacchetti.

La tabella seguente è un elenco delle versioni di .NET Core attualmente supportate e delle versioni di Fedora su cui sono supportate. Queste versioni rimangono supportate fino a quando la versione di [.NET Core non raggiunge la fine del supporto](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la versione di [Fedora raggiunge la fine del ciclo di vita](https://fedoraproject.org/wiki/End_of_life).

- Un ✔️ indica che la versione di Fedora o .NET Core è ancora supportata.
- ❌Indica che la versione di Fedora o .NET Core non è supportata nella versione Fedora.
- Quando una versione di Fedora e una versione di .NET Core hanno ✔️, sono supportate le combinazioni di sistema operativo e .NET.

| Fedora                   | .NET Core 2.1 | .NET Core 3.1 | .NET 5 Preview (solo installazione manuale) |
|--------------------------|---------------|---------------|----------------|
| ✔️ [32](linux-fedora.md#fedora-32-) | ✔️ 2,1        | ✔️ 3,1        | Anteprima di ✔️ 5,0 |
| ✔️ [31](linux-fedora.md#fedora-31-) | ✔️ 2,1        | ✔️ 3,1        | Anteprima di ✔️ 5,0 |
| ❌ [30](linux-fedora.md#fedora-30-) | ✔️ 2,1        | ✔️ 3,1        | ❌Anteprima 5,0 |
| ❌[29](linux-fedora.md#fedora-29-) | ✔️ 2,1        | ✔️ 3,1        | ❌Anteprima 5,0 |
| ❌[28](linux-fedora.md#fedora-28-) | ✔️ 2,1        | ❌3,1        | ❌Anteprima 5,0 |
| ❌[27](linux-fedora.md#fedora-27-) | ✔️ 2,1        | ❌3,1        | ❌Anteprima 5,0 |

Per altre informazioni, vedere [installare .NET Core in Fedora](linux-fedora.md).

## <a name="opensuse"></a>openSUSE

openSUSE usa zypper come gestione pacchetti.

La tabella seguente è un elenco delle versioni di .NET Core attualmente supportate in openSUSE 15. Queste versioni rimangono supportate fino a quando la versione di [.NET Core raggiunge la fine del supporto](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la versione di openSUSE non è più supportata.

- Un ✔️ indica che la versione di openSUSE o .NET Core è ancora supportata.
- ❌Indica che la versione di openSUSE o .NET Core non è supportata nella versione di openSUSE.
- Quando una versione di openSUSE e una versione di .NET Core hanno ✔️, sono supportate le combinazioni di sistema operativo e .NET.

| openSUSE                   | .NET Core 2.1 | .NET Core 3.1 | .NET 5 Preview (solo installazione manuale) |
|----------------------------|---------------|---------------|----------------|
| ✔️ [15](linux-opensuse.md#opensuse-15-)     | ✔️ 2,1        | ✔️ 3,1        | Anteprima di ✔️ 5,0 |

## <a name="red-hat"></a>Red Hat

Red Hat Enterprise Linux (RHEL) usa yum (RHEL 7) e DNF (RHEL 8) come gestione pacchetti.

La tabella seguente è un elenco delle versioni di .NET Core attualmente supportate in RHEL 7 e RHEL 8. Queste versioni rimangono supportate fino a quando la versione di [.NET Core non raggiunge la fine del supporto](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la versione di RHEL non è più supportata.

- Un ✔️ indica che la versione di RHEL o .NET Core è ancora supportata.
- ❌Indica che la versione di RHEL o .NET Core non è supportata nella versione RHEL.
- Quando una versione di RHEL e una versione di .NET Core hanno ✔️, sono supportate le combinazioni di sistema operativo e .NET.

| RHEL                   | .NET Core 2.1 | .NET Core 3.1 | .NET 5 Preview (solo installazione manuale) |
|--------------------------|---------------|---------------|----------------|
| ✔️ [8](linux-rhel.md#rhel-8-) | ✔️ 2,1        | ✔️ 3,1        | Anteprima di ✔️ 5,0 |
| ✔️ [7](linux-rhel.md#rhel-7-) | ✔️ 2,1        | ✔️ 3,1        | Anteprima di ✔️ 5,0 |

## <a name="sles"></a>SLES

SLES USA zypper come gestione pacchetti.

La tabella seguente è un elenco delle versioni di .NET Core attualmente supportate in SLES 12 SP2 e SLES 15. Queste versioni rimangono supportate fino a quando la versione di [.NET Core raggiunge la fine del supporto](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la versione di SLES non è più supportata.

- Un ✔️ indica che la versione di SLES o .NET Core è ancora supportata.
- ❌Indica che la versione di SLES o .NET Core non è supportata nella versione SLES.
- Quando una versione di SLES e una versione di .NET Core hanno ✔️, sono supportate le combinazioni di sistema operativo e .NET.

| SLES                   | .NET Core 2.1 | .NET Core 3.1 | .NET 5 Preview (solo installazione manuale) |
|------------------------|---------------|---------------|----------------|
| ✔️ [15](linux-sles.md#sles-15-)     | ✔️ 2,1        | ✔️ 3,1        | Anteprima di ✔️ 5,0 |
| ✔️ [12 SP2](linux-sles.md#sles-12-) | ✔️ 2,1        | ✔️ 3,1        | Anteprima di ✔️ 5,0 |

## <a name="ubuntu"></a>Ubuntu

Ubuntu usa APT (Advanced Package Tool) come strumento di gestione pacchetti.

La tabella seguente rappresenta lo stato di supporto di Ubuntu e .NET Core.

- Un ✔️ indica che la versione di Ubuntu o .NET Core è ancora supportata.
- ❌Indica che la versione di Ubuntu o .NET Core non è supportata in questa versione di Ubuntu.
- Quando una versione di Ubuntu e una versione di .NET Core hanno ✔️, sono supportate le combinazioni di sistema operativo e .NET.

| Ubuntu                   | .NET Core 2.1 | .NET Core 3.1 | .NET 5 Preview (solo installazione manuale) |
|--------------------------|---------------|---------------|----------------|
| ✔️ [20,04 (LTS)](linux-ubuntu.md#2004-) | ✔️ 2,1        | ✔️ 3,1        | Anteprima di ✔️ 5,0 |
| ✔️ [19,10](linux-ubuntu.md#1910-)       | ✔️ 2,1        | ✔️ 3,1        | Anteprima di ✔️ 5,0 |
| ❌[19,04](linux-ubuntu.md#1904-)       | ✔️ 2,1        | ✔️ 3,1        | ❌Anteprima 5,0 |
| ❌[18,10](linux-ubuntu.md#1810-)       | ✔️ 2,1        | ❌3,1        | ❌Anteprima 5,0 |
| ✔️ [18,04 (LTS)](linux-ubuntu.md#1804-) | ✔️ 2,1        | ✔️ 3,1        | Anteprima di ✔️ 5,0 |
| ❌ [17.10](linux-ubuntu.md#1710-)       | ✔️ 2,1        | ❌3,1        | ❌Anteprima 5,0 |
| ❌ [17.04](linux-ubuntu.md#1704-)       | ✔️ 2,1        | ❌3,1        | ❌Anteprima 5,0 |
| ❌[16,10](linux-ubuntu.md#1610-)       | ❌2,1        | ❌3,1        | ❌Anteprima 5,0 |
| ✔️ [16,04 (LTS)](linux-ubuntu.md#1604-) | ✔️ 2,1        | ✔️ 3,1        | Anteprima di ✔️ 5,0 |

Per altre informazioni, vedere [installare .NET Core in Ubuntu](linux-ubuntu.md).
