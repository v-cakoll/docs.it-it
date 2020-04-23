---
title: Migrazione di app WPF a .NET Core 3,0
description: Informazioni su come eseguire la migrazione di un'app Windows Presentation Foundation (WPF) a .NET Core 3,0.
author: mjrousos
ms.date: 09/12/2019
ms.author: mikerou
ms.openlocfilehash: f52005e7c8a6312b8c4e09a950f1f635af1894e4
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "82071311"
---
# <a name="migrating-wpf-apps-to-net-core"></a>Migrazione di app WPF a .NET Core

Questo articolo illustra i passaggi necessari per eseguire la migrazione di un'app Windows Presentation Foundation (WPF) da .NET Framework a .NET Core 3,0. Se non si ha un'app WPF a disposizione per la porta, ma si vuole provare il processo, è possibile usare l'app **Bean trader** di esempio disponibile in [GitHub](https://github.com/dotnet/windows-desktop/tree/master/Samples/BeanTrader). L'app originale (destinazione .NET Framework 4.7.2) è disponibile nella cartella NetFx\BeanTraderClient. Prima di tutto verranno illustrati i passaggi necessari per la portabilità delle app in generale e verranno illustrate le modifiche specifiche che si applicano all'esempio **Bean trader** .

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

Per eseguire la migrazione a .NET Core, è prima di tutto necessario:

01. Comprendere e aggiornare le dipendenze NuGet:

    01. Aggiornare le dipendenze NuGet per `<PackageReference>` usare il formato.
    01. Esaminare le dipendenze NuGet di primo livello per la compatibilità con .NET Core o .NET Standard.
    01. Aggiornare i pacchetti NuGet a versioni più recenti.
    01. Usare [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) per comprendere le dipendenze di .NET.

01. Migrare il file di progetto nel nuovo formato di tipo SDK:

    01. Scegliere se destinare sia a .NET Core sia a .NET Framework o solo a .NET Core.
    01. Copiare gli elementi e le proprietà del file di progetto pertinenti nel nuovo file di progetto.

01. Risolvere i problemi di compilazione:

    01. Aggiungere un riferimento al pacchetto [Microsoft. Windows. Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility/) .
    01. Trovare e correggere le differenze a livello di API.
    01. Rimuovere le sezioni di *app. config* `appSettings` diverse `connectionStrings`da o.
    01. Rigenerare il codice generato, se necessario.

01. Test di runtime:

    01. Verificare che l'app portata funzioni come previsto.
    01. Prestare attenzione <xref:System.NotSupportedException> alle eccezioni.

## <a name="about-the-sample"></a>Informazioni sull'esempio

Questo articolo fa riferimento all' [app Bean trader di esempio](https://github.com/dotnet/windows-desktop/tree/master/Samples/BeanTrader) perché usa un'ampia gamma di dipendenze simili a quelle che possono avere le app WPF reali. L'app non è di grandi dimensioni, ma è concepita come un passaggio da "Hello World" in termini di complessità. L'app illustra alcuni problemi che possono verificarsi durante il trasferimento di app reali. L'app comunica con un servizio WCF, in modo che venga eseguita correttamente, sarà anche necessario eseguire il progetto BeanTraderServer (disponibile nello stesso repository GitHub) e assicurarsi che la configurazione di BeanTraderClient punti all'endpoint corretto. Per impostazione predefinita, nell'esempio si presuppone che il server sia in esecuzione nello stesso *http://localhost:8090*computer in, che sarà true se si avvia BeanTraderServer localmente.

Tenere presente che questa applicazione di esempio ha lo scopo di illustrare le soluzioni e le soluzioni di porting di .NET Core. Non è progettato per illustrare le procedure consigliate per WPF. In realtà, include deliberatamente alcuni anti-modelli per assicurarsi di affrontare almeno un paio di problemi interessanti durante il trasferimento.

## <a name="getting-ready"></a>Preparazione

Il problema principale della migrazione di un'app .NET Framework a .NET Core è che le dipendenze possono funzionare in modo diverso o non. La migrazione è molto più semplice rispetto a quella usata. molti pacchetti NuGet ora hanno come destinazione .NET Standard. A partire da .NET Core 2,0, le aree di superficie .NET Framework e .NET Core sono diventate simili. Anche in questo caso, vengono mantenute alcune differenze (sia per il supporto dei pacchetti NuGet che nelle API .NET disponibili). Il primo passaggio della migrazione consiste nel rivedere le dipendenze dell'app e verificare che i riferimenti siano in un formato facilmente migrabile a .NET Core.

### <a name="upgrade-to-packagereference-nuget-references"></a>Aggiornare i `<PackageReference>` riferimenti a NuGet

I progetti di .NET Framework precedenti in genere elencano le dipendenze NuGet in un file *packages. config* . Il nuovo formato di file di progetto in stile SDK fa riferimento [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) ai pacchetti NuGet come elementi nel file csproj, anziché in un file di configurazione separato.

Quando si esegue la migrazione, sono disponibili due `<PackageReference>`vantaggi per l'uso di riferimenti in stile:

- Questo è lo stile del riferimento NuGet necessario per il nuovo file di progetto .NET Core. Se si usa `<PackageReference>`già, gli elementi del file di progetto possono essere copiati e incollati direttamente nel nuovo progetto.
- A differenza di un file Packages. `<PackageReference>` config, gli elementi fanno riferimento solo alle dipendenze di livello superiore da cui il progetto dipende direttamente. Tutti gli altri pacchetti NuGet transitivi verranno determinati in fase di ripristino e registrati nel file obj\project.assets.JSON generato automaticamente. In questo modo è molto più semplice determinare le dipendenze del progetto, che risulta utile quando si determina se le dipendenze necessarie funzioneranno o meno in .NET Core.

