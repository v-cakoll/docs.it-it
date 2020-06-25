---
title: Uso dell'autenticazione di macOS Catalina
description: Come gestire i problemi di autenticazione e autenticazione con macOS quando si installa il runtime, l'SDK e le app di .NET Core compilati con .NET Core.
author: adegeo
ms.author: adegeo
ms.date: 02/14/2020
ms.openlocfilehash: cd3886b2e772a182156d212aefb9705a3fb5e17c
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324616"
---
# <a name="macos-catalina-notarization-and-the-impact-on-net-core-downloads-and-projects"></a>Autenticazione di macOS Catalina e l'effetto sui download e sui progetti di .NET Core

A partire da macOS Catalina (versione 10,15), tutto il software creato dopo il 1 ° giugno 2019 e distribuito con ID sviluppatore deve essere autenticato. Questo requisito si applica al runtime di .NET Core, alla .NET Core SDK e al software creato con .NET Core. Questo articolo descrive gli scenari comuni che si possono incontrare con l'autenticazione di .NET Core e macOS.

## <a name="installing-net-core"></a>Installazione di .NET Core

I programmi di installazione per .NET Core (Runtime e SDK) versioni 3,1, 3,0 e 2,1 sono stati autenticati dal 18 febbraio 2020. Le versioni precedenti rilasciate non vengono autenticate. È possibile installare manualmente una versione non autenticata di .NET Core scaricando prima il programma di installazione e quindi usando il `sudo installer` comando. Per altre informazioni, vedere [scaricare e installare manualmente per MacOS](sdk.md?pivots=os-macos#download-and-manually-install).

A partire dalle versioni seguenti, i programmi di installazione di .NET Core sono autenticati:

- Runtime di .NET Core
  - 2.1.16
  - 3.0.3
  - 3.1.2

- .NET Core SDK
  - 2.1.512
  - 3.0.103
  - 3.1.102

## <a name="apphost-is-disabled-by-default"></a>appHost è disabilitato per impostazione predefinita

Per impostazione predefinita, le versioni non autenticate di .NET Core SDK 3,0 e versioni successive producono un eseguibile nativo di Mach-O (noto come **APPHOST**) quando il progetto viene compilato, pubblicato o eseguito. Questo eseguibile è un modo pratico per eseguire l'app. In caso contrario, l'app deve essere avviata eseguendo `dotnet <filename.dll>` . Quando appHost è abilitato, il `dotnet run` comando viene richiamato nel contesto di APPHOST. Per ulteriori informazioni, vedere [contesto di APPHOST](#context-of-the-apphost).

A partire dalle versioni autenticate di .NET Core SDK 3,0 e versioni successive, l'eseguibile appHost non viene generato per impostazione predefinita. È possibile attivare la generazione appHost con l' [`UseAppHost`](../project-sdk/msbuild-props.md#useapphost) impostazione booleana nel file di progetto. È anche possibile impostare appHost con il `-p:UseAppHost` parametro nella riga di comando per il `dotnet` comando specifico eseguito:

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

Quando si pubblica l'app [autonoma](../deploying/index.md#publish-self-contained), viene sempre creato un APPHOST.

Per ulteriori informazioni sull' `UseAppHost` impostazione, vedere [Proprietà MSBuild per Microsoft. NET. SDK](../project-sdk/msbuild-props.md#useapphost).

### <a name="context-of-the-apphost"></a>Contesto di appHost

Quando il appHost è abilitato nel progetto e si usa il `dotnet run` comando per eseguire l'app, l'app viene richiamata nel contesto di APPHOST e non nell'host predefinito (l'host predefinito è il `dotnet` comando). Se il appHost è disabilitato nel progetto, il `dotnet run` comando esegue l'applicazione nel contesto dell'host predefinito. Anche se il appHost è disabilitato, la pubblicazione dell'applicazione come autonoma genera un eseguibile appHost e gli utenti usano tale eseguibile per eseguire l'app. L'esecuzione dell'app con `dotnet <filename.dll>` richiama l'app con l'host predefinito, il runtime condiviso.

Quando viene richiamata un'app che usa il appHost, la partizione del certificato a cui accede l'app è diversa dall'host predefinito autenticato. Se l'app deve accedere ai certificati installati tramite l'host predefinito, usare il `dotnet run` comando per eseguire l'app dal file di progetto oppure usare il `dotnet <filename.dll>` comando per avviare direttamente l'app.

Altre informazioni su questo scenario sono disponibili nella sezione [ASP.NET Core e MacOS e sui certificati](#aspnet-core-and-macos-and-certificates) .

## <a name="aspnet-core-and-macos-and-certificates"></a>ASP.NET Core e macOS e certificati

.NET Core consente di gestire i certificati nel keychain di macOS con la <xref:System.Security.Cryptography.X509Certificates> classe. L'accesso al keychain di macOS usa l'identità delle applicazioni come chiave primaria per decidere quale partizione prendere in considerazione. Ad esempio, le applicazioni non firmate archiviano i segreti nella partizione senza segno, ma le applicazioni firmate archiviano i segreti solo nelle partizioni a cui possono accedere. L'origine di esecuzione che richiama l'app decide quale partizione usare.

.NET Core fornisce tre origini di esecuzione: [APPHOST](#apphost-is-disabled-by-default), l'host predefinito (il `dotnet` comando) e un host personalizzato. Ogni modello di esecuzione può avere identità diverse, con segno o senza segno e ha accesso a partizioni diverse all'interno del keychain. I certificati importati da una modalità potrebbero non essere accessibili da un altro. Ad esempio, le versioni autenticate di .NET Core hanno un host predefinito firmato. I certificati vengono importati in una partizione sicura in base alla relativa identità. Questi certificati non sono accessibili da un appHost generato, perché appHost non è firmato.

Un altro esempio, per impostazione predefinita, ASP.NET Core importa un certificato SSL predefinito tramite l'host predefinito. ASP.NET Core applicazioni che usano un appHost non avranno accesso a questo certificato e riceveranno un errore quando .NET Core rileva che il certificato non è accessibile. Nel messaggio di errore vengono fornite istruzioni su come risolvere il problema.

Se è richiesta la condivisione del certificato, macOS fornisce le opzioni di configurazione con l' `security` utilità.

Per ulteriori informazioni su come risolvere i problemi relativi al certificato ASP.NET Core, vedere [enforce HTTPS in ASP.NET Core](/aspnet/core/security/enforcing-ssl?view=aspnetcore-3.1&tabs=visual-studio#troubleshoot-certificate-problems).

## <a name="default-entitlements"></a>Diritti predefiniti

L'host predefinito di .NET Core (il `dotnet` comando) ha un set di diritti predefiniti. Questi diritti sono necessari per il funzionamento corretto di .NET Core. È possibile che l'applicazione richieda diritti aggiuntivi, nel qual caso sarà necessario generare e usare un [APPHOST](#apphost-is-disabled-by-default) e quindi aggiungere i diritti necessari in locale.

Set predefinito di diritti per .NET Core:

- `com.apple.security.cs.allow-jit`
- `com.apple.security.cs.allow-unsigned-executable-memory`
- `com.apple.security.cs.allow-dyld-environment-variables`
- `com.apple.security.cs.disable-library-validation`

## <a name="notarize-a-net-core-app"></a>Autenticare un'app .NET Core

Se si vuole che l'applicazione venga eseguita in macOS Catalina (versione 10,15) o successiva, è necessario autenticare l'app. I appHost inviati con l'applicazione per l'autenticazione devono essere usati con almeno gli stessi [diritti predefiniti](#default-entitlements) per .NET Core.

## <a name="next-steps"></a>Passaggi successivi

- [Dipendenze e requisiti di .NET Core](dependencies.md).
- [Installare il .NET Core SDK](sdk.md).
- [Installare il runtime di .NET Core](runtime.md)
