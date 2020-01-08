---
title: Integrazione continua (CI) con .NET Core SDK e strumenti
description: Informazioni su come usare il .NET Core SDK e i relativi strumenti nel server di compilazione con integrazione continua.
author: mairaw
ms.date: 05/18/2017
ms.custom: seodec18
ms.openlocfilehash: 0f6049d1f2868ff330fd59c4f40e6c02231c6f71
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75343531"
---
# <a name="using-net-core-sdk-and-tools-in-continuous-integration-ci"></a>Uso di .NET Core SDK e dei relativi strumenti in integrazione continua

Questo documento illustra l'uso di .NET Core SDK e dei relativi strumenti in un server di compilazione. Il set di strumenti di .NET Core funziona interattivamente, quando uno sviluppatore digita i comandi al prompt dei comandi, e automaticamente, quando un server di integrazione continua (CI) esegue uno script di compilazione. I comandi, le opzioni, gli input e gli output sono uguali, e gli unici elementi da specificare sono un modo per acquisire gli strumenti e un sistema per compilare l'app. Questo documento illustra specificatamente gli scenari di acquisizione degli strumenti per CI e include consigli su come progettare e strutturare gli script di compilazione.

## <a name="installation-options-for-ci-build-servers"></a>Opzioni di installazione per i server di compilazione di integrazione continua

### <a name="using-the-native-installers"></a>Uso di programmi di installazione nativi

Sono disponibili programmi di installazione nativi per macOS, Linux e Windows. I programmi di installazione richiedono l'accesso amministratore (sudo) al server di compilazione. L'uso di un programma di installazione nativo offre il vantaggio di installare tutte le dipendenze native necessarie per l'esecuzione degli strumenti. I programmi di installazione nativi offrono anche un'installazione a livello di sistema dell'SDK.

Gli utenti di macOS devono usare i programmi di installazione PKG. In Linux è possibile scegliere di usare un sistema di gestione pacchetti basato su feed, ad esempio apt-get per Ubuntu o yum per CentOS, oppure i pacchetti stessi DEB o RPM. In Windows usare il programma di installazione MSI.

