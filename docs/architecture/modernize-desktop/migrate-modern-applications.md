---
title: Migrazione di applicazioni desktop moderne
description: Tutto ciò che occorre sapere sul processo di migrazione per le moderne applicazioni desktop.
ms.date: 05/12/2020
ms.openlocfilehash: a015b266dc5c36fcef38dad04b9f4f048ee5906a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2020
ms.locfileid: "84446917"
---
# <a name="migrating-modern-desktop-applications"></a>Migrazione di applicazioni desktop moderne

In questo capitolo vengono esaminati i problemi più comuni e le sfide che è possibile affrontare quando si esegue la migrazione di un'applicazione esistente da .NET Framework a .NET Core.

Un'applicazione desktop complessa non funziona in isolamento e necessita di un tipo di interazione con i sottosistemi che possono risiedere nel computer locale o in un server remoto. Probabilmente sarà necessario un tipo di database per connettersi come archivio di persistenza in locale o in remoto. Grazie alla generazione di architetture Internet e orientate ai servizi, è normale che l'applicazione sia connessa a una sorta di servizio che risiede in un server remoto o nel cloud. Potrebbe essere necessario accedere al computer file system per implementare alcune funzionalità. In alternativa, è possibile usare una parte di funzionalità che risiede all'interno di un oggetto COM all'esterno dell'applicazione, che è uno scenario comune se, ad esempio, si stanno integrando gli assembly di Office nell'app.

Sono inoltre presenti differenze nella superficie dell'API esposta da .NET Framework e .NET Core e alcune funzionalità disponibili in .NET Framework non sono disponibili in .NET Core. È quindi importante conoscerli e prenderli in considerazione durante la pianificazione di una migrazione.

## <a name="configuration-files"></a>File di configurazione

I file di configurazione consentono di archiviare set di proprietà che vengono lette in fase di esecuzione e influiscono sul comportamento delle app, ad esempio la posizione in cui individuare un database o il numero di volte in cui eseguire un ciclo. La bellezza di questa tecnica è che è possibile modificare alcuni aspetti dell'applicazione senza la necessità di eseguire la ricompilazione e la ricompilazione. Questa operazione risulta utile quando, ad esempio, lo stesso codice dell'app viene eseguito in un ambiente di sviluppo con un determinato set di valori di configurazione e in produzione con uno diverso.

### <a name="configuration-on-net-framework"></a>Configurazione in .NET Framework

Se si dispone di un'applicazione desktop funzionante .NET Framework, è probabile che si disponga di un file *app. config* a cui si accede tramite la <xref:System.Configuration.AppSettingsSection> classe dallo `System.Configuration` spazio dei nomi.

All'interno dell'infrastruttura di .NET Framework, esiste una gerarchia di file di configurazione che eredita le proprietà dagli elementi padre. È possibile trovare un file *Machine. config* che definisce molte proprietà e sezioni di configurazione che possono essere usate o sottoposte a override in qualsiasi file di configurazione discendente.

### <a name="configuration-on-net-core"></a>Configurazione in .NET Core

Nel mondo di .NET Core non è presente alcun file *Machine. config* . Inoltre, anche se è possibile continuare a usare lo <xref:System.Configuration> spazio dei nomi obsoleto, è possibile passare alla modalità moderna <xref:Microsoft.Extensions.Configuration> , che offre un numero valido di miglioramenti.

L'API di configurazione supporta il concetto di provider di configurazione che definisce l'origine dati da usare per caricare la configurazione. Sono disponibili diversi tipi di provider predefiniti, ad esempio:

- Oggetti .NET in memoria
- File INI
- File JSON
- File XML
- Argomenti della riga di comando
- Variabili di ambiente
- Archivio utente crittografato

 In alternativa, è possibile crearne di personalizzati.

La nuova configurazione consente un elenco di coppie nome-valore che possono essere raggruppate in una gerarchia a più livelli. Qualsiasi valore archiviato viene mappato a una stringa ed è disponibile un supporto di associazione incorporato che consente di deserializzare le impostazioni in un oggetto Plain Old CLR Object personalizzato (POCO).

L' <xref:Microsoft.Extensions.Configuration.ConfigurationBuilder> oggetto consente di aggiungere tutti i provider di configurazione che potrebbero essere necessari per l'applicazione, usando una regola di precedenza per la risoluzione delle preferenze. Quindi, l'ultimo provider aggiunto nel codice sostituirà gli altri. Si tratta di un'ottima funzionalità per la gestione di ambienti diversi per l'esecuzione, poiché è possibile definire diverse configurazioni per gli ambienti di sviluppo, test e produzione e gestirle in una singola funzione all'interno del codice.

