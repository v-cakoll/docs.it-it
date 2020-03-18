---
title: Novità di .NET Core 2.0
description: Informazioni sulle nuove funzionalità in .NET Core.
ms.date: 08/13/2017
ms.openlocfilehash: 115b3adc72b6798c6a7bac9cc18044a8822808a6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398832"
---
# <a name="whats-new-in-net-core-20"></a>Novità di .NET Core 2.0

.NET Core 2.0 include miglioramenti e nuove funzionalità nelle aree seguenti:

- [Strumenti](#tooling)
- [Lingue supportate](#language-support)
- [Miglioramenti della piattaforma](#platform-improvements)
- [Modifiche all'API](#api-changes-and-library-support)
- [Integrazione con Visual Studio](#visual-studio-integration)
- [Miglioramenti alla documentazione](#documentation-improvements)

## <a name="tooling"></a>Strumenti

### <a name="dotnet-restore-runs-implicitly"></a>Il comando dotnet restore viene eseguito in modo implicito

Nelle versioni precedenti di .NET Core, era necessario eseguire il comando [dotnet restore](../tools/dotnet-restore.md) per scaricare le dipendenze immediatamente dopo aver creato un nuovo progetto con il comando [dotnet new](../tools/dotnet-new.md), nonché in seguito all'aggiunta di una nuova dipendenza al progetto.

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

È anche possibile disabilitare la chiamata automatica di `dotnet restore` passando l'opzione `--no-restore` ai comandi `new`, `run`, `build`, `publish`, `pack` e `test`.

### <a name="retargeting-to-net-core-20"></a>Ridestinazione a .NET Core 2.0

Se è installato .NET Core 2.0 SDK, i progetti destinati a .NET Core 1.x possono essere ridestinati a .NET Core 2.0.

Per ridestinare un progetto a .NET Core 2.0, modificare il file di progetto cambiando il valore dell'elemento `<TargetFramework>` (o l'elemento `<TargetFrameworks>` se il file di progetto include più destinazioni) da 1.x a 2.0:

```xml
<PropertyGroup>
    <TargetFramework>netcoreapp2.0</TargetFramework>
 </PropertyGroup>
```

È anche possibile ridestinare le librerie .NET Standard a .NET Standard 2.0 allo stesso modo:

```xml
<PropertyGroup>
    <TargetFramework>netstandard2.0</TargetFramework>
 </PropertyGroup>
```

Per altre informazioni sulla migrazione del progetto a .NET Core 2.0, vedere [Migrating from ASP.NET Core 1.x to ASP.NET Core 2.0](/aspnet/core/migration/1x-to-2x/index) (Migrazione da ASP.NET Core 1.x a ASP.NET Core 2.0).

## <a name="language-support"></a>Lingue supportate

Oltre a supportare C# e F#, .NET Core 2.0 supporta anche Visual Basic.

### <a name="visual-basic"></a>Visual Basic

Con la versione 2.0, .NET Core supporta ora Visual Basic 2017. È possibile usare Visual Basic per creare i tipi di progetto seguenti:

- App console .NET Core
- Librerie di classi .NET Core
- Librerie di classi .NET Standard
- Progetti di unit test .NET Core
- Progetti di unit test xUnit .NET Core

Ad esempio, per creare un'applicazione Visual Basic "Hello World", eseguire i passaggi seguenti dalla riga di comando:

1. Aprire una finestra della console, creare una directory per il progetto e impostarla come directory corrente.

1. Immettere il comando `dotnet new console -lang vb`.

   Il comando crea un file di progetto con estensione `.vbproj` oltre a un file di codice sorgente di Visual Basic denominato *Program.vb*. Questo file contiene il codice sorgente per scrivere la stringa "Hello World!" nella finestra della console.

1. Immettere il comando `dotnet run`. L'[interfaccia della riga di comando di .NET Core](../tools/index.md) compila ed esegue automaticamente l'applicazione, che visualizza il messaggio "Hello World!" nella finestra della console.

### <a name="support-for-c-71"></a>Supporto per C# 7.1

.NET core 2.0 supporta C# 7.1, che aggiunge varie nuove funzionalità, tra cui:

- Il metodo `Main`, ovvero il punto di ingresso dell'applicazione, può essere contrassegnato con la parola chiave [async](../../csharp/language-reference/keywords/async.md).
- Nomi di tupla dedotti.
- Espressioni predefinite.

<!-- For more information see [link to C# what's new](url). -->

## <a name="platform-improvements"></a>Miglioramenti della piattaforma

.NET Core 2.0 include numerose funzionalità che semplificano l'installazione di .NET Core e il relativo uso nei sistemi operativi supportati.

### <a name="net-core-for-linux-is-a-single-implementation"></a>.NET Core per Linux è un'implementazione singola

.NET Core 2.0 offre una singola implementazione di Linux che funziona su più distribuzioni di Linux. In .NET Core 1.x era richiesto il download di un'implementazione di Linux specifica per la distribuzione.

È anche possibile sviluppare app destinate a Linux come unico sistema operativo. In .NET Core 1.x era necessario specificare separatamente ogni distribuzione di Linux come destinazione.

### <a name="support-for-the-apple-cryptographic-libraries"></a>Supporto per le librerie di crittografia Apple

Per .NET Core 1.x in macOS era richiesta la libreria di crittografia del toolkit OpenSSL. .NET Core 2.0 usa le librerie di crittografia Apple e non richiede OpenSSL, pertanto non è più necessario installarlo.

## <a name="api-changes-and-library-support"></a>Modifiche delle API e supporto delle librerie

### <a name="support-for-net-standard-20"></a>Supporto di .NET Standard 2.0

.NET Standard definisce un set di API con versioni specifiche che devono essere disponibili nelle implementazioni .NET conformi con tale versione dello standard. .NET Standard è destinato agli sviluppatori di librerie. L'obiettivo è garantire le funzionalità disponibili in una libreria destinata a una versione di .NET Standard in ogni implementazione di .NET. .NET Core 1.x supporta .NET Standard versione 1.6; .NET Core 2.0 supporta l'ultima versione, ovvero .NET Standard 2.0. Per altre informazioni, vedere [.NET Standard](../../standard/net-standard.md).

.NET Standard 2.0 include più di 20.000 API aggiuntive rispetto a quelle disponibili in .NET Standard 1.6. Gran parte di questa superficie estesa deriva dall'incorporamento in .NET Standard delle API in comune per .NET Framework e Xamarin.

Anche le librerie di classi di .NET Standard 2.0 fanno riferimento alle librerie di classi di .NET Framework, a condizione che chiamino API presenti in .NET Standard 2.0. Non è richiesta alcuna ricompilazione delle librerie di .NET Framework.

Per un elenco delle API che sono state aggiunte allo standard .NET dall'ultima versione, .NET Standard 1.6, vedere [.NET Standard 2.0 vs. 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).

### <a name="expanded-surface-area"></a>Superficie estesa

Il numero totale di API disponibili in .NET Core 2.0 è più che raddoppiato rispetto a .NET Core 1.1.

Con [Windows Compatibility Pack](../porting/windows-compat-pack.md) il trasferimento da .NET Framework è diventato anche molto più semplice.

### <a name="support-for-net-framework-libraries"></a>Supporto delle librerie di .NET Framework

Il codice .NET Core può fare riferimento a librerie esistenti di .NET Framework, inclusi pacchetti NuGet esistenti. Si noti che le librerie devono usare le API disponibili in .NET Standard.

## <a name="visual-studio-integration"></a>Integrazione di Visual Studio

Visual Studio 2017 versione 15.3 e in alcuni casi Visual Studio per Mac offrono numerosi miglioramenti significativi per gli sviluppatori che usano .NET Core.

### <a name="retargeting-net-core-apps-and-net-standard-libraries"></a>Ridestinazione delle app .NET Core e delle librerie .NET Standard

Se è installato .NET Core 2.0 SDK, è possibile ridestinare i progetti .NET Core 1.x a .NET Core 2.0 e le librerie .NET Standard 1.x a .NET Standard 2.0.

Per ridestinare il progetto in Visual Studio, aprire la scheda **Applicazione** della finestra di dialogo delle proprietà del progetto e cambiare il valore di **Framework di destinazione** in **.NET Core 2.0** o **.NET Standard 2.0**. Per cambiare questa impostazione, è anche possibile fare clic con il pulsante destro del mouse sul progetto e scegliere il comando **Modifica file \*.csproj**. Per altre informazioni, vedere la sezione [Strumenti](#tooling) più indietro in questo argomento.

### <a name="live-unit-testing-support-for-net-core"></a>Supporto per Live Unit Testing per .NET Core

Ogni volta che si modifica il codice, Live Unit Testing esegue automaticamente tutti gli unit test interessati in background, visualizzando in tempo reale i risultati e il code coverage nell'ambiente di Visual Studio. .NET Core 2.0 ora supporta Live Unit Testing. In precedenza, Live Unit Testing era disponibile solo per le applicazioni .NET Framework.

Per ulteriori informazioni, vedere [Live Unit Testing con Visual Studio](/visualstudio/test/live-unit-testing) e le domande frequenti su Live Unit [Testing](/visualstudio/test/live-unit-testing-faq).

### <a name="better-support-for-multiple-target-frameworks"></a>Supporto migliorato per più framework di destinazione

Se è necessario ricompilare un progetto per più framework di destinazione, è ora possibile selezionare la piattaforma di destinazione dal menu di primo livello. Nella figura seguente un progetto denominato SCD1 è destinato a macOS X 10.11 a 64 bit (`osx.10.11-x64`) e a Windows 10/Windows Server 2016 a 64 bit (`win10-x64`). È possibile selezionare il framework di destinazione prima di selezionare il pulsante per compilare il progetto, in questo caso per eseguire una build di debug.

![Screenshot che illustra la selezione del framework di destinazione al momento della compilazione di un progetto.](./media/dotnet-core-2-0/target-framework-selection.png)

### <a name="side-by-side-support-for-net-core-sdks"></a>Supporto di .NET Core SDK affiancati

È ora possibile installare .NET Core SDK in modo indipendente da Visual Studio. In questo modo, una singola versione di Visual Studio consente di compilare progetti destinati a versioni diverse di .NET Core. In precedenza, Visual Studio e .NET Core SDK erano strettamente collegati e associati in base a versioni specifiche.

## <a name="documentation-improvements"></a>Miglioramenti alla documentazione

### <a name="net-application-architecture"></a>.NET Application Architecture

Dalla pagina [.NET Application Architecture](https://dotnet.microsoft.com/learn/dotnet/architecture-guides) (Architettura delle applicazioni .NET) è possibile accedere a una serie di eBook che offrono linee guida, procedure consigliate e applicazioni di esempio per l'uso di .NET per creare:

- [Contenitori di microservizi e Docker](../../architecture/microservices/index.md)
- [Applicazioni Web con ASP.NET](../../architecture/modern-web-apps-azure/index.md)
- [Applicazioni mobili con Xamarin](/xamarin/xamarin-forms/enterprise-application-patterns/index)
- [Applicazioni distribuite nel cloud con Azure](/azure/architecture/reference-architectures/index)

## <a name="see-also"></a>Vedere anche

- [Novità di ASP.NET Core 2.0](/aspnet/core/aspnetcore-2.0)
