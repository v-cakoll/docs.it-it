---
title: Migrazione di app WPF a .NET Core 3.0Migrating WPF Apps to .NET Core 3.0
description: Informazioni su come eseguire la migrazione di un'app Windows Presentation Foundation (WPF) a .NET Core 3.0.
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
# <a name="migrating-wpf-apps-to-net-core"></a>Migrazione di app WPF a .NET CoreMigrating WPF apps to .NET Core

Questo articolo illustra i passaggi necessari per eseguire la migrazione di un'app Windows Presentation Foundation (WPF) da .NET Framework a .NET Core 3.0. Se non si dispone di un'app WPF a portata di mano per la porta, ma si desidera provare il processo, è possibile usare l'app di esempio **Bean Trader** disponibile su [GitHub](https://github.com/dotnet/windows-desktop/tree/master/Samples/BeanTrader). L'app originale (destinata a .NET Framework 4.7.2) è disponibile nella cartella NetFx-BeanTraderClient. In primo luogo spiegheremo i passaggi necessari per le applicazioni di porta in generale, e poi vedremo attraverso le modifiche specifiche che si applicano al **commerciante Bean** esempio.

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

Per eseguire la migrazione a .NET Core, è innanzitutto necessario:To migrate to .NET Core, you must first:

01. Comprendere e aggiornare le dipendenze NuGet:Understand and update NuGet dependencies:

    01. Aggiornare le dipendenze `<PackageReference>` NuGet per utilizzare il formato.
    01. Esaminare le dipendenze NuGet di primo livello per la compatibilità .NET Core o .NET Standard.Review top-level NuGet dependencies for .NET Core or .NET Standard compatibility.
    01. Aggiornare i pacchetti NuGet alle versioni più recenti.
    01. Utilizzare [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) per comprendere le dipendenze di .NET.

01. Eseguire la migrazione del file di progetto nel nuovo formato in stile SDK:Migrate the project file to the new SDK-style format:

    01. Scegliere se scegliere se scegliere come destinazione sia .NET Core che .NET Framework o solo .NET Core.
    01. Copiare le proprietà e gli elementi del file di progetto rilevanti nel nuovo file di progetto.