Il primo passaggio per eseguire la migrazione di un'app .NET Framework a .NET Core consiste nell'aggiornarlo per l'uso `<PackageReference>` dei riferimenti NuGet. Visual Studio rende questa operazione semplice. È sufficiente fare clic con il pulsante destro del mouse sul file *packages. config* del progetto in **Esplora soluzioni**di Visual Studio, quindi selezionare **Esegui la migrazione di Packages. config a PackageReference**.

![Aggiornamento a PackageReference](./media/convert-project-from-net-framework/package-reference-migration.png)

Viene visualizzata una finestra di dialogo che mostra le dipendenze NuGet di primo livello calcolate e chiede quali altri pacchetti NuGet devono essere promossi a livello superiore. Nessuno di questi altri pacchetti deve essere di primo livello per l'esempio Bean trader, quindi è possibile deselezionare tutte le caselle. Quindi, fare clic su **OK** e il file *packages. config* verrà rimosso e `<PackageReference>` gli elementi verranno aggiunti al file di progetto.

`<PackageReference>`i riferimenti di tipo non archiviano i pacchetti NuGet localmente in una cartella di pacchetti. Sono invece archiviati globalmente come ottimizzazione. Al termine della migrazione, modificare il file csproj e rimuovere tutti `<Analyzer>` gli elementi che fanno riferimento agli analizzatori che in precedenza provengono da *.. Directory \Packages* . Nessun problema; Poiché sono ancora presenti i riferimenti ai pacchetti NuGet, gli analizzatori verranno inclusi nel progetto. È sufficiente pulire i vecchi elementi di tipo `<Analyzer>` Packages. config.

### <a name="review-nuget-packages"></a>Esaminare i pacchetti NuGet

