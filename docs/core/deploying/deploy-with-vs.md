---
title: Distribuire app .NET Core con Visual Studio
description: Informazioni su come distribuire un'app .NET Core con Visual Studio.
ms.date: 09/03/2018
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 23dc0f691c8a8d80a0bd2a5d301ace0d129007af
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920897"
---
# <a name="deploy-net-core-apps-with-visual-studio"></a>Distribuire app .NET Core con Visual Studio

È possibile distribuire un'app .NET Core come *distribuzione dipendente dal framework*, che include i file binari dell'applicazione ma dipende dalla presenza di .NET Core nel sistema di destinazione oppure come *distribuzione autonoma*, che include l'applicazione e i file binari di .NET Core. Per una panoramica della distribuzione di applicazioni .NET Core, vedere [Distribuzione di applicazioni .NET Core](index.md).

Le sezioni seguenti illustrano l'uso di Microsoft Visual Studio per creare i tipi di distribuzione seguenti:

- Distribuzione dipendente dal framework
- Distribuzione dipendente dal framework con dipendenze di terze parti
- Distribuzione autonoma
- Distribuzione autonoma con dipendenze di terze parti

Per informazioni sull'uso di Visual Studio per lo sviluppo di applicazioni .NET Core, vedere [dipendenze e requisiti di .NET Core](../install/dependencies.md?tabs=netcore30&pivots=os-windows).

## <a name="framework-dependent-deployment"></a>Distribuzione dipendente dal framework

Una distribuzione dipendente dal framework senza dipendenze di terze parti richiede la compilazione, il testing e la pubblicazione dell'app. Il processo viene illustrato da un semplice esempio scritto in C#.

