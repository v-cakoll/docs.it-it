---
title: Esempio di migrazione a .NET Core 3.1
description: Viene illustrato come eseguire la migrazione di applicazioni di esempio destinate a .NET Framework a .NET Core 3,1.
ms.date: 05/12/2020
ms.openlocfilehash: ef8a0c24ec81a21eb89411ed4c9a543d4d70d89f
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83423383"
---
# <a name="example-of-migrating-to-net-core-31"></a>Esempio di migrazione a .NET Core 3.1

In questo capitolo vengono presentate linee guida pratiche che consentono di eseguire la migrazione dell'applicazione esistente da .NET Framework a .NET Core.

Viene presentato un processo ben strutturato che è possibile seguire e le considerazioni più importanti da tenere in considerazione per ogni passaggio.

Viene quindi documentato un processo di migrazione dettagliato per un'applicazione desktop di esempio, sia da WinForms che da versioni WPF.

## <a name="migration-process-overview"></a>Panoramica del processo di migrazione

Il processo di migrazione è costituito da quattro passaggi sequenziali:

1. **Preparazione**: comprendere le dipendenze che il progetto deve avere un'idea del futuro. In questo passaggio il progetto corrente viene portato a uno stato che semplifica il punto di avvio per la migrazione.

2. **Esegui la migrazione del file di progetto:** i progetti .NET Core usano il nuovo formato di progetto in stile SDK. Creare un nuovo file di progetto con questo formato o aggiornare quello necessario per usare lo stile SDK.

3. **Correzione del codice e della compilazione:** Compilare il codice in .NET Core che indirizza le differenze a livello di API tra .NET Framework e .NET Core. Se necessario, aggiornare i pacchetti di terze parti a quelli che supportano .NET Core.

4. **Esecuzione e test:** Potrebbero esserci differenze che non vengono visualizzate fino alla fase di esecuzione. Quindi, non dimenticare di eseguire l'applicazione e verificare che tutto funzioni come previsto.

### <a name="preparation"></a>Preparazione

#### <a name="migrate-packagesconfig-file"></a>Esegui la migrazione del file Packages. config

In un'applicazione .NET Framework tutti i riferimenti ai pacchetti esterni vengono dichiarati nel file *packages. config* . In .NET Core non è più necessario usare il file *packages. config* . Usare invece la proprietà [PackageReference](../../core/project-sdk/msbuild-props.md#packagereference) all'interno del file di progetto per specificare i pacchetti NuGet per l'app.

Quindi, è necessario eseguire la transizione da un formato a un altro. È possibile eseguire l'aggiornamento manualmente, prendendo le dipendenze contenute nel file *packages. config* e eseguendone la migrazione al file di progetto con il `PackageReference` formato. In alternativa, è possibile consentire a Visual Studio di eseguire il lavoro per l'utente: fare clic con il pulsante destro del mouse sul file *packages. config* e selezionare l'opzione **migrate Packages. config to PackageReference** .

#### <a name="verify-every-dependency-compatibility-in-net-core"></a>Verificare la compatibilità di tutte le dipendenze in .NET Core

Dopo aver eseguito la migrazione dei riferimenti ai pacchetti, è necessario controllare la compatibilità di ogni riferimento. È possibile esplorare le dipendenze di ogni pacchetto NuGet usato dall'applicazione in [NuGet.org](https://www.nuget.org/). Se il pacchetto ha .NET Standard dipendenze, funzionerà in .NET Core perché .NET Core 3,1 [supporta](../../standard/net-standard.md#net-implementation-support) tutte le versioni di .NET standard. Nell'immagine seguente vengono illustrate le dipendenze per il `Castle.Windsor` pacchetto:

![Screenshot delle dipendenze NuGet per il pacchetto Castle. Windsor](./media/example-migration-core/nuget-dependencies.png)

Per controllare la compatibilità dei pacchetti, è possibile utilizzare lo strumento <http://fuget.org> che offre informazioni più dettagliate sulle versioni e sulle dipendenze.