### <a name="migrating-configuration-files"></a>Migrazione dei file di configurazione

È possibile continuare a usare il file XML di app. config esistente. Tuttavia, è possibile eseguire la migrazione della configurazione per trarre vantaggio dai diversi miglioramenti apportati a .NET Core.

Per eseguire la migrazione da un file *app. config* obsoleto a un nuovo file di configurazione, è necessario scegliere tra un formato XML e un formato JSON.

Se si sceglie XML, la conversione è semplice. Poiché il contenuto è lo stesso, è sufficiente rinominare il file *app. config* in un file con estensione XML. Modificare quindi il codice che fa riferimento a AppSettings per utilizzare la `ConfigurationBuilder` classe. Questa modifica dovrebbe essere semplice.

Se si vuole usare un formato JSON e non si vuole eseguire la migrazione manualmente, è disponibile uno strumento denominato [DotNet-config2json](https://www.nuget.org/packages/dotnet-config2json/) disponibile in .NET Core che può convertire un file *app. config* in un file di configurazione JSON.

È possibile che si verifichino alcuni problemi anche quando si usano le sezioni di configurazione definite nel file *Machine. config* . Si consideri, ad esempio, la configurazione seguente:

```xml
<configuration>
    <system.diagnostics>
        <switches>
            <add name="General" value="4" />
        </switches>
        <trace autoflush="true" indentsize="2">
            <listeners>
                <add name="myListener"
                     type="System.Diagnostics.TextWriterTraceListener,
                           System, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"
                     initializeData="MyListener.log"
                     traceOutputOptions="ProcessId, LogicalOperationStack, Timestamp, ThreadId, Callstack, DateTime" />
            </listeners>
        </trace>
    </system.diagnostics>
</configuration>
```

Se questa configurazione viene eseguita in .NET Core, si otterrà un'eccezione:

Sezione di configurazione non riconosciuta System. Diagnostics

Questa eccezione si verifica perché la sezione e l'assembly responsabili della gestione di tale sezione sono stati definiti nel file *Machine. config* , che ora non esiste.

Per risolvere facilmente il problema, è possibile copiare la definizione della sezione dal file *Machine. config* precedente al nuovo file di configurazione:

```xml
<configSections>
    <section name="system.diagnostics"
             type="System.Diagnostics.SystemDiagnosticsSection,
                   System, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>
</configSections>
```

## <a name="accessing-databases"></a>Accesso ai database

Quasi tutte le applicazioni desktop necessitano di un tipo di database. Per il desktop, è comune trovare architetture client-server con una connessione diretta tra l'app desktop e il motore di database. Questi database possono essere locali o remoti, a seconda della necessità di condividere le informazioni tra utenti diversi.

Dal punto di vista del codice sono state apportate numerose tecnologie e Framework per offrire allo sviluppatore la possibilità di connettersi, eseguire query e aggiornare un database.

Gli esempi più comuni di database che è possibile trovare quando si parla di applicazioni desktop di Windows sono Microsoft Access e Microsoft SQL Server. Se si dispone di più di 20 anni di programmazione dell'esperienza per il desktop, nomi come ODBC, OLEDB, RDO, ADO, ADO.NET, LINQ e Entity Framework avranno un suono familiare.

### <a name="odbc"></a>ODBC

È possibile continuare a usare ODBC in .NET Core poiché Microsoft fornisce la `System.Data.Odbc` libreria compatibile con .NET Standard 2,0.

### <a name="ole-db"></a>OLE DB

[OLE DB](https://docs.microsoft.com/previous-versions/windows/desktop/ms722784(v=vs.85))   è stato un ottimo modo per accedere a diverse origini dati in modo uniforme. Ma si basava su COM, che è una tecnologia solo per Windows e, di conseguenza, non era la soluzione ideale per una tecnologia multipiattaforma, ad esempio .NET Core. Non è supportata anche in SQL Server versioni 2014 e successive. Per questi motivi, OLE DB non sarà supportato da .NET Core.

### <a name="adonet"></a>ADO.NET

È comunque possibile usare ADO.NET dal codice desktop esistente in .NET Core. È sufficiente aggiornare alcuni pacchetti NuGet.

### <a name="ef-core-vs-ef6"></a>Confronto tra EF Core e EF6

Sono disponibili due versioni attualmente supportate di Entity Framework (EF), Entity Framework 6 (EF6) e EF Core.

La tecnologia più recente rilasciata come parte del .NET Framework mondo è Entity Framework, con 6,4 la versione più recente. Con il lancio di .NET Core, Microsoft ha rilasciato anche un nuovo stack di accesso ai dati basato su Entity Framework e chiamato Entity Framework Core.

È possibile usare EF 6,4 e EF Core da .NET Framework e .NET Core. Quindi, quali sono i driver decisionali che consentono di decidere tra i due?

EF 6,3 è la prima versione di EF6 che può essere eseguita in .NET Core e lavorare su più piattaforme. In realtà, l'obiettivo principale di questa versione è quello di semplificare la migrazione delle applicazioni esistenti che usano EF6 a .NET Core.

EF Core è stato progettato per offrire un'esperienza di sviluppo simile a EF6. Molte delle principali API sono invariate, in modo che EF Core risulti familiare agli sviluppatori che hanno usato EF6.

Sebbene siano compatibili, esistono differenze nell'implementazione che è necessario verificare prima di prendere una decisione.
Per ulteriori informazioni, vedere [confrontare EF Core & EF6](/ef/efcore-and-ef6/).

Si consiglia di utilizzare EF Core se:

* Per l'app sono necessarie le funzionalità di .NET Core.
* EF Core supporta tutte le funzionalità necessarie per l'app.

È consigliabile usare EF6 se vengono soddisfatte entrambe le condizioni seguenti:

* L'app viene eseguita in Windows e .NET Framework 4,0 o versione successiva.
* EF6 supporta tutte le funzionalità necessarie per l'app.

### <a name="relational-databases"></a>Database relazionali

#### <a name="sql-server"></a>SQL Server

SQL Server è stato uno dei database preferiti se si sta sviluppando per il desktop alcuni anni fa. Con l'uso di <xref:System.Data.SqlClient> in .NET Framework, è possibile accedere alle versioni di SQL Server, che incapsula i protocolli specifici del database.

In .NET Core è possibile trovare una nuova `SqlClient` classe, completamente compatibile con quella esistente nel .NET Framework ma che si trova nella <xref:Microsoft.Data.SqlClient> libreria. È sufficiente aggiungere un riferimento al pacchetto NuGet [Microsoft. Data. SqlClient](https://www.nuget.org/packages/Microsoft.Data.SqlClient/) ed eseguire alcune operazioni di ridenominazione per gli spazi dei nomi e tutti gli elementi dovrebbero funzionare come previsto.

#### <a name="microsoft-access"></a>Microsoft Access

Microsoft Access è stato usato per anni quando il SQL Server sofisticato e più scalabile non era necessario. È comunque possibile connettersi a Microsoft Access tramite la <xref:System.Data.Odbc> libreria.

## <a name="consuming-services"></a>Utilizzo dei servizi

Grazie alla generazione di architetture orientate ai servizi, le applicazioni desktop hanno iniziato a evolversi da un modello client-server all'approccio a tre livelli. Nell'approccio client-server viene stabilita una connessione di database diretta dal client che contiene la logica di business in genere all'interno di un singolo file EXE. D'altra parte, l'approccio a tre livelli stabilisce un livello di servizio intermedio che implementa la logica di business e l'accesso al database, consentendo una migliore sicurezza, scalabilità e riusabilità. Anziché utilizzare direttamente i set di dati di dati, l'approccio del livello si basa su un set di servizi che implementano contratti e oggetti di tipi come modo per implementare il trasferimento dei dati.

Se si dispone di un'applicazione desktop che utilizza un servizio WCF e si desidera eseguirne la migrazione a .NET Core, è necessario prendere in considerazione alcuni aspetti.

La prima cosa da fare è come risolvere la configurazione per accedere al servizio. Poiché la configurazione è diversa in .NET Core, è necessario effettuare alcuni aggiornamenti nel file di configurazione.

In secondo luogo, sarà necessario rigenerare il client del servizio con i nuovi strumenti presenti in Visual Studio 2019. In questo passaggio è necessario prendere in considerazione l'attivazione della generazione delle operazioni sincrone per rendere il client compatibile con il codice esistente.

Dopo la migrazione, se si ritiene che siano presenti librerie necessarie che non sono presenti in .NET Core, è possibile aggiungere un riferimento al pacchetto NuGet [Microsoft. Windows. Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) e verificare se le funzioni mancanti sono presenti.

Se si usa la <xref:System.Net.WebRequest> classe per eseguire chiamate al servizio Web, è possibile riscontrare alcune differenze in .NET Core. Si consiglia di usare invece System .NET. http. HttpClient.

## <a name="consuming-a-com-object"></a>Utilizzo di un oggetto COM

Attualmente, non è possibile aggiungere un riferimento a un oggetto COM da Visual Studio 2019 da usare con .NET Core. Quindi, è necessario modificare manualmente il file di progetto.

Inserire una `COMReference` struttura all'interno del file di progetto, come nell'esempio seguente:

```xml
<ItemGroup>
    <COMReference Include="MSHTML">
        <Guid>{3050F1C5-98B5-11CF-BB82-00AA00BDCE0B}\</Guid>
        <VersionMajor>4</VersionMajor>
        <VersionMinor>0</VersionMinor>
        <Lcid>0</Lcid>
        <WrapperTool>primary</WrapperTool>
        <Isolated>false</Isolated>
    </COMReference>
</ItemGroup>
```

## <a name="more-things-to-consider"></a>Altri aspetti da considerare

Diverse tecnologie disponibili per le librerie .NET Framework non sono disponibili per .NET Core. Se il codice si basa su alcune di queste tecnologie, prendere in considerazione gli approcci alternativi descritti in questa sezione.

[Windows Compatibility Pack](../../core/porting/windows-compat-pack.md) fornisce l'accesso alle API che in precedenza erano disponibili solo per .NET Framework. Può essere usato nei progetti .NET Core e .NET Standard.

Per ulteriori informazioni sulla compatibilità delle API, è possibile trovare la documentazione sulle modifiche di rilievo e le API deprecate/legacy all'indirizzo <https://docs.microsoft.com/dotnet/core/compatibility/fx-core> .

### <a name="appdomains"></a>AppDomain

I domini applicazione (AppDomain) consentono di isolare le app l'una dall'altra. Per gli AppDomain è necessario il supporto in fase di esecuzione e sono costosi. La creazione di domini app aggiuntivi non è supportata. Per l'isolamento del codice, è consigliabile separare i processi o usare i contenitori in alternativa. Per il caricamento dinamico degli assembly, è consigliabile utilizzare la nuova  <xref:System.Runtime.Loader.AssemblyLoadContext> classe.

Per semplificare la migrazione del codice da .NET Framework, .NET Core espone parte della superficie dell'API AppDomain. Parte della funzione API normalmente (ad esempio,  <xref:System.AppDomain.UnhandledException?displayProperty=nameWithType> ), alcuni membri non eseguono alcuna operazione (ad esempio,  <xref:System.AppDomain.SetCachePath%2A> ) e alcuni di essi generano <xref:System.PlatformNotSupportedException> (ad esempio,  <xref:System.AppDomain.CreateDomain%2A> ).

### <a name="remoting"></a>Comunicazione remota

.NET Remoting è stato usato per la comunicazione tra domini AppDomain, che non è più supportata. Per i servizi remoti è richiesto anche il supporto del runtime, costoso da gestire. Per questi motivi, .NET Remoting non è supportato in .NET Core.

Per la comunicazione tra processi, è consigliabile prendere in considerazione i meccanismi di comunicazione interprocesso (IPC) come alternativa alla comunicazione remota, ad esempio la <xref:System.IO.Pipes?displayProperty=nameWithType> <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> classe o.

Per le comunicazioni tra computer, usare una soluzione basata su rete in alternativa. Preferibilmente, usare un protocollo di testo normale con overhead ridotto, ad esempio HTTP. Il server Web Kestrel, ovvero il server Web usato da ASP.NET Core, rappresenta un'opzione praticabile in questo caso.

### <a name="code-access-security-cas"></a>Sicurezza dall'accesso di codice (CAS, Code Access Security)

Il sandboxing, che si basa sul runtime o sul Framework per vincolare le risorse utilizzate o eseguite da un'applicazione o da una libreria gestita, non è supportato in .NET Core.

Usare i limiti di sicurezza forniti dal sistema operativo, ad esempio la virtualizzazione, i contenitori o gli account utente per l'esecuzione di processi con il set minimo di privilegi.

### <a name="security-transparency"></a>Trasparenza della sicurezza

Analogamente alla sicurezza dall'accesso di codice, la trasparenza della sicurezza separa il codice in modalità sandbox dal codice critico per la sicurezza in modalità dichiarativa, ma non è più supportata come limite di sicurezza.

Usare i limiti di sicurezza forniti dal sistema operativo, ad esempio la virtualizzazione, i contenitori o gli account utente per l'esecuzione di processi con il minor set di privilegi.

>[!div class="step-by-step"]
>[Precedente](whats-new-dotnet-core.md ) 
> [Avanti](windows-migration.md)
