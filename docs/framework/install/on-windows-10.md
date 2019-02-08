---
title: Installare .NET Framework in Windows 10
description: Informazioni sull'installazione di .NET Framework in Windows 10 o Windows Server 2016.
author: rlander
ms.author: mairaw
ms.date: 04/10/2018
ms.custom: updateeachrelease
ms.openlocfilehash: db5c6a45db299d716b2fdd115086e0dbc5952a59
ms.sourcegitcommit: e39d93d358974b9ed4541cedf4e25c0101015c3c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "55204301"
---
# <a name="install-the-net-framework-on-windows-10-and-windows-server-2016-and-later"></a>Installare .NET Framework in Windows 10 e Windows Server 2016 e versioni successive

.NET Framework è necessario per l'esecuzione di diverse applicazioni in Windows. Le istruzioni contenute in questo articolo consentono di installare le versioni di .NET Framework necessarie. [.NET Framework 4.7.2](https://dotnet.microsoft.com/download/dotnet-framework-runtime/net472) è la versione più recente disponibile.

È possibile che si sia arrivati a questa pagina dopo avere provato a eseguire un'applicazione e avere visualizzato sul computer una finestra di dialogo simile a quella seguente:

![Impossibile avviare l'applicazione](./media/this-application-could-not-be-started.png)

## <a name="net-framework-472"></a>.NET Framework 4.7.2

.NET Framework 4.7.2 è incluso in:

* [Aggiornamento di Windows 10 (ottobre 2018)](https://support.microsoft.com/help/4028685/windows-10-get-the-update)

* [Aggiornamento di Windows 10 (aprile 2018)](https://www.microsoft.com/software-download/windows10)

* Windows Server 2019

* Windows Server, versione 1809

* Windows Server, versione 1803

> [!div class="button"]
> [Scaricare .NET Framework 4.7.2](https://dotnet.microsoft.com/download/dotnet-framework-runtime/net472)

[.NET Framework 4.7.2](https://dotnet.microsoft.com/download/dotnet-framework-runtime/net472) può essere usato per eseguire le applicazioni create per le versioni di .NET Framework da 4.0 a 4.7.1.

È possibile installare [.NET Framework 4.7.2](https://dotnet.microsoft.com/download/dotnet-framework-runtime/net472) in:

* Windows 10 Fall Creators Update (versione 1709)
* Windows 10 Creators Update (versione 1703)
* Aggiornamento dell'anniversario di Windows 10 (versione 1607)
* Windows Server, versione 1709
* Windows Server 2016

.NET Framework 4.7.2 non è supportato in:

* Windows 10 1507
* Windows 10 1511

Se si usa Windows 10 1507 o 1511 e si vuole installare .NET Framework 4.7.2, è prima necessario eseguire l'aggiornamento a una versione più recente di Windows 10.

## <a name="net-framework-462"></a>.NET Framework 4.6.2

[.NET Framework 4.6.2](https://www.microsoft.com/en-us/download/details.aspx?id=53345) è la versione di .NET Framework supportata più recente in Windows 10 1507 e 1511.

.NET Framework 4.6.2 supporta le app create per .NET Framework da 4.0 a 4.6.2.

## <a name="net-framework-35"></a>.NET Framework 3.5

Seguire le istruzioni per l'installazione di [.NET Framework 3.5 in Windows 10](dotnet-35-windows-10.md).

.NET Framework 3.5 supporta le app create per .NET Framework da 1.0 a 3.5.

## <a name="additional-information"></a>Informazioni aggiuntive

Le versioni 4.x di .NET Framework sono aggiornamenti sul posto di versioni precedenti. Ciò significa che:

- Nel computer può essere installata una sola versione di .NET Framework 4.x.

- Non è possibile installare una versione precedente elencata di .NET Framework nel computer se è già installata una versione successiva.

- Le versioni 4.x di .NET Framework possono essere usate per eseguire le applicazioni create per .NET Framework da 4.0 a tale versione. .NET Framework 4.7, ad esempio, può essere usato per eseguire le applicazioni create per le versioni di .NET Framework da 4.0 a 4.7. La versione più recente (.NET Framework 4.7.2) può essere usata per eseguire le applicazioni create con tutte le versioni di .NET Framework a partire dalla 4.0.

Per un elenco di tutte le versioni di .NET Framework disponibili per il download, vedere la pagina [.NET Downloads](https://www.microsoft.com/net/download?utm_source=ms-docs&utm_medium=referral) (Download di .NET).

## <a name="help"></a>?

Se non si riesce a installare la versione corretta di .NET Framework, è possibile [contattare Microsoft per assistenza](mailto:dotnet-install-help@service.microsoft.com?subject=Install-Help).

## <a name="see-also"></a>Vedere anche

- [.NET Downloads](https://www.microsoft.com/net/download?utm_source=ms-docs&utm_medium=referral) (Download di .NET)
- [Risolvere i problemi relativi alle installazioni e alle disinstallazioni bloccate di .NET Framework](troubleshoot-blocked-installations-and-uninstallations.md)
- [Installare .NET Framework per sviluppatori](guide-for-developers.md)
