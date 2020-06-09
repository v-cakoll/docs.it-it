---
ms.openlocfilehash: b371525c9f4e57c6a09e5bb9232884e5c5e707e0
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84603006"
---

Quando si installa con una gestione pacchetti, queste librerie vengono installate. Tuttavia, se si installa manualmente .NET Core o si pubblica un'app autonoma, è necessario assicurarsi che siano installate le librerie seguenti:

- lttng-ust
- libcurl
- openssl-libs
- krb5-libs
- libicu
- zlib
- libunwind
- libuuid

Se la versione OpenSSL dell'ambiente di runtime di destinazione è 1,1 o successiva, è necessario installare **compat-openssl10**.

Per altre informazioni sulle dipendenze, vedere [app Linux](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)autosufficienti.

Per le app .NET Core che usano l'assembly *System. Drawing. Common* , è necessaria anche la dipendenza seguente:

- [libgdiplus (versione 6.0.1 o successiva)](https://www.mono-project.com/docs/gui/libgdiplus/)

  > [!WARNING]
  > È possibile installare una versione recente di *libgdiplus* aggiungendo il repository mono al sistema. Per altre informazioni, vedere <https://www.mono-project.com/download/stable/>.