Ora che è possibile visualizzare i pacchetti NuGet di primo livello da cui dipende il progetto, è possibile verificare se tali pacchetti sono disponibili in .NET Core. È possibile determinare se un pacchetto supporta .NET Core osservando le relative dipendenze in [NuGet.org](https://www.nuget.org/). Il sito [fuget.org](https://www.fuget.org/) creato dalla community Mostra queste informazioni in primo piano nella parte superiore della pagina delle informazioni sul pacchetto.

Quando la destinazione è .NET Core 3,0, tutti i pacchetti destinati a .NET Core o .NET Standard dovrebbero funzionare (poiché .NET Core implementa la superficie di attacco .NET Standard). In alcuni casi, la versione specifica di un pacchetto usato non sarà destinata a .NET Core o .NET Standard, ma saranno disponibili versioni più recenti. In questo caso, è consigliabile eseguire l'aggiornamento alla versione più recente del pacchetto.

È anche possibile usare i pacchetti destinati a .NET Framework, ma ciò comporta un certo rischio. Sono consentite le dipendenze di .NET Core per .NET Framework perché .NET Core e .NET Framework aree di attacco sono sufficientemente simili che *spesso* tali dipendenze funzionano. Tuttavia, se il pacchetto tenta di usare un'API .NET che non è presente in .NET Core, si verificherà un'eccezione di Runtime. Per questo motivo, è consigliabile fare riferimento ai pacchetti .NET Framework solo quando non sono disponibili altre opzioni e comprendere che questa operazione impone un carico di test.

Se sono presenti pacchetti a cui si fa riferimento che non sono destinati a .NET Core o .NET Standard, è necessario considerare altre alternative:

- Sono presenti altri pacchetti simili che è possibile usare in alternativa? Talvolta gli autori NuGet pubblicano un separatore. Versioni di base delle librerie destinate specificamente a .NET Core. I pacchetti della libreria Enterprise sono un esempio della pubblicazione della community ". NetCore "alternative. In altri casi, gli SDK più recenti per un servizio specifico (talvolta con nomi di pacchetto diversi) sono disponibili per .NET Standard. Se non sono disponibili alternative, è possibile continuare a usare i pacchetti di destinazione .NET Framework, tenendo presente che è necessario testarli accuratamente una volta in esecuzione in .NET Core.

L'esempio Bean trader presenta le seguenti dipendenze NuGet di primo livello:

- [**Castle. Windsor, versione 4.1.1**](https://www.castleproject.org/projects/windsor/)  

  Questo pacchetto è destinato a .NET Standard 1,6, quindi funziona in .NET Core.

- [**Microsoft. CodeAnalysis. FxCopAnalyzers, versione 2.6.3**](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers/2.6.3)  
  Si tratta di un metapacchetto, quindi non è immediatamente ovvio quali sono le piattaforme supportate, ma la [documentazione](https://github.com/dotnet/roslyn-analyzers#microsoftcodeanalysisfxcopanalyzers) indica che la versione più recente (2.9.2) funzionerà sia per .NET Framework sia per .NET Core.

- [**Nito. AsyncEx, versione 4.0.1**](https://www.nuget.org/packages/Nito.AsyncEx/4.0.1)  

  Questo pacchetto non è destinato a .NET Core, ma è la versione più recente di 5,0. Si tratta di un'operazione comune durante la migrazione perché molti pacchetti NuGet hanno aggiunto .NET Standard supporto di recente, ma le versioni precedenti del progetto avranno come destinazione solo .NET Framework. Se la differenza di versione è solo una differenza di versione secondaria, spesso è facile eseguire l'aggiornamento alla versione più recente. Poiché si tratta di una modifica di versione principale, è necessario eseguire un aggiornamento prudente poiché potrebbero verificarsi modifiche di rilievo nel pacchetto. Tuttavia, esiste un percorso positivo.

- [**MahApps. metro, versione 1.6.5**](https://www.nuget.org/packages/MahApps.Metro/1.6.5)  

  Anche questo pacchetto non è destinato a .NET Core, ma dispone di una versione non definitiva più recente (2,0-Alpha). Anche in questo caso, è necessario esaminare le modifiche di rilievo, ma il pacchetto più recente è incoraggiante.

Le dipendenze NuGet dell'esempio Bean trader sono tutte destinate .NET Standard/. NET Core o hanno versioni più recenti, quindi è improbabile che si verifichino problemi di blocco.

### <a name="upgrade-nuget-packages"></a>Aggiornare i pacchetti NuGet

Se possibile, è consigliabile aggiornare le versioni di tutti i pacchetti che hanno come destinazione solo .NET Core o .NET Standard con versioni più recenti in questa fase (con il progetto ancora destinato .NET Framework) per individuare e risolvere le modifiche di rilievo in anticipo.

Se non si apportano modifiche sostanziali alla versione .NET Framework esistente dell'app, questo può attendere fino a quando non si dispone di un nuovo file di progetto destinato a .NET Core. Tuttavia, l'aggiornamento dei pacchetti NuGet a versioni compatibili con .NET Core in anticipo rende ancora più semplice il processo di migrazione dopo aver creato il nuovo file di progetto e ridotto il numero di differenze tra le versioni .NET Framework e .NET Core dell'app.

Con l'esempio Bean trader, tutti gli aggiornamenti necessari possono essere resi facilmente (usando Gestione pacchetti NuGet di Visual Studio) con un'unica eccezione: l'aggiornamento da **MahApps. metro 1.6.5** a **2,0** rivela modifiche di rilievo correlate alle API di gestione dei temi e degli accenti.

Idealmente, l'app verrà aggiornata in modo da usare la versione più recente del pacchetto (poiché è più probabile che funzioni in .NET Core). In alcuni casi, tuttavia, potrebbe non essere fattibile. In questi casi, non aggiornare **MahApps. metro** perché le modifiche necessarie sono non semplici e questa esercitazione è incentrata sulla migrazione a .NET Core 3, non a **MahApps. metro 2.** Si tratta anche di una dipendenza a basso rischio .NET Framework perché l'app Bean trader esercita solo una piccola parte di **MahApps. metro**. Naturalmente, sarà necessario eseguire test per verificare che tutti gli elementi funzionino al termine della migrazione. Se si trattasse di uno scenario reale, sarebbe opportuno archiviare un problema per tenere traccia del lavoro per passare a **MahApps. metro** versione 2,0, perché la migrazione non è ora in ritardo con un debito tecnico.

Una volta aggiornati i pacchetti NuGet con le versioni recenti, `<PackageReference>` il gruppo di elementi nel file di progetto Bean trader sample dovrebbe essere simile al seguente.

```xml
<ItemGroup>
  <PackageReference Include="Castle.Windsor">
    <Version>4.1.1</Version>
  </PackageReference>
  <PackageReference Include="MahApps.Metro">
    <Version>1.6.5</Version>
  </PackageReference>
  <PackageReference Include="Microsoft.CodeAnalysis.FxCopAnalyzers">
    <Version>2.9.2</Version>
  </PackageReference>
  <PackageReference Include="Nito.AsyncEx">
    <Version>5.0.0</Version>
  </PackageReference>
</ItemGroup>
```

### <a name="net-framework-portability-analysis"></a>Analisi della portabilità .NET Framework

Quando si comprende lo stato delle dipendenze NuGet del progetto, l'elemento successivo da considerare è .NET Framework le dipendenze dell'API. Lo strumento [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) è utile per comprendere quali API .NET il progetto utilizza sono disponibili su altre piattaforme .NET.

Lo strumento è un plug-in di [Visual Studio](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer), uno [strumento da riga di comando](https://github.com/Microsoft/dotnet-apiport/releases)o incluso in una [semplice GUI](https://github.com/Microsoft/dotnet-apiport-ui), che semplifica le opzioni. Per altre informazioni sull'uso di .NET Portability Analyzer (porta API), vedere il post di Blog relativo al [porting di applicazioni desktop per .NET Core](https://devblogs.microsoft.com/dotnet/porting-desktop-apps-to-net-core/) . Se si preferisce usare la riga di comando, i passaggi necessari sono i seguenti:

1. Scaricare [.NET Portability Analyzer](https://github.com/Microsoft/dotnet-apiport/releases) , se non è già presente.
1. Assicurarsi che l'app .NET Framework venga compilata correttamente. Questa è una valida idea prima della migrazione indipendentemente dal fatto.
1. Eseguire la porta API con una riga di comando simile alla seguente.

    ```console
    ApiPort.exe analyze -f <PathToBeanTraderBinaries> -r html -r excel -t ".NET Core"
    ```

    L' `-f` argomento specifica il percorso contenente i binari da analizzare. L' `-r` argomento specifica il formato del file di output desiderato. L' `-t` argomento specifica la piattaforma .NET in base a cui analizzare l'utilizzo dell'API. In questo caso, si vuole usare .NET Core.

Quando si apre il report HTML, nella prima sezione vengono elencati tutti i file binari analizzati e la percentuale delle API .NET che usano sono disponibili nella piattaforma di destinazione. La percentuale non è significativa da sola. Ciò che è più utile è vedere le API specifiche mancanti. A tale scopo, selezionare un nome di assembly o scorrere verso il basso fino ai rapporti per singoli assembly.

Concentrarsi sugli assembly per i quali si è proprietari del codice sorgente. Nel report Bean trader ApiPort, ad esempio, sono elencati molti file binari, ma la maggior parte di essi appartengono a pacchetti NuGet. `Castle.Windsor`Mostra che dipende da alcune API System. Web mancanti in .NET Core. Questo non è un problema perché in precedenza è `Castle.Windsor` stato verificato che supporta .NET Core. È comune che i pacchetti NuGet dispongano di binari diversi per l'uso con diverse piattaforme .NET, quindi se la versione `Castle.Windsor` .NET Framework di USA API System. Web o meno, è irrilevante, purché il pacchetto sia destinato anche .NET standard o .NET Core (operazione eseguita).

Con l'esempio Bean trader, l'unico file binario che è necessario prendere in considerazione è **BeanTraderClient** e il report mostra che mancano solo due API `System.ServiceModel.ClientBase<T>.Close` .NET `System.ServiceModel.ClientBase<T>.Open`: e.

![Report sulla portabilità di BeanTraderClient](./media/convert-project-from-net-framework/portability-report.png)

È improbabile che si verifichino problemi di blocco perché le API client WCF sono (per lo più) supportate in .NET Core, quindi è necessario che siano disponibili alternative per queste API centrali. In realtà, osservando `System.ServiceModel`la superficie di attacco di .NET Core <https://apisof.net>(usando), si noterà che in .NET Core sono disponibili alternative asincrone.

In base a questo report e all'analisi delle dipendenze NuGet precedente, sembra che non siano presenti problemi principali per la migrazione dell'esempio Bean trader a .NET Core. Si è pronti per il passaggio successivo in cui verrà avviata la migrazione.

## <a name="migrating-the-project-file"></a>Migrazione del file di progetto

Se l'app non usa il nuovo [formato di file di progetto in stile SDK](../../core/tools/csproj.md), sarà necessario un nuovo file di progetto per la destinazione di .NET Core. È possibile sostituire il file csproj esistente o, se si preferisce che il progetto esistente rimanga intatto nello stato corrente, è possibile aggiungere un nuovo file csproj destinato a .NET Core. È possibile compilare versioni dell'app per .NET Framework e .NET Core con un singolo file di progetto in stile SDK con [multi-targeting](../../standard/library-guidance/cross-platform-targeting.md) (specificando `<TargetFrameworks>` più destinazioni).

Per creare il nuovo file di progetto, è possibile creare un nuovo progetto WPF in Visual Studio o usare `dotnet new wpf` il comando in una directory temporanea per generare il file di progetto e quindi copiarlo o rinominarlo nella posizione corretta. È disponibile anche uno strumento creato dalla community, [CsprojToVs2017](https://github.com/hvanbakel/CsprojToVs2017), che consente di automatizzare parte della migrazione dei file di progetto. Lo strumento è utile, ma necessita ancora di un uomo per esaminare i risultati per assicurarsi che tutti i dettagli della migrazione siano corretti. Una particolare area che lo strumento non gestisce in modo ottimale è la migrazione dei pacchetti NuGet dai file *packages. config* . Se lo strumento viene eseguito in un file di progetto che usa ancora un file *packages. config* per fare riferimento ai pacchetti NuGet `<PackageReference>` , eseguirà automaticamente la migrazione `<PackageReference>` agli elementi, ma aggiungerà elementi per *tutti* i pacchetti anziché solo quelli di primo livello. Se è già stata eseguita la migrazione`<PackageReference>` a elementi con Visual Studio (come è stato fatto in questo esempio), lo strumento può essere utile per il resto della conversione. Come Scott Hanselr consiglia nel [suo post di Blog sulla migrazione dei file csproj](https://www.hanselman.com/blog/UpgradingAnExistingNETProjectFilesToTheLeanNewCSPROJFormatFromNETCore.aspx), il porting manuale è educativo e fornisce risultati migliori se si dispone solo di alcuni progetti da trasferire. Tuttavia, se si esegue il porting di dozzine o centinaia di file di progetto, uno strumento come [CsprojToVs2017] può essere una guida.

Per creare un nuovo file di progetto per l'esempio Bean trader, `dotnet new wpf` eseguire in una directory temporanea e spostare il file con *estensione csproj* generato nella cartella *BeanTraderClient* e rinominarlo **BeanTraderClient. Core. csproj**.

Poiché il nuovo formato del file di progetto include automaticamente i file C#, i file *resx* e i file XAML che trova in o sotto la relativa directory, il file di progetto è già quasi completo. Per completare la migrazione, aprire i file di progetto vecchi e nuovi side-by-side ed esaminare quello precedente per verificare se è necessario eseguire la migrazione di tutte le informazioni in esso contenute. Nel caso di esempio Bean trader, gli elementi seguenti devono essere copiati nel nuovo progetto:

- Tutte `<RootNamespace>`le `<AssemblyName>`proprietà, `<ApplicationIcon>` e devono essere copiate.

- È anche necessario aggiungere una `<GenerateAssemblyInfo>false</GenerateAssemblyInfo>` proprietà al nuovo file di progetto perché l'esempio Bean trader include attributi a livello di assembly (ad `[AssemblyTitle]`esempio) in un file AssemblyInfo.cs. Per impostazione predefinita, i nuovi progetti in stile SDK genereranno automaticamente questi attributi in base alle proprietà nel file csproj. Poiché non si vuole che questo avvenga in questo caso (gli attributi generati automaticamente sono in conflitto con quelli di AssemblyInfo.cs), si disabilitano gli attributi generati `<GenerateAssemblyInfo>`automaticamente con.

- Sebbene i file *resx* vengano automaticamente inclusi come risorse incorporate `<Resource>` , non sono presenti altri elementi come le immagini. Copiare quindi gli `<Resource>` elementi per incorporare i file di immagine e icona. È possibile semplificare i riferimenti png a una singola riga usando il nuovo supporto del formato di file di progetto per i modelli `<Resource Include="**\*.png" />`glob:.

- Analogamente `<None>` , gli elementi vengono inclusi automaticamente, ma non vengono copiati nella directory di output per impostazione predefinita. Poiché il progetto Bean trader include un `<None>` elemento che *viene* copiato nella directory di output (usando `PreserveNewest` i comportamenti), è necessario aggiornare l'elemento popolato `<None>` automaticamente per il file, come indicato di seguito.

  ```xml
  <None Update="BeanTrader.pfx">
    <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>
  </None>
  ```

- L'esempio Bean trader include un file XAML (default. Accent. Xaml) come `Content` (anziché come `Page`) perché i temi e gli accenti definiti in questo file vengono caricati dal codice XAML del file in fase di esecuzione, anziché incorporarli nell'app stessa. Tuttavia, il nuovo sistema di progetto include automaticamente questo `<Page>`file, poiché si tratta di un file XAML. Quindi, è necessario rimuovere il file XAML come pagina (`<Page Remove="**\Default.Accent.xaml" />`) e aggiungerlo come contenuto.

  ```xml
  <Content Include="Resources\Themes\Default.Accent.xaml">
      <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>
  </Content>
  ```

- Infine, aggiungere i `<ItemGroup>` riferimenti NuGet copiando con tutti gli `<PackageReference>` elementi. Se in precedenza non sono stati aggiornati i pacchetti NuGet alle versioni compatibili con .NET Core, è possibile farlo ora che i riferimenti al pacchetto si trovano in un progetto specifico di .NET Core.

A questo punto, dovrebbe essere possibile aggiungere il nuovo progetto alla soluzione BeanTrader e aprirlo in Visual Studio. Il progetto dovrebbe essere corretto in **Esplora soluzioni**e `dotnet restore BeanTraderClient.Core.csproj` dovrebbe ripristinare correttamente i pacchetti (con due avvisi previsti correlati alla versione di MahApps. metro che si sta usando come destinazione .NET Framework).

Sebbene sia possibile conservare entrambi i file di progetto side-by-Side (e potrebbe essere anche auspicabile se si vuole creare il progetto precedente esattamente com'era), questo complica il processo di migrazione (i due progetti proveranno a usare le stesse cartelle bin e obj) e in genere non sono necessari. Se si vuole compilare per le destinazioni .NET Core e .NET Framework, è possibile sostituire la `<TargetFramework>netcoreapp3.0</TargetFramework>` proprietà nel nuovo file di progetto con. `<TargetFrameworks>netcoreapp3.0;net472</TargetFrameworks>` Per l'esempio Bean trader, eliminare il vecchio file di progetto (BeanTraderClient. csproj) perché non è più necessario. Se si preferisce tenere entrambi i file di progetto, assicurarsi di fare in modo che vengano compilati in diversi percorsi di output e intermedi di output.

## <a name="fix-build-issues"></a>Risolvere i problemi di compilazione

Il terzo passaggio del processo di porting consiste nell'ottenere il progetto da compilare. Alcune app vengono già compilate correttamente dopo la conversione del file di progetto in un progetto di tipo SDK. Se questo è il caso dell'app, congratulazioni! È possibile procedere al passaggio 4. Altre app necessiteranno di alcuni aggiornamenti per crearli per .NET Core. Se si tenta di eseguire `dotnet build` il progetto di esempio Bean trader, ad esempio (o di compilarlo in Visual Studio), si verificano molti errori, ma si otterranno rapidamente corretti.

### <a name="systemservicemodel-references-and-microsoftwindowscompatibility"></a>System. ServiceModel References e Microsoft. Windows. Compatibility

Una fonte comune di errori mancano riferimenti per le API disponibili per .NET Core, ma non incluse automaticamente nel metapacchetto dell'app .NET Core. Per risolvere questo problema, è necessario fare `Microsoft.Windows.Compatibility` riferimento al pacchetto. Il pacchetto di compatibilità include un ampio set di API comuni nelle applicazioni desktop di Windows, ad esempio client WCF, servizi directory, registro di sistema, configurazione, API ACL e altro ancora.

Con l'esempio Bean trader, la maggior parte degli errori di compilazione sono dovuti <xref:System.ServiceModel> a tipi mancanti. Per risolvere il problema, fare riferimento ai pacchetti NuGet WCF necessari. Tuttavia, le API client WCF sono tra quelle `Microsoft.Windows.Compatibility` presenti nel pacchetto, quindi fare riferimento al pacchetto di compatibilità è una soluzione ancora migliore (poiché risolve anche eventuali problemi correlati alle API, nonché soluzioni ai problemi WCF resi disponibili dal pacchetto di compatibilità). Il `Microsoft.Windows.Compatibility` pacchetto è utile nella maggior parte degli scenari di porting WPF e WinForms di .net core 3,0. Dopo l'aggiunta del riferimento NuGet `Microsoft.Windows.Compatibility`a, rimane un solo errore di compilazione.

### <a name="cleaning-up-unused-files"></a>Pulizia dei file non utilizzati

Un tipo di problema di migrazione spesso si riferisce a file C# e XAML che in precedenza non erano inclusi nella compilazione prelevati dai nuovi progetti in stile SDK che includono *tutte le* origini automaticamente.

Il successivo errore di compilazione visualizzato nell'esempio Bean trader si riferisce a un'implementazione di interfaccia errata in *OldUnusedViewModel.cs*. Il nome del file è un suggerimento, ma durante l'ispezione si noterà che il file di origine non è corretto. Non ha causato problemi in precedenza perché non era incluso nel progetto .NET Framework originale. I file di origine presenti sul disco ma non inclusi nel vecchio *csproj* sono ora inclusi automaticamente.

Per problemi di questo tipo, è facile confrontarsi con l' *csproj* precedente per verificare che il file non sia necessario e quindi `<Compile Remove="" />` , se il file di origine non è più necessario, eliminarlo. In questo caso, è possibile eliminare solo *OldUnusedViewModel.cs*.

Se si dispone di molti file di origine che devono essere esclusi in questo modo, è possibile disabilitare l'inclusione automatica dei file C# `<EnableDefaultCompileItems>` impostando la proprietà su false nel file di progetto. Quindi, è possibile copiare `<Compile Include>` gli elementi dal file di progetto precedente a quello nuovo in modo da creare solo le origini che si intende includere. Analogamente `<EnableDefaultPageItems>` , può essere usato per disattivare l'inclusione automatica di pagine XAML `<EnableDefaultItems>` e può controllare entrambe con una singola proprietà.

### <a name="a-brief-aside-on-multi-pass-compilers"></a>Una breve panoramica sui compilatori a più passaggi

Dopo aver rimosso il file danneggiato dall'esempio Bean trader, è possibile ricompilare e ricevere quattro errori. Non ne hai ancora uno? Perché è stato impostato il numero di errori? Il compilatore C# è un [compilatore](https://docs.microsoft.com/archive/blogs/ericlippert/how-many-passes)a più passaggi. Ciò significa che viene eseguito due volte ogni file di origine. In primo luogo, il compilatore esamina solo i metadati e le dichiarazioni in ogni file di origine e identifica eventuali problemi a livello di dichiarazione. Si tratta degli errori corretti. Quindi esegue nuovamente il codice per compilare l'origine C# in IL. si tratta del secondo set di errori che si sta osservando.

> [!NOTE]
> Il compilatore C# esegue [più di due passaggi](https://docs.microsoft.com/archive/blogs/ericlippert/how-many-passes), ma il risultato finale è che gli errori del compilatore per modifiche di codice di grandi dimensioni, ad esempio, tendono a essere disponibili in due onde.

### <a name="third-party-dependency-fixes-castlewindsor"></a>Correzioni di dipendenze di terze parti (Castle. Windsor)

Un'altra classe di problemi che si verificano in alcuni scenari di migrazione è rappresentata dalle differenze di API tra .NET Framework e le versioni .NET Core delle dipendenze. Anche se un pacchetto NuGet è destinato sia a .NET Framework sia a .NET Standard o .NET Core, è possibile che siano presenti librerie diverse da usare con destinazioni .NET diverse. Questo consente ai pacchetti di supportare diverse piattaforme .NET, che possono richiedere implementazioni diverse. Significa anche che è possibile che nelle librerie siano presenti piccole differenze nell'API quando la destinazione è costituita da diverse piattaforme .NET.

Il set di errori successivo visualizzato nell'esempio Bean trader è correlato alle `Castle.Windsor` API. Il progetto .NET Core Bean trader usa la stessa versione di `Castle.Windsor` del progetto di destinazione .NET Framework (4.1.1), ma le implementazioni per queste due piattaforme sono leggermente diverse.

In questo caso, vengono visualizzati i seguenti problemi che devono essere corretti:

1. `Castle.MicroKernel.Registration.Classes.FromThisAssembly`non è disponibile in .NET Core. Tuttavia `Classes.FromAssemblyContaining` , l'API simile è disponibile, pertanto è possibile sostituire entrambi gli utilizzi di `Classes.FromThisAssembly()` con chiamate a, `Classes.FromAssemblyContaining(t)`dove `t` è il tipo che effettua la chiamata.
1. Analogamente, *Bootstrapper.cs*in Bootstrapper.cs `Castle.Windsor.Installer.FromAssembly`,. Questa operazione non è disponibile in .NET Core. Al contrario, la chiamata può essere sostituita con `FromAssembly.Containing(typeof(Bootstrapper))`.

### <a name="updating-wcf-client-usage"></a>Aggiornamento dell'utilizzo del client WCF

Con la correzione `Castle.Windsor` delle differenze, l'ultimo errore di compilazione nel progetto .NET Core Bean trader è che `BeanTraderServiceClient` , che deriva da `DuplexClientBase`, non ha un `Open` metodo. Questa operazione non è sorprendente perché si tratta di un'API che è stata evidenziata da .NET Portability Analyzer all'inizio di questo processo di migrazione. Tuttavia, `BeanTraderServiceClient` la ricerca di richiama l'attenzione su un problema più grande. Questo client WCF è stato generato automaticamente dallo strumento [Svcutil. exe](../../framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) .

**I client WCF generati da Svcutil sono destinati all'uso in .NET Framework.**

Per le soluzioni che usano client WCF generati da Svcutil è necessario rigenerare client compatibili con .NET Standard per l'uso con .NET Core. Uno dei motivi principali per cui i client precedenti non funziona è che dipendono dalla configurazione dell'app per la definizione di associazioni e endpoint WCF. Poiché .NET Standard le API WCF possono funzionare su più piattaforme (in cui non sono disponibili API System. Configuration), i client WCF per gli scenari .NET Core e .NET Standard devono definire associazioni ed endpoint a livello di codice anziché nella configurazione.

Di fatto, è necessario modificare qualsiasi utilizzo del `<system.serviceModel>` client WCF che dipende dalla sezione app. config (creata con Svcutil o manualmente) per funzionare in .NET Core.

Esistono due modi per generare automaticamente client WCF compatibili con .NET Standard:

- Lo `dotnet-svcutil` strumento è uno strumento .NET che genera client WCF in modo analogo al modo in cui Svcutil funzionava in precedenza.
- Visual Studio è in grado di generare client WCF utilizzando l'opzione di [riferimento al servizio Web WCF](../../core/additional-tools/wcf-web-service-reference-guide.md) della funzionalità Servizi connessi.

Entrambi gli approcci funzionano correttamente. In alternativa, ovviamente, è possibile scrivere il codice client WCF manualmente. Per questo esempio si è scelto di usare la funzionalità servizio connesso di Visual Studio. A tale scopo, fare clic con il pulsante destro del mouse sul progetto *BeanTraderClient. Core* in Esplora soluzioni di Visual Studio e scegliere **Aggiungi** > **servizio connesso**. Scegliere quindi il provider di riferimento al servizio Web WCF. Verrà visualizzata una finestra di dialogo in cui è possibile specificare l'indirizzo del servizio Web back-end trader`localhost:8080` (se si esegue il server in locale) e lo spazio dei nomi che i tipi generati devono usare (ad esempio,**BeanTrader. Service**).

![Finestra di dialogo del servizio connesso di riferimento al servizio Web WCF](./media/convert-project-from-net-framework/connected-service-dialog.png)

Dopo aver selezionato il pulsante **fine** , viene aggiunto un nuovo nodo servizi connessi al progetto e viene aggiunto un file Reference.cs in quel nodo che contiene il nuovo client .NET standard WCF per accedere al servizio Bean trader. Se si osservano i `GetEndpointAddress` metodi `GetBindingForEndpoint` o in quel file, si noterà che le associazioni e gli endpoint vengono ora generati a livello di codice, anziché tramite la configurazione dell'app. La funzionalità' Aggiungi Servizi connessi ' può anche aggiungere riferimenti ad alcuni pacchetti System. ServiceModel nel file di progetto, che non sono necessari perché tutti i pacchetti WCF necessari sono inclusi tramite Microsoft. Windows. Compatibility. Controllare csproj per verificare se sono stati aggiunti elementi System. `<PackageReference>` ServiceModel aggiuntivi e, in caso affermativo, rimuoverli.

Il progetto include nuove classi client WCF ora (in *Reference.cs*), ma ha ancora le versioni precedenti (in BeanTrader.cs). A questo punto sono disponibili due opzioni:

- Se si vuole essere in grado di compilare il progetto di .NET Framework originale (insieme alla nuova versione di destinazione di .NET Core), è possibile `<Compile Remove="BeanTrader.cs" />` usare un elemento nel file csproj del progetto .NET Core in modo che le versioni di .NET Framework e .NET Core usino client WCF diversi. Questo ha il vantaggio di lasciare invariato il progetto di .NET Framework esistente, tuttavia, presenta lo svantaggio che il codice che usa i client WCF generati potrebbe dover essere leggermente diverso nel caso di .NET Core rispetto al progetto .NET Framework, quindi è probabile che si debbano usare `#if` le direttive per compilare in modo condizionale l'utilizzo del client WCF (creando client, ad esempio) per funzionare in modo singolo quando viene compilato per la .NET Framework.

- Se, invece, la varianza del codice nel progetto .NET Framework esistente è accettabile, è possibile rimuovere *BeanTrader.cs* tutti insieme. Poiché il nuovo client WCF viene compilato per .NET Standard, funzionerà in scenari .NET Core e .NET Framework. Se si sta compilando per .NET Framework oltre a .NET Core (mediante la funzionalità multitargeting o con due file csproj), è possibile usare questo nuovo file *Reference.cs* per entrambe le destinazioni. Questo approccio offre il vantaggio che il codice non deve biforcate per supportare due diversi client WCF; lo stesso codice verrà usato ovunque. Lo svantaggio è che comporta la modifica del progetto (presumibilmente stabile) .NET Framework.

Nel caso dell'esempio Bean trader, è possibile apportare piccole modifiche al progetto originale se semplifica la migrazione, quindi attenersi alla procedura seguente per riconciliare l'utilizzo dei client WCF:

01. Aggiungere il nuovo file Reference.cs al progetto .NET Framework *BeanTraderClient. csproj* usando il menu di scelta rapida "Aggiungi elemento esistente" da Esplora soluzioni. Assicurarsi di aggiungere "As link" in modo che lo stesso file venga usato da entrambi i progetti, anziché copiare il file C#. Questo passaggio non è necessario se si compila sia per .NET Core che per .NET Framework con un solo csproj (usando la funzionalità multitargeting).

01. Elimina *BeanTrader.cs*.

01. Il nuovo client WCF è simile a quello precedente, ma un numero di spazi dei nomi nel codice generato è diverso. Per questo motivo, è necessario aggiornare il progetto in modo che i tipi di client WCF vengano utilizzati da BeanTrader. Service (o qualsiasi altro nome di spazio dei nomi scelto) anziché BeanTrader. Model o senza uno spazio dei nomi. La compilazione di *BeanTraderClient. Core. csproj* consente di identificare la posizione in cui devono essere apportate le modifiche. Le correzioni saranno necessarie sia in C# che nei file di origine XAML.

01. Infine, si noterà che si verifica un errore in *BeanTraderServiceClientFactory.cs* perché i costruttori disponibili per il `BeanTraderServiceClient` tipo sono stati modificati. È stato usato per fornire un `InstanceContext` argomento, che è stato creato usando un `CallbackHandler` del contenitore `Castle.Windsor` IOC. I nuovi costruttori creano nuovi `CallbackHandler`oggetti. Esistono, tuttavia, i costruttori nel tipo `BeanTraderServiceClient`di base corrispondente a quello desiderato. Poiché il codice client WCF generato automaticamente esiste in classi parziali, è possibile estenderlo facilmente. A tale scopo, creare un nuovo file denominato *BeanTraderServiceClient.cs* e quindi creare una classe parziale con lo stesso nome (usando lo spazio dei nomi BeanTrader. Service). Aggiungere quindi un costruttore al tipo parziale, come illustrato di seguito.

    ```csharp
    public BeanTraderServiceClient(System.ServiceModel.InstanceContext callbackInstance) :
        base(callbackInstance, EndpointConfiguration.NetTcpBinding_BeanTraderService)
            { }
    ```

Con le modifiche apportate, l'esempio Bean trader utilizzerà ora un nuovo client WCF compatibile con .NET Standard ed è possibile apportare la correzione finale per modificare `Open` la chiamata in *TradingService.cs* in `await OpenAsync` modo da usare invece.

Con i problemi di WCF risolti, la versione .NET Core dell'esempio Bean trader viene ora compilata in modo corretto.

## <a name="runtime-testing"></a>Test di runtime

È facile dimenticare che il lavoro di migrazione non viene eseguito non appena il progetto viene compilato correttamente con .NET Core. È importante non perdere tempo per il test dell'app portata. Una volta completata la compilazione, assicurarsi che l'app venga eseguita e funzioni come previsto, soprattutto se si usano pacchetti destinati a .NET Framework.

Si proverà ad avviare l'app del trader Bean trasferita per vedere cosa accade. L'app non si trova molto prima di avere esito negativo con l'eccezione seguente.

```output
System.Configuration.ConfigurationErrorsException: 'Configuration system failed to initialize'

Inner Exception
ConfigurationErrorsException: Unrecognized configuration section system.serviceModel.
```

Questa operazione ha senso, ovviamente. Tenere presente che WCF non usa più la configurazione dell'app, quindi è necessario rimuovere la precedente sezione System. serviceModel del file app. config. Il client WCF aggiornato include tutte le stesse informazioni nel codice, quindi la sezione config non è più necessaria. Se si desidera che l'endpoint WCF possa essere configurato in app. config, è possibile aggiungerlo come impostazione dell'app e aggiornare il codice client WCF per recuperare l'endpoint del servizio WCF dalla configurazione.

Dopo la rimozione della sezione System. serviceModel di *app. config*, l'app viene avviata ma non riesce con un'altra eccezione quando un utente esegue l'accesso.

```output
System.PlatformNotSupportedException: 'Operation is not supported on this platform.'
```

L'API non supportata è `Func<T>.BeginInvoke`. Come spiegato in [DotNet/CoreFx # 5940](https://github.com/dotnet/corefx/issues/5940), .NET Core non supporta i `BeginInvoke` metodi `EndInvoke` e sui tipi delegati a causa di dipendenze di comunicazione remota sottostanti. Questo problema e la relativa correzione sono illustrati in modo più dettagliato nel post di Blog relativo alla [migrazione di delegati. BeginInvoke calls for .NET Core](https://devblogs.microsoft.com/dotnet/migrating-delegate-begininvoke-calls-for-net-core/) , ma la sostanza è che `BeginInvoke` le chiamate e `EndInvoke` devono essere sostituite con `Task.Run` (o alternative asincrone, se possibile). Applicando la soluzione generale, la `BeginInvoke` chiamata può essere sostituita con `Invoke` una chiamata avviata da `Task.Run`.

```csharp
Task.Run(() =>
{
    return userInfoRetriever.Invoke();
}).ContinueWith(result =>
{
    // BeginInvoke's callback is replaced with ContinueWith
    var task = result.ConfigureAwait(false);
    CurrentTrader = task.GetAwaiter().GetResult();
}, TaskScheduler.Default);
```

Dopo la rimozione `BeginInvoke` dell'utilizzo, l'app Bean trader viene eseguita correttamente in .NET Core.

![Trader Bean in esecuzione su .NET Core](./media/convert-project-from-net-framework/running-on-core.png)

Tutte le app sono diverse, quindi i passaggi specifici necessari per eseguire la migrazione delle proprie app a .NET Core possono variare. Tuttavia, l'esempio Bean trader illustra il flusso di lavoro generale e i tipi di problemi che è possibile prevedere. Nonostante la lunghezza di questo articolo, le modifiche effettive necessarie nell'esempio Bean trader per farlo funzionare in .NET Core erano piuttosto limitate. Molte app vengono migrate a .NET Core nello stesso modo; con limitazioni o persino senza modifiche al codice necessarie.
