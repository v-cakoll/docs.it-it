---
title: Installare .NET Core in SLES 15-Package Manager-.NET Core
description: Usare uno Gestione pacchetti per installare .NET Core SDK e Runtime in SLES 15.
author: thraka
ms.author: adegeo
ms.date: 11/06/2019
ms.openlocfilehash: 8e773dbc63ad8c969ae5c85c05ba9ed0c67311ac
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450968"
---
# <a name="sles-15-package-manager---install-net-core"></a>Gestione pacchetti SLES 15-installare .NET Core

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

Questo articolo descrive come usare un gestore di pacchetti per installare .NET Core in SLES 15. Se si sta installando il runtime, si consiglia di installare il [runtime di ASP.NET Core](#install-the-aspnet-core-runtime), perché include sia .NET Core che ASP.NET Core Runtime.

## <a name="register-microsoft-key-and-feed"></a>Registrare la chiave e il feed Microsoft

Prima di installare .NET, è necessario:

- Registrare la chiave Microsoft
- registrare il repository del prodotto
- Installare le dipendenze necessarie

Questa operazione deve essere eseguita solo una volta per ogni computer.

Aprire un terminale ed eseguire il comando seguente.

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/15/packages-microsoft-prod.rpm
```

## <a name="install-the-net-core-sdk"></a>Installare il .NET Core SDK

Aggiornare i prodotti disponibili per l'installazione, quindi installare il .NET Core SDK. Nel terminale eseguire il comando seguente.

```bash
sudo zypper install dotnet-sdk-3.0
```

## <a name="install-the-aspnet-core-runtime"></a>Installare il runtime di ASP.NET Core

Aggiornare i prodotti disponibili per l'installazione, quindi installare il runtime di ASP.NET. Nel terminale eseguire il comando seguente.

```bash
sudo zypper install aspnetcore-runtime-3.0
```

## <a name="install-the-net-core-runtime"></a>Installare il runtime di .NET Core

Aggiornare i prodotti disponibili per l'installazione, quindi installare il runtime di .NET Core. Nel terminale eseguire il comando seguente.

```bash
sudo zypper install dotnet-runtime-3.0
```

## <a name="how-to-install-other-versions"></a>Come installare altre versioni

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]
