---
ms.openlocfilehash: 3d8179c5c0e84f8ff1197cce7790c80a5f5a4f6d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619449"
---

Quando si installa con una gestione pacchetti, queste librerie vengono installate. Tuttavia, se si installa manualmente .NET Core o si pubblica un'app autonoma, è necessario assicurarsi che siano installate le librerie seguenti:

- krb5-libs
- libicu
- openssl-libs

Se la versione OpenSSL dell'ambiente di runtime di destinazione è 1,1 o successiva, è necessario installare **compat-openssl10**.

Per altre informazioni sulle dipendenze, vedere [app Linux](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)autosufficienti.

Per le app .NET Core che usano l'assembly *System. Drawing. Common* , è necessaria anche la dipendenza seguente:

- [libgdiplus (versione 6.0.1 o successiva)](https://www.mono-project.com/docs/gui/libgdiplus/)

  > [!WARNING]
  > È possibile installare una versione recente di *libgdiplus* aggiungendo il repository mono al sistema. Per altre informazioni, vedere <https://www.mono-project.com/download/stable/>.
