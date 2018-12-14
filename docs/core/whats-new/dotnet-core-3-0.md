---
title: Novità di .NET Core 3.0
description: Informazioni sulle nuove funzionalità in .NET Core 3.0.
dev_langs:
- csharp
- vb
author: thraka
ms.author: adegeo
ms.date: 12/04/2018
ms.openlocfilehash: 3ca833031eb8bb0f43a334f833f2e0075842d57d
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53156669"
---
# <a name="whats-new-in-net-core-30-preview-1"></a>Novità di .NET Core 3.0 (Preview 1)

Questo articolo descrive le novità di .NET Core 3.0 (Preview 1). Uno dei principali miglioramenti è il supporto per le applicazioni desktop di Windows (solo Windows). Utilizzando un componente di .NET Core 3.0 denominato Windows Desktop, è possibile convertire le applicazioni WPF (Windows Presentation Foundation) Windows Form. Il componente Windows Desktop è dunque supportato solo in Windows. Per altre informazioni, vedere la sezione [Desktop di Windows](#windows-desktop) riportata di seguito.

.NET Core 3.0 aggiunge il supporto per C# 8.0.

[Scaricare e iniziare subito a usare .NET Core 3 Preview 1](https://aka.ms/netcore3download) in Windows, Mac e Linux. È possibile visualizzare i dettagli completi della versione nelle [note sulla versione di .NET Core 3 Preview 1](https://aka.ms/netcore3releasenotes).

Per altre informazioni, vedere l'[annuncio relativo a .NET Core 3.0 Preview 1](https://blogs.msdn.microsoft.com/dotnet/2018/12/04/announcing-net-core-3-preview-1-and-open-sourcing-windows-desktop-frameworks/).

## <a name="net-standard-21"></a>.NET Standard 2.1

.NET Core 3.0 implementa .NET Standard 2.1.

## <a name="default-executables"></a>File eseguibili predefiniti

.NET Core compilerà ora i file eseguibili per impostazione predefinita. Si tratta di una novità per le applicazioni che usano una versione di .NET Core installata a livello globale. Finora solo le [distribuzioni autonome](../deploying/index.md#self-contained-deployments-scd) avevano file eseguibili.

Durante `dotnet build` o `dotnet publish`, viene creato un file eseguibile purché corrisponda all'ambiente e alla piattaforma dell'SDK usato. Il comportamento di questi file eseguibili è uguale a quello degli altri file eseguibili nativi, ad esempio:

* È possibile fare doppio clic sul file eseguibile.
* È possibile avviare l'applicazione direttamente da un prompt dei comandi, ad esempio `myapp.exe` in Windows e `./myapp` in Linux e macOS.

> [!NOTE]
> Non è supportata la specifica di un determinato runtime con gli argomenti `dotnet publish -r` o `dotnet build -r` per gli altri ambienti di runtime.

## <a name="build-copies-dependencies"></a>Copia delle dipendenze tramite la compilazione

`dotnet build` ora copia le dipendenze NuGet per l'applicazione dalla cache NuGet alla cartella di output per la compilazione. In precedenza, le dipendenze venivano copiate solo come parte di `dotnet publish`. 

Esistono alcune operazioni, ad esempio il collegamento e la pubblicazione della pagina razor per cui sarà comunque necessaria la pubblicazione.


## <a name="local-dotnet-tools"></a>Strumenti dotnet locali

Mentre .NET Core 2.1 supportava strumenti globali, .NET Core 3.0 ha ora strumenti locali. Gli strumenti locali sono simili agli strumenti globali, ma sono associati a una determinata posizione sul disco. Ciò consente di usare strumenti specifici per ogni progetto e ogni repository. Gli strumenti installati in locale non sono disponibili a livello globale.

Gli strumenti locali si basano sul nome file manifesto `dotnet-tools.json` nella directory corrente. Questo file manifesto definisce gli strumenti che devono essere disponibili. Creando questo file manifesto nella radice del repository, si ha la certezza che chiunque cloni il codice non possa ripristinare e usare gli strumenti necessari per lavorare in modo corretto con il codice.

Quando il file manifesto degli strumenti locali è disponibile, usare il comando seguente per scaricare e installare automaticamente tali strumenti in locale:

```console
dotnet tool restore
```

Eseguire uno strumento locale con il comando seguente:

```console
dotnet tool run <tool-command-name>
```

Quando viene chiamato uno strumento locale, dotnet cerca un manifesto nella struttura di directory. Quando viene trovato un file manifesto degli strumenti, viene eseguita la ricerca dello strumento richiesto. Lo strumento, se trovato, include le informazioni necessarie per trovare lo strumento nel percorso globale dei pacchetti NuGet. 

Se lo strumento viene trovato nel manifesto, ma non la cache, l'utente visualizza un errore. Il messaggio verrà migliorato dopo l'anteprima 1 per chiedere all'utente di eseguire `dotnet tool restore`.

Per aggiungere gli strumenti locali a una directory, è necessario creare prima il file manifesto degli strumenti. Dopo l'anteprima 1, sarà disponibile un meccanismo per la creazione di file manifesto degli strumenti, ad esempio un nuovo modello dotnet. Per l'anteprima 1 è necessario creare il file denominato `dotnet-tools.json` con il contenuto seguente:

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {}
}
```

Dopo aver creato il manifesto, è possibile aggiungere gli strumenti locali usando:

```console
dotnet tool install <toolPackageId>
```

Questo comando installa la versione più recente dello strumento, a meno che non venga specificata un'altra versione.  Anche se è stata scelta automaticamente la versione più recente, la versione dello strumento viene scritta nel file manifesto dello strumento per consentire il ripristino o l'esecuzione della versione corretta dello strumento.

Il file manifesto dello strumento è progettato per consentire la modifica manuale, ad esempio per aggiornare la versione necessaria per usare il repository.

Ecco un file `dotnet-tools.json` di esempio:

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {
    "dotnetsay": {
      "version": "2.1.4",
      "commands": [
        "dotnetsay"
      ]
    },
    "t-rex": {
      "version": "1.0.103",
      "commands": [
        "t-rex"
      ]
    }
  }
}
```

Per rimuovere uno strumento dal file manifesto, eseguire il comando seguente:

```console
dotnet tool uninstall <toolPackageId>
```

Per gli strumenti sia locali che globali, è necessaria una versione compatibile del runtime. Molti strumenti attualmente presenti su NuGet.org hanno come destinazione .NET Core Runtime 2.1. Per installarli a livello globale o locale, è ancora necessario installare il [runtime di NET Core 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1).

Per altre informazioni, vedere [Local Tools Early Preview Documentation](https://github.com/dotnet/cli/issues/10288) (Documentazione dell'anteprima preliminare degli strumenti locali).

## <a name="windows-desktop"></a>Desktop di Windows

A partire da .NET Core 3.0 Preview 1, è possibile compilare applicazioni desktop di Windows con WPF e Windows Form. Questi framework supportano anche l'uso di controlli moderni e dello stile Fluent dalla libreria XAML dell'interfaccia utente di Windows tramite [isole XAML](/windows/uwp/xaml-platform/xaml-host-controls).

Il componente Windows Desktop fa parte di Windows .NET Core 3.0 SDK.

È possibile creare una nuova app WPF o Windows Form con i comandi `dotnet` seguenti:

```console
dotnet new wpf
dotnet new winforms
```

È anche possibile aprire, avviare ed eseguire il debug di progetti .NET Core 3.0 WPF e Windows Form in Visual Studio 2019 Preview 1. Anche se attualmente è possibile aprire questi progetti in Visual Studio 2017 15.9, questo non è uno scenario supportato (ed è necessario [abilitare le anteprime](https://blogs.msdn.microsoft.com/dotnet/2018/11/13/net-core-tooling-update-for-visual-studio-2017-version-15-9/)).

I nuovi progetti sono uguali ai progetti .NET Core esistenti, con alcune aggiunte. Di seguito è riportato il confronto tra il progetto console .NET Core di base e un progetto Windows Form e WPF di base.

In un progetto console .NET Core il progetto usa l'SDK `Microsoft.NET.Sdk` e dichiara una dipendenza da .NET Core 3.0 tramite il framework di destinazione `netcoreapp3.0`. Per creare un'app desktop di Windows, usare l'SDK `Microsoft.NET.Sdk.WindowsDesktop` e scegliere quale framework interfaccia utente usare:

```diff
-<Project Sdk="Microsoft.NET.Sdk">
+<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
+   <UseWPF>true</UseWPF>
  </PropertyGroup>
</Project>
```

Per scegliere Windows Form invece di WPF, impostare `UseWindowsForms` invece che `UseWPF`:

```diff
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
-   <UseWPF>true</UseWPF>
+   <UseWindowsForms>true</UseWindowsForms>
  </PropertyGroup>
</Project>
```

Sia `UseWPF` che `UseWindowsForms` possono essere impostati su `true` se l'app usa entrambi i framework, ad esempio quando una finestra di dialogo di Windows Form ospita un controllo WPF.

Condividere commenti e suggerimenti nei repository [dotnet/winforms](https://github.com/dotnet/winforms/issues), [dotnet/wpf](https://github.com/dotnet/wpf/issues) e [dotnet/core](https://github.com/dotnet/core/issues).

## <a name="fast-built-in-json-support"></a>Supporto JSON predefinito rapido

`System.Text.Json.Utf8JsonReader` è un lettore forward-only a prestazioni elevate e allocazione ridotta per il testo JSON con codifica UTF-8, letto da `ReadOnlySpan<byte>`. `Utf8JsonReader` è un tipo di base di basso livello, che può essere sfruttato per compilare parser e deserializzatori personalizzati. La lettura di un payload JSON con il nuovo `Utf8JsonReader` è due volte più veloce che con il lettore di [Json.NET](https://www.newtonsoft.com/json). Non viene allocato fino a quando non è necessario realizzare i token JSON come stringhe (UTF-16).

Questa nuova API includerà i componenti seguenti:

* Nell'anteprima 1: lettore JSON (accesso sequenziale)
* Presto disponibili: writer JSON, DOM (accesso casuale), serializzatore poco, deserializzatore poco

Ecco il ciclo del lettore di base per `Utf8JsonReader` che può essere usato come punto iniziale:

```csharp
using System.Text.Json;

public static void Utf8JsonReaderLoop(ReadOnlySpan<byte> dataUtf8)
{
    var json = new Utf8JsonReader(dataUtf8, isFinalBlock: true, state: default);

    while (json.Read())
    {
        JsonTokenType tokenType = json.TokenType;
        ReadOnlySpan<byte> valueSpan = json.ValueSpan;
        switch (tokenType)
        {
            case JsonTokenType.StartObject:
            case JsonTokenType.EndObject:
                break;
            case JsonTokenType.StartArray:
            case JsonTokenType.EndArray:
                break;
            case JsonTokenType.PropertyName:
                break;
            case JsonTokenType.String:
                string valueString = json.GetStringValue();
                break;
            case JsonTokenType.Number:
                if (!json.TryGetInt32Value(out int valueInteger))
                {
                    throw new FormatException();
                }
                break;
            case JsonTokenType.True:
            case JsonTokenType.False:
                bool valueBool = json.GetBooleanValue();
                break;
            case JsonTokenType.Null:
                break;
            default:
                throw new ArgumentException();
        }
    }

    dataUtf8 = dataUtf8.Slice((int)json.BytesConsumed);
    JsonReaderState state = json.CurrentState;
}
```

L'ecosistema .NET si è basato su [Json.NET](https://www.newtonsoft.com/json) e altre librerie JSON molto diffuse, che rimangono sempre scelte valide. Come tipo di dati di base JSON.NET usa le stringhe .NET, che in realtà sono UTF-16. 

In .NET Core 2.1 e 3.0 sono state aggiunte nuove API per poter scrivere API JSON (ad esempio, `Utf8JsonReader`) che richiedono molta meno memoria, in base sull'uso di stringhe UTF-8 e `Span<T>`, e soddisfano meglio le esigenze delle applicazioni a velocità effettiva elevata, come Kestrel, il server Web ASP.NET Core.

## <a name="ranges-and-indices"></a>Gli intervalli e indici

Il nuovo tipo `Index` può essere usato per l'indicizzazione. È possibile crearne uno da `int`, che esegue il conteggio dall'inizio, o con un operatore prefisso `^` (C#), che esegue il conteggio dalla fine:

```csharp
Index i1 = 3;  // number 3 from beginning
Index i2 = ^4; // number 4 from end
int[] a = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
Console.WriteLine($"{a[i1]}, {a[i2]}"); // "3, 6"
```

Esiste anche un tipo `Range`, costituito da due valori `Index`, uno per l'inizio e uno per la fine, che può essere scritto con un'espressione intervallo `x..y` (C#). È quindi possibile eseguire l'indicizzazione con `Range` per generare una sezione:

```csharp
var slice = a[i1..i2]; // { 3, 4, 5 }
```

> [!NOTE]
> Solo [C# 8.0](https://blogs.msdn.microsoft.com/dotnet/2018/11/12/building-c-8-0/) supporta la sintassi per `Range` e `Index`.

## <a name="async-streams"></a>Flussi asincroni

Il tipo `IAsyncEnumerable<T>` è una nuova versione asincrona di `IEnumerable<T>`. Il linguaggio consente di usare `await foreach` su questi tipi per utilizzarne gli elementi e di usare `yield return` per generare gli elementi.

L'esempio seguente illustra sia la produzione che l'utilizzo dei flussi asincroni. L'istruzione `foreach` è asincrona e usa `yield return` per produrre un flusso asincrono per i chiamanti. Questo modello (con `yield return`) è quello consigliato per la produzione di flussi asincroni.

```csharp
async IAsyncEnumerable<int> GetBigResultsAsync()
{
    await foreach (var result in GetResultsAsync())
    {
        if (result > 20) yield return result; 
    }
}
```

> [!WARNING]
> .NET Core 3.0 Preview 1 presenta attualmente un bug relativo a `await foreach`. Usare invece `GetEnumerator` e `MoveNext` per elaborare gli elementi. Per altre informazioni, vedere [roslyn/#31268](https://github.com/dotnet/roslyn/issues/31268).

Oltre a poter usare `await foreach`, è anche possibile creare iteratori asincroni, ad esempio un iteratore che restituisce `IAsyncEnumerable/IAsyncEnumerator` in cui è possibile usare sia `await` che `yield`. Per gli oggetti che devono essere eliminati, è possibile usare `IAsyncDisposable`, implementato da diversi tipi BCL, ad esempio `Stream` e `Timer`.

> [!NOTE]
> Solo [C# 8.0](https://blogs.msdn.microsoft.com/dotnet/2018/11/12/building-c-8-0/) supporta la sintassi `await foreach`.

## <a name="type-sequencereader"></a>Tipo: SequenceReader

In .NET Core 3.0 è stato aggiunto `System.Buffers.SequenceReader` che può essere usato come lettore per `ReadOnlySequence<T>`. Ciò consente un'analisi semplice, a prestazioni elevate e allocazione ridotta dei dati di `System.IO.Pipelines` che possono attraversare più buffer sottostanti. 

L'esempio seguente suddivide un elemento `Sequence` di input in righe delimitate da `CR/LF` valide:

```csharp
private static ReadOnlySpan<byte> CRLF => new byte[] { (byte)'\r', (byte)'\n' };

public static void ReadLines(ReadOnlySequence<byte> sequence)
{
    SequenceReader<byte> reader = new SequenceReader<byte>(sequence);

    while (!reader.End)
    {
        if (!reader.TryReadToAny(out ReadOnlySpan<byte> line, CRLF, advancePastDelimiter:false))
        {
            // Couldn't find another delimiter
            // ...
        }

        if (!reader.IsNext(CRLF, advancePast: true))
        {
            // Not a good CR/LF pair
            // ...
        }

        // line is valid, process
        ProcessLine(line);
    }
}
```

## <a name="type-metadataloadcontext"></a>Tipo: MetadataLoadContext

È stato aggiunto il tipo `MetadataLoadContext` che consente la lettura dei metadati dell'assembly senza impatto sul dominio dell'applicazione del chiamante. Gli assembly vengono letti come dati, inclusi gli assembly compilati per architetture e piattaforme diverse da quelle dell'ambiente di runtime corrente. `MetadataLoadContext` si sovrappone a <xref:System.Reflection.Assembly.ReflectionOnlyLoad*>, che è disponibile solo in .NET Framework.

`MetdataLoadContext` è disponibile nel pacchetto [System.Reflection.MetadataLoadContext](https://www.nuget.org/packages/System.Reflection.MetadataLoadContext). Si tratta di un pacchetto .NET Standard 2.0.

`MetadataLoadContext` espone API simili al tipo <xref:System.Runtime.Loader.AssemblyLoadContext>, ma non si basa su tale tipo. In modo analogo a <xref:System.Runtime.Loader.AssemblyLoadContext>, `MetadataLoadContext` consente il caricamento degli assembly all'interno di un universo di caricamento di assembly isolato. Le API `MetdataLoadContext` restituiscono oggetti <xref:System.Reflection.Assembly>, consentendo l'uso di API di reflection familiari. Le API orientate all'esecuzione, ad esempio [MethodBase.Invoke](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/src/System/Reflection/TypeLoading/Methods/RoMethod.cs#L127), non sono consentite e genereranno l'eccezione InvalidOperationException.

L'esempio seguente illustra come trovare tipi concreti in un assembly che implementa una determinata interfaccia:

```csharp
var paths = new string[] {@"C:\myapp\mscorlib.dll", @"C:\myapp\myapp.dll"};
var resolver = new PathAssemblyResolver(paths);
using (var lc = new MetadataLoadContext(resolver))
{
    Assembly a = lc.LoadFromAssemblyName("myapp");
    Type myInterface = a.GetType("MyApp.IPluginInterface");
    foreach (Type t in a.GetTypes())
    {
        if (t.IsClass && myInterface.IsAssignableFrom(t))
            Console.WriteLine($"Class {t.FullName} implements IPluginInterface");
    }
}
```

Gli scenari per `MetadataLoadContext` includono funzionalità della fase di progettazione, strumenti della fase di compilazione e funzionalità esclusive di runtime che devono esaminare un set di assembly come dati e i cui blocchi di file e la cui memoria vengono liberati dopo l'esecuzione dell'ispezione.

`MetadataLoadContext` ha una classe resolver passata al costruttore. Il processo del resolver consiste nel caricare un `Assembly`, dato il relativo `AssemblyName`. La classe resolver deriva dalla classe astratta `MetadataAssemblyResolver`. Con `PathAssemblyResolver` viene fornita un'implementazione del resolver per gli scenari basati sul percorso.

I [test di MetadataLoadContext](https://github.com/dotnet/corefx/tree/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests) illustrano numerosi casi d'uso. I [test di Assembly](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests/Assembly/AssemblyTests.cs) sono un buon punto di partenza.

## <a name="tls-13--openssl-111-on-linux"></a>TLS 1.3 e OpenSSL 1.1.1 in Linux

.NET Core sfrutterà ora il [supporto di TLS 1.3 in OpenSSL 1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/), quando è disponibile in un determinato ambiente. I vantaggi di TLS 1.3 sono diversi, secondo il [team di OpenSSL](https://www.openssl.org/blog/blog/2018/09/11/release111/):

* Durata della connessione migliorata grazie alla riduzione del numero di round trip necessari tra il client e il server.

* Maggiore sicurezza grazie alla rimozione di algoritmi di crittografia obsoleti e non sicuri e alla crittografia di più elementi dell'handshake della connessione.

.NET Core 3.0 Preview 1 può utilizzare **OpenSSL 1.1.1**, **OpenSSL 1.1.0** o **OpenSSL 1.0.2** (a seconda della versione migliore trovata, in un sistema Linux).  Quando **OpenSSL 1.1.1** è disponibile, i tipi SslStream e HttpClient useranno **TLS 1.3** quando si usa `SslProtocols.None` (protocolli predefiniti di sistema), presupponendo che sia il client che il server supportino **TLS 1.3**.

L'esempio seguente illustra .NET Core 3.0 Preview 1 in Ubuntu 18.10 che si connette a <https://www.cloudflare.com>:

```csharp
using System;
using System.Net.Security;
using System.Net.Sockets;
using System.Threading.Tasks;

namespace tlstest
{
    class Program
    {
        static async Task Main()
        {
            using (TcpClient tcpClient = new TcpClient())
            {
                string targetHost = "www.cloudflare.com";

                await tcpClient.ConnectAsync(targetHost, 443);

                using (SslStream sslStream = new SslStream(tcpClient.GetStream()))
                {
                    await sslStream.AuthenticateAsClientAsync(targetHost);
                    await Console.Out.WriteLineAsync($"Connected to {targetHost} with {sslStream.SslProtocol}");
                }
            }
        }
    }
}
```

```console
user@comp-ubuntu1810:~/tlstest$ dotnet run
Connected to www.cloudflare.com with Tls13
user@comp-ubuntu1810:~/tlstest$ openssl version
OpenSSL 1.1.1  11 Sep 2018
```

>[!IMPORTANT]
>Windows e macOS non supportano ancora **TLS 1.3**. .NET Core 3.0 supporterà **TLS 1.3** in questi sistemi operativi quando il supporto sarà disponibile.

## <a name="cryptography"></a>Crittografia

È stato aggiunto il supporto per le modalità di crittografia **AES-GCM** e **AES-CCM**, implementate tramite `System.Security.Cryptography.AesGcm` e `System.Security.Cryptography.AesCcm`. Questi algoritmi sono entrambi [algoritmi di cifratura autenticata con dati di associazione](https://en.wikipedia.org/wiki/Authenticated_encryption) nonché i primi algoritmi di cifratura autenticata aggiunti a .NET Core.

Il codice seguente illustra l'uso della modalità di crittografia **AesGcm** per crittografare e decrittografare dati casuali.

Il codice per **AesCcm** sarà pressoché identico, con la sola differenza dei nomi di variabile di classe.

```csharp
// key should be: pre-known, derived, or transported via another channel, such as RSA encryption
byte[] key = new byte[16];
RandomNumberGenerator.Fill(key);

byte[] nonce = new byte[12];
RandomNumberGenerator.Fill(nonce);

// normally this would be your data
byte[] dataToEncrypt = new byte[1234];
byte[] associatedData = new byte[333];
RandomNumberGenerator.Fill(dataToEncrypt);
RandomNumberGenerator.Fill(associatedData);

// these will be filled during the encryption
byte[] tag = new byte[16];
byte[] ciphertext = new byte[dataToEncrypt.Length];

using (AesGcm aesGcm = new AesGcm(key))
{
    aesGcm.Encrypt(nonce, dataToEncrypt, ciphertext, tag, associatedData);
}

// tag, nonce, ciphertext, associatedData should be sent to the other part

byte[] decryptedData = new byte[ciphertext.Length];

using (AesGcm aesGcm = new AesGcm(key))
{
    aesGcm.Decrypt(nonce, ciphertext, tag, decryptedData, associatedData);
}

// do something with the data
// this should always print that data is the same
Console.WriteLine($"AES-GCM: Decrypted data is{(dataToEncrypt.SequenceEqual(decryptedData) ? "the same as" : "different than")} original data.");
```

## <a name="cryptographic-key-importexport"></a>Importazione/Esportazione di chiavi crittografiche

.NET core 3.0 Preview 1 supporta l'importazione e l'esportazione di chiavi pubbliche e private asimmetriche dai formati standard, senza bisogno usare un certificato X.509.

Tutti i tipi di chiavi (RSA, DSA, ECDsa, ECDiffieHellman) supportano il formato **X.509 SubjectPublicKeyInfo** per le chiavi pubbliche e i formati **PKCS#8 PrivateKeyInfo** e **PKCS#8 EncryptedPrivateKeyInfo** per le chiavi private. RSA supporta anche **PKCS#1 RSAPublicKey** e **PKCS#1 RSAPrivateKey**. Tutti i metodi di esportazione producono dati binari con codifica DER e i metodi di importazione presentano lo stesso comportamento. Se una chiave viene archiviata nel formato PEM per il testo, il chiamante dovrà applicare la decodifica Base 64 al contenuto prima di chiamare un metodo di importazione.

```csharp
using System;
using System.IO;
using System.Security.Cryptography;

namespace rsakeyprint
{
    class Program
    {
        static void Main(string[] args)
        {
            using (RSA rsa = RSA.Create())
            {
                byte[] keyBytes = File.ReadAllBytes(args[0]);
                rsa.ImportRSAPrivateKey(keyBytes, out int bytesRead);
 
                Console.WriteLine($"Read {bytesRead} bytes, {keyBytes.Length-bytesRead} extra byte(s) in file.");
                RSAParameters rsaParameters = rsa.ExportParameters(true);
                Console.WriteLine(BitConverter.ToString(rsaParameters.D));
            }
        }
    }
}
```

```console
user@comp-ubuntu1810:~/rsakeyprint$ echo Making a small key to save on screen space.
Making a small key to save on screen space.
user@comp-ubuntu1810:~/rsakeyprint$ openssl genrsa 768 | openssl rsa -outform der -out rsa.key
Generating RSA private key, 768 bit long modulus (2 primes)
..+++++++
........+++++++
e is 65537 (0x010001)
writing RSA key
user@comp-ubuntu1810:~/rsakeyprint$ dotnet run rsa.key
Read 461 bytes, 0 extra byte(s) in file.
0F-D0-82-34-F8-13-38-4A-7F-C7-52-4A-F6-93-F8-FB-6D-98-7A-6A-04-3B-BC-35-8C-7D-AC-A5-A3-6E-AD-C1-66-30-81-2C-2A-DE-DA-60-03-6A-2C-D9-76-15-7F-61-97-57-
79-E1-6E-45-62-C3-83-04-97-CB-32-EF-C5-17-5F-99-60-92-AE-B6-34-6F-30-06-03-AC-BF-15-24-43-84-EB-83-60-EF-4D-3B-BD-D9-5D-56-26-F0-51-CE-F1
user@comp-ubuntu1810:~/rsakeyprint$ openssl rsa -in rsa.key -inform der -text -noout | grep -A7 private
privateExponent:
    0f:d0:82:34:f8:13:38:4a:7f:c7:52:4a:f6:93:f8:
    fb:6d:98:7a:6a:04:3b:bc:35:8c:7d:ac:a5:a3:6e:
    ad:c1:66:30:81:2c:2a:de:da:60:03:6a:2c:d9:76:
    15:7f:61:97:57:79:e1:6e:45:62:c3:83:04:97:cb:
    32:ef:c5:17:5f:99:60:92:ae:b6:34:6f:30:06:03:
    ac:bf:15:24:43:84:eb:83:60:ef:4d:3b:bd:d9:5d:
    56:26:f0:51:ce:f1
```

I file PKCS#8 possono essere esaminati con la classe `System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo`.

I file PFX/PKCS#12 possono essere esaminati e modificati rispettivamente con `System.Security.Cryptography.Pkcs.Pkcs12Info` e `System.Security.Cryptography.Pkcs.Pkcs12Builder`.

## <a name="serialport-for-linux"></a>SerialPort per Linux

.NET Core 3.0 supporta ora <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> in Linux.

In precedenza, .NET Core supportava solo l'uso del tipo `SerialPort` in Windows.

## <a name="more-bcl-improvements"></a>Altri miglioramenti BCL

`Span<T>`, `Memory<T>` e i tipi correlati introdotti in .NET Core 2.1 sono stati ottimizzati in .NET Core 3.0. Le operazioni comuni, ad esempio la costruzione di intervalli, il sezionamento, l'analisi e la formattazione offrono ora prestazioni migliori. 

Inoltre, i tipi come `String` sono stati sottoposti a miglioramenti per aumentarne l'efficienza quando sono usati come chiavi con `Dictionary<TKey, TValue>` e altre raccolte. Per trarre vantaggio da questi miglioramenti, non sono necessarie modifiche al codice.

.NET Core 3 Preview 1 presenta anche i nuovi miglioramenti seguenti:

* Supporto di Brotli predefinito in HttpClient
* ThreadPool.UnsafeQueueWorkItem(IThreadPoolWorkItem)
* Unsafe.Unbox
* CancellationToken.Unregister
* Operatori aritmetici complessi
* API socket per il keep-alive TCP
* StringBuilder.GetChunks
* Analisi IPEndPoint
* RandomNumberGenerator.GetInt32

## <a name="tiered-compilation"></a>Compilazione a livelli

Per impostazione predefinita, con .NET Core 3.0 la [compilazione a livelli](https://blogs.msdn.microsoft.com/dotnet/2018/08/02/tiered-compilation-preview-in-net-core-2-1/) è attiva. È una funzionalità che consente al runtime di usare in modo più adattivo il compilatore JIT per ottenere prestazioni migliori, sia all'avvio che per ottimizzare la velocità effettiva.

Questa funzionalità è stata aggiunta come funzionalità con consenso esplicito in [.NET Core 2.1](https://blogs.msdn.microsoft.com/dotnet/2018/05/30/announcing-net-core-2-1/) ed è stata abilitata per impostazione predefinita in [.NET Core 2.2 Preview 2](https://blogs.msdn.microsoft.com/dotnet/2018/09/12/announcing-net-core-2-2-preview-2/). Successivamente, è stata ripristinata come funzionalità con consenso esplicito nella versione .NET Core 2.2.

## <a name="arm64-linux-support"></a>Supporto ARM64 per Linux

In questa versione verrà aggiunto il supporto per ARM64 per Linux. Per il contesto, è stato aggiunto il supporto per ARM32 per Linux con .NET Core 2.1 e per Windows con .NET Core 2.2. Il caso d'uso principale per ARM64 è attualmente con gli scenari IoT.

[Sono disponibili immagini Docker per .NET Core per ARM64](https://hub.docker.com/r/microsoft/dotnet/) di Alpine, Debian e Ubuntu.

Per altre informazioni., vedere [Stato di ARM64 per .NET Core](https://github.com/dotnet/announcements/issues/82).

>[!NOTE]
> Il supporto **ARM64** per Windows non è ancora disponibile.