1. Creare il progetto.

   Selezionare **File** > **Nuovo** > **Progetto**. Nella finestra di dialogo **Nuovo progetto** espandere le categorie di progetti del linguaggio (C# o Visual Basic) nel riquadro dei tipi di progetti **Installati**, scegliere il modello **.NET Core** e selezionare il modello **Console App (.NET Core)** (App console (.NET Core)) nel riquadro centrale. Immettere un nome di progetto, ad esempio "FDD", nella casella di testo **Nome**. Selezionare il pulsante **OK** .

1. Aggiungere il codice sorgente dell'applicazione.

   Aprire il file *Program.cs* o *Program. vb* nell'editor e sostituire il codice generato automaticamente con il codice seguente. Questo codice richiede all'utente di immettere del testo e visualizza le singole parole immesse dall'utente. Usa l'espressione regolare `\w+` per separare le parole nel testo di input.

   [!code-csharp[deployment#1](~/samples/snippets/core/deploying/cs/deployment-example.cs)]
   [!code-vb[deployment#1](~/samples/snippets/core/deploying/vb/deployment-example.vb)]

1. Creare una build di debug dell'app.

   Selezionare **Compila** > **Compila soluzione**. È anche possibile compilare ed eseguire la build di debug dell'applicazione selezionando **Esegui debug** > **Avvia debug**.

1. Distribuire l'app.

   Dopo aver eseguito il debug e il test del programma, creare i file da distribuire con l'app. Per la pubblicazione da Visual Studio eseguire le operazioni seguenti:

      1. Modificare la configurazione della soluzione da **Debug** a **Release** sulla barra degli strumenti, per creare una versione di rilascio dell'app (invece di una versione di debug).

      1. Fare clic con il pulsante destro del mouse sul progetto (non sulla soluzione) in **Esplora soluzioni** e selezionare **Pubblica**.

      1. Nella scheda **Pubblica** selezionare **Pubblica**. I file che costituiscono l'applicazione vengono salvati nel file system locale.

      1. La scheda **Pubblica** ora visualizza un unico profilo **FolderProfile**. Le impostazioni di configurazione del profilo vengono visualizzate nella sezione **Riepilogo** della scheda.

   I file risultanti vengono inseriti in una directory di nome `Publish` in Windows e `publish` nei sistemi Unix, che è una sottodirectory della directory *.\bin\release\netcoreapp2.1* del progetto.

Insieme ai file dell'applicazione, il processo di pubblicazione genera un file del database di programma (con estensione pdb) che contiene le informazioni di debug relative all'app. Il file è utile soprattutto per il debug delle eccezioni. È possibile scegliere di non includerlo nel pacchetto dei file dell'applicazione. È tuttavia consigliabile salvarlo perché può risultare utile per il debug della build di rilascio dell'app.

Distribuire il set completo dei file dell'applicazione con il metodo desiderato. È ad esempio possibile inserire i file in un file zip, usare un semplice comando `copy` o distribuire i file con un pacchetto di installazione a scelta. Dopo aver completato l'installazione gli utenti possono eseguire l'applicazione usando il comando `dotnet` e fornendo il nome file dell'applicazione, ad esempio `dotnet fdd.dll`.

Oltre ai file binari dell'applicazione, il programma di installazione deve aggregare il programma di installazione framework condiviso oppure rilevarlo come prerequisito durante l'installazione dell'applicazione.  L'installazione del framework condiviso richiede l'accesso amministratore o alla radice perché è a livello di computer.

## <a name="framework-dependent-deployment-with-third-party-dependencies"></a>Distribuzione dipendente dal framework con dipendenze di terze parti

In una distribuzione dipendente dal framework con una o più dipendenze di terze parti, le dipendenze devono essere disponibili per il progetto. Prima della compilazione dell'app è necessario eseguire i passaggi aggiuntivi:

1. Usare **Gestione pacchetti NuGet** per aggiungere al progetto un riferimento a un pacchetto NuGet e per installare il pacchetto se non è già disponibile nel sistema. Per aprire lo strumento per la gestione dei pacchetti, selezionare **Strumenti** > **Gestione pacchetti NuGet** > **Gestisci pacchetti NuGet per la soluzione**.

1. Verificare che le dipendenze di terze parti, ad esempio `Newtonsoft.Json`, siano installate nel sistema e, in caso affermativo, installarle. La scheda **Installati** elenca i pacchetti NuGet installati nel sistema. Se `Newtonsoft.Json` non è presente nell'elenco, selezionare la scheda **Sfoglia** e immettere "Newtonsoft.Json" nella casella di ricerca. Selezionare `Newtonsoft.Json`, selezionare il progetto nel riquadro destro e quindi selezionare **Installa**.

1. Se `Newtonsoft.Json` è già installato nel sistema aggiungerlo al progetto selezionando il progetto stesso nel riquadro destro della scheda **Gestisci i pacchetti per la soluzione**.

Una distribuzione dipendente dal Framework con dipendenze di terze parti è portabile come dipendenze di terze parti. Se ad esempio una libreria di terze parti supporta solo macOS, l'app non è portabile in sistemi Windows. Questa situazione si verifica se la dipendenza di terze parti stessa dipende da codice nativo. Un buon esempio è il [server Kestrel](https://docs.microsoft.com/aspnet/core/fundamentals/servers/kestrel), che richiede una dipendenza nativa da [libuv](https://github.com/libuv/libuv). Quando viene creata una distribuzione dipendente dal framework per un'applicazione con questo tipo di dipendenze di terze parti, l'output pubblicato contiene una cartella per ogni [identificatore di runtime (RID)](../rid-catalog.md) supportato dalla dipendenza nativa (e presente nel relativo pacchetto NuGet).

## <a name="simpleSelf"></a> Distribuzione autonoma senza dipendenze di terze parti

La pubblicazione di una distribuzione autonoma senza dipendenze di terze parti comporta la creazione del progetto, la modifica del file *csproj*, la compilazione, il test e la pubblicazione dell'app. Il processo viene illustrato da un semplice esempio scritto in C#. Creare, codificare e testare inizialmente il progetto come nel caso di una distribuzione dipendente dal framework:

1. Creare il progetto.

   Selezionare **File** > **Nuovo** > **Progetto**. Nella finestra di dialogo **Nuovo progetto** espandere le categorie di progetti del linguaggio (C# o Visual Basic) nel riquadro dei tipi di progetti **Installati**, scegliere il modello **.NET Core** e selezionare il modello **Console App (.NET Core)** (App console (.NET Core)) nel riquadro centrale. Immettere un nome di progetto, ad esempio "SCD" nella casella di testo **Nome**, quindi selezionare il pulsante **OK**.

1. Aggiungere il codice sorgente dell'applicazione.

   Aprire il file *Program.cs* o *Program. vb* nell'editor e sostituire il codice generato automaticamente con il codice seguente. Questo codice richiede all'utente di immettere del testo e visualizza le singole parole immesse dall'utente. Usa l'espressione regolare `\w+` per separare le parole nel testo di input.

   [!code-csharp[deployment#1](~/samples/snippets/core/deploying/cs/deployment-example.cs)]
   [!code-vb[deployment#1](~/samples/snippets/core/deploying/vb/deployment-example.vb)]

1. Specificare se si intende usare la modalità invariante della globalizzazione.

   In particolare, se l'app è destinata a Linux, è possibile ridurre le dimensioni totali della distribuzione sfruttando la [modalità invariante della globalizzazione](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md). La modalità invariante della globalizzazione è utile per le applicazioni che non sono compatibili a livello globale e possono usare le convenzioni di formattazione, le convenzioni sulla combinazione di maiuscole e minuscole, il confronto tra stringhe e l'ordinamento delle [impostazioni cultura invarianti](xref:System.Globalization.CultureInfo.InvariantCulture).

   Per abilitare la modalità invariante fare clic con il pulsante destro del mouse sul progetto (non sulla soluzione) in **Esplora soluzioni** e selezionare **Modifica SCD.csproj** o **Modifica SCD.vbproj**. Aggiungere al file le seguenti righe evidenziate:

   [!code-xml[globalization-invariant-mode](~/samples/snippets/core/deploying/xml/invariant.csproj?highlight=6-8)]

1. Creare una build di debug dell'applicazione.

   Selezionare **Compila** > **Compila soluzione**. È anche possibile compilare ed eseguire la build di debug dell'applicazione selezionando **Esegui debug** > **Avvia debug**. Questo passaggio di debug consente di identificare i problemi dell'applicazione quando è in esecuzione sulla piattaforma host. È tuttavia necessario testarla sulle singole piattaforme di destinazione.

   Se è stata abilitata la modalità invariante della globalizzazione, verificare soprattutto se l'assenza di dati dipendenti dalle impostazioni cultura sia adatta per l'applicazione.

Dopo aver terminato il debug, è possibile pubblicare la distribuzione autonoma:

<!-- markdownlint-disable MD025 -->

# <a name="visual-studio-156-and-earliertabvs156"></a>[Visual Studio 15.6 e versioni precedenti](#tab/vs156)

Dopo aver eseguito il debug e il test del programma creare i file da distribuire con l'app per ogni piattaforma di destinazione.

Per pubblicare l'app da Visual Studio eseguire le operazioni seguenti:

1. Definire le piattaforme di destinazione per l'app.

   1. Fare clic con il pulsante destro del mouse sul progetto (non sulla soluzione) in **Esplora soluzioni** e selezionare **Modifica SCD.csproj**.

   1. Creare un tag `<RuntimeIdentifiers>` nella sezione `<PropertyGroup>` del file *csproj* che definisce le piattaforme di destinazione dell'app e specifica l'identificatore di runtime di ogni piattaforma di destinazione. È anche necessario aggiungere un punto e virgola per separare il RID. Per un elenco degli identificatori di runtime, vedere [Runtime IDentifier catalog](../rid-catalog.md) (Catalogo degli identificatori di runtime).

   L'esempio seguente indica che l'app viene eseguita in sistemi operativi Windows 10 a 64 bit e nel sistema operativo OS X versione 10.11 a 64 bit.

   ```xml
   <PropertyGroup>
      <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
   </PropertyGroup>
   ```

   L'elemento `<RuntimeIdentifiers>` può entrare in qualsiasi `<PropertyGroup>` presente nel file *csproj* . Un file di esempio *csproj* completo è disponibile più avanti in questa sezione.

1. Pubblicare l'app.

   Dopo aver eseguito il debug e il test del programma creare i file da distribuire con l'app per ogni piattaforma di destinazione.

   Per pubblicare l'app da Visual Studio eseguire le operazioni seguenti:

      1. Modificare la configurazione della soluzione da **Debug** a **Release** sulla barra degli strumenti, per creare una versione di rilascio dell'app (invece di una versione di debug).

      1. Fare clic con il pulsante destro del mouse sul progetto (non sulla soluzione) in **Esplora soluzioni** e selezionare **Pubblica**.

      1. Nella scheda **Pubblica** selezionare **Pubblica**. I file che costituiscono l'applicazione vengono salvati nel file system locale.

      1. La scheda **Pubblica** ora visualizza un unico profilo **FolderProfile**. Le impostazioni di configurazione del profilo sono mostrate nella sezione **Riepilogo** della scheda. il **runtime di destinazione** identifica il runtime pubblicato e il **percorso di destinazione** identifica la posizione in cui sono stati scritti i file per la distribuzione autonoma.

      1. Per impostazione predefinita tutti i file pubblicati vengono salvati in una singola directory. Per praticità è consigliabile creare un profilo separato per ogni runtime di destinazione e inserire i file pubblicati in una directory specifica per la piattaforma. Questo richiede la creazione di un profilo di pubblicazione separato per ogni piattaforma di destinazione. A questo punto ricompilare l'applicazione per ogni piattaforma procedendo nel modo seguente:

         1. Selezionare **Crea nuovo profilo** nella finestra di dialogo **Pubblica**.

         1. Nella finestra di dialogo **Selezionare una destinazione di pubblicazione**, in **Scegliere una cartella** impostare il percorso su *bin\Release\PublishOutput\win10-x64*. Scegliere **OK**.

         1. Selezionare il nuovo profilo (**FolderProfile1**) nell'elenco dei profili e assicurarsi che **Runtime di destinazione** sia `win10-x64`. In caso contrario, selezionare **Impostazioni**. Nella finestra di dialogo **Impostazioni profilo** impostare **Runtime di destinazione** su `win10-x64` e selezionare **Salva**. In alternativa selezionare **Annulla**.

         1. Selezionare **Pubblica** per pubblicare l'app per le piattaforme Windows 10 a 64 bit.

         1. Eseguire nuovamente la procedura per creare un profilo per la piattaforma `osx.10.11-x64`. Il valore di **Percorso di destinazione** deve essere *bin\Release\PublishOutput\osx.10.11-x64* e **Runtime di destinazione** deve essere `osx.10.11-x64`. Il nome assegnato a questo profilo in Visual Studio è **FolderProfile2**.

      Ogni percorso di destinazione contiene il set completo di file (i file dell'app e tutti i file di .NET Core) necessari per avviare l'app.

Insieme ai file dell'applicazione, il processo di pubblicazione genera un file del database di programma (con estensione pdb) che contiene le informazioni di debug relative all'app. Il file è utile soprattutto per il debug delle eccezioni. È possibile scegliere di non includerlo nel pacchetto dei file dell'applicazione. È tuttavia consigliabile salvarlo perché può risultare utile per il debug della build di rilascio dell'app.

Distribuire i file pubblicati con il metodo desiderato. È ad esempio possibile inserire i file in un file zip, usare un semplice comando `copy` o distribuire i file con un pacchetto di installazione a scelta.

Di seguito è riportato il file *csproj* completo per questo progetto.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
</Project>
```

# <a name="visual-studio-157-and-latertabvs157"></a>[Visual Studio 15.7 e versioni successive](#tab/vs157)

Dopo aver eseguito il debug e il test del programma creare i file da distribuire con l'app per ogni piattaforma di destinazione. Questo richiede la creazione di un profilo separato per ogni piattaforma di destinazione.

Eseguire le operazioni seguenti per ogni piattaforma a cui è destinata l'applicazione:

1. Creare un profilo per la piattaforma di destinazione.

   Se si tratta del primo profilo creato, fare clic con il pulsante destro del mouse sul progetto (non sulla soluzione) in **Esplora soluzioni** e selezionare **Pubblica**.

   Se è già stato creato un profilo, fare clic con il pulsante destro del mouse sul progetto per aprire la finestra di dialogo **Pubblica** se non è già aperta. Selezionare quindi **Nuovo profilo**.

   Viene visualizzata la finestra di dialogo **Selezionare una destinazione di pubblicazione**.

1. Selezionare la posizione in cui Visual Studio pubblica l'applicazione.

   Se si esegue la pubblicazione in una sola piattaforma, è possibile accettare il valore predefinito nella casella di testo **scegliere una cartella** . in questo modo viene pubblicata la distribuzione dipendente dal framework dell'applicazione nella directory *\<Project-directory > \bin\Release\netcoreapp2.1\publish* .

   Se esegue la pubblicazione in più di una piattaforma, aggiungere una stringa che identifica la piattaforma di destinazione. Se ad esempio si aggiunge la stringa "Linux" al percorso del file, Visual Studio pubblica la distribuzione dipendente dal framework dell'applicazione nella directory *\<Project-directory > \bin\Release\netcoreapp2.1\publish\linux* .

1. Creare il profilo selezionando l'icona dell'elenco a discesa accanto al pulsante **Pubblica** e selezionando **Crea profilo**. Selezionare il pulsante **Crea profilo** per creare il profilo.

1. Specificare che si sta pubblicando una distribuzione autonoma e definire una piattaforma di destinazione per l'app.

   1. Nella finestra di dialogo **Pubblica** selezionare il collegamento **Configura** per aprire la finestra di dialogo **Impostazioni profilo**.

   1. Selezionare **Indipendente** nella casella di riepilogo **Modalità di distribuzione**.

   1. Nella casella di riepilogo **Runtime di destinazione** selezionare una delle piattaforme di destinazione dell'applicazione.

   1. Selezionare **Salva** per salvare le modifiche e chiudere la finestra di dialogo.

1. Assegnare un nome al profilo.

   1. Selezionare **Azioni** > **Rinomina profilo** per assegnare un nome al profilo.

   2. Assegnare al profilo un nome che identifica la piattaforma di destinazione e quindi selezionare **Salva*.

Ripetere questi passaggi per definire eventuali piattaforme di destinazione dell'applicazione.

I profili sono stati configurati e ora si è pronti per pubblicare l'applicazione. Per eseguire questa operazione:

   1. Se la finestra **Pubblica** non è attualmente aperta, fare clic con il pulsante destro del mouse sul progetto (non sulla soluzione) in **Esplora soluzioni** e selezionare **Pubblica**.

   2. Selezionare il profilo che si intende pubblicare e selezionare **Pubblica**. Eseguire questa operazione per ogni profilo da pubblicare.

   Ogni percorso di destinazione (nel caso dell'esempio, bin\release\netcoreapp2.1\publish\\*profile-name* contiene il set completo di file (i file dell'app e tutti i file di .NET Core) necessari per avviare l'app.

Insieme ai file dell'applicazione, il processo di pubblicazione genera un file del database di programma (con estensione pdb) che contiene le informazioni di debug relative all'app. Il file è utile soprattutto per il debug delle eccezioni. È possibile scegliere di non includerlo nel pacchetto dei file dell'applicazione. È tuttavia consigliabile salvarlo perché può risultare utile per il debug della build di rilascio dell'app.

Distribuire i file pubblicati con il metodo desiderato. È ad esempio possibile inserire i file in un file zip, usare un semplice comando `copy` o distribuire i file con un pacchetto di installazione a scelta.

Di seguito è riportato il file *csproj* completo per questo progetto.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
  </PropertyGroup>
</Project>
```

Visual Studio crea anche un profilo di pubblicazione separato (\*.pubxml) per ogni piattaforma di destinazione. Ad esempio, il file per il profilo di linux (linux.pubxml) viene visualizzato come segue:

```xml
<?xml version="1.0" encoding="utf-8"?>
<!--
https://go.microsoft.com/fwlink/?LinkID=208121.
-->
<Project ToolsVersion="4.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <PropertyGroup>
    <PublishProtocol>FileSystem</PublishProtocol>
    <Configuration>Release</Configuration>
    <Platform>Any CPU</Platform>
    <TargetFramework>netcoreapp2.1</TargetFramework>
    <PublishDir>bin\Release\netcoreapp2.1\publish\linux</PublishDir>
    <RuntimeIdentifier>win-x86</RuntimeIdentifier>
    <SelfContained>true</SelfContained>
    <_IsPortable>false</_IsPortable>
  </PropertyGroup>
</Project>
```

---

## <a name="self-contained-deployment-with-third-party-dependencies"></a>Distribuzione autonoma con dipendenze di terze parti

Una distribuzione autonoma con una o più dipendenze di terze parti comporta l'aggiunta delle dipendenze. Prima della compilazione dell'app è necessario eseguire i passaggi aggiuntivi:

1. Usare **Gestione pacchetti NuGet** per aggiungere al progetto un riferimento a un pacchetto NuGet e per installare il pacchetto se non è già disponibile nel sistema. Per aprire lo strumento per la gestione dei pacchetti, selezionare **Strumenti** > **Gestione pacchetti NuGet** > **Gestisci pacchetti NuGet per la soluzione**.

1. Verificare che le dipendenze di terze parti, ad esempio `Newtonsoft.Json`, siano installate nel sistema e, in caso affermativo, installarle. La scheda **Installati** elenca i pacchetti NuGet installati nel sistema. Se `Newtonsoft.Json` non è presente nell'elenco, selezionare la scheda **Sfoglia** e immettere "Newtonsoft.Json" nella casella di ricerca. Selezionare `Newtonsoft.Json`, selezionare il progetto nel riquadro destro e quindi selezionare **Installa**.

1. Se `Newtonsoft.Json` è già installato nel sistema aggiungerlo al progetto selezionando il progetto stesso nel riquadro destro della scheda **Gestisci i pacchetti per la soluzione**.

Di seguito è riportato il file *csproj* completo per questo progetto:

# <a name="visual-studio-156-and-earliertabvs156"></a>[Visual Studio 15.6 e versioni precedenti](#tab/vs156)

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
  </ItemGroup>
</Project>
```

# <a name="visual-studio-157-and-latertabvs157"></a>[Visual Studio 15.7 e versioni successive](#tab/vs157)

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
  </ItemGroup>
</Project>
```

---

Quando si distribuisce l'applicazione, anche le dipendenze di terze parti usate nell'app sono contenute nei file dell'applicazione. Non è necessario che le librerie di terze parti siano già presenti nel sistema in cui viene eseguita l'app.

È possibile distribuire una distribuzione autonoma solo con una libreria di terze parti alle piattaforme supportate da tale libreria. Il caso è simile alla presenza di dipendenze di terze parti con dipendenze native in una distribuzione dipendente dal framework: le dipendenze native esistono nella piattaforma di destinazione solo se sono state installate in precedenza in tale piattaforma.

## <a name="see-also"></a>Vedere anche

- [Distribuzione di applicazioni .NET Core](index.md)
- [Catalogo dei RID (Runtime IDentifier) di .NET Core](../rid-catalog.md)