I file binari stabili più recenti sono reperibili in [.NET downloads](https://dotnet.microsoft.com/download) (Download di .NET). Se si vuole usare gli strumenti della versione non definitiva più recente (e potenzialmente instabile), vedere i collegamenti riportati nel [repository GitHub dotnet/core-sdk](https://github.com/dotnet/core-sdk#installers-and-binaries). Per le distribuzioni di Linux, sono disponibili gli archivi `tar.gz` (noti anche come `tarballs`). Usare gli script di installazione all'interno degli archivi per installare .NET Core.

### <a name="using-the-installer-script"></a>Uso dello script di installazione

L'uso dello script di installazione consente di installare il sistema senza privilegi amministrativi nel server di compilazione e offre un'automazione semplice per ottenere gli strumenti. Lo script esegue automaticamente il download e l'estrazione degli strumenti in un percorso predefinito o specificato per l'uso. È anche possibile specificare la versione degli strumenti che si vogliono installare e se si vuole installare l'intero SDK o solo il runtime condiviso.

Lo script di installazione viene automatizzato per essere eseguito all'inizio della compilazione per recuperare e installare la versione necessaria dell'SDK. La *versione necessaria* è la versione dell'SDK più adatta per compilare i progetti. Lo script consente di installare l'SDK in una directory locale del server, eseguire gli strumenti dal percorso di installazione e quindi pulire (o consentire al servizio CI di eseguire la pulizia) al termine della compilazione. Ciò consente incapsulamento e isolamento per l'intero processo di compilazione. I riferimenti agli script di installazione sono reperibili nell'articolo [dotnet-install](dotnet-install-script.md).

> [!NOTE]
> **Azure DevOps Services**
>
> Quando si usa lo script di installazione, le dipendenze native non vengono installate automaticamente. È necessario installare le dipendenze native, se non sono già presenti nel sistema operativo. Per altre informazioni, vedere [dipendenze e requisiti di .NET Core](../install/dependencies.md?tabs=netcore30&pivots=os-linux).

## <a name="ci-setup-examples"></a>Esempi di installazione di CI

Questa sezione illustra un'installazione manuale tramite uno script di PowerShell o Bash e include la descrizione di alcune soluzioni CI SaaS (software come un servizio). Le soluzioni CI SaaS illustrate sono [Travis CI](https://travis-ci.org/), [AppVeyor](https://www.appveyor.com/) e [Azure Pipelines](https://docs.microsoft.com/azure/devops/pipelines/index).

### <a name="manual-setup"></a>Installazione manuale

Ogni servizio SaaS ha i propri metodi per la creazione e la configurazione di un processo di compilazione. Se si usano soluzioni SaaS diversi da quelli elencati o è necessaria una personalizzazione del supporto non inclusa nei pacchetti predefiniti, si devono eseguire alcune configurazioni manuali.

In genere, un'installazione manuale deve ottenere una versione di strumenti (o le compilazioni notturne più recente degli strumenti) ed eseguire lo script di compilazione. È possibile usare uno script di PowerShell o Bash per orchestrare i comandi di .NET Core o usare un file di progetto che descriva il processo di compilazione. La [sezione sull'orchestrazione](#orchestrating-the-build) offre più dettagli su queste opzioni.

Dopo aver creato uno script che esegue un'installazione manuale del server di compilazione CI, usarlo nel computer di sviluppo per compilare il codice localmente a scopo di test. Dopo aver verificato che lo script viene eseguito correttamente nel computer locale, distribuirlo al server di compilazione CI. Di seguito viene specificato uno script di PowerShell relativamente semplice che illustra come ottenere .NET Core SDK e installarlo in un server di compilazione di Windows:

```powershell
$ErrorActionPreference="Stop"
$ProgressPreference="SilentlyContinue"

# $LocalDotnet is the path to the locally-installed SDK to ensure the
#   correct version of the tools are executed.
$LocalDotnet=""
# $InstallDir and $CliVersion variables can come from options to the
#   script.
$InstallDir = "./cli-tools"
$CliVersion = "1.0.1"

# Test the path provided by $InstallDir to confirm it exists. If it
#   does, it's removed. This is not strictly required, but it's a
#   good way to reset the environment.
if (Test-Path $InstallDir)
{
    rm -Recurse $InstallDir
}
New-Item -Type "directory" -Path $InstallDir

Write-Host "Downloading the CLI installer..."

# Use the Invoke-WebRequest PowerShell cmdlet to obtain the
#   installation script and save it into the installation directory.
Invoke-WebRequest `
    -Uri "https://dot.net/v1/dotnet-install.ps1" `
    -OutFile "$InstallDir/dotnet-install.ps1"

Write-Host "Installing the CLI requested version ($CliVersion) ..."

# Install the SDK of the version specified in $CliVersion into the
#   specified location ($InstallDir).
& $InstallDir/dotnet-install.ps1 -Version $CliVersion `
    -InstallDir $InstallDir

Write-Host "Downloading and installation of the SDK is complete."

# $LocalDotnet holds the path to dotnet.exe for future use by the
#   script.
$LocalDotnet = "$InstallDir/dotnet"

# Run the build process now. Implement your build script here.
```

L'implementazione per il processo di compilazione viene specificata alla fine dello script. Lo script acquisisce gli strumenti e quindi esegue il processo di compilazione. Per i computer UNIX, lo script Bash seguente esegue le azioni descritte nello script di PowerShell allo stesso modo:

```bash
#!/bin/bash
INSTALLDIR="cli-tools"
CLI_VERSION=1.0.1
DOWNLOADER=$(which curl)
if [ -d "$INSTALLDIR" ]
then
    rm -rf "$INSTALLDIR"
fi
mkdir -p "$INSTALLDIR"
echo Downloading the CLI installer.
$DOWNLOADER https://dot.net/v1/dotnet-install.sh > "$INSTALLDIR/dotnet-install.sh"
chmod +x "$INSTALLDIR/dotnet-install.sh"
echo Installing the CLI requested version $CLI_VERSION. Please wait, installation may take a few minutes.
"$INSTALLDIR/dotnet-install.sh" --install-dir "$INSTALLDIR" --version $CLI_VERSION
if [ $? -ne 0 ]
then
    echo Download of $CLI_VERSION version of the CLI failed. Exiting now.
    exit 0
fi
echo The CLI has been installed.
LOCALDOTNET="$INSTALLDIR/dotnet"
# Run the build process now. Implement your build script here.
```

### <a name="travis-ci"></a>Travis CI

È possibile configurare [Travis CI](https://travis-ci.org/) per installare .NET Core SDK usando il linguaggio `csharp` e la chiave `dotnet`. Per altre informazioni, vedere i documenti ufficiali di Travis CI in [Building a C#, F#, or Visual Basic Project](https://docs.travis-ci.com/user/languages/csharp/) (Compilazione di un progetto C#, F# o Visual Basic). Quando si accede alle informazioni su Travis CI si noti che l'identificatore del linguaggio `language: csharp` gestito dalla community funziona per tutti i linguaggi .NET, inclusi F# e Mono.

Travis CI esegue entrambi i processi macOS e Linux in una *matrice di compilazione*, in cui si specifica una combinazione di runtime, ambiente ed esclusioni/inclusioni per includere le combinazioni di compilazione per l'app. Per altre informazioni, vedere [Customizing the Build](https://docs.travis-ci.com/user/customizing-the-build) (Personalizzazione della compilazione) nella documentazione di Travis CI. Gli strumenti basati su MSBuild includono i runtime LTS (1.0.x) e Current (1.1.x) nel pacchetto. Per questo motivo, l'installazione dell'SDK installa tutti gli elementi necessari per la compilazione.

### <a name="appveyor"></a>AppVeyor

[AppVeyor](https://www.appveyor.com/) installa .NET Core 1.0.1 SDK con l'immagine di lavoro della build `Visual Studio 2017`. Sono disponibili altre immagini di compilazione con versioni diverse di .NET Core SDK. Per altre informazioni, vedere l'esempio [appveyor.yml](https://github.com/dotnet/docs/blob/master/appveyor.yml) e l'articolo [Build worker images](https://www.appveyor.com/docs/build-environment/#build-worker-images) (Compilare immagini di lavoro) nella documentazione di AppVeyor.

I file binari di .NET Core SDK vengono scaricati ed estratti in una sottodirectory tramite lo script di installazione e aggiunti alla variabile di ambiente `PATH`. Aggiungere una matrice di compilazione per eseguire test di integrazione con più versioni di .NET Core SDK:

```yaml
environment:
  matrix:
    - CLI_VERSION: 1.0.1
    - CLI_VERSION: Latest

install:
  # See appveyor.yml example for install script
```

### <a name="azure-devops-services"></a>Azure DevOps Services

Configurare Azure DevOps Services per compilare i progetti .NET Core usando uno di questi approcci:

1. Eseguire lo script del [passaggio di installazione manuale](#manual-setup) usando i comandi.
1. Creare una build composta da diverse attività di compilazione incorporate di Azure DevOps Services configurate per usare gli strumenti di .NET Core.

Entrambe le soluzioni sono valide. Tramite uno script di installazione manuale, si controlla la versione degli strumenti ricevuti, dopo averli scaricati come parte della compilazione. La compilazione viene eseguita da uno script che deve essere creato. Questo articolo descrive solo l'opzione manuale. Per altre informazioni sulla creazione di una build con le attività di compilazione di Azure DevOps Services, vedere la documentazione di [Azure Pipelines](https://docs.microsoft.com/azure/devops/pipelines/index).

Per usare uno script di installazione manuale in Azure DevOps Services, creare una nuova definizione di compilazione e specificare lo script da eseguire per l'istruzione di compilazione. Questa operazione viene eseguita tramite l'interfaccia utente di Azure DevOps Services:

1. Iniziare con la creazione di una nuova definizione di compilazione. Quando viene visualizzata la schermata che offre un'opzione per definire il tipo di compilazione da creare, selezionare **Vuota**.

   ![Selezione di una definizione vuota di compilazione](./media/using-ci-with-cli/select-empty-build-definition.png)

1. Dopo aver configurato il repository per la compilazione, si viene indirizzati alle definizioni della compilazione. Selezionare **Aggiungi istruzione di compilazione**:

   ![Aggiunta di un'istruzione di compilazione](./media/using-ci-with-cli/add-build-step.png)

1. Viene visualizzato il **catalogo delle attività**. Il catalogo include le attività da usare nella compilazione. Poiché è disponibile uno script, selezionare il pulsante **Aggiungi** di **PowerShell: Consente di eseguire uno script PowerShell**.

   ![Aggiunta di un'istruzione di script di PowerShell](./media/using-ci-with-cli/add-powershell-script.png)

1. Configurare l'istruzione di compilazione. Aggiungere lo script dal repository che si sta creando:

   ![Specifica dello script di PowerShell da eseguire](./media/using-ci-with-cli/powershell-script-path.png)

## <a name="orchestrating-the-build"></a>Orchestrazione della compilazione

La maggior parte di questo documento illustra come acquisire gli strumenti di .NET Core e configurare i vari servizi CI senza specificare le informazioni su come orchestrare, o *compilare effettivamente*, il codice con .NET Core. Le scelte su come strutturare il processo di compilazione dipendono da molti fattori che non possono essere illustrati in modo generico. Per altre informazioni sull'orchestrazione delle compilazioni con ogni tecnologia, vedere le risorse e gli esempi inclusi nei set di documentazione di [Travis CI](https://travis-ci.org/), [AppVeyor](https://www.appveyor.com/) e [Azure Pipelines](https://docs.microsoft.com/azure/devops/pipelines/index).

Due approcci generali accettati nella strutturazione del processo di compilazione per il codice .NET Core tramite gli strumenti di .NET Core consistono nell'usare MSBuild direttamente o i comandi della riga di comando di .NET Core. L'approccio da adottare è determinato dal livello di esperienza con gli approcci e dai pro e contro in termini di complessità. MSBuild offre la possibilità di esprimere il processo di compilazione come attività e destinazioni, ma è accompagnato dalla complessità nel dover imparare la sintassi dei file di progetto di MSBuild. L'uso degli strumenti da riga di comando di .NET Core è probabilmente più semplice, ma richiede la scrittura logica di orchestrazione in un linguaggio di scripting, ad esempio `bash` o PowerShell.

## <a name="see-also"></a>Vedere anche

- [.NET Downloads - Linux](https://dotnet.microsoft.com/download?initial-os=linux) (Download di .NET - Linux)
