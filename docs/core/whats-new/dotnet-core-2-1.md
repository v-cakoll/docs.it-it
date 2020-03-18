---
title: Novità di .NET Core 2.1
description: Informazioni sulle nuove funzionalità in .NET Core 2.1.
dev_langs:
- csharp
- vb
ms.date: 10/10/2018
ms.openlocfilehash: 54ace52fc6a8f4614c1f762b65453979bcb92c7a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398867"
---
# <a name="whats-new-in-net-core-21"></a>Novità di .NET Core 2.1

.NET Core 2.1 include miglioramenti e nuove funzionalità nelle aree seguenti:

- [Strumenti](#tooling)
- [Roll forward](#roll-forward)
- [Distribuzione](#deployment)
- [Windows Compatibility Pack](#windows-compatibility-pack)
- [Miglioramenti della compilazione JIT](#jit-compiler-improvements)
- [Modifiche all'API](#api-changes)

## <a name="tooling"></a>Strumenti

.NET Core 2.1 SDK (v 2.1.300), ovvero il set di strumenti incluso in .NET Core 2.1, include le modifiche e i miglioramenti seguenti:

### <a name="build-performance-improvements"></a>Miglioramenti delle prestazioni di compilazione

Un obiettivo fondamentale di .NET Core 2.1 è il miglioramento delle prestazioni in fase di compilazione, in particolare per le compilazioni incrementali. Questi miglioramenti delle prestazioni si applicano sia alle compilazioni dalla riga di comando con `dotnet build` che alle compilazioni in Visual Studio. Alcune aree specifiche di miglioramento includono:

- Per la risoluzione degli asset dei pacchetti, risoluzione solo degli asset usati da una compilazione anziché di tutti gli asset.

- Memorizzazione nella cache dei riferimenti agli assembly.

- Uso dei server di compilazione SDK a esecuzione prolungata, ovvero processi che si estendono attraverso singole chiamate a `dotnet build`. Eliminano la necessità di compilare tramite JIT blocchi di codice di grandi dimensioni ogni volta che viene eseguito `dotnet build`. I processi del server di compilazione possono essere terminati automaticamente con il comando seguente:

   ```dotnetcli
   dotnet buildserver shutdown
   ```

### <a name="new-cli-commands"></a>Nuovi comandi dell'interfaccia della riga di comando

Numerosi strumenti precedentemente disponibili solo a livello di singolo progetto usando `DotnetCliToolReference` sono ora disponibili come parte di .NET Core SDK. Questi strumenti comprendono:

- `dotnet watch` fornisce un watcher del file system che rimane in attesa delle modifiche a un file prima di eseguire un determinato set di comandi. Ad esempio, il comando seguente ricompila automaticamente il progetto corrente e genera un output dettagliato ogni volta che viene modificato un file in esso contenuto:

   ```dotnetcli
   dotnet watch -- --verbose build
   ```

   Si noti l'opzione `--` che precede l'opzione `--verbose`. Delimita le opzioni passate direttamente al comando `dotnet watch` dagli argomenti passati al processo figlio `dotnet`. Senza di essa, l'opzione `--verbose` si applica al comando `dotnet watch` e non al comando `dotnet build`.
  
   Per ulteriori informazioni, consultate [Sviluppare app ASP.NET Core usando l'orologio dotnet.](/aspnet/core/tutorials/dotnet-watch)

- `dotnet dev-certs` genera e gestisce i certificati usati durante lo sviluppo nelle applicazioni ASP.NET Core.

- `dotnet user-secrets` gestisce i segreti in un archivio di segreti dell'utente nelle applicazioni ASP.NET Core.

- `dotnet sql-cache` crea una tabella e gli indici in un database di Microsoft SQL Server da usare per la memorizzazione nella cache distribuita.

- `dotnet ef` è uno strumento per la gestione di database, oggetti <xref:Microsoft.EntityFrameworkCore.DbContext> e migrazioni in applicazioni Entity Framework Core. Per altre informazioni, vedere [Strumenti da riga di comando di EF Core .NET](/ef/core/miscellaneous/cli/dotnet).

### <a name="global-tools"></a>Strumenti globali

.NET Core 2.1 supporta gli *strumenti globali*, vale a dire strumenti personalizzati disponibili globalmente dalla riga di comando. Il modello di estendibilità nelle versioni precedenti di .NET Core rendeva disponibili gli strumenti personalizzati a livello di singolo progetto solo usando `DotnetCliToolReference`.

Per installare uno strumento globale, usare il comando [dotnet tool install](../tools/dotnet-tool-install.md). Ad esempio:

```dotnetcli
dotnet tool install -g dotnetsay
```

Dopo l'installazione, lo strumento può essere eseguito dalla riga di comando specificando il nome dello strumento. Per altre informazioni, vedere [Panoramica degli strumenti globali .NET Core](../tools/global-tools.md).

### <a name="tool-management-with-the-dotnet-tool-command"></a>Strumento di gestione con il comando `dotnet tool`

In .NET Core 2.1 SDK tutte le operazioni con gli strumenti usano il comando `dotnet tool`. Sono disponibili le opzioni seguenti:

- [`dotnet tool install`](../tools/dotnet-tool-install.md)per installare uno strumento.

- [`dotnet tool update`](../tools/dotnet-tool-update.md)per disinstallare e reinstallare uno strumento, che lo aggiorna in modo efficace.

- [`dotnet tool list`](../tools/dotnet-tool-list.md)per elencare gli strumenti attualmente installati.

- [`dotnet tool uninstall`](../tools/dotnet-tool-uninstall.md)per disinstallare gli strumenti attualmente installati.

## <a name="roll-forward"></a>Roll forward

Di tutte le applicazioni .NET Core a partire da .NET Core 2.0 viene eseguito automaticamente il roll forward alla *versione secondaria* più recente installata in un sistema.

A partire da .NET Core 2.0, se la versione di .NET Core con cui è stata compilata un'applicazione non è presente in fase di esecuzione, l'applicazione verrà eseguita automaticamente con la *versione secondaria* installata più recente di .NET Core. In altre parole, se un'applicazione è compilata con .NET Core 2.0 e .NET Core 2.0 non è presente nel sistema host ma .NET Core 2.1 lo è, l'applicazione verrà eseguita con .NET Core 2.1.

> [!IMPORTANT]
> Questo comportamento di roll forward non si applica alle versioni di anteprima, Per impostazione predefinita, non si applica nemmeno alle versioni principali, ma il comportamento si può modificare con le impostazioni seguenti.

Per modificare questo comportamento, cambiare l'impostazione per il roll forward scegliendo di non eseguirlo su framework condiviso candidato. Le impostazioni disponibili sono:

- `0` - Disabilitare il comportamento del roll forward per la versione secondaria. Con questa impostazione, un'applicazione creata per .NET Core 2.0.0 esegue il roll forward a .NET Core 2.0.1, ma non a .NET Core 2.2.0 o .NET Core 3.0.0.
- `1` - Abilitare il comportamento del roll forward per la versione secondaria. Questo è il valore predefinito per l'impostazione. Con questa impostazione, un'applicazione creata per .NET Core 2.0.0 esegue il roll forward a .NET Core 2.0.1 o a .NET Core 2.2.0, a seconda di quale dei due è installato, ma non a .NET Core 3.0.0.
- `2` - Abilitare il comportamento del roll forward per le versioni principale e secondaria. Se impostata, vengono considerate anche diverse versioni principali, in modo che un'applicazione compilata per .NET Core 2.0.0 esegua il roll forward a .NET Core 3.0.0.

È possibile modificare questa impostazione in tre modi:

- Impostare la variabile di ambiente `DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX` su un valore.

- Aggiungere la riga seguente con il valore desiderato al file *.runtimeconfig.json*:

   ```json
   "rollForwardOnNoCandidateFx" : 0
   ```

- Quando si utilizza l'interfaccia della riga di comando [di .NET](../tools/index.md)Core `run`, aggiungere l'opzione seguente con il valore desiderato a un comando .NET Core, ad esempio :

   ```dotnetcli
   dotnet run --rollForwardOnNoCandidateFx=0
   ```

Il roll forward della versione della patch è indipendente da questa impostazione e viene eseguito dopo gli eventuali roll forward della versione principale o secondaria.

## <a name="deployment"></a>Distribuzione

### <a name="self-contained-application-servicing"></a>Manutenzione di un'applicazione autonoma

`dotnet publish` pubblica ora applicazioni autonome con una versione runtime servita. Quando si pubblica un'applicazione autonoma con .NET Core 2.1 SDK (v 2.1.300), l'applicazione include l'ultima versione runtime servita conosciuta da tale SDK. Quando si esegue l'aggiornamento all'SDK più recente, si pubblicherà con la versione di runtime di .NET Core più recente. Questo vale per i runtime di .NET Core 1.0 e versioni successive.

La pubblicazione autonoma si basa sulle versioni di runtime in NuGet.org. Non è necessario disporre del runtime servito nel computer.

Tramite .NET Core 2.0 SDK, le applicazioni autonome sono pubblicate con il runtime .NET Core 2.0.0, a meno che non venga specificata un'altra versione tramite la proprietà `RuntimeFrameworkVersion`. Con questo nuovo comportamento, non sarà più necessario impostare questa proprietà per selezionare una versione di runtime superiore per un'applicazione autonoma. L'approccio più semplice in futuro consiste nel pubblicare sempre con .NET Core 2.1 SDK (v 2.1.300).

Per altre informazioni, vedere [Roll forward del runtime di distribuzione autonoma](../deploying/runtime-patch-selection.md).
## <a name="windows-compatibility-pack"></a>Windows Compatibility Pack

Quando si porta il codice esistente da .NET Framework a .NET Core, è possibile usare [Windows Compatibility Pack](https://www.nuget.org/packages/Microsoft.Windows.Compatibility), che garantisce l'accesso a 20.000 API in più rispetto a quelle disponibili in .NET Core. Queste API includono tipi nello spazio dei nomi <xref:System.Drawing?displayProperty=nameWithType>, la classe <xref:System.Diagnostics.EventLog>, WMI, contatori delle prestazioni, servizi di Windows e tipi e membri del Registro di sistema di Windows.

## <a name="jit-compiler-improvements"></a>Miglioramenti del compilatore JIT

.NET Core include una nuova tecnologia del compilatore JIT denominata *compilazione a livelli* (nota anche come *ottimizzazione adattiva*) che può migliorare significativamente le prestazioni. La compilazione a livelli è un'impostazione che prevede il consenso esplicito.

Una delle attività importanti eseguite dal compilatore JIT è l'ottimizzazione dell'esecuzione del codice. Per i percorsi del codice poco usati, tuttavia, il compilatore può richiedere più tempo per l'ottimizzazione del codice rispetto a quanto impiegato dal runtime per l'esecuzione del codice non ottimizzato. La compilazione a livelli introduce due fasi nella compilazione JIT:

- Un **primo livello**, che genera il codice il più rapidamente possibile.

- Un **secondo livello**, che genera codice ottimizzato per i metodi che vengono eseguiti frequentemente. Il secondo livello di compilazione viene eseguito in parallelo per prestazioni migliorate.

È possibile acconsentire esplicitamente alla compilazione a livelli in uno dei due modi seguenti.

- Per usare la compilazione a livelli in tutti i progetti che usano .NET Core 2.1 SDK, impostare la variabile di ambiente seguente:

  ```console
  COMPlus_TieredCompilation="1"
  ```

- Per usare la compilazione a livelli in base al progetto, aggiungere la proprietà `<TieredCompilation>` alla sezione `<PropertyGroup>` del file di progetto MSBuild, come illustrato nell'esempio seguente:

   ```xml
   <PropertyGroup>
      <!-- other property definitions -->

      <TieredCompilation>true</TieredCompilation>
   </PropertyGroup>
   ```

## <a name="api-changes"></a>Modifiche all'API

### <a name="spant-and-memoryt"></a>`Span<T>` e `Memory<T>`

.NET Core 2.1 include alcuni nuovi tipi che rendono molto più efficiente l'uso di matrici e altri tipi di memoria. I nuovi tipi includono:

- <xref:System.Span%601?displayProperty=nameWithType> e <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>.

- <xref:System.Memory%601?displayProperty=nameWithType> e <xref:System.ReadOnlyMemory%601?displayProperty=nameWithType>.

Senza questi tipi, quando si passano elementi quali una parte di una matrice o una sezione di un buffer di memoria, è necessario creare una copia di una parte dei dati prima di passarli a un metodo. Questi tipi forniscono una visualizzazione virtuale dei dati che elimina la necessità di un'allocazione di memoria e di operazioni di copia aggiuntive.

L'esempio seguente usa un'istanza <xref:System.Span%601> e un'istanza <xref:System.Memory%601> per fornire una visualizzazione virtuale di 10 elementi di una matrice.

[!code-csharp[Span\<T>](~/samples/snippets/core/whats-new/whats-new-in-21/csharp/program.cs)]

[!code-vb[Memory\<T>](~/samples/snippets/core/whats-new/whats-new-in-21/vb/program.vb)]

### <a name="brotli-compression"></a>Compressione Brotli

.NET Core 2.1 aggiunge il supporto per la compressione e la decompressione Brotli. Brotli è un algoritmo di compressione generico senza perdita di dati definito in [RFC 7932](https://www.ietf.org/rfc/rfc7932.txt) e supportato dalla maggior parte dei Web browser e dai principali server Web. È possibile usare la classe <xref:System.IO.Compression.BrotliStream?displayProperty=nameWithType> basata sul flusso o le classi <xref:System.IO.Compression.BrotliEncoder?displayProperty=nameWithType> e <xref:System.IO.Compression.BrotliDecoder?displayProperty=nameWithType> basate sull'intervallo a prestazioni elevate. L'esempio seguente illustra la compressione con la classe <xref:System.IO.Compression.BrotliStream>:

[!code-csharp[Brotli compression](~/samples/snippets/core/whats-new/whats-new-in-21/csharp/brotli.cs#1)]

[!code-vb[Brotli compression](~/samples/snippets/core/whats-new/whats-new-in-21/vb/brotli.vb#1)]

Il comportamento di <xref:System.IO.Compression.BrotliStream> è lo stesso di <xref:System.IO.Compression.DeflateStream> e <xref:System.IO.Compression.GZipStream>, che rende più facile convertire il codice che chiama queste API in <xref:System.IO.Compression.BrotliStream>.

### <a name="new-cryptography-apis-and-cryptography-improvements"></a>Nuove API di crittografia e miglioramenti della crittografia

.NET Core 2.1 include numerosi miglioramenti alle API di crittografia:

- <xref:System.Security.Cryptography.Pkcs.SignedCms?displayProperty=nameWithType> è disponibile nel pacchetto System.Security.Cryptography.Pkcs. L'implementazione è la stessa della classe <xref:System.Security.Cryptography.Pkcs.SignedCms> in .NET Framework.

- I nuovi overload dei metodi <xref:System.Security.Cryptography.X509Certificates.X509Certificate.GetCertHash%2A?displayProperty=nameWithType> e <xref:System.Security.Cryptography.X509Certificates.X509Certificate.GetCertHashString%2A?displayProperty=nameWithType> accettano un identificatore dell'algoritmo hash per consentire ai chiamanti di ottenere i valori di identificazione personale dei certificati usando algoritmi diversi da SHA-1.

- Le nuove API di crittografia basate su <xref:System.Span%601> sono disponibili per hashing, HMAC, generazione casuale di numeri crittografici, generazione di firma asimmetrica, elaborazione di firma asimmetrica e crittografia RSA.

- Le prestazioni di <xref:System.Security.Cryptography.Rfc2898DeriveBytes?displayProperty=nameWithType> risultano migliorate del 15% circa con un'implementazione basata su <xref:System.Span%601>.

- La nuova classe <xref:System.Security.Cryptography.CryptographicOperations?displayProperty=nameWithType> include due nuovi metodi:

  - <xref:System.Security.Cryptography.CryptographicOperations.FixedTimeEquals%2A> richiede una quantità fissa di tempo per restituire uno tra due input della stessa lunghezza, pertanto è appropriato per l'uso nella verifica crittografica per evitare di contribuire alle informazioni side-channel sulla durata.

  - <xref:System.Security.Cryptography.CryptographicOperations.ZeroMemory%2A> è una routine di cancellazione della memoria che non può essere ottimizzata.

- Il metodo statico <xref:System.Security.Cryptography.RandomNumberGenerator.Fill%2A?displayProperty=nameWithType> riempie un <xref:System.Span%601> con valori casuali.

- Il <xref:System.Security.Cryptography.Pkcs.EnvelopedCms?displayProperty=nameWithType> è ora supportato su Linux e macOS.

- Diffie-Hellman a curva ellittica (ECDH) è ora disponibile nella famiglia di classi <xref:System.Security.Cryptography.ECDiffieHellman?displayProperty=nameWithType>. La superficie di attacco è uguale a quella di .NET Framework.

- L'istanza restituita da <xref:System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType> può eseguire la crittografia o la decrittografia con OAEP usando un digest SHA-2, nonché generare o convalidare firme con RSA-PSS.

### <a name="sockets-improvements"></a>Miglioramenti del socket

.NET Core include un nuovo tipo, <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType>, e un tipo <xref:System.Net.Http.HttpMessageHandler?displayProperty=nameWithType> riscritto, che costituiscono la base delle API di rete di livello superiore.  <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType>, ad esempio, è la base dell'implementazione di <xref:System.Net.Http.HttpClient>. Nelle versioni precedenti di .NET Core le API di livello superiore si basavano su implementazioni di rete native.

L'implementazione dei socket introdotta in .NET Core 2.1 comporta numerosi vantaggi:

- Miglioramento significativo delle prestazioni rispetto all'implementazione precedente.

- Eliminazione delle dipendenze della piattaforma, con una conseguente semplificazione della distribuzione e della manutenzione.

- Comportamento coerente in tutte le piattaforme .NET Core.

<xref:System.Net.Http.SocketsHttpHandler> è l'implementazione predefinita in .NET Core 2.1. Tuttavia, è possibile configurare l'applicazione per usare la classe <xref:System.Net.Http.HttpClientHandler> precedente chiamando il metodo <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>:

```csharp
AppContext.SetSwitch("System.Net.Http.UseSocketsHttpHandler", false);
```

```vb
AppContext.SetSwitch("System.Net.Http.UseSocketsHttpHandler", False)
```

È anche possibile usare una variabile di ambiente per rifiutare esplicitamente l'uso di implementazioni dei socket basate su <xref:System.Net.Http.SocketsHttpHandler>. A tale scopo, impostare `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` su `false` o su 0.

In Windows è anche possibile scegliere di usare <xref:System.Net.Http.WinHttpHandler?displayProperty=nameWithType>, che si basa su un'implementazione nativa, o la classe <xref:System.Net.Http.SocketsHttpHandler> passando un'istanza della classe al costruttore <xref:System.Net.Http.HttpClient>.

In Linux e macOS è possibile configurare <xref:System.Net.Http.HttpClient> solo in base al processo. In Linux è necessario distribuire [libcurl](https://curl.haxx.se/libcurl/) se si vuole usare l'implementazione precedente di <xref:System.Net.Http.HttpClient> (installato con .NET Core 2.0).

### <a name="breaking-changes"></a>Modifiche di rilievo

Per informazioni sulle modifiche di rilievo, vedere [Modifiche di rilievo per la migrazione dalla versione 2.0 alla 2.1](../compatibility/2.0-2.1.md).

## <a name="see-also"></a>Vedere anche

- [Novità di .NET Core](index.md)
- [Nuove funzionalità di EF Core 2.1](/ef/core/what-is-new/ef-core-2.1)
- [Novità di ASP.NET Core 2.1](/aspnet/core/aspnetcore-2.1)
