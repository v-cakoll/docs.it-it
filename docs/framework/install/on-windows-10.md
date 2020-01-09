---
title: Installare .NET Framework in Windows 10
description: Informazioni sull'installazione di .NET Framework in Windows 10 o Windows Server 2016.
ms.date: 04/18/2019
ms.custom: updateeachrelease
ms.openlocfilehash: c2b274bb85b6d4c496e7b6b6b62f05aa932202dd
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716376"
---
# <a name="install-the-net-framework-on-windows-10-and-windows-server-2016-and-later"></a>Installare .NET Framework in Windows 10 e Windows Server 2016 e versioni successive

.NET Framework è necessario per l'esecuzione di diverse applicazioni in Windows. Le istruzioni contenute in questo articolo consentono di installare le versioni di .NET Framework necessarie. [.NET Framework 4.8](https://github.com/Microsoft/dotnet/tree/master/releases/net48) è la versione più recente disponibile.

È possibile che si sia arrivati a questa pagina dopo avere provato a eseguire un'applicazione e avere visualizzato sul computer una finestra di dialogo simile a quella seguente:

![Impossibile avviare l'applicazione](./media/this-application-could-not-be-started.png)

## <a name="net-framework-48"></a>.NET Framework 4.8

.NET Framework 4.8 è incluso in:

- [Aggiornamento di Windows di 10 maggio 2019](https://support.microsoft.com/help/4028685/windows-10-get-the-update)

> [!div class="button"]
> [Download di .NET Framework 4.8](https://dotnet.microsoft.com/download/dotnet-framework/net48)

È possibile usare [.NET Framework 4.8](https://dotnet.microsoft.com/download/dotnet-framework/net48) per eseguire applicazioni compilate per le versioni di .NET Framework da 4.0 a 4.7.2.

È possibile installare [.NET Framework 4.8](https://dotnet.microsoft.com/download/dotnet-framework/net48) in:

- Aggiornamento di Windows 10 di ottobre 2018 (versione 1809)
- Aggiornamento di Windows 10 di aprile 2018 (versione 1803)
- Windows 10 Fall Creators Update (versione 1709)
- Windows 10 Creators Update (versione 1703)
- Aggiornamento dell'anniversario di Windows 10 (versione 1607)
- Windows Server 2019
- Windows Server, versione 1809
- Windows Server, versione 1803
- Windows Server 2016

.NET Framework 4.8 non è supportato in:

- Windows 10 1507
- Windows 10 1511

Se si usa Windows 10 1507 o 1511 e si vuole installare .NET Framework 4.8, è prima necessario eseguire l'aggiornamento a una versione più recente di Windows 10.

## <a name="net-framework-462"></a>.NET Framework 4.6.2

[.NET Framework 4.6.2](https://www.microsoft.com/download/details.aspx?id=53345) è la versione di .NET Framework supportata più recente in Windows 10 1507 e 1511.

.NET Framework 4.6.2 supporta le app create per .NET Framework da 4.0 a 4.6.2.

## <a name="net-framework-35"></a>.NET Framework 3.5

Seguire le istruzioni per l'installazione di [.NET Framework 3.5 in Windows 10](dotnet-35-windows-10.md).

.NET Framework 3.5 supporta le app create per .NET Framework da 1.0 a 3.5.

## <a name="additional-information"></a>Informazioni aggiuntive

Le versioni 4.x di .NET Framework sono aggiornamenti sul posto di versioni precedenti. Ciò significa che:

- Nel computer può essere installata una sola versione di .NET Framework 4.x.

- Non è possibile installare una versione precedente elencata di .NET Framework nel computer se è già installata una versione successiva.

- Le versioni 4.x di .NET Framework possono essere usate per eseguire le applicazioni create per .NET Framework da 4.0 a tale versione. .NET Framework 4.7, ad esempio, può essere usato per eseguire le applicazioni create per le versioni di .NET Framework da 4.0 a 4.7. La versione più recente (.NET Framework 4.8) può essere usata per eseguire applicazioni compilate con tutte le versioni di .NET Framework a partire dalla 4.0.

Per un elenco di tutte le versioni di .NET Framework disponibili per il download, vedere la pagina [.NET Downloads](https://dotnet.microsoft.com/download) (Download di .NET).

## <a name="help"></a>Guida di

Se non si riesce a installare la versione corretta di .NET Framework, è possibile [contattare Microsoft per assistenza](mailto:dotnet-install-help@service.microsoft.com?subject=Install-Help).

## <a name="see-also"></a>Vedere anche

- [.NET Downloads](https://dotnet.microsoft.com/download) (Download di .NET)
- [Risolvere i problemi relativi alle installazioni e alle disinstallazioni bloccate di .NET Framework](troubleshoot-blocked-installations-and-uninstallations.md)
- [Installare .NET Framework per sviluppatori](guide-for-developers.md)