01. Risolvere i problemi di compilazione:Fix build issues:

    01. Aggiungere un riferimento al pacchetto [Microsoft.Windows.Compatibility.Add](https://www.nuget.org/packages/Microsoft.Windows.Compatibility/) a reference to the Microsoft.Windows.Compatibility package.
    01. Trovare e correggere le differenze a livello di API.
    01. Rimuovere le sezioni *app.config* diverse da `appSettings` o `connectionStrings`.
    01. Rigenerare il codice generato, se necessario.

01. Test di runtime:

    01. Verificare che l'app con conversione funzioni come previsto.
    01. Attenzione alle <xref:System.NotSupportedException> eccezioni.

## <a name="about-the-sample"></a>Informazioni sull'esempio

Questo articolo fa riferimento [all'app di esempio Bean Trader](https://github.com/dotnet/windows-desktop/tree/master/Samples/BeanTrader) perché usa una varietà di dipendenze simili a quelle che le app WPF del mondo reale potrebbero avere. L'app non è grande, ma è pensata per essere un passo avanti rispetto a 'Hello World' in termini di complessità. L'app dimostra alcuni problemi che gli utenti possono riscontrare durante il porting di app reali. L'app comunica con un servizio WCF, pertanto per la corretta esecuzione, è inoltre necessario eseguire il progetto BeanTraderServer (disponibile nello stesso repository GitHub) e assicurarsi che la configurazione BeanTraderClient punti di configurazione all'endpoint corretto. Per impostazione predefinita, nell'esempio si presuppone che *http://localhost:8090*il server sia in esecuzione sullo stesso computer in , che sarà vero se si avvia BeanTraderServer localmente.)

Tieni presente che questa app di esempio ha lo scopo di illustrare le sfide e le soluzioni di porting di .NET Core.Keep in mind that this sample app is meant to demonstrate .NET Core porting challenges and solutions. Non è destinato a dimostrare le procedure consigliate WPFWPF. Infatti, include deliberatamente alcuni anti-modelli per assicurarsi di incontrare almeno un paio di sfide interessanti durante il porting.

## <a name="getting-ready"></a>Preparazione

La sfida principale della migrazione di un'app .NET Framework a .NET Core è che le relative dipendenze potrebbero funzionare in modo diverso o non funzionare affatto. La migrazione è molto più facile di prima; molti pacchetti NuGet ora sono destinati a .NET Standard. A partire da .NET Core 2.0, le aree di superficie di .NET Framework e .NET Core sono diventate simili. Anche così, rimangono alcune differenze (sia nel supporto dei pacchetti NuGet che nelle API .NET disponibili). The first step in migrating is to review the app's dependencies and make sure references are in a format that's easily migrated to .NET Core.

### <a name="upgrade-to-packagereference-nuget-references"></a>Eseguire `<PackageReference>` l'aggiornamento ai riferimenti NuGetUpgrade to NuGet references

I progetti .NET Framework meno recenti in genere elencano le dipendenze NuGet in un file *packages.config.* Il nuovo formato di file di progetto [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) in stile SDK fa riferimento ai pacchetti NuGet come elementi nel file csproj stesso anziché in un file di configurazione separato.

Durante la migrazione, l'utilizzo dei riferimenti di stile presenta due vantaggi:When migrating, there are two advantages to using `<PackageReference>`-style references:

- Questo è lo stile di riferimento NuGet necessario per il nuovo file di progetto .NET Core.This is the style of NuGet reference that is required for the new .NET Core project file. Se si sta `<PackageReference>`già utilizzando , tali elementi del file di progetto possono essere copiati e incollati direttamente nel nuovo progetto.
- A differenza di un `<PackageReference>` file packages.config, gli elementi fanno riferimento solo alle dipendenze di primo livello da cui dipende direttamente il progetto. Tutti gli altri pacchetti NuGet transitivi verranno determinati in fase di ripristino e registrati nel file obj-project.assets.json generato automaticamente. In questo modo è molto più semplice determinare le dipendenze del progetto, che è utile per determinare se le dipendenze necessarie funzioneranno su .NET Core o meno.

Il primo passaggio per la migrazione di un'app .NET Framework a .NET Core consiste nell'aggiornarla per usare `<PackageReference>` i riferimenti NuGet. Visual Studio semplifica questa operazione. È sufficiente fare clic con il pulsante destro del mouse sul file *packages.config* del progetto in **Esplora soluzioni**di Visual Studio , quindi **scegliere Migrate packages.config to PackageReference**.

![Aggiornamento a PackageReferenceUpgrading to PackageReference](./media/convert-project-from-net-framework/package-reference-migration.png)

Viene visualizzata una finestra di dialogo che mostra le dipendenze NuGet di primo livello calcolate e chiede quali altri pacchetti NuGet devono essere promossi a livello superiore. Nessuno di questi altri pacchetti deve essere di primo livello per l'esempio Bean Trader, in modo da poter deselezionare tutte queste caselle. Quindi, fare clic su **OK** e `<PackageReference>` il file *packages.config* viene rimosso e gli elementi vengono aggiunti al file di progetto.

`<PackageReference>`I riferimenti -style non archiviano i pacchetti NuGet localmente in una cartella di pacchetti. Al contrario, vengono archiviati a livello globale come ottimizzazione. Al termine della migrazione, modificare il file `<Analyzer>` csproj e rimuovere tutti gli elementi che fanno riferimento agli analizzatori che in precedenza provenivano da *.. directory packages.* Non ti preoccupare; poiché si dispone ancora dei riferimenti al pacchetto NuGet, gli analizzatori verranno inclusi nel progetto. Hai solo bisogno di pulire i vecchi `<Analyzer>` elementi packages.config-style.

### <a name="review-nuget-packages"></a>Esaminare i pacchetti NuGetReview NuGet packages

Ora che è possibile visualizzare i pacchetti NuGet di primo livello da cui dipende il progetto, è possibile verificare se tali pacchetti sono disponibili in .NET Core.Now that you can see the top-level NuGet packages that the project depends on, you can review whether those packages are available on .NET Core. È possibile determinare se un pacchetto supporta .NET Core esaminando le relative dipendenze da [nuget.org](https://www.nuget.org/). Il sito [fuget.org](https://www.fuget.org/) creato dalla comunità mostra queste informazioni in primo piano nella parte superiore della pagina delle informazioni del pacchetto.

Quando la destinazione è .NET Core 3.0, tutti i pacchetti destinati a .NET Core o .NET Standard dovrebbero funzionare (poiché .NET Core implementa l'area di superficie standard .NET). In alcuni casi, la versione specifica di un pacchetto utilizzato non è destinata a .NET Core o .NET Standard, ma le versioni più recenti. In questo caso, è consigliabile eseguire l'aggiornamento alla versione più recente del pacchetto.

È possibile usare anche i pacchetti destinati a .NET Framework, ma ciò introduce alcuni rischi. Le dipendenze da .NET Core a .NET Framework sono consentite perché le aree di superficie di .NET Core e .NET Framework sono abbastanza simili che tali dipendenze *spesso* funzionano. Tuttavia, se il pacchetto tenta di utilizzare un'API .NET che non è presente in .NET Core, si verificherà un'eccezione di runtime. Per questo scopo, è necessario fare riferimento ai pacchetti .NET Framework solo quando non sono disponibili altre opzioni e comprendere che questa operazione impone un onere per i test.

Se ci sono pacchetti a cui viene fatto riferimento che non sono destinati a .NET Core o .NET Standard, dovrete pensare ad altre alternative:

- Ci sono altri pacchetti simili che possono essere utilizzati invece? A volte gli autori NuGet pubblicano 'separati'. Versioni di base delle librerie destinate in modo specifico a .NET Core.Core' versions of their libraries specifically ing .NET Core. I pacchetti Enterprise Library sono un esempio della pubblicazione della community ". NetCore" alternative. In other cases, newer SDKs for a particular service (sometimes with different package names) are available for .NET Standard. Se non sono disponibili alternative, è possibile procedere utilizzando i pacchetti di .NET Framework mirati, tenendo presente che è necessario testarli accuratamente una volta eseguito su .NET Core.

L'esempio Bean Trader ha le seguenti dipendenze NuGet di primo livello:

- [**Castle.Windsor, versione 4.1.1**](https://www.castleproject.org/projects/windsor/)  

  Questo pacchetto è destinato a .NET Standard 1.6, quindi funziona in .NET Core.This package targets .NET Standard 1.6, so it works on .NET Core.

- [**Microsoft.CodeAnalysis.FxCopAnalyzers, versione 2.6.3**](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers/2.6.3)  
  Questo è un meta-pacchetto, quindi non è immediatamente ovvio quali piattaforme supporta, ma la [documentazione](https://github.com/dotnet/roslyn-analyzers#microsoftcodeanalysisfxcopanalyzers) indica che la sua versione più recente (2.9.2) funzionerà sia per .NET Framework che per .NET Core.

- [**Nito.AsyncEx, versione 4.0.1**](https://www.nuget.org/packages/Nito.AsyncEx/4.0.1)  

  Questo pacchetto non è destinato a .NET Core, ma la versione 5.0 più recente. Ciò è comune durante la migrazione perché molti pacchetti NuGet hanno aggiunto di recente il supporto .NET Standard, ma le versioni di progetto precedenti saranno destinate solo a .NET Framework. Se la differenza di versione è solo una differenza di versione minore, è spesso facile eseguire l'aggiornamento alla versione più recente. Poiché si tratta di una modifica di versione principale, è necessario prestare attenzione all'aggiornamento poiché potrebbero essere presenti modifiche di rilievo nel pacchetto. C'è una strada da percorrere, però, che è buona.

- [**MahApps.Metro, versione 1.6.5**](https://www.nuget.org/packages/MahApps.Metro/1.6.5)  

  Questo pacchetto non è destinato a .NET Core, ma ha una versione non definitiva più recente (2.0-alfa) che ha. Ancora una volta, si deve guardare fuori per i cambiamenti di rottura, ma il pacchetto più recente è incoraggiante.

Dipendenze NuGet dell'esempio Bean Trader sono tutte destinate a .NET Standard/.NET Core o con versioni più recenti che lo fanno, pertanto è improbabile che vi siano problemi di blocco qui.

### <a name="upgrade-nuget-packages"></a>Aggiornare i pacchetti NuGetUpgrade NuGet packages

Se possibile, sarebbe bene aggiornare le versioni di tutti i pacchetti destinati solo a .NET Core o .NET Standard con versioni più recenti a questo punto (con il progetto ancora destinato a .NET Framework) per individuare e risolvere in anticipo eventuali modifiche di rilievo.

Se si preferisce non apportare modifiche rilevanti alla versione .NET Framework esistente dell'app, questa operazione può attendere fino a quando non si dispone di un nuovo file di progetto destinato a .NET Core. Tuttavia, l'aggiornamento dei pacchetti NuGet alle versioni compatibili con .NET Core in anticipo rende il processo di migrazione ancora più semplice dopo aver creato il nuovo file di progetto e riduce il numero di differenze tra le versioni di .NET Framework e .NET Core dell'app.

Con l'esempio Bean Trader, tutti gli aggiornamenti necessari possono essere effettuati facilmente (utilizzando il gestore di pacchetti NuGet di Visual Studio) con un'eccezione: l'aggiornamento da **MahApps.Metro 1.6.5** a **2.0** rivela le modifiche di rilievo relative alle API di gestione del tema e dell'accento.

Idealmente, l'app verrebbe aggiornata per usare la versione più recente del pacchetto (poiché è più probabile che funzioni su .NET Core). In alcuni casi, tuttavia, ciò potrebbe non essere fattibile. In questi casi, non aggiornare **MahApps.Metro** perché le modifiche necessarie non sono banali e questa esercitazione si concentra sulla migrazione a .NET Core 3, non a **MahApps.Metro 2.** Inoltre, si tratta di una dipendenza .NET Framework a basso rischio perché l'app Bean Trader esercita solo una piccola parte di **MahApps.Metro**. Naturalmente, richiederà test per assicurarsi che tutto funzioni una volta completata la migrazione. Se questo fosse uno scenario reale, sarebbe bene presentare un problema per tenere traccia del lavoro per passare a **MahApps.Metro** versione 2.0 poiché non facendo la migrazione ora lascia dietro di sé un certo debito tecnico.

Una volta che i pacchetti NuGet `<PackageReference>` vengono aggiornati alle versioni recenti, il gruppo di elementi nel file di progetto dell'esempio Bean Trader dovrebbe essere simile al seguente.

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

### <a name="net-framework-portability-analysis"></a>Analisi della portabilità di .NET Framework

Una volta compreso lo stato delle dipendenze NuGet del progetto, l'elemento successivo da considerare è le dipendenze dell'API di .NET Framework. Lo strumento [analizzatore di portabilità .NET](../../standard/analyzers/portability-analyzer.md) è utile per comprendere quali API .NET utilizzate dal progetto sono disponibili in altre piattaforme .NET.

Lo strumento viene fornito come un [plug-in](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)di Visual Studio , uno strumento da riga di [comando](https://github.com/Microsoft/dotnet-apiport/releases)o avvolto in una [semplice GUI](https://github.com/Microsoft/dotnet-apiport-ui), che semplifica le opzioni. Per altre informazioni sull'uso di .NET Portability Analyzer (porta API) usando la GUI nel post di blog [Porting desktop apps to .NET Core.](https://devblogs.microsoft.com/dotnet/porting-desktop-apps-to-net-core/) Se si preferisce utilizzare la riga di comando, i passaggi necessari sono:

1. Scaricare [.NET Portability Analyzer](https://github.com/Microsoft/dotnet-apiport/releases) se non è già presente.
1. Assicurarsi che l'app .NET Framework da convertire compilazioni correttamente (questa è una buona idea prima della migrazione indipendentemente).
1. Eseguire Porta API con una riga di comando come questa.

    ```console
    ApiPort.exe analyze -f <PathToBeanTraderBinaries> -r html -r excel -t ".NET Core"
    ```

    L'argomento `-f` specifica il percorso contenente i file binari da analizzare. L'argomento `-r` consente di specificare il formato di file di output desiderato. L'argomento `-t` specifica la piattaforma .NET con cui analizzare l'utilizzo delle API. In this case, you want .NET Core.

Quando si apre il report HTML, la prima sezione elencherà tutti i file binari analizzati e la percentuale delle API .NET utilizzate sono disponibili nella piattaforma di destinazione. La percentuale non è significativa da sola. La cosa più utile è vedere le API specifiche che mancano. A tale scopo, selezionare il nome di un assembly o scorrere verso il basso fino ai report per i singoli assembly.

Concentrarsi sugli assembly di cui si è proprietari del codice sorgente. Nel report Bean Trader ApiPort, ad esempio, sono elencati molti file binari, ma la maggior parte di essi appartiene ai pacchetti NuGet. `Castle.Windsor`dimostra che dipende da alcune API System.Web mancanti in .NET Core. Questo non è un problema perché `Castle.Windsor` in precedenza verificato che supporta .NET Core. È comune che i pacchetti NuGet dispongano di file binari diversi per l'utilizzo `Castle.Windsor` con piattaforme .NET diverse, pertanto se la versione di .NET Framework degli utilizzi o meno delle API System.Web è irrilevante, purché il pacchetto sia destinato anche a .NET Standard o .NET Core (operazione che viene).

Con l'esempio Bean Trader, l'unico binario che è necessario considerare è **BeanTraderClient** e `System.ServiceModel.ClientBase<T>.Close` `System.ServiceModel.ClientBase<T>.Open`il report mostra che mancano solo due API .NET: e .

![Report di portabilità BeanTraderClient](./media/convert-project-from-net-framework/portability-report.png)

È improbabile che si tratti di problemi di blocco perché le API client WCF sono (per lo più) supportate in .NET Core, pertanto devono essere disponibili alternative per queste API centrali. Infatti, esaminando `System.ServiceModel`l'area di superficie <https://apisof.net>di .NET Core (utilizzando ), si nota che esistono alternative asincrone in .NET Core.

Sulla base di questo report e l'analisi delle dipendenze NuGet precedente, sembra che non dovrebbero esserci problemi importanti la migrazione dell'esempio Bean Trader a .NET Core. Si è pronti per il passaggio successivo in cui si avvierà effettivamente la migrazione.

## <a name="migrating-the-project-file"></a>Migrazione del file di progetto

Se l'app non usa il nuovo formato di file di [progetto in stile SDK,](../../core/tools/csproj.md)è necessario un nuovo file di progetto per impostare come destinazione .NET Core. È possibile sostituire il file csproj esistente o, se si preferisce mantenere il progetto esistente invariato nello stato corrente, è possibile aggiungere un nuovo file csproj destinato a .NET Core. Puoi compilare versioni dell'app per .NET Framework e .NET Core con un singolo file `<TargetFrameworks>` di progetto in stile SDK con [multitargeting](../../standard/library-guidance/cross-platform-targeting.md) (specificando più destinazioni).

Per creare il nuovo file di progetto, è possibile creare `dotnet new wpf` un nuovo progetto WPF in Visual Studio o usare il comando in una directory temporanea per generare il file di progetto e quindi copiarlo/rinominarlo nel percorso corretto. C'è anche uno strumento creato dalla comunità, [CsprojToVs2017](https://github.com/hvanbakel/CsprojToVs2017), che può automatizzare parte della migrazione dei file di progetto. Lo strumento è utile, ma ha ancora bisogno di un essere umano per esaminare i risultati per assicurarsi che tutti i dettagli della migrazione siano corretti. Un'area particolare che lo strumento non gestisce in modo ottimale è la migrazione dei pacchetti NuGet dai file *packages.config.* Se lo strumento viene eseguito in un file di progetto che usa ancora un file *packages.config* per fare riferimento ai pacchetti NuGet, verrà eseguita automaticamente la migrazione agli `<PackageReference>` elementi, ma aggiungerà `<PackageReference>` elementi per tutti *i* pacchetti anziché solo quelli di primo livello. Se è già stata`<PackageReference>` eseguita la migrazione agli elementi con Visual Studio (come è stato fatto in questo esempio), lo strumento può aiutare con il resto della conversione. Come Scott Hanselman raccomanda nel [suo post sul blog sulla migrazione di file csproj](https://www.hanselman.com/blog/UpgradingAnExistingNETProjectFilesToTheLeanNewCSPROJFormatFromNETCore.aspx), porting a mano è educativo e darà risultati migliori se si dispone solo di pochi progetti da portare. Ma se si esegue il porting di decine o centinaia di file di progetto, uno strumento come [CsprojToVs2017] può essere d'aiuto.

Per creare un nuovo file di progetto `dotnet new wpf` per l'esempio Bean Trader, eseguire in una directory temporanea e spostare il file *con estensione csproj* generato nella cartella *BeanTraderClient* e rinominarlo **BeanTraderClient.Core.csproj**.

Poiché il nuovo formato di file di progetto include automaticamente i file di C, i file *resx* e i file XAML trovati nella directory o nella directory, il file di progetto è già quasi completo. Per completare la migrazione, aprire i file di progetto vecchi e nuovi side-by-side e guardare attraverso quello precedente per vedere se tutte le informazioni che contiene deve essere migrato. Nel caso di esempio Bean Trader, i seguenti elementi devono essere copiati nel nuovo progetto:

- Le `<RootNamespace>` `<AssemblyName>`proprietà `<ApplicationIcon>` , e devono essere tutte copiate.

- È inoltre necessario `<GenerateAssemblyInfo>false</GenerateAssemblyInfo>` aggiungere una proprietà al nuovo file di progetto poiché `[AssemblyTitle]`l'esempio Bean Trader include attributi a livello di assembly (ad esempio ) in un file di AssemblyInfo.cs. Per impostazione predefinita, i nuovi progetti in stile SDK genereranno automaticamente questi attributi in base alle proprietà nel file csproj. Poiché non si desidera che ciò accada in questo caso (gli attributi generati automaticamente `<GenerateAssemblyInfo>`sarebbero in conflitto con quelli di AssemblyInfo.cs), si disattivano gli attributi generati automaticamente con .

- Anche se i file *resx* vengono `<Resource>` inclusi automaticamente come risorse incorporate, altri elementi come le immagini non lo sono. Quindi, copiare gli `<Resource>` elementi per incorporare i file di immagine e icona. È possibile semplificare i riferimenti png a una singola riga utilizzando il supporto `<Resource Include="**\*.png" />`del nuovo formato di file di progetto per i modelli di globbing: .

- Analogamente, `<None>` gli elementi vengono inclusi automaticamente, ma non vengono copiati nella directory di output, per impostazione predefinita. Poiché `<None>` il progetto Bean Trader include un elemento che *viene* copiato nella directory di output (utilizzando `PreserveNewest` i comportamenti), è necessario aggiornare l'elemento popolato `<None>` automaticamente per tale file, in questo modo.

  ```xml
  <None Update="BeanTrader.pfx">
    <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>
  </None>
  ```

- L'esempio Bean Trader include un file XAML `Content` (Default.Accent.xaml) come (anziché come un `Page`) perché i temi e gli accenti definiti in questo file vengono caricati dal codice XAML del file in fase di esecuzione, anziché essere incorporati nell'app stessa. Il nuovo sistema del progetto `<Page>`include automaticamente questo file come , tuttavia, poiché si tratta di un file XAML. Pertanto, è necessario rimuovere il file`<Page Remove="**\Default.Accent.xaml" />`XAML come pagina ( ) e aggiungerlo come contenuto.

  ```xml
  <Content Include="Resources\Themes\Default.Accent.xaml">
      <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>
  </Content>
  ```

- Infine, aggiungere riferimenti NuGet `<ItemGroup>` copiando `<PackageReference>` l'oggetto con tutti gli elementi. Se in precedenza non è stato aggiornato i pacchetti NuGet alle versioni compatibili con .NET Core, è possibile farlo ora che i riferimenti al pacchetto sono in un progetto specifico di .NET Core.

A questo punto, dovrebbe essere possibile aggiungere il nuovo progetto alla soluzione BeanTrader e aprirlo in Visual Studio. Il progetto deve essere corretto `dotnet restore BeanTraderClient.Core.csproj` in **Esplora soluzioni**e deve ripristinare correttamente i pacchetti (con due avvisi previsti relativi alla versione di MahApps.Metro in uso con .NET Framework di destinazione).

Anche se è possibile mantenere entrambi i file di progetto side-by-side (e può anche essere auspicabile se si desidera continuare a compilare il vecchio progetto esattamente come era), complica il processo di migrazione (i due progetti tenteranno di utilizzare le stesse cartelle bin e obj) e di solito non è necessario. Se si desidera compilare sia per destinazioni .NET Core `<TargetFramework>netcoreapp3.0</TargetFramework>` che .NET Framework, è possibile sostituire la proprietà nel nuovo file di progetto con `<TargetFrameworks>netcoreapp3.0;net472</TargetFrameworks>` invece. Per l'esempio Bean Trader, eliminare il file di progetto precedente (BeanTraderClient.csproj) poiché non è più necessario. Se si preferisce mantenere entrambi i file di progetto, assicurarsi di compilarli in percorsi di output e intermedi diversi.

## <a name="fix-build-issues"></a>Risolvere i problemi di compilazione

Il terzo passaggio del processo di porting consiste nell'ottenere la compilazione del progetto. Alcune app verranno già compilate correttamente dopo la conversione del file di progetto in un progetto di tipo SDK. Se questo è il caso per la tua app, congratulazioni! Si può andare al passo 4. Altre app avranno bisogno di alcuni aggiornamenti per farli costruire per .NET Core. Se si tenta `dotnet build` di eseguire sul progetto di esempio Bean Trader ora, ad esempio, (o compilarlo in Visual Studio), ci saranno molti errori, ma si otterrà risolverli rapidamente.

### <a name="systemservicemodel-references-and-microsoftwindowscompatibility"></a>Riferimenti a System.ServiceModel e Microsoft.Windows.Compatibility

Un'origine comune di errori mancano riferimenti per le API disponibili per .NET Core ma non inclusi automaticamente nel metapacchetto dell'app .NET Core.A common source of errors is missing references for APIs that are available for .NET Core but not automatically included in the .NET Core app metapackage. Per risolvere questo problema, `Microsoft.Windows.Compatibility` è necessario fare riferimento al pacchetto. Il pacchetto di compatibilità include un'ampia gamma di API comuni nelle app desktop di Windows, ad esempio il client WCF, i servizi directory, il Registro di sistema, la configurazione, le API ACLs e altro ancora.

Con l'esempio Bean Trader, la maggior parte <xref:System.ServiceModel> degli errori di compilazione sono dovuti a tipi mancanti. Questi potrebbero essere risolti facendo riferimento ai pacchetti WCF NuGet necessari. Le API client WCF sono tra `Microsoft.Windows.Compatibility` quelle presenti nel pacchetto, tuttavia, pertanto il riferimento al pacchetto di compatibilità è una soluzione ancora migliore (poiché risolve anche eventuali problemi relativi alle API, nonché soluzioni ai problemi WCF resi disponibili dal pacchetto di compatibilità). Il `Microsoft.Windows.Compatibility` pacchetto è utile nella maggior parte degli scenari di conversione di .NET Core 3.0 WPF e WinForms.The package helps in most .NET Core 3.0 WPF and WinForms porting scenarios. Dopo aver aggiunto il `Microsoft.Windows.Compatibility`riferimento NuGet a , rimane un solo errore di compilazione.

### <a name="cleaning-up-unused-files"></a>Pulizia dei file inutilizzati

Un tipo di problema di migrazione che si presenta spesso si riferisce ai file c'è e XAML che non sono stati precedentemente inclusi nella compilazione vengono prelevati dai nuovi progetti in stile SDK che includono automaticamente *tutte le* origini.

Il prossimo errore di compilazione visualizzato nell'esempio Bean Trader si riferisce a un'implementazione dell'interfaccia non valida in *OldUnusedViewModel.cs*. Il nome del file è un suggerimento, ma durante l'ispezione, si scoprirà che questo file di origine non è corretto. Non causava problemi in precedenza perché non era incluso nel progetto .NET Framework originale. I file di origine presenti sul disco ma non inclusi nel *vecchio csproj* vengono ora inclusi automaticamente.

Per problemi una tantum come questo, è facile confrontare con il *csproj* precedente per `<Compile Remove="" />` confermare che il file non è necessario e quindi o, se il file di origine non è più necessario da nessuna parte, eliminarlo. In questo caso, è sicuro eliminare solo *OldUnusedViewModel.cs*.

Se si dispone di molti file di origine che devono essere esclusi in questo `<EnableDefaultCompileItems>` modo, è possibile disabilitare l'inclusione automatica dei file di C , impostando la proprietà su false nel file di progetto. Quindi, è `<Compile Include>` possibile copiare gli elementi dal file di progetto precedente a quello nuovo per compilare solo le origini che si intende includere. Analogamente, `<EnableDefaultPageItems>` può essere usato per disattivare `<EnableDefaultItems>` l'inclusione automatica delle pagine XAML e può controllare entrambi con una singola proprietà.

### <a name="a-brief-aside-on-multi-pass-compilers"></a>Una breve parte sui compilatori multi-pass

Dopo aver rimosso il file incriminato dall'esempio Bean Trader, è possibile ricompilare e otterrà quattro errori. Non ne avevi uno prima? Perché il numero di errori è aumentato? Il compilatore di Cè è un [compilatore a più passaggi.](https://docs.microsoft.com/archive/blogs/ericlippert/how-many-passes) Ciò significa che passa attraverso ogni file di origine due volte. In primo luogo, il compilatore esamina solo i metadati e le dichiarazioni in ogni file di origine e identifica eventuali problemi a livello di dichiarazione. Questi sono gli errori che hai risolto. Quindi passa attraverso il codice di nuovo per compilare l'origine C , in IL; questi sono il secondo set di errori che si sta vedendo ora.

> [!NOTE]
> Il compilatore di C, non solo [due passaggi](https://docs.microsoft.com/archive/blogs/ericlippert/how-many-passes), ma il risultato finale è che gli errori del compilatore per le modifiche di codice di grandi dimensioni come questo tendono a venire in due onde.

### <a name="third-party-dependency-fixes-castlewindsor"></a>Correzioni di dipendenza di terze parti (Castle.Windsor)

Un'altra classe di problemi che si presenta in alcuni scenari di migrazione è differenze DI API tra .NET Framework e .NET Core versioni delle dipendenze. Anche se un pacchetto NuGet è destinato sia a .NET Framework che a .NET Standard o a .NET Core, potrebbero essere presenti librerie diverse da utilizzare con destinazioni .NET diverse. Ciò consente ai pacchetti di supportare molte piattaforme .NET diverse, che possono richiedere implementazioni diverse. Significa anche che potrebbero esserci piccole differenze API nelle librerie quando si prendono di mira diverse piattaforme .NET.

Il successivo set di errori che vedrai nell'esempio `Castle.Windsor` Bean Trader è correlato alle API. Il progetto .NET Core Bean Trader `Castle.Windsor` utilizza la stessa versione del progetto di destinazione di .NET Framework (4.1.1), ma le implementazioni per queste due piattaforme sono leggermente diverse.

In questo caso, vengono visualizzati i seguenti problemi che devono essere risolti:

1. `Castle.MicroKernel.Registration.Classes.FromThisAssembly`non è disponibile in .NET Core. Esiste, `Classes.FromAssemblyContaining` tuttavia, l'API simile disponibile, pertanto è possibile sostituire entrambi gli utilizzi di `Classes.FromThisAssembly()` con le chiamate a `Classes.FromAssemblyContaining(t)`, dove `t` è il tipo che effettua la chiamata.
1. Analogamente, *Bootstrapper.cs*in `Castle.Windsor.Installer.FromAssembly`Bootstrapper.cs , . Questa opzione non è disponibile in .NET Core. Al contrario, tale `FromAssembly.Containing(typeof(Bootstrapper))`chiamata può essere sostituita con .

### <a name="updating-wcf-client-usage"></a>Aggiornamento dell'utilizzo del client WCFUpdating WCF client usage

Dopo aver `Castle.Windsor` corretto le differenze, l'ultimo errore di compilazione rimanente nel progetto .NET Core Bean Trader è che `BeanTraderServiceClient` (che deriva da `DuplexClientBase`) non dispone di un `Open` metodo. Questo non è sorprendente poiché si tratta di un'API che è stata evidenziata da .NET Portability Analyzer all'inizio di questo processo di migrazione. Guardando `BeanTraderServiceClient` attira la nostra attenzione su una questione più grande, però. Questo client WCF è stato generato automaticamente dallo strumento [Svcutil.exe.](../../framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)

**WCF clients generated by Svcutil are meant for use on .NET Framework.**

Le soluzioni che utilizzano client WCF generati da svcutil dovranno rigenerare i client compatibili con .NET Standard per l'utilizzo con .NET Core.Solutions that use svcutil-generated WCF clients will need to regenerate .NET Standard-compatible clients for use with .NET Core. Uno dei motivi principali per cui i client precedenti non funzioneranno è che dipendono dalla configurazione dell'app per la definizione di associazioni ed endpoint WCF. Poiché le API WCF di .NET Standard possono funzionare multipiattaforma (dove le API System.Configuration non sono disponibili), i client WCF per gli scenari .NET Core e .NET Standard devono definire associazioni ed endpoint a livello di codice anziché nella configurazione.

In effetti, qualsiasi utilizzo del `<system.serviceModel>` client WCF che dipende dalla sezione app.config (se creato con Svcutil o manualmente) dovrà essere modificato per funzionare in .NET Core.

Esistono due modi per generare automaticamente client WCF compatibili con .NET Standard:There are two ways to automatically generate .NET Standard-compatible clients:

- Lo `dotnet-svcutil` strumento è uno strumento .NET che genera client WCF in un modo simile a come Svcutil funzionava in precedenza.
- Visual Studio può generare client WCF utilizzando l'opzione [Riferimento al servizio Web WCF](../../core/additional-tools/wcf-web-service-reference-guide.md) della relativa funzionalità di servizi connessi.

Entrambi gli approcci funzionano bene. In alternativa, è possibile scrivere manualmente il codice client WCF. Per questo esempio, ho scelto di usare la funzionalità servizio connesso di Visual Studio.For this sample, I chose to use the Visual Studio Connected Service feature. A tale scopo, fare clic con il pulsante destro del mouse sul progetto *BeanTraderClient.Core* in Esplora soluzioni di Visual Studio e scegliere **Aggiungi** > **servizio connesso**. Successivamente, scegliere il provider di riferimento del servizio Web WCF. Verrà visualizzata una finestra di dialogo in cui è possibile`localhost:8080` specificare l'indirizzo del servizio Web Bean Trader back-end (se si esegue il server in locale) e lo spazio dei nomi che i tipi generati devono utilizzare (**BeanTrader.Service**, ad esempio).

![Finestra di dialogo Servizio connesso a riferimento al servizio Web WCFWCF Web Service Reference Connected Service Dialog](./media/convert-project-from-net-framework/connected-service-dialog.png)

Dopo aver selezionato **il** fine pulsante, un nuovo nodo servizi connessi viene aggiunto al progetto e un file di Reference.cs viene aggiunto in tale nodo contenente il nuovo client WCF .NET Standard per l'accesso al servizio Bean Trader. Se si esaminano i `GetEndpointAddress` metodi o `GetBindingForEndpoint` in tale file, si noterà che le associazioni e gli endpoint vengono ora generati a livello di codice (anziché tramite la configurazione dell'app). The 'Add Connected Services' feature may also add references to some System.ServiceModel packages in the project file, which aren't needed since all necessary WCF packages are included via Microsoft.Windows.Compatibility. Controllare il csproj per verificare se `<PackageReference>` sono stati aggiunti ulteriori elementi System.ServiceModel e, in caso affermativo, rimuoverli.

Il progetto ha nuove classi client WCF ora (in *Reference.cs*), ma ha anche quelle precedenti (in BeanTrader.cs). Ci sono due opzioni a questo punto:

- Se si desidera essere in grado di compilare il progetto .NET Framework originale (insieme al nuovo .NET Core di destinazione), è possibile utilizzare un `<Compile Remove="BeanTrader.cs" />` elemento nel file csproj del progetto .NET Core in modo che le versioni di .NET Framework e .NET Core dell'app utilizzano client WCF diversi. Questo ha il vantaggio di lasciare invariato il progetto .NET Framework esistente, ma presenta lo svantaggio che il codice che utilizza i client WCF generati potrebbe `#if` essere necessario essere leggermente diverso nel caso .NET Core rispetto a .NET Framework, pertanto è probabile che sia necessario utilizzare le direttive per compilare in modo condizionale alcuni utilizzi client WCF (creazione di client, ad esempio) per funzionare in un modo quando compilato per .NET Core e un altro modo quando viene compilato per .NET Framework.

- Se, d'altra parte, parte della varianza del codice nel progetto .NET Framework esistente è accettabile, è possibile rimuovere *BeanTrader.cs* tutti insieme. Poiché il nuovo client WCF è compilato per .NET Standard, funzionerà sia in scenari .NET Core che .NET Framework. Se si compila per .NET Framework in aggiunta a .NET Core (tramite multitargeting o con due file csproj), è possibile utilizzare questo nuovo *file di Reference.cs* per entrambe le destinazioni. Questo approccio ha il vantaggio che il codice non sarà necessario biforcare per supportare due client WCF diversi; lo stesso codice verrà utilizzato ovunque. Lo svantaggio è che si tratta di modificare il progetto .NET Framework (presumibilmente stabile).

Nel caso dell'esempio Bean Trader, è possibile apportare piccole modifiche al progetto originale se semplifica la migrazione, pertanto attenersi alla seguente procedura per riconciliare l'utilizzo del client WCF:In the case of the Bean Trader sample, you can make small changes to the original project if it makes migration easier, so follow these steps to reconcile WCF client usage:

01. Aggiungere il nuovo file di Reference.cs al progetto *BeanTraderClient.csproj* di .NET Framework utilizzando il menu di scelta rapida 'Aggiungi elemento esistente' da Esplora soluzioni. Assicurarsi di aggiungere 'come collegamento' in modo che lo stesso file viene utilizzato da entrambi i progetti (anziché copiare il file di C . Se si compila sia per .NET Core che per .NET Framework con un singolo csproj (utilizzando il multitargeting), questo passaggio non è necessario.

01. Eliminare *BeanTrader.cs*.

01. Il nuovo client WCF è simile a quello precedente, ma un numero di spazi dei nomi nel codice generato sono diversi. Per questo motivo, è necessario aggiornare il progetto in modo che i tipi di client WCF vengono utilizzati da BeanTrader.Service (o qualsiasi nome dello spazio dei nomi scelto) anziché BeanTrader.Model o senza uno spazio dei nomi. La compilazione di *BeanTraderClient.Core.csproj* consentirà di identificare dove devono essere apportate queste modifiche. Le correzioni saranno necessarie sia nei file di origine in C, sia nei file di origine XAML.

01. Infine, si scoprirà che si *BeanTraderServiceClientFactory.cs* è verificato un errore `BeanTraderServiceClient` nel BeanTraderServiceClientFactory.cs perché i costruttori disponibili per il tipo sono stati modificati. Consente di fornire un `InstanceContext` argomento (creato utilizzando `CallbackHandler` un `Castle.Windsor` dal contenitore IoC). I nuovi costruttori `CallbackHandler`creano nuovi s. Esistono, tuttavia, costruttori nel `BeanTraderServiceClient`tipo di base 's che corrispondono a quello che si desidera. Poiché il codice client WCF generato automaticamente esiste tutto in classi parziali, è possibile estenderlo facilmente. A tale scopo, creare un nuovo file denominato *BeanTraderServiceClient.cs* e quindi creare una classe parziale con lo stesso nome (utilizzando lo spazio dei nomi BeanTrader.Service). Quindi, aggiungere un costruttore al tipo parziale, come illustrato di seguito.

    ```csharp
    public BeanTraderServiceClient(System.ServiceModel.InstanceContext callbackInstance) :
        base(callbackInstance, EndpointConfiguration.NetTcpBinding_BeanTraderService)
            { }
    ```

Con le modifiche apportate, l'esempio Bean Trader utilizzerà ora un nuovo client WCF compatibile `Open` con .NET `await OpenAsync` Standard ed è possibile effettuare la correzione finale della modifica della chiamata in *TradingService.cs* da utilizzare.

Con i problemi WCF risolti, la versione .NET Core dell'esempio Bean Trader ora si compila in modo pulito!

## <a name="runtime-testing"></a>Test di runtime

È facile dimenticare che il lavoro di migrazione non viene eseguito non appena il progetto viene compilato in modo pulito rispetto a .NET Core. È importante lasciare il tempo per testare anche l'app con porting. Una volta che le cose vengono compilate correttamente, assicurati che l'app venga eseguita e funzioni come previsto, soprattutto se usi pacchetti destinati a .NET Framework.

Proviamo a lanciare l'app Bean Trader portata e vediamo cosa succede. L'app non arriva lontano prima di non riuscire con l'eccezione seguente.

```output
System.Configuration.ConfigurationErrorsException: 'Configuration system failed to initialize'

Inner Exception
ConfigurationErrorsException: Unrecognized configuration section system.serviceModel.
```

Questo ha un senso, naturalmente. Tenere presente che WCF non usa più la configurazione dell'app, pertanto la sezione system.serviceModel precedente del file app.config deve essere rimossa. Il client WCF aggiornato include tutte le stesse informazioni nel codice, pertanto la sezione di configurazione non è più necessaria. Se si desidera che l'endpoint WCF sia configurabile in app.config, è possibile aggiungerlo come impostazione dell'app e aggiornare il codice client WCF per recuperare l'endpoint del servizio WCF dalla configurazione.

Dopo aver rimosso la sezione system.serviceModel di *app.config*, l'app viene avviata ma non riesce con un'altra eccezione quando un utente accede.

```output
System.PlatformNotSupportedException: 'Operation is not supported on this platform.'
```

L'API non `Func<T>.BeginInvoke`supportata è . Come illustrato in [dotnet/corefx-5940](https://github.com/dotnet/corefx/issues/5940), .NET `BeginInvoke` Core `EndInvoke` non supporta i metodi e sui tipi delegati a causa delle dipendenze remote sottostanti. Questo problema e la relativa correzione sono spiegati in modo più dettagliato nel post di `BeginInvoke` blog `EndInvoke` [Delega.BeginInvoke migrazione per .NET Core,](https://devblogs.microsoft.com/dotnet/migrating-delegate-begininvoke-calls-for-net-core/) ma il succo è che e le chiamate devono essere sostituiti con `Task.Run` (o alternative asincrone, se possibile). Applicando la soluzione generale `BeginInvoke` qui, la chiamata `Invoke` può `Task.Run`essere sostituita con una chiamata avviata da .

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

Dopo aver `BeginInvoke` rimosso l'utilizzo, l'app Bean Trader viene eseguita correttamente in .NET Core!

![Bean Trader in esecuzione su .NET Core](./media/convert-project-from-net-framework/running-on-core.png)

Tutte le app sono diverse, pertanto i passaggi specifici necessari per eseguire la migrazione delle proprie app a .NET Core variano. Ma si spera che l'esempio Bean Trader dimostra il flusso di lavoro generale e i tipi di problemi che ci si può aspettare. E, nonostante la lunghezza di questo articolo, le modifiche effettive necessarie nell'esempio Bean Trader per farlo funzionare su .NET Core erano piuttosto limitate. Molte app migrano a .NET Core nello stesso modo; con modifiche al codice limitate o addirittura senza necessità.