Forse il progetto fa riferimento a versioni precedenti del pacchetto che non supportano .NET Core, ma è possibile trovare versioni più recenti che lo supportano. Pertanto, l'aggiornamento dei pacchetti a versioni più recenti è in genere una raccomandazione efficace. Tuttavia, è necessario tenere presente che l'aggiornamento della versione del pacchetto può introdurre alcune modifiche di rilievo che forzano l'aggiornamento del codice.

Cosa accade se non si trova una versione compatibile? Cosa accade se non si vuole aggiornare la versione di un pacchetto a causa di queste modifiche di rilievo? Non preoccuparti perché è possibile dipendere da .NET Framework pacchetti da un'applicazione .NET Core. Non dimenticare di testarlo ampiamente perché può causare errori di run-time se il pacchetto esterno chiama un'API che non è disponibile in .NET Core. Questa operazione è molto importante quando si usa un pacchetto obsoleto che non verrà aggiornato ed è possibile semplicemente ridestinarlo per lavorare a .NET Core.

#### <a name="check-for-api-compatibility"></a>Verifica la compatibilità delle API

Poiché la superficie dell'API in .NET Framework e .NET Core è simile, ma non identica, è necessario verificare quali API sono disponibili in .NET Core e quali non lo sono. È possibile usare lo strumento .NET Portability Analyzer per visualizzare le API usate che non sono presenti in .NET Core. Esamina il livello binario dell'app, estrae tutte le API chiamate e quindi elenca le API non disponibili nel Framework di destinazione (in questo caso, .NET Core 3,1).

Per ulteriori informazioni su questo strumento, vedere:

<https://docs.microsoft.com/dotnet/standard/analyzers/portability-analyzer>

Un aspetto interessante di questo strumento è costituito dal modo in cui vengono evidenziate solo le differenze dal codice e non dal codice dei pacchetti esterni, che non è possibile modificare. Tenere presente che la maggior parte di questi pacchetti è stata aggiornata per renderli compatibili con .NET Core.

### <a name="migrate-project-file"></a>Esegui migrazione del file di progetto

#### <a name="create-the-new-net-core-project"></a>Creare il nuovo progetto .NET Core

Nella maggior parte dei casi, è consigliabile aggiornare il progetto esistente al nuovo formato di .NET Core. Tuttavia, è anche possibile creare un nuovo progetto mantenendo quello precedente. Lo svantaggio principale dell'aggiornamento del vecchio progetto è la perdita del supporto della finestra di progettazione, che può rivelarsi importante. Se si vuole proseguire con la finestra di progettazione, è necessario creare un nuovo progetto .NET Core in parallelo con quello precedente e condividere gli asset. Se è necessario modificare gli elementi dell'interfaccia utente nella finestra di progettazione, è possibile passare al progetto precedente a tale scopo. Poiché gli asset sono collegati, verranno aggiornati anche nel progetto .NET Core.

