---
title: Lavorare con la notarizzazione di catalina di macOS
description: Come gestire i problemi di notarizzazione e certificato con macOS quando installi il runtime di .NET Core, l'SDK e le app create con .NET Core.
author: thraka
ms.author: adegeo
ms.date: 02/14/2020
ms.openlocfilehash: be39c1ea56699f84736a2b37bc958507b16e826b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79146749"
---
# <a name="macos-catalina-notarization-and-the-impact-on-net-core-downloads-and-projects"></a>notarazione catalina di macOS e impatto sui download e progetti di .NET Core

A partire da macOS Catalina (versione 10.15), tutti i software creati dopo il 1 giugno 2019 e distribuiti con l'ID sviluppatore devono essere notarizzati. Questo requisito si applica al runtime .NET Core, a .NET Core SDK e al software creato con .NET Core. In questo articolo vengono descritti gli scenari comuni che è possibile affrontare con la notarizzazione di .NET Core e macOS.

## <a name="installing-net-core"></a>Installazione di .NET Core

I programmi di installazione per .NET Core (sia runtime che SDK) versioni 3.1, 3.0 e 2.1, sono stati notarizzati dal 18 febbraio 2020. Le versioni rilasciate precedenti non sono notificate. È possibile installare manualmente una versione non notarizzata di .NET Core scaricando prima il programma di installazione e quindi utilizzando il `sudo installer` comando . Per ulteriori informazioni, consultate [Scaricare e installare manualmente per macOS.](sdk.md?pivots=os-macos#download-and-manually-install)

A partire dalle versioni seguenti, i programmi di installazione di .NET Core sono degni di notarizzazione:

- Runtime di .NET Core
  - 2.1.16
  - 3.0.3
  - 3.1.2

- .NET Core SDK
  - 2.1.512
  - 3.0.103
  - 3.1.102

## <a name="apphost-is-disabled-by-default"></a>appHost è disabilitato per impostazione predefinita

Per impostazione predefinita, le versioni non notarizzate di .NET Core SDK 3.0 e versioni successive producono un eseguibile Mach-O nativo (noto come **appHost**) quando il progetto viene compilato, pubblicato o eseguito. Questo eseguibile è un modo pratico per eseguire l'app. In caso contrario, l'app deve essere avviata eseguendo `dotnet <filename.dll>`. Quando appHost è abilitato, il `dotnet run` comando viene richiamato nel contesto di appHost. Per ulteriori informazioni, consultate [Contesto dell'appHost.](#context-of-the-apphost)

A partire dalle versioni notarized di .NET Core SDK 3.0 e versioni successive, l'eseguibile appHost non viene generato per impostazione predefinita. È possibile attivare la [`UseAppHost`](../project-sdk/msbuild-props.md#useapphost) generazione di appHost con l'impostazione booleana nel file di progetto. È anche possibile attivare/disattivare l'appHost con il `-p:UseAppHost` parametro nella riga di comando per il comando specifico `dotnet` eseguito:

- File di progetto

  ```xml
  <PropertyGroup>
    <UseAppHost>true</UseAppHost>
  </PropertyGroup>
  ```

- Parametro della riga di comando

  ```dotnetcli
  dotnet run -p:UseAppHost=true
  ```

Un appHost viene sempre creato quando si pubblica l'app [indipendente.](../deploying/index.md#publish-self-contained)

Per ulteriori informazioni `UseAppHost` sull'impostazione, vedere [Proprietà MSBuild per Microsoft.NET.Sdk](../project-sdk/msbuild-props.md#useapphost).

### <a name="context-of-the-apphost"></a>Contesto dell'appHost

Quando l'appHost è abilitato nel progetto `dotnet run` e si usa il comando per eseguire l'app, l'app viene richiamata `dotnet` nel contesto di appHost e non nell'host predefinito (l'host predefinito è il comando). Se l'appHost è disabilitato `dotnet run` nel progetto, il comando esegue l'app nel contesto dell'host predefinito. Anche se l'appHost è disabilitato, la pubblicazione dell'app come autonoma genera un eseguibile appHost e gli utenti usano tale eseguibile per eseguire l'app. L'esecuzione `dotnet <filename.dll>` dell'app con richiama l'app con l'host predefinito, il runtime condiviso.

Quando viene richiamata un'app che usa appHost, la partizione del certificato a cui accede l'app è diversa dall'host predefinito notarizzato. Se l'app deve accedere ai certificati `dotnet run` installati tramite l'host predefinito, usa `dotnet <filename.dll>` il comando per eseguire l'app dal relativo file di progetto oppure usa il comando per avviare direttamente l'app.

Ulteriori informazioni su questo scenario sono disponibili nella sezione [ASP.NET Core, macOS e certificati.](#aspnet-core-and-macos-and-certificates)

## <a name="aspnet-core-and-macos-and-certificates"></a>ASP.NET Core e macOS e certificati

.NET Core offre la possibilità di gestire i certificati <xref:System.Security.Cryptography.X509Certificates> nel portachiavi di macOS con la classe. L'accesso al portachiavi macOS utilizza l'identità delle applicazioni come chiave primaria per decidere quale partizione prendere in considerazione. Ad esempio, le applicazioni non firmate archiviano i segreti nella partizione non firmata, ma le applicazioni firmate archiviano i segreti solo nelle partizioni a cui possono accedere. L'origine di esecuzione che richiama l'app decide quale partizione usare.

.NET Core fornisce tre origini di esecuzione: `dotnet` [appHost](#apphost-is-disabled-by-default), host predefinito (il comando) e un host personalizzato. Ogni modello di esecuzione può avere identità diverse, firmate o non firmate, e hanno accesso a partizioni diverse all'interno del portachiavi. I certificati importati da una modalità potrebbero non essere accessibili da un'altra. Ad esempio, le versioni notarizzate di .NET Core hanno un host predefinito firmato. I certificati vengono importati in una partizione sicura in base alla relativa identità. Questi certificati non sono accessibili da un appHost generato, poiché appHost non è firmato.

Un altro esempio, per impostazione predefinita, ASP.NET Core importa un certificato SSL predefinito tramite l'host predefinito. ASP.NET applicazioni Core che usano un appHost non avranno accesso a questo certificato e riceveranno un errore quando .NET Core rileva che il certificato non è accessibile. Il messaggio di errore fornisce istruzioni su come risolvere il problema.

Se è necessaria la condivisione dei certificati, macOS fornisce opzioni di configurazione con l'utilità. `security`

Per ulteriori informazioni su come risolvere i problemi relativi ai certificati ASP.NET Core, vedere [Applicare HTTPS in ASP.NET Core](/aspnet/core/security/enforcing-ssl?view=aspnetcore-3.1&tabs=visual-studio#troubleshoot-certificate-problems).

## <a name="default-entitlements"></a>Diritti predefiniti

L'host predefinito di .NET Core (il `dotnet` comando) dispone di un set di permessi predefiniti. Questi diritti sono necessari per il corretto funzionamento di .NET Core.These entitlements are required for proper operation of .NET Core. È possibile che l'applicazione necessiti di diritti aggiuntivi, nel qual caso sarà necessario generare e usare un [appHost](#apphost-is-disabled-by-default) e quindi aggiungere i permessi necessari in locale.

Set predefinito di permessi per .NET Core:

- `com.apple.security.cs.allow-jit`
- `com.apple.security.cs.allow-unsigned-executable-memory`
- `com.apple.security.cs.allow-dyld-environment-variables`
- `com.apple.security.cs.disable-library-validation`

## <a name="notarize-a-net-core-app"></a>Annotare un'app .NET Core

Se vuoi che l'applicazione venga eseguita su macOS Catalina (versione 10.15) o successiva, ti consigliamo di annotare la tua app. L'appHost inviato con l'applicazione per la notarizzazione deve essere usato con almeno gli stessi permessi predefiniti per .NET Core.The appHost you submit with your application for notarization should be used with at least the same [default entitlements](#default-entitlements) for .NET Core.

## <a name="next-steps"></a>Passaggi successivi

- [Dipendenze e requisiti di .NET Core.](dependencies.md)
- [Installare .NET Core SDK](sdk.md).
- [Installare .NET Core Runtime](runtime.md)