Il [progetto di tipo SDK](../../core/project-sdk/msbuild-props.md) per .NET Core è molto più semplice del formato di progetto di .NET Framework. Oltre alle voci citate in precedenza `PackageReference` , non è necessario eseguire molte altre operazioni. Il nuovo formato di progetto include alcune estensioni [di file per impostazione predefinita](../../core/tools/csproj.md#default-compilation-includes-in-net-core-projects), ad esempio `.cs` `.xaml` i file e, senza la necessità di includerle in modo esplicito nel file di progetto.

#### <a name="assemblyinfo-considerations"></a>Considerazioni su Assembly.info

Gli attributi vengono generati automaticamente nei progetti .NET Core. Se il progetto contiene un file *AssemblyInfo.cs* , le definizioni verranno duplicate, che causeranno conflitti di compilazione. È possibile eliminare il file *AssemblyInfo.cs* precedente o disabilitare la generazione di autogenerazione aggiungendo la voce seguente al file di progetto .NET Core:

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
  <PropertyGroup>
    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
  </PropertyGroup>
</Project>
```

#### <a name="resources"></a>Risorse

Le risorse incorporate sono incluse automaticamente, ma le risorse non sono, quindi è necessario eseguire la migrazione delle risorse nel nuovo file di progetto.

#### <a name="package-references"></a>Riferimenti ai pacchetti

Con l'opzione **migrate Packages. config to PackageReference** è possibile spostare facilmente i riferimenti al pacchetto esterno nel nuovo formato come indicato in precedenza.

#### <a name="update-package-references"></a>Aggiornare i riferimenti del pacchetto

Aggiornare le versioni dei pacchetti risultanti compatibili, come illustrato nella sezione precedente.

### <a name="fix-the-code-and-build"></a>Correggere il codice e compilare

#### <a name="microsoftwindowscompatibility"></a>Microsoft. Windows. Compatibility

Se l'applicazione dipende da API non disponibili in .NET Core, ad esempio registro di sistema, ACL o WCF, è necessario includere un riferimento al `Microsoft.Windows.Compatibility` pacchetto per aggiungere queste API specifiche di Windows. Funzionano in .NET Core, ma non sono inclusi perché non sono multipiattaforma.

È disponibile uno strumento chiamato analizzatore API ( <https://docs.microsoft.com/dotnet/standard/analyzers/api-analyzer> ) che consente di identificare le API che non sono compatibili con il codice.

#### <a name="use-if-directives"></a>USA \# direttive if

Se sono necessari percorsi di esecuzione diversi quando la destinazione è .NET Framework e .NET Core, è necessario usare le costanti di compilazione. Aggiungere alcune \# direttive if al codice per avere la stessa codebase per entrambe le destinazioni.

#### <a name="technologies-not-available-on-net-core"></a>Tecnologie non disponibili in .NET Core

Alcune tecnologie non sono disponibili in .NET Core, ad esempio:

* AppDomain
* Comunicazione remota
* Sicurezza dall'accesso di codice
* Server WCF
* Flusso di lavoro di Windows

Per questo motivo è necessario trovare una sostituzione per queste tecnologie se vengono usate nell'applicazione. Per ulteriori informazioni, vedere l'articolo relativo alle [tecnologie .NET Framework non disponibili in .NET Core](../../core/porting/net-framework-tech-unavailable.md) .

#### <a name="regenerate-autogenerated-clients"></a>Rigenera client generati automaticamente

Se l'applicazione usa codice generato automaticamente, ad esempio un client WCF, potrebbe essere necessario rigenerare questo codice per definire .NET Core come destinazione. In alcuni casi, è possibile trovare alcuni riferimenti mancanti poiché potrebbero non essere inclusi come parte del set di assembly .NET Core predefiniti. Usando uno strumento come <https://apisof.net/> , è possibile individuare facilmente l'assembly in cui risiede il riferimento mancante e aggiungerlo da NuGet.

#### <a name="rolling-back-package-versions"></a>Rollback delle versioni del pacchetto

Come regola generale, è stato precedentemente indicato che è consigliabile aggiornare ogni singola versione del pacchetto in modo che sia compatibile con .NET Core. Tuttavia, è possibile trovare che la destinazione di una versione aggiornata e compatibile di un assembly non viene addebitata. Se il costo della modifica non è accettabile, è possibile prendere in considerazione la possibilità di eseguire il rollback delle versioni dei pacchetti mantenendo quelle utilizzate in .NET Framework. Sebbene non siano destinati a .NET Core, dovrebbero funzionare correttamente a meno che non chiamino alcune API non supportate.

### <a name="run-and-test"></a>Esecuzione e test

Quando l'applicazione viene compilata senza errori, è possibile avviare l'ultimo passaggio della migrazione testando tutte le funzionalità.

In questo passaggio finale è possibile trovare diversi problemi a seconda della complessità dell'applicazione e delle dipendenze e delle API in uso.

Ad esempio, se si usano i file di configurazione (*app. config*), potrebbero verificarsi alcuni errori in fase di esecuzione, come le sezioni di configurazione non presenti. Usare il `Microsoft.Extensions.Configuration` pacchetto NuGet per correggere l'errore.

Un altro motivo per gli errori è l'uso `BeginInvoke` dei `EndInvoke` metodi e perché non sono supportati in .NET Core. Non sono supportati in .NET Core perché hanno una dipendenza dalla comunicazione remota, che non esiste in .NET Core. Per risolvere questo problema, provare a usare la `await` parola chiave (se disponibile) o il <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> metodo.

È possibile usare gli analizzatori di compatibilità per identificare API e modelli di codice nel codice che potrebbero causare problemi in fase di esecuzione con .NET Core. Passare a <http://github.com/dotnet/platform-compat> e usare l'analizzatore di API .NET nel progetto.

## <a name="migrating-a-windows-forms-application"></a>Migrazione di un Windows Forms Application

Per presentare un processo completo di migrazione di una Windows Forms Application, è stato scelto di eseguire la migrazione dell'applicazione di esempio eShop disponibile all'indirizzo <https://github.com/dotnet-architecture/eShopModernizing/tree/master/eShopLegacyNTier/src/eShopWinForms> . È possibile trovare il risultato completo della migrazione in <https://github.com/dotnet-architecture/eShopModernizing/tree/master/eShopModernizedNTier/src/eShopWinForms> .

Questa applicazione mostra un catalogo di prodotti e consente all'utente di spostarsi, filtrare e cercare i prodotti. Dal punto di vista dell'architettura, l'app si basa su un servizio WCF esterno che funge da facciata per un database back-end.

È possibile visualizzare la finestra principale dell'applicazione nell'immagine seguente:

![Finestra principale dell'applicazione](./media/example-migration-core/main-application-window.png)

Se si apre il file di progetto con *estensione csproj* , è possibile visualizzare una schermata simile alla seguente:

![Screenshot del contenuto del file csproj](./media/example-migration-core/csproj-file.png)

Come indicato in precedenza, il progetto .NET Core ha uno stile più compatto ed è necessario eseguire la migrazione della struttura del progetto al nuovo stile .NET Core SDK.

Nella Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto Windows Forms e scegliere **Scarica**  >  **modifica**progetto.

A questo punto è possibile aggiornare il file con estensione csproj. L'intero contenuto verrà eliminato e sostituito con il codice seguente:

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
    <PropertyGroup>
        <OutputType>WinExe</OutputType>
        <TargetFramework>netcoreapp3.1</TargetFramework>
        <UseWindowsForms>true</UseWindowsForms>
        <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    </PropertyGroup>
</Project>
```

Salvare e ricaricare il progetto. A questo punto è stato completato l'aggiornamento del file di progetto e il progetto è destinato a .NET Core.

Se si compila il progetto a questo punto, sono presenti alcuni errori correlati al riferimento al client WCF. Poiché questo codice viene generato automaticamente, è necessario rigenerarlo per la destinazione di .NET Core.

![Screenshot degli errori di compilazione in Visual Studio](./media/example-migration-core/winforms-compilation-errors.png)

Eliminare il file *Reference.cs* e generare un nuovo client del servizio.

Fare clic con il pulsante destro del mouse su **servizi connessi** e selezionare l'opzione **Aggiungi servizio connesso** .

![Screenshot del menu Servizi connessi con l'opzione Aggiungi servizio connesso selezionata](./media/example-migration-core/add-connected-service.png)

Viene visualizzata la finestra Servizi connessi. Selezionare l'opzione **Microsoft WCF Web Service** .

![Screenshot della finestra di Servizi connessi](./media/example-migration-core/connected-services-window.png)

Se il servizio WCF si trova nella stessa soluzione di questo esempio, è possibile selezionare l'opzione **Discover** invece di specificare un URL del servizio.

![Screenshot della finestra di riferimento per la configurazione del servizio Web WCF](./media/example-migration-core/configure-wcf-reference.png)

Una volta individuato il servizio, lo strumento riflette il contratto API implementato dal servizio. Modificare il nome dello spazio dei nomi in `eShopServiceReference` modo che sia come illustrato nell'immagine seguente:

![Screenshot del contratto API e dello spazio dei nomi modificato](./media/example-migration-core/api-contract-namespace.png)

Selezionare il pulsante **fine** . Dopo un certo periodo di tempo, verrà visualizzato il codice generato.

Verranno visualizzati tre file generati automaticamente:

1. *Introduzione*: un collegamento a GitHub per fornire alcune informazioni su WCF.
2. *ConnectedService. JSON*: parametri di configurazione per la connessione al servizio.
3. *Reference.cs*: codice client WCF effettivo.

![Screenshot della finestra di Esplora soluzioni con i tre file generati automaticamente](./media/example-migration-core/autogenerated-files.png)

Se si compila nuovamente, verranno visualizzati molti errori provenienti dai file con *estensione cs* all'interno della cartella *Helper* . Questa cartella era presente nella versione .NET Framework ma non è inclusa nel vecchio *. csproj*. Tuttavia, con il nuovo progetto in stile SDK, ogni file di codice presente sotto il percorso del file di progetto è incluso per impostazione predefinita. Ovvero il nuovo progetto .NET Core tenta di compilare i file all'interno della cartella *Helper* . Poiché tale cartella non è necessaria, è possibile eliminarla in modo sicuro.

Se si compila di nuovo il progetto e lo si esegue, non verranno visualizzate le immagini del prodotto. Il problema è che ora il percorso dei file è leggermente modificato. Per risolvere questo problema, è necessario aggiungere un altro livello di profondità nel percorso, aggiornando nel file `CatalogView.cs` la riga:

```csharp
string image_name = Environment.CurrentDirectory + "\\..\\..\\Assets\\Images\\Catalog\\" + catalogItems.Picturefilename;
```

to

```csharp
string image_name = Environment.CurrentDirectory + "\\..\\..\\..\\Assets\\Images\\Catalog\\" + catalogItems.Picturefilename;
```

Dopo questa modifica, è possibile verificare che l'applicazione venga avviata e venga eseguita come previsto in .NET Core.

## <a name="migrating-a-wpf-application"></a>Migrazione di un'applicazione WPF

`Shop.ClassicWPF`Per eseguire la migrazione verrà utilizzata l'applicazione di esempio. La figura seguente mostra una schermata dell'app prima della migrazione:

![App di esempio prima della migrazione](./media/example-migration-core/app-before-migration.png)

Questa applicazione usa un database di SQL Server Express locale per conservare le informazioni sul catalogo di prodotti. È possibile accedere a questo database direttamente dall'applicazione WPF.

In primo luogo, è necessario aggiornare il file con *estensione csproj* al nuovo stile SDK usato dalle applicazioni .NET Core. Si seguiranno gli stessi passaggi descritti nella migrazione del Windows Forms: si scaricherà il progetto, si aprirà il file con *estensione csproj* , ne aggiornerà il contenuto e si ricaricherà il progetto.

In tal caso, eliminare tutto il contenuto del file con *estensione csproj* e sostituirlo con il codice seguente:

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
    <PropertyGroup>
        <OutputType>WinExe</OutputType>
        <TargetFramework>netcoreapp3.1</TargetFramework>
        <UseWPF>true</UseWPF>
        <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    </PropertyGroup>
</Project>
```

Se si ricarica il progetto e lo si compila, si otterrà l'errore seguente:

![Screenshot degli errori di compilazione in Visual Studio](./media/example-migration-core/wpf-compilation-error.png)

Poiché è stato eliminato tutto il contenuto *. csproj* , è stata persa una specifica del riferimento al progetto presente nel vecchio progetto. È sufficiente aggiungere questa riga al file con *estensione csproj* per includere il riferimento al progetto:

```xml
<ItemGroup>
    <ProjectReference Include="..\\eShop.SqlProvider\\eShop.SqlProvider.csproj" />
<ItemGroup>
```

È anche possibile consentire a Visual Studio di aiutarti facendo clic con il pulsante destro del mouse sul nodo **dipendenze** e scegliendo **Aggiungi riferimento al progetto**. Selezionare il progetto dalla soluzione e fare clic su **OK**:

![Screenshot della finestra di dialogo Gestione riferimenti con il progetto eShop. sqlfornir selezionato](./media/example-migration-core/reference-manager.png)

Una volta aggiunto il riferimento a progetto mancante, l'applicazione viene compilata ed eseguita come previsto in .NET Core.

>[!div class="step-by-step"]
>[Precedente](windows-migration.md) 
> [Avanti](deploy-modern-applications.md)
