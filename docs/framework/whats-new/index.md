---
title: Novità di .NET Framework
description: Vedere Novità di diverse versioni di .NET Framework. Leggere un riepilogo delle nuove funzionalità e dei miglioramenti principali in ogni versione.
ms.custom: updateeachrelease
ms.date: 04/18/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- what's new [.NET Framework]
ms.assetid: 1d971dd7-10fc-4692-8dac-30ca308fc0fa
ms.openlocfilehash: 42f872bba87a88fc92a37879e815ee7068407cf7
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925592"
---
# <a name="whats-new-in-net-framework"></a>Novità di .NET Framework

Questo articolo riepiloga le nuove funzionalità e i principali miglioramenti apportati alle versioni seguenti di .NET Framework:

- [.NET Framework 4,8](#v48)
- [.NET Framework 4.7.2](#v472)
- [.NET Framework 4.7.1](#v471)
- [.NET Framework 4,7](#v47)
- [.NET Framework 4.6.2](#v462)
- [.NET Framework 4.6.1](#v461)
- [.NET 2015 e .NET Framework 4.6](#v46)
- [.NET Framework 4.5.2](#v452)
- [.NET Framework 4.5.1](#v451)
- [.NET Framework 4.5](#v45)

Non vengono fornite informazioni complete su ogni nuova funzionalità e l'articolo è soggetto a modifiche. Per informazioni generali su .NET Framework, vedere [Introduzione a .NET Framework](../get-started/index.md). Per informazioni sulle piattaforme supportate, vedere [Requisiti di sistema di .NET Framework](../get-started/system-requirements.md). Per i collegamenti per il download e le istruzioni di installazione, vedere [Guida all'installazione](../install/guide-for-developers.md).

> [!NOTE]
> Il team di .NET Framework rende disponibili anche alcune funzionalità fuori programma con NuGet per espandere le piattaforme supportate e introdurre nuove funzionalità, ad esempio le raccolte non modificabili e i tipi di vettore abilitati per SIMD. Per altre informazioni, vedere [API e librerie di classi aggiuntive](../additional-apis/index.md) e [.NET Framework e rilascio fuori programma](../get-started/the-net-framework-and-out-of-band-releases.md).
> Vedere un [elenco completo dei pacchetti NuGet](https://www.nuget.org/profiles/dotnetframework) per .NET Framework.

<a name="v48"></a>

## <a name="introducing-net-framework-48"></a>Introduzione a .NET Framework 4.8

.NET Framework 4.8 è basato sulle versioni precedenti di .NET Framework 4.x con l'aggiunta di molte nuove correzioni e diverse nuove funzionalità, pur rimanendo un prodotto molto stabile.

### <a name="download-and-install-net-framework-48"></a>Scaricare e installare .NET Framework 4,8

È possibile scaricare .NET Framework 4.8 dalle posizioni seguenti:

- [Programma di installazione Web di .NET Framework 4.8](https://dotnet.microsoft.com/download/dotnet-framework/net48)

- [Programma di installazione offline di .NET Framework 4.8](https://dotnet.microsoft.com/download/dotnet-framework/net48)

.NET Framework 4.8 può essere installato in Windows 10, Windows 8.1, Windows 7 SP1 e nelle piattaforme server corrispondenti a partire da Windows Server 2008 R2 SP1. È possibile installare .NET Framework 4.8 usando il programma di installazione Web o il programma di installazione offline. Per la maggior parte degli utenti è consigliabile usare il programma di installazione Web.

Per .NET Framework 4.8 in Visual Studio 2012 o versioni successive è possibile installare [.NET Framework 4.8 Developer Pack](https://go.microsoft.com/fwlink/?LinkId=2085167).

### <a name="whats-new-in-net-framework-48"></a>Novità di .NET Framework 4.8

.NET Framework 4.8 include nuove funzionalità nelle aree seguenti:

- [Classi di base](#core48)
- [Windows Communication Foundation (WCF)](#wcf48)
- [Windows Presentation Foundation (WPF)](#wpf48)
- [Common Language Runtime](#clr48)

Un'accessibilità migliorata, grazie alla quale un'applicazione può offrire un'esperienza appropriata agli utenti di Assistive Technology, continua a essere uno dei principali obiettivi di .NET Framework 4.8. Per informazioni sui miglioramenti apportati all'accessibilità in .NET Framework 4.8, vedere [Nuove funzionalità di accessibilità in .NET Framework](whats-new-in-accessibility.md).

<a name="core48"></a>

#### <a name="base-classes"></a>Classi di base

**Impatto ridotto di FIPS sulla crittografia**. Nelle versioni precedenti del .NET Framework, le classi del provider di crittografia gestite, ad esempio <xref:System.Security.Cryptography.SHA256Managed> generano un' <xref:System.Security.Cryptography.CryptographicException> quando le librerie di crittografia di sistema sono configurate in "modalità FIPS". Queste eccezioni vengono generate perché le versioni gestite delle classi del provider del servizio di crittografia, a differenza delle librerie di crittografia del sistema, non hanno ottenuto la certificazione FIPS (Federal Information Processing Standards) 140-2. Poiché alcuni sviluppatori usano computer in modalità FIPS per lo sviluppo, le eccezioni vengono di solito generate nei sistemi di produzione.

Per impostazione predefinita, nelle applicazioni destinate a .NET Framework 4.8 le classi di crittografia gestite seguenti non generano più un'eccezione <xref:System.Security.Cryptography.CryptographicException> in questo caso:

- <xref:System.Security.Cryptography.MD5Cng>
- <xref:System.Security.Cryptography.MD5CryptoServiceProvider>
- <xref:System.Security.Cryptography.RC2CryptoServiceProvider>
- <xref:System.Security.Cryptography.RijndaelManaged>
- <xref:System.Security.Cryptography.RIPEMD160Managed>
- <xref:System.Security.Cryptography.SHA256Managed>

Al contrario, queste classi reindirizzano le operazioni di crittografia a una libreria di crittografia del sistema. Questa modifica rimuove in modo efficiente una differenza potenzialmente fuorviante tra ambienti di sviluppo e ambienti di produzione e rende possibile eseguire i componenti nativi e i componenti gestiti in base agli stessi criteri di crittografia. Le applicazioni che dipendono da queste eccezioni possono ripristinare il comportamento precedente impostando l'opzione di AppContext `Switch.System.Security.Cryptography.UseLegacyFipsThrow` su `true`. Per altre informazioni, vedere la sezione relativa alle [classi di crittografia gestite che non generano un'eccezione CryptographyException in modalità FIPS](../migration-guide/retargeting/4.7.2-4.8.md#managed-cryptography-classes-do-not-throw-a-cryptographyexception-in-fips-mode).

**Uso della versione aggiornata di ZLib**

A partire da .NET Framework 4.5, l'assembly clrcompression.dll usa [ZLib](https://www.zlib.net), una libreria esterna nativa per la compressione dei dati, al fine di fornire un'implementazione per l'algoritmo deflate. Il file clrcompression.dll di .NET Framework 4.8 viene aggiornato in modo da usare ZLib versione 1.2.11, che include varie correzioni e alcuni miglioramenti chiave.

<a name="wcf48"></a>

#### <a name="windows-communication-foundation-wcf"></a>Windows Communication Foundation (WCF)

**Introduzione di ServiceHealthBehavior**

Gli endpoint di integrità vengono ampiamente usati tramite gli strumenti di orchestrazione per gestire i servizi in base allo stato di integrità. I controlli di integrità possono anche essere usati tramite strumenti di monitoraggio, al fine di tenere traccia e fornire notifiche sulla disponibilità e sulle prestazioni di un servizio.

**ServiceHealthBehavior** è il comportamento di un servizio WCF che estende <xref:System.ServiceModel.Description.IServiceBehavior>.  Se aggiunto alla raccolta <xref:System.ServiceModel.Description.ServiceDescription.Behaviors?displayProperty=nameWithType>, il comportamento di un servizio esegue queste operazioni:

- Restituisce lo stato di integrità del servizio con codici di risposta HTTP. È possibile specificare in una stringa di query il codice di stato HTTP per una richiesta di probe di integrità HTTP/GET.

- Pubblica informazioni sull'integrità del servizio. Dettagli specifici del servizio, tra cui stato del servizio, numero di limitazioni e capacità, possono essere visualizzati tramite una richiesta HTTP/GET con la stringa di query `?health`. L'accessibilità a tali informazioni è importante durante la risoluzione dei problemi relativi a un servizio WCF che non funziona correttamente.

Esistono due modi per esporre l'endpoint di integrità e pubblicare le informazioni di integrità del servizio WCF:

- Tramite codice. Ad esempio:

  ```csharp
  ServiceHost host = new ServiceHost(typeof(Service1),
                     new Uri("http://contoso:81/Service1"));
  ServiceHealthBehavior healthBehavior =
      host.Description.Behaviors.Find<ServiceHealthBehavior>();
  healthBehavior ??= new ServiceHealthBehavior();
  host.Description.Behaviors.Add(healthBehavior);
  ```

  ```vb
  Dim host As New ServiceHost(GetType(Service1),
              New Uri("http://contoso:81/Service1"))
  Dim healthBehavior As ServiceHealthBehavior =
     host.Description.Behaviors.Find(Of ServiceHealthBehavior)()
  If healthBehavior Is Nothing Then
     healthBehavior = New ServiceHealthBehavior()
  End If
  host.Description.Behaviors.Add(healthBehavior)
  ```

- Tramite un file di configurazione. Ad esempio:

  ```xml
  <behaviors>
    <serviceBehaviors>
      <behavior name="DefaultBehavior">
        <serviceHealth httpsGetEnabled="true"/>
      </behavior>
    </serviceBehaviors>
  </behaviors>
  ```

È possibile eseguire una query sullo stato di integrità di un servizio usando i parametri di query, ad esempio `OnServiceFailure`, `OnDispatcherFailure`, `OnListenerFailure`, `OnThrottlePercentExceeded`. Un codice di risposta HTTP può inoltre essere specificato per ogni parametro di query. Se si omette il codice di risposta HTTP per un parametro di query, per impostazione predefinita viene usato un codice di risposta HTTP 503. Ad esempio:

- OnServiceFailure: `https://contoso:81/Service1?health&OnServiceFailure=450`

  Un codice di stato di risposta HTTP U 450 viene restituito quando [ServiceHost.State](xref:System.ServiceModel.Channels.CommunicationObject.State) è maggiore di <xref:System.ServiceModel.CommunicationState.Opened?displayProperty=nameWithType>.
Esempi e parametri di query:

- OnDispatcherFailure: `https://contoso:81/Service1?health&OnDispatcherFailure=455`

  Un codice di stato della risposta HTTP 455 viene restituito quando lo stato di uno dei dispatcher di canale è maggiore di <xref:System.ServiceModel.CommunicationState.Opened?displayProperty=nameWithType>.

- OnListenerFailure: `https://contoso:81/Service1?health&OnListenerFailure=465`

  Un codice di stato della risposta HTTP 465 viene restituito quando lo stato di uno dei listener di canale è maggiore di <xref:System.ServiceModel.CommunicationState.Opened?displayProperty=nameWithType>.

- OnThrottlePercentExceeded: `https://contoso:81/Service1?health&OnThrottlePercentExceeded= 70:350,95:500`

  Specifica la percentuale {1-100} che attiva la risposta e il relativo codice di risposta HTTP {599-200}. In questo esempio:

  - Se la percentuale è maggiore di 95, viene restituito un codice di risposta HTTP 500.

  - Se la percentuale equivale a 70 e 95 o è inclusa tra tali valori, viene restituito 350.

  - In caso contrario, viene restituito 200.

Lo stato di integrità del servizio può essere visualizzato in HTML, specificando una stringa di query come `https://contoso:81/Service1?health`, o in codice XML, specificando una stringa di query come `https://contoso:81/Service1?health&Xml`. Una stringa di query come `https://contoso:81/Service1?health&NoContent` restituisce una pagina HTML vuota.

<a name="wpf48"></a>

#### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)

**Miglioramenti a valori DPI alti**

In .NET Framework 4.8 WPF aggiunge supporto per la sensibilità ai valori DPI per monitor V2 e per il ridimensionamento DPI in modalità mista. Vedere la pagina [High DPI Desktop Application Development on Windows](/windows/win32/hidpi/high-dpi-desktop-application-development-on-windows) (Sviluppo di applicazioni desktop con valori DPI alti in Windows) per altre informazioni sullo sviluppo con valori DPI alti.

.NET Framework 4.8 migliora il supporto per le finestre HWND ospitate e l'interoperatività di Windows Form nelle applicazioni WPF con valori DPI alti in piattaforme che supportano il ridimensionamento DPI in modalità mista, a partire dall'Aggiornamento di Windows 10 (aprile 2018). Quando le finestre HWND ospitate o i controlli Windows Form vengono creati come finestre con ridimensionamento DPI in modalità mista chiamando [SetThreadDpiHostingBehavior](/windows/desktop/api/winuser/nf-winuser-setthreaddpihostingbehavior) e [SetThreadDpiAwarenessContext](/windows/desktop/api/winuser/nf-winuser-setthreaddpiawarenesscontext), possono essere ospitati in un'applicazione WPF per monitor V2 e vengono ridimensionati in modo appropriato. Il rendering di questi contenuti ospitati non viene eseguito in base ai valori DPI nativi. Il sistema operativo ridimensiona infatti i contenuti ospitati in modo appropriato. Il supporto per la sensibilità ai valori DPI per monitor V2 consente anche l'hosting dei controlli WPF, ad esempio con associazione con elemento padre, in una finestra nativa in un'applicazione con valori DPI alti.

Per abilitare il supporto per il ridimensionamento con valori DPI alti in modalità mista, è possibile impostare le opzioni [AppContext](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) seguenti per il file di configurazione dell'applicazione:

```xml
<runtime>
   <AppContextSwitchOverrides value = "Switch.System.Windows.DoNotScaleForDpiChanges=false; Switch.System.Windows.DoNotUsePresentationDpiCapabilityTier2OrGreater=false"/>
</runtime>
```

<a name="clr48"></a>

#### <a name="common-language-runtime"></a>Common Language Runtime

Il runtime in .NET Framework 4.8 include le modifiche e i miglioramenti seguenti:

**Miglioramenti al compilatore JIT**. Il compilatore JIT in .NET Framework 4.8 è basato sul compilatore JIT in .NET Core 2.1. Molte delle ottimizzazioni e tutte le correzioni di bug apportate al compilatore JIT di .NET Core 2.1 sono incluse nel compilatore JIT di .NET Framework 4.8.

**Miglioramenti di NGEN**. Il runtime ha migliorato la gestione della memoria per le immagini del [generatore di immagini native](../tools/ngen-exe-native-image-generator.md) (NGEN) in modo tale che i dati mappati dalle immagini NGEN non siano residenti in memoria. In questo modo viene ridotta la superficie di attacco vulnerabile agli attacchi che tentano di eseguire codice arbitrario mediante la modifica della memoria.

**Analisi antimalware per tutti gli assembly**. Nelle versioni precedenti di .NET Framework il runtime esegue l'analisi di tutti gli assembly caricati da disco tramite Windows Defender o software antimalware di terze parti. Gli assembly caricati da altre origini, ad esempio tramite il metodo <xref:System.Reflection.Assembly.Load(System.Byte[])?displayProperty=nameWithType>, non vengono tuttavia analizzati e potrebbero contenere malware non rilevato. A partire da .NET Framework 4.8 eseguito su Windows 10, il runtime attiva un'analisi tramite soluzioni antimalware che implementano l'[interfaccia AMSI (Antimalware Scan Interface)](/windows/desktop/AMSI/antimalware-scan-interface-portal).

<a name="v472"></a>

## <a name="whats-new-in-net-framework-472"></a>Novità di .NET Framework 4.7.2

.NET Framework 4.7.2 include nuove funzionalità nelle aree seguenti:

- [Classi di base](#core-472)
- [ASP.NET](#asp-net472)
- [Rete](#net472)
- [SQL](#sql472)
- [WPF](#wpf472)
- [ClickOnce](#clickonce)

Un'accessibilità migliorata, grazie alla quale un'applicazione può offrire un'esperienza appropriata agli utenti di Assistive Technology, continua a essere uno dei principali obiettivi di .NET Framework 4.7.2. Per informazioni sui miglioramenti apportati all'accessibilità in .NET Framework 4.7.2, vedere [Nuove funzionalità di accessibilità in .NET Framework](whats-new-in-accessibility.md).

<a name="core-472"></a>

#### <a name="base-classes"></a>Classi di base

.NET Framework 4.7.2 presenta un numero elevato di miglioramenti della crittografia, un supporto aggiornato per la decompressione degli archivi ZIP e nuove API della raccolta.

**Nuovi overload di RSA.Create e DSA.Create**

I metodi <xref:System.Security.Cryptography.DSA.Create(System.Security.Cryptography.DSAParameters)?displayProperty=nameWithType> e <xref:System.Security.Cryptography.RSA.Create(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType> consentono di specificare parametri chiave quando si crea un'istanza di una nuova chiave <xref:System.Security.Cryptography.DSA> o <xref:System.Security.Cryptography.RSA>. Consentono di sostituire codice come il seguente:

```csharp
// Before .NET Framework 4.7.2
using (RSA rsa = RSA.Create())
{
   rsa.ImportParameters(rsaParameters);
   // Other code to execute using the RSA instance.
}
```

```vb
' Before .NET Framework 4.7.2
Using rsa = RSA.Create()
   rsa.ImportParameters(rsaParameters)
   ' Other code to execute using the rsa instance.
End Using
```

con codice come il seguente:

```csharp
// Starting with .NET Framework 4.7.2
using (RSA rsa = RSA.Create(rsaParameters))
{
   // Other code to execute using the rsa instance.
}
```

```vb
' Starting with .NET Framework 4.7.2
Using rsa = RSA.Create(rsaParameters)
   ' Other code to execute using the rsa instance.
End Using
```

I metodi <xref:System.Security.Cryptography.DSA.Create(System.Int32)?displayProperty=nameWithType> e <xref:System.Security.Cryptography.RSA.Create(System.Int32)?displayProperty=nameWithType> consentono di generare nuove chiavi <xref:System.Security.Cryptography.DSA> o <xref:System.Security.Cryptography.RSA> con dimensioni chiave specifiche. Ad esempio:

```csharp
using (DSA dsa = DSA.Create(2048))
{
   // Other code to execute using the dsa instance.
}
```

```vb
Using dsa = DSA.Create(2048)
   ' Other code to execute using the dsa instance.
End Using
```

**I costruttori Rfc2898DeriveBytes accettano un nome di algoritmo hash**

La classe <xref:System.Security.Cryptography.Rfc2898DeriveBytes> include tre nuovi costruttori con un parametro <xref:System.Security.Cryptography.HashAlgorithmName> che identifica l'algoritmo HMAC da usare per la derivazione delle chiavi. Invece di usare SHA-1, gli sviluppatori potranno usare un HMAC basato su SHA-2 come SHA-256, come illustrato nell'esempio seguente:

```csharp
private static byte[] DeriveKey(string password, out int iterations, out byte[] salt,
                                out HashAlgorithmName algorithm)
{
   iterations = 100000;
   algorithm = HashAlgorithmName.SHA256;

   const int SaltSize = 32;
   const int DerivedValueSize = 32;

   using (Rfc2898DeriveBytes pbkdf2 = new Rfc2898DeriveBytes(password, SaltSize,
                                                             iterations, algorithm))
   {
      salt = pbkdf2.Salt;
      return pbkdf2.GetBytes(DerivedValueSize);
   }
}
```

```vb
Private Shared Function DeriveKey(password As String, ByRef iterations As Integer,
                                  ByRef salt AS Byte(), ByRef algorithm As HashAlgorithmName) As Byte()
   iterations = 100000
   algorithm = HashAlgorithmName.SHA256

   Const SaltSize As Integer = 32
   Const  DerivedValueSize As Integer = 32

   Using pbkdf2 = New Rfc2898DeriveBytes(password, SaltSize, iterations, algorithm)
      salt = pbkdf2.Salt
      Return pbkdf2.GetBytes(DerivedValueSize)
   End Using
End Function
```

**Supporto per le chiavi temporanee**

L'importazione PFX può caricare chiavi private direttamente dalla memoria, ignorando il disco rigido.Quando il nuovo flag <xref:System.Security.Cryptography.X509Certificates.X509KeyStorageFlags.EphemeralKeySet?displayProperty=nameWithType> è specificato in un costruttore <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> o in uno degli overload del metodo <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.Import%2A?displayProperty=nameWithType>, le chiavi private vengono caricate come chiavi temporanee. Ciò impedisce che le chiavi siano visibili sul disco. Tuttavia:

- Poiché le chiavi non vengono gestite su disco, i certificati caricati con questo flag non sono candidati ottimali per l'aggiunta a un archivio X509.

- Le chiavi caricate in questo modo vengono caricate quasi sempre tramite Windows CNG. Pertanto i chiamanti devono accedere alla chiave privata chiamando metodi di estensione, ad esempio [cert.GetRSAPrivateKey()](xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey%2A). La proprietà <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> non funziona.

- Dato che la proprietà legacy <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> non funziona con i certificati, gli sviluppatori devono eseguire test rigorosi prima di passare alle chiavi temporanee.

**Creazione a livello di codice di richieste di firma dei certificati PKCS #10 e certificati chiave pubblica X.509**

A partire da .NET Framework 4.7.2, i carichi di lavoro possono generare richieste di firma dei certificati (CSR), che consentono la gestione temporanea della generazione di richieste di certificati negli strumenti esistenti. Ciò è spesso utile negli scenari di test.

Per altre informazioni ed esempi di codice, vedere "Creazione a livello di codice di richieste di firma dei certificati PKCS #10 e certificati chiave pubblica X.509" nel [blog di .NET](https://devblogs.microsoft.com/dotnet/net-framework-4-7-2-developer-pack-early-access-build-3056-is-available/).

**Nuovi membri SignerInfo**

A partire da .NET Framework 4.7.2 la classe <xref:System.Security.Cryptography.Pkcs.SignerInfo> espone maggiori informazioni sulla firma. È possibile recuperare il valore della proprietà <xref:System.Security.Cryptography.Pkcs.SignerInfo.SignatureAlgorithm?displayProperty=fullName> per determinare l'algoritmo di firma usato dal firmatario. È possibile chiamare <xref:System.Security.Cryptography.Pkcs.SignerInfo.GetSignature%2A?displayProperty=nameWithType> per ottenere una copia della firma crittografica del firmatario.

**Lasciare aperto un flusso con wrapping dopo l'eliminazione di CryptoStream**

A partire da .NET Framework 4.7.2 la classe <xref:System.Security.Cryptography.CryptoStream> dispone di un costruttore <xref:System.Security.Cryptography.CryptoStream.Dispose%2A> aggiuntivo per evitare la chiusura del flusso con wrapping.Per mantenere aperto il flusso con wrapping dopo l'eliminazione dell'istanza <xref:System.Security.Cryptography.CryptoStream>, chiamare il nuovo costruttore <xref:System.Security.Cryptography.CryptoStream> come indicato di seguito:

```csharp
var cStream = new CryptoStream(stream, transform, mode, leaveOpen: true);
```

```vb
Dim cStream = New CryptoStream(stream, transform, mode, leaveOpen:=true)
```

**Modifiche alla decompressione in DeflateStream**

A partire da .NET Framework 4.7.2 l'implementazione di operazioni di decompressione nella classe <xref:System.IO.Compression.DeflateStream> è stata modificata in modo da usare le API di Windows native per impostazione predefinita. In genere questo comporta un miglioramento significativo delle prestazioni.

Il supporto della decompressione mediante le API di Windows è abilitato per impostazione predefinita per le applicazioni destinate a .NET Framework 4.7.2. Le applicazioni destinate a versioni precedenti di .NET Framework ma eseguite in .NET Framework 4.7.2 possono scegliere il nuovo comportamento aggiungendo la seguente [opzione AppContext](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) al file di configurazione dell'applicazione:

```xml
<AppContextSwitchOverrides value="Switch.System.IO.Compression.DoNotUseNativeZipLibraryForDecompression=false" />
```

**API aggiuntive della raccolta**

.NET Framework 4.7.2 aggiunge varie API nuove ai tipi <xref:System.Collections.Generic.SortedSet%601> e <xref:System.Collections.Generic.HashSet%601>. Queste includono:

- Metodi `TryGetValue`, che estendono il modello Try usato in altri tipi di raccolta per questi due tipi. I metodi sono:

  - [public bool HashSet\<T>.TryGetValue(T equalValue, out T actualValue)](xref:System.Collections.Generic.SortedSet%601.TryGetValue%2A)
  - [public bool SortedSet\<T>.TryGetValue(T equalValue, out T actualValue)](xref:System.Collections.Generic.SortedSet%601.TryGetValue%2A)

- Metodi di estensione `Enumerable.To*`, che convertono una raccolta in un elemento <xref:System.Collections.Generic.HashSet%601>:

  - [public static HashSet\<TSource> ToHashSet\<TSource>(this IEnumerable\<TSource> source)](xref:System.Linq.Enumerable.ToHashSet%2A)
  - [public static HashSet\<TSource> ToHashSet\<TSource>(this IEnumerable\<TSource> source, IEqualityComparer\<TSource> comparer)](xref:System.Linq.Enumerable.ToHashSet%2A)

- Nuovi costruttori <xref:System.Collections.Generic.HashSet%601> che consentono di impostare la capacità della raccolta e di ottenere un miglioramento delle prestazioni quando si conosce in anticipo la dimensione dell'elemento <xref:System.Collections.Generic.HashSet%601>:

  - [public HashSet(int capacity)](xref:System.Collections.Generic.HashSet%601.%23ctor(System.Int32))
  - [public HashSet(int capacity, IEqualityComparer\<T> comparer)](xref:System.Collections.Generic.HashSet%601.%23ctor(System.Int32,System.Collections.Generic.IEqualityComparer%7B%600%7D))

La classe <xref:System.Collections.Concurrent.ConcurrentDictionary%602> include nuovi overload dei metodi <xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A> e <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> per recuperare un valore dal dizionario o aggiungerlo se non viene trovato e per aggiungere un valore al dizionario o aggiornarlo se esiste già.

```csharp
public TValue AddOrUpdate<TArg>(TKey key, Func<TKey, TArg, TValue> addValueFactory, Func<TKey, TValue, TArg, TValue> updateValueFactory, TArg factoryArgument)

public TValue GetOrAdd<TArg>(TKey key, Func<TKey, TArg, TValue> valueFactory, TArg factoryArgument)
```

```vb
Public AddOrUpdate(Of TArg)(key As TKey, addValueFactory As Func(Of TKey, TArg, TValue), updateValueFactory As Func(Of TKey, TValue, TArg, TValue), factoryArgument As TArg) As TValue

Public GetOrAdd(Of TArg)(key As TKey, valueFactory As Func(Of TKey, TArg, TValue), factoryArgument As TArg) As TValue
```

<a name="asp-net472"></a>

#### <a name="aspnet"></a>ASP.NET

**Supporto dell'inserimento di dipendenze in Web Form**

L'[inserimento di dipendenze (DI)](/aspnet/core/fundamentals/dependency-injection#overview-of-dependency-injection) separa gli oggetti e le relative dipendenze, in modo che il codice di un oggetto non deve più essere modificato solo perché è stata modificata una dipendenza. Quando si sviluppano applicazioni ASP.NET destinate a .NET Framework 4.7.2, è possibile:

- Usare l'inserimento basato sui setter, basato sull'interfaccia e basato sul costruttore in [gestori e i moduli](https://docs.microsoft.com/previous-versions/aspnet/bb398986(v=vs.100)), [istanze di pagina](xref:System.Web.UI.Page) e [controlli utente](https://docs.microsoft.com/previous-versions/aspnet/y6wb1a0e(v=vs.100)) dei progetti di applicazione Web ASP.NET.

- Usare l'inserimento basato sui setter e basato sull'interfaccia in [gestori e moduli](https://docs.microsoft.com/previous-versions/aspnet/bb398986(v=vs.100)), [istanze di pagina](xref:System.Web.UI.Page) e [controlli utente](https://docs.microsoft.com/previous-versions/aspnet/y6wb1a0e(v=vs.100)) dei progetti di sito Web ASP.NET.

- Associare diversi framework di inserimento delle dipendenze.

**Supporto dei cookie SameSite**

[SameSite](https://tools.ietf.org/html/draft-west-first-party-cookies-07) impedisce a un browser di inviare un cookie insieme a una richiesta intersito. .NET Framework 4.7.2 aggiunge una proprietà <xref:System.Web.HttpCookie.SameSite?displayProperty=nameWithType> il cui valore è un membro dell'enumerazione <xref:System.Web.SameSiteMode?displayProperty=nameWithType>. Se il valore è <xref:System.Web.SameSiteMode.Strict?displayProperty=nameWithType> oppure <xref:System.Web.SameSiteMode.Lax?displayProperty=nameWithType>, ASP.NET aggiunge l'attributo `SameSite` all'intestazione set-cookie. Il supporto SameSite è valido per gli oggetti <xref:System.Web.HttpCookie> e per i cookie <xref:System.Web.Security.FormsAuthentication> e <xref:System.Web.SessionState>.

È possibile impostare SameSite per un oggetto <xref:System.Web.HttpCookie> come segue:

```csharp
var c = new HttpCookie("secureCookie", "same origin");
c.SameSite = SameSiteMode.Lax;
```

```vb
Dim c As New HttpCookie("secureCookie", "same origin")
c.SameSite = SameSiteMode.Lax
```

È anche possibile configurare i cookie SameSite a livello di applicazione modificando il file web.config:

```xml
<system.web>
   <httpCookies sameSite="Strict" />
</system.web>
```

È possibile aggiungere SameSite per i cookie <xref:System.Web.Security.FormsAuthentication> e <xref:System.Web.SessionState> modificando il file di configurazione Web:

```xml
<system.web>
   <authentication mode="Forms">
      <forms cookieSameSite="Lax">
         <!-- ...   -->
      </forms>
   </authentication>
   <sessionState cookieSameSite="Lax"></sessionState>
</system.web>
```

<a name="net472"></a>

#### <a name="networking"></a>Rete

**Implementazione di proprietà HttpClientHandler**

.NET Framework 4.7.1 ha aggiunto otto proprietà alla classe <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType>. Tuttavia, due proprietà generavano un'eccezione <xref:System.PlatformNotSupportedException>. Ora .NET Framework 4.7.2 include un'implementazione per queste proprietà. Le proprietà sono:

- <xref:System.Net.Http.HttpClientHandler.CheckCertificateRevocationList>
- <xref:System.Net.Http.HttpClientHandler.SslProtocols>

<a name="sql472"></a>

#### <a name="sqlclient"></a>SQLClient

**Supporto per l'autenticazione universale e l'autenticazione a più fattori di Azure Active Directory**

In seguito alle crescenti esigenze di conformità e sicurezza, molti clienti si orientano verso l'uso dell'autenticazione a più fattori (MFA). Le procedure consigliate attuali sconsigliano anche l'aggiunta delle password utente direttamente nelle stringhe di connessione. Per supportare queste modifiche, .NET Framework 4.7.2 estende le [stringhe di connessione SQLClient](xref:System.Data.SqlClient.SqlConnection.ConnectionString) aggiungendo un nuovo valore "Active Directory Interactive", in modo che la parola chiave "Authentication" esistente supporti MFA e l'[Autenticazione di Azure AD](/azure/sql-database/sql-database-aad-authentication-configure). Il nuovo metodo interattivo supporta gli utenti di Azure AD nativi e federati, nonché gli utenti guest. Quando si usa questo metodo l'autenticazione MFA imposta da Azure AD è supportata per i database SQL. Il processo di autenticazione richiede anche che una password utente sia conforme alle procedure consigliate di sicurezza.

Nelle versioni precedenti di .NET Framework la connettività SQL supportava solo le opzioni <xref:System.Data.SqlClient.SqlAuthenticationMethod.ActiveDirectoryPassword?displayProperty=nameWithType> e <xref:System.Data.SqlClient.SqlAuthenticationMethod.ActiveDirectoryIntegrated?displayProperty=nameWithType>. Entrambe sono incluse nel [protocollo ADAL](/azure/active-directory/develop/active-directory-authentication-libraries) non interattivo, che non supporta l'autenticazione a più fattori. Con la nuova opzione <xref:System.Data.SqlClient.SqlAuthenticationMethod.ActiveDirectoryInteractive?displayProperty=nameWithType> la connettività SQL supporta l'autenticazione a più fattori oltre ai metodi di autenticazione esistenti (password e autenticazione integrata) e consente agli utenti di immettere le password in modo interattivo, evitando di salvare in modo permanente le password nella stringa di connessione.

Per altre informazioni e un esempio, vedere "SQL -- Azure AD Universal and Multi-factor Authentication Support" (SQL - Supporto dell'autenticazione universale e a più fattori in Azure AD) nel [blog di .NET](https://devblogs.microsoft.com/dotnet/net-framework-4-7-2-developer-pack-early-access-build-3056-is-available/).

**Supporto di Always Encrypted versione 2**

NET Framework 4.7.2 aggiunge il supporto per Always Encrypted basato su enclave. La versione originale di Always Encrypted è una tecnologia di crittografia lato client in cui la crittografia delle chiavi non lascia mai il client. In Always Encrypted basato su enclave il client può inviare le chiavi di crittografia a un'enclave protetta, ovvero un'entità di elaborazione protetta che può essere considerata come parte di SQL Server ma non può essere alterata tramite codice SQL Server. Per supportare Always Encrypted basato su enclave, .NET Framework 4.7.2 aggiunge i tipi e i membri seguenti allo spazio dei nomi <xref:System.Data.SqlClient>:

- <xref:System.Data.SqlClient.SqlConnectionStringBuilder.EnclaveAttestationUrl?displayProperty=nameWithType>, che consente di specificare l'URI per Always Encrypted basato su enclave.

- <xref:System.Data.SqlClient.SqlColumnEncryptionEnclaveProvider>, una classe astratta dalla quale derivano tutti i provider di enclave.

- <xref:System.Data.SqlClient.SqlEnclaveSession>, che incapsula lo stato per una sessione enclave specifica.

- <xref:System.Data.SqlClient.SqlEnclaveAttestationParameters>, che specifica i parametri di attestazione usati da SQL Server per ottenere le informazioni necessarie per l'esecuzione di un protocollo di attestazione particolare.

Il file di configurazione dell'applicazione specifica quindi un'implementazione concreta della classe <xref:System.Data.SqlClient.SqlColumnEncryptionEnclaveProvider?displayProperty=nameWithType> astratta, che offre la funzionalità per il provider dell'enclave. Ad esempio:

```xml
<configuration>
  <configSections>
    <section name="SqlColumnEncryptionEnclaveProviders" type="System.Data.SqlClient.SqlColumnEncryptionEnclaveProviderConfigurationSection,System.Data,Version=4.0.0.0,Culture=neutral,PublicKeyToken=b77a5c561934e089"/>
  </configSections>
  <SqlColumnEncryptionEnclaveProviders>
    <providers>
      <add name="Azure" type="Microsoft.SqlServer.Management.AlwaysEncrypted.AzureEnclaveProvider,MyApp"/>
      <add name="HGS" type="Microsoft.SqlServer.Management.AlwaysEncrypted.HGSEnclaveProvider,MyApp" />
    </providers>
  </SqlColumnEncryptionEnclaveProviders >
</configuration>
```

Il flusso base di Always Encrypted basato su enclave è il seguente:

1. L'utente crea una connessione AlwaysEncrypted a SQL Server che supporta Always Encrypted basato su enclave. Il driver contatta il servizio di attestazione per garantire che si sta connettendo all'enclave corretta.

1. Dopo l'attestazione dell'enclave, il driver stabilisce un canale protetto con l'enclave protetta ospitata su SQL Server.

1. Il driver condivide le chiavi di crittografia autorizzate dal client con l'enclave protetta per la durata della connessione SQL.

<a name="wpf472"></a>

#### <a name="windows-presentation-foundation"></a>Windows Presentation Foundation

**Ricerca di ResourceDictionary in base all'origine**

A partire da .NET Framework 4.7.2, un assistente di diagnostica può trovare gli oggetti  <xref:System.Windows.Xps.Packaging.IXpsFixedPageReader.ResourceDictionaries> creati da un URI di origine specificato.Questa funzionalità può essere usata dagli assistenti di diagnostica, non dalle applicazioni di produzione. Un assistente di diagnostica come la funzionalità "modifica e continuazione" di Visual Studio consente all'utente di modificare un oggetto ResourceDictionary con l'intento di applicare le modifiche all'applicazione in esecuzione. Un passaggio per ottenere questo risultato è la ricerca di tutti i ResourceDictionaries creati dall'applicazione in esecuzione dal dizionario in corso di modifica. Ad esempio un'applicazione può dichiarare un ResourceDictionary il cui contenuto viene copiato da un determinato URI di origine:

```xml
<ResourceDictionary Source="MyRD.xaml" />
```

Un assistente di diagnostica che modifica il markup originale in *MyRD. XAML*   può utilizzare la nuova funzionalità per individuare il dizionario.La funzionalità è implementata dal nuovo metodo statico <xref:System.Windows.Diagnostics.ResourceDictionaryDiagnostics.GetResourceDictionariesForSource%2A?displayProperty=nameWithType>. L'assistente di diagnostica chiama il nuovo metodo usando un URI assoluto che identifica il codice originale, come illustrato nel codice seguente:

```csharp
IEnumerable<ResourceDictionary> dictionaries = ResourceDictionaryDiagnostics.GetResourceDictionariesForSource(new Uri("pack://application:,,,/MyApp;component/MyRD.xaml"));
```

```vb
Dim dictionaries As IEnumerable(Of ResourceDictionary) = ResourceDictionaryDiagnostics.GetResourceDictionariesForSource(New Uri("pack://application:,,,/MyApp;component/MyRD.xaml"))
```

Il metodo restituisce un enumerabile vuoto, a meno che non  <xref:System.Windows.Diagnostics.VisualDiagnostics> sia abilitato e che sia [`ENABLE_XAML_DIAGNOSTICS_SOURCE_INFO`](xref:System.Windows.Diagnostics.VisualDiagnostics.GetXamlSourceInfo%2A)   impostata la variabile di ambiente.

**Rilevamento di proprietari di ResourceDictionary**

A partire da .NET Framework 4.7.2 un assistente di diagnostica può trovare i proprietari di un determinato oggetto <xref:Windows.UI.Xaml.ResourceDictionary>.(La funzionalità può essere usata dagli assistenti di diagnostica e non dalle applicazioni di produzione). Ogni volta che viene apportata una modifica a un oggetto <xref:Windows.UI.Xaml.ResourceDictionary> , WPF trova automaticamente tutti i riferimenti [DynamicResource](../wpf/advanced/dynamicresource-markup-extension.md) che potrebbero essere interessati dalla modifica.

Un assistente di diagnostica come la funzionalità di Visual Studio "modifica e continuazione" potrebbe voler estenderlo per gestire i riferimenti [StaticResource](../wpf/advanced/staticresource-markup-extension.md) . Il primo passaggio in questo processo è il rilevamento dei proprietari del dizionario, ovvero di tutti gli oggetti la cui proprietà `Resources` fa riferimento al dizionario (direttamente o indirettamente tramite la proprietà <xref:System.Windows.ResourceDictionary.MergedDictionaries?displayProperty=nameWithType>). Questa fase è supportata da tre nuovi metodi statici implementati nella classe <xref:System.Windows.Diagnostics.ResourceDictionaryDiagnostics?displayProperty=nameWithType>, uno per ogni tipo di base che dispone di una proprietà `Resources`:

- [`public static IEnumerable<FrameworkElement> GetFrameworkElementOwners(ResourceDictionary dictionary);`](xref:System.Windows.Diagnostics.ResourceDictionaryDiagnostics.GetFrameworkElementOwners%2A)

- [`public static IEnumerable<FrameworkContentElement> GetFrameworkContentElementOwners(ResourceDictionary dictionary);`](xref:System.Windows.Diagnostics.ResourceDictionaryDiagnostics.GetFrameworkContentElementOwners%2A)

- [`public static IEnumerable<Application> GetApplicationOwners(ResourceDictionary dictionary);`](xref:System.Windows.Diagnostics.ResourceDictionaryDiagnostics.GetApplicationOwners%2A)

Questi metodi restituiscono un oggetto enumerabile vuoto, a meno che non  <xref:System.Windows.Diagnostics.VisualDiagnostics> sia abilitato e che sia [`ENABLE_XAML_DIAGNOSTICS_SOURCE_INFO`](xref:System.Windows.Diagnostics.VisualDiagnostics.GetXamlSourceInfo%2A)   impostata la variabile di ambiente.

**Ricerca di riferimenti StaticResource**

Ora un assistente di diagnostica può ricevere una notifica ogni volta che viene risolto un riferimento [StaticResource](../wpf/advanced/staticresource-markup-extension.md).(La funzionalità può essere usata dagli assistenti di diagnostica, non dalle applicazioni di produzione). Un assistente di diagnostica come la funzionalità di Visual Studio "modifica e continuazione" può voler aggiornare tutti gli usi di una risorsa quando il relativo valore in <xref:Windows.UI.Xaml.ResourceDictionary> viene modificato. WPF esegue automaticamente questa operazione per i riferimenti [DynamicResource](../wpf/advanced/dynamicresource-markup-extension.md), ma evita deliberatamente l'esecuzione per i riferimenti [StaticResource](../wpf/advanced/staticresource-markup-extension.md). A partire da .NET Framework 4.7.2 l'assistente di diagnostica può usare queste notifiche per trovare tali usi della risorsa statica.

La notifica viene implementata dal nuovo evento <xref:System.Windows.Diagnostics.ResourceDictionaryDiagnostics.StaticResourceResolved?displayProperty=nameWithType>:

```csharp
public static event EventHandler<StaticResourceResolvedEventArgs> StaticResourceResolved;
```

```vb
Public Shared Event StaticResourceResolved As EventHandler(Of StaticResourceResolvedEventArgs)
```

Questo evento viene generato ogni volta che il runtime risolve un riferimento [StaticResource](../wpf/advanced/staticresource-markup-extension.md).Gli argomenti <xref:System.Windows.Diagnostics.StaticResourceResolvedEventArgs> descrivono la risoluzione e indicano l'oggetto e la proprietà che ospitano il riferimento [StaticResource](../wpf/advanced/staticresource-markup-extension.md) e il <xref:Windows.UI.Xaml.ResourceDictionary> e la chiave usati per la risoluzione:

```csharp
public class StaticResourceResolvedEventArgs : EventArgs
{
   public Object TargetObject { get; }

   public Object TargetProperty { get; }

   public ResourceDictionary ResourceDictionary { get; }

   public object ResourceKey { get; }
}
```

```vb
Public Class StaticResourceResolvedEventArgs : Inherits EventArgs
   Public ReadOnly Property TargetObject As Object
   Public ReadOnly Property TargetProperty As Object
   Public ReadOnly Property ResourceDictionary As ResourceDictionary
   Public ReadOnly Property ResourceKey As Object
End Class
```

L'evento non viene generato (e la relativa `add` funzione di accesso viene ignorata), a meno che non  <xref:System.Windows.Diagnostics.VisualDiagnostics> sia abilitato e non sia [`ENABLE_XAML_DIAGNOSTICS_SOURCE_INFO`](xref:System.Windows.Diagnostics.VisualDiagnostics.GetXamlSourceInfo%2A)   impostata la variabile di ambiente.

#### <a name="clickonce"></a>ClickOnce

ClickOnce consente la distribuzione di applicazioni con supporto HDPI per Windows Forms, Windows Presentation Foundation (WPF) e Visual Studio Tools per Office (VSTO). Se la voce seguente viene rilevata nel manifesto dell'applicazione, la distribuzione avrà esito positivo in .NET Framework 4.7.2:

```xml
<windowsSettings>
   <dpiAware xmlns="http://schemas.microsoft.com/SMI/2005/WindowsSettings">true</dpiAware>
</windowsSettings>
```

Per le applicazioni Windows Forms, la soluzione alternativa precedente, con impostazione del rilevamento DPI nel file di configurazione dell'applicazione anziché nel manifesto dell'applicazione, non è più necessaria per garantire l'esito positivo della distribuzione tramite ClickOnce.

<a name="v471"></a>

## <a name="whats-new-in-net-framework-471"></a>Novità di .NET Framework 4.7.1

.NET Framework 4.7.1 include nuove funzionalità nelle aree seguenti:

- [Classi di base](#core471)
- [Common Language Runtime (CLR)](#clr)
- [Rete](#net471)
- [ASP.NET](#asp-net471)

Un'accessibilità migliorata, grazie alla quale un'applicazione può offrire un'esperienza appropriata agli utenti di Assistive Technology, continua a essere uno dei principali obiettivi di .NET Framework 4.7.1. Per informazioni sui miglioramenti apportati all'accessibilità in .NET Framework 4.7.1, vedere [Nuove funzionalità di accessibilità in .NET Framework](whats-new-in-accessibility.md).

<a name="core471"></a>

#### <a name="base-classes"></a>Classi di base

**Supporto di .NET Standard 2.0**

[.NET Standard](../../standard/net-standard.md) definisce un set di API che devono essere disponibili in ogni implementazione .NET conforme alla versione dello strumento standard. .NET Framework 4.7.1 supporta completamente .NET Standard 2.0 e aggiunge [circa 200 API](https://github.com/dotnet/standard/blob/master/src/netstandard/src/ApiCompatBaseline.net461.txt), definite in .NET Standard 2.0 e non incluse in .NET Framework 4.6.1, 4.6.2 e 4.7. Si noti che queste versioni del .NET Framework supportano .NET Standard 2,0 solo se nel sistema di destinazione sono distribuiti anche altri file di supporto di .NET Standard. Per ulteriori informazioni, vedere il post di Blog relativo al supporto di BCL-.NET Standard 2,0 nel post di Blog relativo alle [funzionalità di runtime e compilatore di .NET Framework 4.7.1](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-runtime-and-compiler-features/) .

**Supporto per generatori di configurazioni**

I generatori di configurazioni consentono agli sviluppatori di inserire e compilare dinamicamente impostazioni di configurazione per le applicazioni in fase di esecuzione. È possibile usare generatori di configurazioni personalizzati per modificare dati esistenti in una sezione di configurazione oppure per compilare una sezione di configurazione completamente da zero. Senza i generatori di configurazioni, i file con estensione config sono statici e le rispettive impostazioni vengono definite prima dell'avvio di un'applicazione.

Per creare un generatore di configurazioni personalizzato, è necessario derivare il generatore dalla classe astratta <xref:System.Configuration.ConfigurationBuilder> ed eseguire l'override di <xref:System.Configuration.ConfigurationBuilder.ProcessConfigurationSection%2A?displayProperty=nameWithType> e <xref:System.Configuration.ConfigurationBuilder.ProcessRawXml%2A?displayProperty=nameWithType> del generatore. È necessario definire i generatori anche nel file con estensione config. Per altre informazioni, vedere la sezione relativa ai generatori di configurazioni nel post di blog [.NET Framework 4.7.1 ASP.NET and Configuration Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-asp-net-and-configuration-features/) (Funzionalità di ASP.NET e di configurazione di .NET Framework 4.7.1).

**Rilevamento delle funzionalità in fase di esecuzione**

La classe <xref:System.Runtime.CompilerServices.RuntimeFeature?displayProperty=nameWithType> fornisce un meccanismo per determinare se una funzionalità predefinita è supportata in un'implementazione .NET specifica in fase di compilazione o di esecuzione. In fase di compilazione un compilatore può verificare se sia presente un campo specifico per determinare se la funzionalità è supportata. In questo caso, può emettere il codice che sfrutta questa funzionalità. In fase di esecuzione un'applicazione può chiamare il metodo <xref:System.Runtime.CompilerServices.RuntimeFeature.IsSupported%2A?displayProperty=nameWithType> prima di emettere il codice in fase di esecuzione. Per altre informazioni, vedere [Add helper method to describe features supported by the runtime](https://github.com/dotnet/corefx/issues/17116) (Aggiungere un metodo helper per descrivere le funzionalità supportate dal runtime).

**I tipi di tupla di valori sono serializzabili**

A partire da .NET Framework 4.7.1, <xref:System.ValueTuple?displayProperty=nameWithType> e i tipi generici associati sono contrassegnati come oggetti [Serializable](xref:System.SerializableAttribute), consentendo la serializzazione binaria. Questa novità dovrebbe semplificare la migrazione dei tipi di tupla, come <xref:System.Tuple%603> e <xref:System.Tuple%604>, ai tipi di tupla di valori. Per altre informazioni, vedere la sezione relativa al compilatore e alla serializzazione di ValueTuple nel post di blog [.NET Framework 4.7.1 Runtime and Compiler Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-runtime-and-compiler-features/) (Funzionalità del runtime e del compilatore di .NET Framework 4.7.1).

**Supporto per riferimenti di sola lettura**

.NET Framework 4.7.1 aggiunge l'oggetto <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute?displayProperty=nameWithType>. Questo attributo viene usato dai compilatori dei linguaggi per contrassegnare i membri che hanno tipi o parametri restituiti per riferimenti di sola lettura. Per altre informazioni, vedere la sezione relativa al compilatore e al supporto per ReadOnlyReferences nel post di blog [.NET Framework 4.7.1 Runtime and Compiler Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-runtime-and-compiler-features/) (Funzionalità del runtime e del compilatore di .NET Framework 4.7.1). Per informazioni sui valori restituiti per riferimenti, vedere [Valori restituiti e variabili locali ref](../../csharp/programming-guide/classes-and-structs/ref-returns.md) e [Ref return values (Visual Basic)](../../visual-basic/programming-guide/language-features/procedures/ref-return-values.md) (Valori restituiti per riferimenti - Visual Basic).

<a name="clr"></a>

#### <a name="common-language-runtime-clr"></a>Common Language Runtime (CLR)

**Miglioramento delle prestazioni di Garbage Collection**

Le modifiche apportate a Garbage Collection (GC) in .NET Framework 4.7.1 migliorano le prestazioni complessive, soprattutto per le allocazioni heap oggetti grandi (LOH). In .NET Framework 4.7.1, i blocchi separati vengono usati per le allocazioni di heap oggetti piccoli (SOH) e LOH, che consente l'esecuzione delle allocazioni LOH quando il catalogo globale in background sta diffondendo il rapporto di integrità. Di conseguenza, le applicazioni che eseguono una quantità elevata di allocazioni di heap di oggetti grandi riscontreranno una riduzione dei conflitti di blocco delle allocazioni e prestazioni migliori. Per altre informazioni, vedere la sezione relativa al runtime e ai miglioramenti per le prestazioni di Garbage Collection nel post di blog [.NET Framework 4.7.1 Runtime and Compiler Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-runtime-and-compiler-features/) (Funzionalità del runtime e del compilatore di .NET Framework 4.7.1).

<a name="net471"/>

#### <a name="networking"></a>Rete

**Supporto di SHA-2 per Message.HashAlgorithm**

In .NET Framework 4.7 e versioni precedenti la proprietà <xref:System.Messaging.Message.HashAlgorithm%2A?displayProperty=nameWithType> supporta solo i valori <xref:System.Messaging.HashAlgorithm.Md5?displayProperty=nameWithType> e <xref:System.Messaging.HashAlgorithm.Sha?displayProperty=nameWithType>. A partire da .NET Framework 4.7.1, sono supportati anche <xref:System.Messaging.HashAlgorithm.Sha256?displayProperty=nameWithType>, <xref:System.Messaging.HashAlgorithm.Sha384?displayProperty=nameWithType> e <xref:System.Messaging.HashAlgorithm.Sha512?displayProperty=nameWithType>. Il fatto che questo valore venga effettivamente usato dipende da MSMQ, perché l'istanza <xref:System.Messaging.Message> stessa non esegue alcun hashing, ma semplicemente passa i valori a MSMQ. Per altre informazioni, vedere la sezione relativa al supporto di SHA-2 per Message.HashAlgorithm nel post di blog [.NET Framework 4.7.1 ASP.NET and Configuration Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-asp-net-and-configuration-features/) (Funzionalità di ASP.NET e di configurazione di .NET Framework 4.7.1).

<a name="asp-net471"></a>

#### <a name="aspnet"></a>ASP.NET

**Passaggi di esecuzione nelle applicazioni ASP.NET**

ASP.NET elabora le richieste in una pipeline predefinita che include 23 eventi. ASP.NET esegue ogni gestore eventi come passaggio di esecuzione. Nelle versioni di ASP.NET fino a .NET Framework 4.7, ASP.NET non può eseguire il flusso del contesto di esecuzione a causa del passaggio tra thread nativi e gestiti. ASP.NET esegue selettivamente il flusso solo di <xref:System.Web.HttpContext>. A partire da .NET Framework 4.7.1, il metodo <xref:System.Web.HttpApplication.OnExecuteRequestStep(System.Action{System.Web.HttpContextBase,System.Action})?displayProperty=nameWithType> consente anche ai moduli di ripristinare i dati di ambiente. Questa funzionalità è destinata alle librerie per quanto riguarda analisi, profilatura, diagnostica o transazioni, ad esempio, che si occupano del flusso di esecuzione per l'applicazione. Per altre informazioni, vedere la sezione relativa alla funzionalità dei passaggi di esecuzione di ASP.NET nel post di blog [.NET Framework 4.7.1 ASP.NET and Configuration Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-asp-net-and-configuration-features/) (Funzionalità di ASP.NET e di configurazione di .NET Framework 4.7.1).

**Analisi HttpCookie di ASP.NET**

.NET Framework 4.7.1 include un nuovo metodo, <xref:System.Web.HttpCookie.TryParse%2A?displayProperty=nameWithType>, che offre un modo standardizzato per creare un oggetto <xref:System.Web.HttpCookie> da una stringa e assegnare accuratamente valori di cookie come la data di scadenza e il percorso. Per altre informazioni, vedere la sezione relativa all'analisi HttpCookie di ASP.NET nel post di blog [.NET Framework 4.7.1 ASP.NET and Configuration Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-asp-net-and-configuration-features/) (Funzionalità di ASP.NET e di configurazione di .NET Framework 4.7.1).

**Opzioni di hash SHA-2 per le credenziali di autenticazione di ASP.NET Forms**

In .NET Framework 4.7 e versioni precedenti, ASP.NET consente agli sviluppatori di archiviare le credenziali utente con password con hash in file di configurazione usando MD5 o SHA1. A partire da .NET Framework 4.7.1, ASP.NET supporta anche nuove opzioni di hash SHA-2 sicure come SHA256, SHA384 e SHA512. SHA1 resta l'opzione predefinita ed è possibile definire un algoritmo hash non predefinito nel file di configurazione Web. Ad esempio:

```xml
<system.web>
    <authentication mode="Forms">
        <forms loginUrl="~/login.aspx">
          <credentials passwordFormat="SHA512">
            <user name="jdoe" password="6D003E98EA1C7F04ABF8FCB375388907B7F3EE06F278DB966BE960E7CBBD103DF30CA6D61F7E7FD981B2E4E3A64D43C836A4BEDCA165C33B163E6BCDC538A664" />
          </credentials>
        </forms>
    </authentication>
</system.web>
```

<a name="v47"></a>

## <a name="whats-new-in-net-framework-47"></a>Novità di .NET Framework 4.7

.NET Framework 4.7 include nuove funzionalità nelle aree seguenti:

- [Classi di base](#Core47)
- [Rete](#net47)
- [ASP.NET](#ASP-NET47)
- [Windows Communication Foundation (WCF)](#wcf47)
- [Windows Forms](#wf47)
- [Windows Presentation Foundation (WPF)](#WPF47)

Per l'elenco delle nuove API aggiunte a .NET Framework 4.7, vedere l'argomento [.NET Framework 4.7 API Changes](https://github.com/Microsoft/dotnet/blob/master/releases/net47/dotnet47-api-changes.md) (Modifiche alle API di .NET Framework 4.7) su GitHub. Per un elenco dei miglioramenti apportati alle funzionalità e delle correzioni di bug in .NET Framework 4.7, vedere[.NET Framework 4.7 List of Changes](https://github.com/Microsoft/dotnet/blob/master/releases/net47/dotnet47-changes.md) (Elenco delle modifiche di .NET Framework 4.7) su GitHub. Per ulteriori informazioni, vedere [annunciare il .NET Framework 4,7](https://devblogs.microsoft.com/dotnet/announcing-the-net-framework-4-7/) nel Blog di .NET.

<a name="Core47"></a>

#### <a name="base-classes"></a>Classi di base

.NET Framework 4.7 migliora la serializzazione di <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>:

**Funzionalità migliorata con la crittografia a curva ellittica (ECC)***

In .NET Framework 4.7 sono stati aggiunti i metodi `ImportParameters(ECParameters)` alle classi <xref:System.Security.Cryptography.ECDsa> e <xref:System.Security.Cryptography.ECDiffieHellman> per consentire a un oggetto di rappresentare una chiave già stabilita. È stato anche aggiunto un metodo `ExportParameters(Boolean)` per l'esportazione della chiave usando parametri della curva esplicita.

.NET Framework 4.7 aggiunge anche il supporto per le curve aggiuntive (inclusa la suite di curve Brainpool) e ha aggiunto definizioni predefinite per semplificare la creazione attraverso i nuovi metodi factory <xref:System.Security.Cryptography.ECDsa.Create%2A> e <xref:System.Security.Cryptography.ECDiffieHellman.Create%2A>.

È possibile visualizzare un [esempio dei miglioramenti alla crittografia di .NET Framework 4.7](https://gist.github.com/richlander/5a182899895a87a296c21ada97f7a54e) su GitHub.

**Supporto migliorato per i caratteri di controllo da DataContractJsonSerializer**

Nella .NET Framework 4,7 la <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> classe serializza i caratteri di controllo in conformità con lo standard ECMAScript 6. Questo comportamento è abilitato per impostazione predefinita per le applicazioni destinate a .NET Framework 4,7 ed è una funzionalità di consenso esplicito per le applicazioni in esecuzione con .NET Framework 4,7, ma destinate a una versione precedente di .NET Framework. Per ulteriori informazioni, vedere la sezione relativa alla [compatibilità delle applicazioni](../migration-guide/application-compatibility.md) .

<a name="net47"></a>

#### <a name="networking"></a>Rete

.NET Framework 4.7 aggiunge la funzionalità seguente relativa alla rete:

**Supporto del sistema operativo predefinito per i protocolli TLS***

Lo stack TLS, che viene usato da <xref:System.Net.Security.SslStream?displayProperty=nameWithType> e i componenti up-stack, ad esempio HTTP, FTP e SMTP, consentono agli sviluppatori di usare i protocolli TLS predefiniti supportati dal sistema operativo. Gli sviluppatori non devono più impostare come hardcoded una versione TLS.

<a name="ASP-NET47"></a>

#### <a name="aspnet"></a>ASP.NET

In .NET Framework 4.7 ASP.NET include le nuove funzionalità seguenti:

**Estendibilità della cache oggetti**

A partire da .NET Framework 4.7, ASP.NET aggiunge un nuovo set di API che consente agli sviluppatori di sostituire le implementazioni di ASP.NET predefinite per la cache di oggetti in memoria e il monitoraggio della memoria. Gli sviluppatori possono ora sostituire uno qualsiasi dei seguenti tre componenti se l'implementazione di ASP.NET non è sufficiente:

- **Archivio cache oggetti**. Usando la nuova sezione di configurazione dei provider di cache, gli sviluppatori possono inserire nuove implementazioni di una cache oggetti per un'applicazione ASP.NET con la nuova interfaccia **ICacheStoreProvider**.

- **Monitoraggio della memoria**. Il monitoraggio della memoria predefinito in ASP.NET invia una notifica alle applicazioni quando stanno per raggiungere il limite di byte privati configurato per il processo o quando la RAM fisica totale disponibile nel computer è insufficiente. Quando si approssimano questi limiti, vengono generate le notifiche. Per alcune applicazioni, le notifiche vengono generate troppo vicino ai limiti configurati per consentire reazioni utili. Gli sviluppatori possono ora scrivere monitoraggi della memoria personalizzati in modo da sostituire quello predefinito usando la proprietà <xref:System.Web.Hosting.ApplicationMonitors.MemoryMonitor%2A?displayProperty=nameWithType>.

- **Reazioni al limite di memoria**. Per impostazione predefinita, ASP.NET prova a ridurre la cache oggetti e a chiamare periodicamente <xref:System.GC.Collect%2A?displayProperty=nameWithType> quando si approssima il limite di byte privati per il processo. Per alcune applicazioni, la frequenza delle chiamate a <xref:System.GC.Collect%2A?displayProperty=nameWithType> o la quantità di cache che verrà tagliata sono inefficienti. Gli sviluppatori possono ora sostituire o integrare il comportamento predefinito sottoscrivendo le implementazioni **IObserver** al monitoraggio della memoria dell'applicazione.

<a name="wcf47"></a>

#### <a name="windows-communication-foundation-wcf"></a>Windows Communication Foundation (WCF)

Windows Communication Foundation (WCF) aggiunge le seguenti funzionalità e modifiche:

**Possibilità di configurare le impostazioni predefinite di sicurezza dei messaggi su TLS 1.1 o TLS 1.2**

A partire da .NET Framework 4.7, WCF consente di configurare TLS 1.1 o TLS 1.2, oltre a SSL 3.0 e TLS 1.0, come protocollo di sicurezza del messaggio predefinito. Questa funzionalità prevede il consenso esplicito e occorre quindi aggiungere la voce seguente al file di configurazione dell'applicazione:

```xml
<runtime>
   <AppContextSwitchOverrides value="Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols=false;Switch.System.Net.DontEnableSchUseStrongCrypto=false" />
</runtime>
```

**Miglioramento dell'affidabilità le applicazioni WCF e della serializzazione WCF**

WCF include un numero di modifiche al codice che eliminano le race condition, migliorando così le prestazioni e l'affidabilità delle opzioni di serializzazione. Queste includono:

- Supporto migliorato per la combinazione di codice sincrono e asincrono nelle chiamate a **SocketConnection.BeginRead** e **SocketConnection.Read**.
- Maggiore affidabilità durante l'interruzione di una connessione con **SharedConnectionListener** e **DuplexChannelBinder**.
- Maggiore affidabilità delle operazioni di serializzazione quando si chiama il metodo <xref:System.Runtime.Serialization.FormatterServices.GetSerializableMembers%28System.Type%29?displayProperty=nameWithType>.
- Maggiore affidabilità durante la rimozione di un oggetto waiter con la chiamata del metodo **ChannelSynchronizer.RemoveWaiter**.

<a name="wf47"></a>

#### <a name="windows-forms"></a>Windows Forms

In .NET Framework 4.7 Windows Form migliora il supporto per i monitor con valori DPI alti.

**Supporto di valori DPI alti**

A partire dalle applicazioni destinate a .NET Framework 4.7, le funzionalità di .NET Framework prevedono il supporto dei di valori DPI alti e dinamici per Windows Forms Application. Il supporto di valori DPI alti migliora il layout e l'aspetto dei moduli e dei controlli nei monitor di valori DPI alti. I valori DPI cambiano il layout e l'aspetto dei moduli e dei controlli quando l'utente modifica i valori DPI o visualizza il fattore di scala di un'applicazione in esecuzione.

Il supporto di valori DPI alti è una funzionalità di consenso esplicito che è possibile configurare definendo una [\<System.Windows.Forms.ConfigurationSection>](../configure-apps/file-schema/winforms/index.md) sezione nel file di configurazione dell'applicazione. Per altre informazioni sull'aggiunta del supporto di valori DPI elevati e dinamici a un'applicazione Windows Form, vedere [Supporto di valori DPI elevati in Windows Form](../winforms/high-dpi-support-in-windows-forms.md).

<a name="WPF47"></a>

#### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)

In .NET Framework 4.7 WPF include i miglioramenti seguenti:

**Supporto per lo stack di tocco/stilo basato sui messaggi basato sui messaggi WM_POINTER Windows**

È ora possibile scegliere di usare uno stack di tocco/stilo basato sui [messaggi WM_POINTER](https://docs.microsoft.com/previous-versions/windows/desktop/InputMsg/messages) invece che su WISP (Windows Ink Services Platform). Si tratta di una funzionalità di consenso esplicito in .NET Framework. Per ulteriori informazioni, vedere la sezione relativa alla [compatibilità delle applicazioni](../migration-guide/application-compatibility.md) .

**Nuova implementazione per le API di stampa WPF**

Le API di stampa di WPF nella classe <xref:System.Printing.PrintQueue?displayProperty=nameWithType> chiamano l'[API di gestione del pacchetto dei documenti di stampa](/windows/desktop/printdocs/tailored-app-printing-api) invece dell'[API di stampa XPS](/windows/desktop/printdocs/xps-printing) deprecata. Per informazioni sull'effetto di questa modifica sulla compatibilità delle applicazioni, vedere la sezione relativa alla [compatibilità delle applicazioni](../migration-guide/application-compatibility.md) .

<a name="v462"></a>

## <a name="whats-new-in-net-framework-462"></a>Novità di .NET Framework 4.6.2

.NET Framework 4.6.2 include nuove funzionalità nelle aree seguenti:

- [ASP.NET](#ASPNET462)

- [Categorie di caratteri](#Strings)

- [Crittografia](#Crypto462)

- [SqlClient](#SQLClient)

- [Windows Communication Foundation](#WCF)

- [Windows Presentation Foundation (WPF)](#WPF462)

- [Windows Workflow Foundation (WF)](#WF462)

- [ClickOnce](#clickonce-1)

- [Conversione di app Windows Forms e WPF in app UWP](#UWPConvert)

- [Miglioramenti apportati al debug](#Debug462)

Per un elenco delle nuove API aggiunte a .NET Framework 4.6.2, vedere l'argomento [.NET Framework 4.6.2 API Changes](https://github.com/Microsoft/dotnet/blob/master/releases/net462/dotnet462-api-changes.md) (Modifiche alle API di .NET Framework 4.6.2) su GitHub. Per un elenco dei miglioramenti apportati alle funzionalità e delle correzioni di bug in .NET Framework 4.6.2, vedere[.NET Framework 4.6.2 List of Changes](https://github.com/Microsoft/dotnet/blob/master/releases/net462/dotnet462-changes.md) (Elenco delle modifiche di .NET Framework 4.6.2) su GitHub. Per ulteriori informazioni, vedere [annuncio .NET Framework 4.6.2](https://devblogs.microsoft.com/dotnet/announcing-net-framework-4-6-2/) nel Blog di .NET.

<a name="ASPNET462"></a>

### <a name="aspnet"></a>ASP.NET

In .NET Framework 4.6.2, ASP.NET include i miglioramenti seguenti:

**Supporto migliorato per i messaggi di errore localizzati nei validator di annotazione dei dati**

I validator di annotazione dei dati consentono di eseguire la convalida aggiungendo uno o più attributi a una proprietà di classe. L'elemento <xref:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage%2A?displayProperty=nameWithType> dell'attributo definisce il testo del messaggio di errore se la convalida non riesce. A partire da .NET Framework 4.6.2, ASP.NET semplifica la localizzazione dei messaggi di errore. I messaggi di errore verranno localizzati se:

1. <xref:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage%2A?displayProperty=nameWithType> viene indicato nell'attributo di convalida.

2. Il file di risorse è archiviato nella cartella App_LocalResources.

3. Il nome del file di risorse localizzato ha il formato `DataAnnotation.Localization.{` *nome* `}.resx` , dove *nome* è un nome di impostazioni cultura nel formato *codiceLingua* `-` *paese/codicepaese* o *codiceLingua*.

4. Il nome della chiave della risorsa è la stringa assegnata all'attributo <xref:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage%2A?displayProperty=nameWithType> e il relativo valore è il messaggio di errore localizzato.

Ad esempio, l'attributo di annotazione dei dati seguente definisce il messaggio di errore delle impostazioni cultura predefinite per una classificazione non valida.

```csharp
public class RatingInfo
{
   [Required(ErrorMessage = "The rating must be between 1 and 10.")]
   [Display(Name = "Your Rating")]
   public int Rating { get; set; }
}
```

```vb
Public Class RatingInfo
   <Required(ErrorMessage = "The rating must be between 1 and 10.")>
   <Display(Name = "Your Rating")>
   Public Property Rating As Integer = 1
End Class
```

È quindi possibile creare il file di risorse DataAnnotation.Localization.fr.resx, la cui chiave è la stringa del messaggio di errore e il cui valore è il messaggio di errore localizzato. Il file deve essere salvato nella cartella `App.LocalResources`. Ad esempio, di seguito vengono riportati la chiave e il relativo valore in un messaggio di errore in lingua francese (fr):

| Nome                                 | valore                                     |
| ------------------------------------ | ----------------------------------------- |
| La classificazione deve essere compresa tra 1 e 10. | La note doit être comprise entre 1 et 10. |

 La localizzazione dell'annotazione dei dati è anche estensibile. Gli sviluppatori possono collegare il proprio provider di localizzazione delle stringhe implementando l'interfaccia di <xref:System.Web.Globalization.IStringLocalizerProvider> per archiviare la stringa di localizzazione in un posto diverso da un file di risorse.

 **Supporto asincrono con i provider dell'archivio per lo stato sessione**

 ASP.NET ora offre metodi di restituzione di Task da usare con i provider dell'archivio per lo stato sessione, consentendo quindi alle applicazioni ASP.NET di sfruttare i vantaggi delle operazioni asincrone in termini di scalabilità. Per supportare le operazioni asincrone con i provider dell'archivio per lo stato sessione, ASP.NET include una nuova interfaccia, <xref:System.Web.SessionState.ISessionStateModule?displayProperty=nameWithType>, che eredita da <xref:System.Web.IHttpModule> e consente agli sviluppatori di implementare i propri provider di moduli dello stato sessione e di archiviazione asincrona delle sessioni. L'interfaccia viene definita come segue:

```csharp
public interface ISessionStateModule : IHttpModule {
    void ReleaseSessionState(HttpContext context);
    Task ReleaseSessionStateAsync(HttpContext context);
}
```

```vb
Public Interface ISessionStateModule : Inherits IHttpModule
   Sub ReleaseSessionState(context As HttpContext)
   Function ReleaseSessionStateAsync(context As HttpContext) As Task
End Interface
```

 La classe <xref:System.Web.SessionState.SessionStateUtility> include anche due nuovi metodi, <xref:System.Web.SessionState.SessionStateUtility.IsSessionStateReadOnly%2A> e <xref:System.Web.SessionState.SessionStateUtility.IsSessionStateRequired%2A>, che possono essere usati a supporto delle operazioni asincrone.

 **Supporto asincrono per i provider di cache di output**

 A partire da .NET Framework 4.6.2, i metodi di restituzione di Task possono essere usati con i provider di cache di output per usufruire dei vantaggi di scalabilità offerti dalle operazioni asincrone.  I provider che implementano questi metodi riducono i blocchi dei thread su un server Web e migliorano la scalabilità di un servizio ASP.NET.

 Per supportare i provider di cache di output asincroni sono state aggiunte le API seguenti:

- La classe <xref:System.Web.Caching.OutputCacheProviderAsync?displayProperty=nameWithType>, che eredita da <xref:System.Web.Caching.OutputCacheProvider?displayProperty=nameWithType> e consente agli sviluppatori di implementare un provider di cache di output asincrono.

- La classe <xref:System.Web.Caching.OutputCacheUtility>, che fornisce metodi di supporto per la configurazione della cache di output.

- 18 nuovi metodi nella classe <xref:System.Web.HttpCachePolicy?displayProperty=nameWithType>. Sono inclusi <xref:System.Web.HttpCachePolicy.GetCacheability%2A>, <xref:System.Web.HttpCachePolicy.GetCacheExtensions%2A>, <xref:System.Web.HttpCachePolicy.GetETag%2A>, <xref:System.Web.HttpCachePolicy.GetETagFromFileDependencies%2A>, <xref:System.Web.HttpCachePolicy.GetMaxAge%2A>, <xref:System.Web.HttpCachePolicy.GetMaxAge%2A>, <xref:System.Web.HttpCachePolicy.GetNoStore%2A>, <xref:System.Web.HttpCachePolicy.GetNoTransforms%2A>, <xref:System.Web.HttpCachePolicy.GetOmitVaryStar%2A>, <xref:System.Web.HttpCachePolicy.GetProxyMaxAge%2A>, <xref:System.Web.HttpCachePolicy.GetRevalidation%2A>, <xref:System.Web.HttpCachePolicy.GetUtcLastModified%2A>, <xref:System.Web.HttpCachePolicy.GetVaryByCustom%2A>, <xref:System.Web.HttpCachePolicy.HasSlidingExpiration%2A> e <xref:System.Web.HttpCachePolicy.IsValidUntilExpires%2A>.

- 2 nuovi metodi nella classe <xref:System.Web.HttpCacheVaryByContentEncodings?displayProperty=nameWithType>: <xref:System.Web.HttpCacheVaryByContentEncodings.GetContentEncodings%2A> e <xref:System.Web.HttpCacheVaryByContentEncodings.SetContentEncodings%2A>.

- 2 nuovi metodi nella classe <xref:System.Web.HttpCacheVaryByHeaders?displayProperty=nameWithType>: <xref:System.Web.HttpCacheVaryByHeaders.GetHeaders%2A> e <xref:System.Web.HttpCacheVaryByHeaders.SetHeaders%2A>.

- 2 nuovi metodi nella classe <xref:System.Web.HttpCacheVaryByParams?displayProperty=nameWithType>: <xref:System.Web.HttpCacheVaryByParams.GetParams%2A> e <xref:System.Web.HttpCacheVaryByParams.SetParams%2A>.

- Nella classe <xref:System.Web.Caching.AggregateCacheDependency?displayProperty=nameWithType> il metodo <xref:System.Web.Caching.AggregateCacheDependency.GetFileDependencies%2A>.

- In <xref:System.Web.Caching.CacheDependency> il metodo <xref:System.Web.Caching.CacheDependency.GetFileDependencies%2A>.

<a name="Strings"></a>

### <a name="character-categories"></a>Categorie di caratteri

I caratteri in .NET Framework 4.6.2 sono classificati in base allo standard [Unicode, versione 8.0.0](https://www.unicode.org/versions/Unicode8.0.0/). In .NET Framework 4.6 e .NET Framework 4.6.1, i caratteri sono stati classificati in base alle categorie di caratteri Unicode 6.3.

Il supporto per Unicode 8.0 è limitato alla classificazione dei caratteri della classe <xref:System.Globalization.CharUnicodeInfo> e ai tipi e metodi basati sulla stessa. Sono inclusi la classe <xref:System.Globalization.StringInfo>, il metodo <xref:System.Char.GetUnicodeCategory%2A?displayProperty=nameWithType> in overload e le [classi di caratteri](../../standard/base-types/character-classes-in-regular-expressions.md) riconosciute dal motore delle espressioni regolari di .NET Framework.  Il confronto e l'ordinamento di stringhe e caratteri non sono interessati da questa modifica e continuano a basarsi sul sistema operativo sottostante o, nei sistemi Windows 7, sui dati dei caratteri provenienti da .NET Framework.

Per informazioni sulle modifiche nelle categorie di caratteri da Unicode 6.0 a Unicode 7.0, vedere [The Unicode Standard, Version 7.0.0](https://www.unicode.org/versions/Unicode7.0.0/) nel sito Web The Unicode Consortium. Per informazioni sulle modifiche da Unicode 7.0 a Unicode 8.0, vedere [The Unicode Standard, Version 8.0.0](https://www.unicode.org/versions/Unicode8.0.0/) nel sito Web The Unicode Consortium.

<a name="Crypto462"></a>

### <a name="cryptography"></a>Crittografia

**Supporto per i certificati X509 contenenti FIPS 186-3 DSA**

.NET Framework 4.6.2 aggiunge il supporto per certificati DSA (Digital Signature Algorithm) X509 le cui chiavi superano il limite di 1024 bit di FIPS 186-2.

Oltre a supportare le dimensioni della chiave più grandi di FIPS 186-3, .NET Framework 4.6.2 consente di calcolare le firme con la famiglia SHA-2 di algoritmi hash (SHA256, SHA384 e SHA512). Il supporto per FIPS 186-3 è assicurato dalla nuova classe <xref:System.Security.Cryptography.DSACng?displayProperty=nameWithType>.

In conformità alle recenti modifiche apportate alla classe <xref:System.Security.Cryptography.RSA> in .NET Framework 4.6 e alla classe <xref:System.Security.Cryptography.ECDsa> in .NET Framework 4.6.1, la classe di base astratta <xref:System.Security.Cryptography.DSA> in .NET Framework 4.6.2 offre metodi aggiuntivi per consentire ai chiamanti di usare questa funzionalità senza eseguire il cast. È possibile chiamare il metodo di estensione <xref:System.Security.Cryptography.X509Certificates.DSACertificateExtensions.GetDSAPrivateKey%2A?displayProperty=nameWithType> per firmare i dati, come illustrato nell'esempio seguente.

```csharp
public static byte[] SignDataDsaSha384(byte[] data, X509Certificate2 cert)
{
    using (DSA dsa = cert.GetDSAPrivateKey())
    {
        return dsa.SignData(data, HashAlgorithmName.SHA384);
    }
}
```

```vb
Public Shared Function SignDataDsaSha384(data As Byte(), cert As X509Certificate2) As Byte()
    Using DSA As DSA = cert.GetDSAPrivateKey()
        Return DSA.SignData(data, HashAlgorithmName.SHA384)
    End Using
End Function
```

Ed è possibile chiamare il metodo di estensione <xref:System.Security.Cryptography.X509Certificates.DSACertificateExtensions.GetDSAPublicKey%2A?displayProperty=nameWithType> per verificare i dati firmati, come illustrato nell'esempio seguente.

```csharp
public static bool VerifyDataDsaSha384(byte[] data, byte[] signature, X509Certificate2 cert)
{
    using (DSA dsa = cert.GetDSAPublicKey())
    {
        return dsa.VerifyData(data, signature, HashAlgorithmName.SHA384);
    }
}
```

```vb
 Public Shared Function VerifyDataDsaSha384(data As Byte(), signature As Byte(), cert As X509Certificate2) As Boolean
    Using dsa As DSA = cert.GetDSAPublicKey()
        Return dsa.VerifyData(data, signature, HashAlgorithmName.SHA384)
    End Using
End Function
```

**Maggiore chiarezza degli input per le routine di derivazione di chiave ECDiffieHellman**

.NET Framework 3.5 offre in più il supporto per la chiave concordata Elliptic Curve Diffie-Hellman con tre diverse routine di funzione di derivazione di chiave (KDF). Gli input per le routine e le routine stesse sono stati configurati usando le proprietà dell'oggetto <xref:System.Security.Cryptography.ECDiffieHellmanCng>. Ma poiché non tutte le routine leggono tutte le proprietà di input, in passato era molto probabile che si creasse confusione per lo sviluppatore.

Per gestire questo aspetto in .NET Framework 4.6.2 sono stati aggiunti i tre metodi seguenti alla classe base <xref:System.Security.Cryptography.ECDiffieHellman> per rappresentare in modo chiaro le routine di funzione di derivazione chiave e i rispettivi input:

|Metodo ECDiffieHellman|Descrizione|
|----------------------------|-----------------|
|<xref:System.Security.Cryptography.ECDiffieHellman.DeriveKeyFromHash%28System.Security.Cryptography.ECDiffieHellmanPublicKey%2CSystem.Security.Cryptography.HashAlgorithmName%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%29>|Deriva il materiale della chiave usando la formula<br /><br /> HASH(secretPrepend &#124;&#124; *x* &#124;&#124; secretAppend)<br /><br /> HASH(secretPrepend OrElse *x* OrElse secretAppend)<br /><br /> dove *x* è il risultato calcolato dell'algoritmo EC Diffie-Hellman.|
|<xref:System.Security.Cryptography.ECDiffieHellman.DeriveKeyFromHmac%28System.Security.Cryptography.ECDiffieHellmanPublicKey%2CSystem.Security.Cryptography.HashAlgorithmName%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%29>|Deriva il materiale della chiave usando la formula<br /><br /> HMAC(hmacKey, secretPrepend &#124;&#124; *x* &#124;&#124; secretAppend)<br /><br /> HMAC(hmacKey, secretPrepend OrElse *x* OrElse secretAppend)<br /><br /> dove *x* è il risultato calcolato dell'algoritmo EC Diffie-Hellman.|
|<xref:System.Security.Cryptography.ECDiffieHellman.DeriveKeyTls%28System.Security.Cryptography.ECDiffieHellmanPublicKey%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%29>|Deriva il materiale della chiave usando l'algoritmo di derivazione TLS della funzione pseudocasuale.|

**Supporto per la crittografia simmetrica con chiave persistente**

La libreria di crittografia di Windows (CNG) ha aggiunto il supporto per l'archiviazione delle chiavi simmetriche persistenti e l'uso delle chiavi simmetriche archiviate nell'hardware e .NET Framework 4.6.2 ha reso possibile l'uso di questa funzionalità da parte degli sviluppatori.  Poiché le nozioni di nome della chiave e provider di chiavi sono specifiche dell'implementazione, questa funzionalità richiede l'uso del costruttore dei tipi di implementazione concreti anziché della modalità factory preferita, ad esempio la chiamata a `Aes.Create`.

Il supporto per la crittografia simmetrica con chiave persistente esiste per gli algoritmi AES (<xref:System.Security.Cryptography.AesCng>) e 3DES (<xref:System.Security.Cryptography.TripleDESCng>). Ad esempio:

```csharp
public static byte[] EncryptDataWithPersistedKey(byte[] data, byte[] iv)
{
    using (Aes aes = new AesCng("AesDemoKey", CngProvider.MicrosoftSoftwareKeyStorageProvider))
    {
        aes.IV = iv;

        // Using the zero-argument overload is required to make use of the persisted key
        using (ICryptoTransform encryptor = aes.CreateEncryptor())
        {
            if (!encryptor.CanTransformMultipleBlocks)
            {
                throw new InvalidOperationException("This is a sample, this case wasn't handled...");
            }

            return encryptor.TransformFinalBlock(data, 0, data.Length);
        }
    }
}
```

```vb
Public Shared Function EncryptDataWithPersistedKey(data As Byte(), iv As Byte()) As Byte()
    Using Aes As Aes = New AesCng("AesDemoKey", CngProvider.MicrosoftSoftwareKeyStorageProvider)
        Aes.IV = iv

        ' Using the zero-argument overload Is required to make use of the persisted key
        Using encryptor As ICryptoTransform = Aes.CreateEncryptor()
            If Not encryptor.CanTransformMultipleBlocks Then
                Throw New InvalidOperationException("This is a sample, this case wasn't handled...")
            End If
            Return encryptor.TransformFinalBlock(data, 0, data.Length)
        End Using
    End Using
End Function
```

**Supporto SignedXml per generazione di hash SHA-2**

.NET Framework 4.6.2 offre il supporto per la classe <xref:System.Security.Cryptography.Xml.SignedXml> per i metodi di firma SHA256, RSA-SHA384 e RSA-SHA512 PKCS#1, mentre SHA256, SHA384 e SHA512 fanno riferimento agli algoritmi con classificazione.

Le costanti URI sono tutte esposte in <xref:System.Security.Cryptography.Xml.SignedXml>:

|Campo SignedXml|Costante|
|---------------------|--------------|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigSHA256Url>|"http://www.w3.org/2001/04/xmlenc#sha256"|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigRSASHA256Url>|"http://www.w3.org/2001/04/xmldsig-more#rsa-sha256"|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigSHA384Url>|"http://www.w3.org/2001/04/xmldsig-more#sha384"|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigRSASHA384Url>|"http://www.w3.org/2001/04/xmldsig-more#rsa-sha384"|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigSHA512Url>|"http://www.w3.org/2001/04/xmlenc#sha512"|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigRSASHA512Url>|"http://www.w3.org/2001/04/xmldsig-more#rsa-sha512"|

 Tutti i programmi che hanno registrato un gestore personalizzato <xref:System.Security.Cryptography.SignatureDescription> in <xref:System.Security.Cryptography.CryptoConfig> per aggiungere il supporto per questi algoritmi continueranno a funzionare come prima, ma poiché ora esistono impostazioni predefinite nella piattaforma, la registrazione di <xref:System.Security.Cryptography.CryptoConfig> non è più necessaria.

<a name="SQLClient"></a>

### <a name="sqlclient"></a>SqlClient

Il provider di dati .NET Framework per SQL Server (<xref:System.Data.SqlClient?displayProperty=nameWithType>) include le nuove funzionalità seguenti in .NET Framework 4.6.2:

**Pool di connessioni e timeout con i database SQL di Azure**

Quando il pool di connessioni è abilitato e si verifica un timeout o un altro errore di accesso, viene memorizzata nella cache un'eccezione e l'eccezione memorizzata nella cache viene generata per qualsiasi tentativo di connessione successivo per i 5 secondi successivi a 1 minuto. Per altre informazioni, vedere [Pool di connessioni SQL Server (ADO.NET)](../data/adonet/sql-server-connection-pooling.md).

Questo comportamento è da evitare quando ci si connette ai database SQL di Azure, poiché i tentativi di connessione possono non riuscire per errori temporanei che in genere si risolvono rapidamente. Per ottimizzare l'esperienza dei tentativi di connessione, il comportamento del periodo di blocco del pool di connessioni viene rimosso quando le connessioni ai database SQL di Azure hanno esito negativo.

L'aggiunta della nuova `PoolBlockingPeriod` parola chiave consente di selezionare il periodo di blocco più adatto per l'app. I possibili valori sono:

<xref:System.Data.SqlClient.PoolBlockingPeriod.Auto>

Il periodo di blocco del pool di connessioni per un'applicazione che si connette a un database SQL di Azure è disabilitato e il periodo di blocco del pool di connessioni per un'applicazione che si connette a qualsiasi altra istanza di SQL Server è abilitato. Si tratta del valore predefinito. Se il nome dell'endpoint server termina in uno dei modi seguenti, vengono considerati i database SQL di Azure:

- .database.windows.net

- .database.chinacloudapi.cn

- .database.usgovcloudapi.net

- .database.cloudapi.de

<xref:System.Data.SqlClient.PoolBlockingPeriod.AlwaysBlock>

Il periodo di blocco del pool di connessioni è sempre abilitato.

<xref:System.Data.SqlClient.PoolBlockingPeriod.NeverBlock>

Il periodo di blocco del pool di connessioni è sempre disabilitato.

**Miglioramenti per Always Encrypted**

SQLClient introduce due miglioramenti per Always Encrypted:

- Per migliorare le prestazioni delle query con parametri su colonne di database crittografate, i metadati di crittografia per i parametri di query ora vengono memorizzati nella cache. Con la proprietà <xref:System.Data.SqlClient.SqlConnection.ColumnEncryptionQueryMetadataCacheEnabled%2A?displayProperty=nameWithType> impostata su `true`, ovvero il valore predefinito, se la stessa query viene chiamata più volte, il client recupera i metadati dei parametri dal server una sola volta.

- Le voci delle chiavi di crittografia delle colonne nella cache delle chiavi ora vengono eliminate dopo un intervallo di tempo configurabile, impostato usando la proprietà <xref:System.Data.SqlClient.SqlConnection.ColumnEncryptionKeyCacheTtl%2A?displayProperty=nameWithType>.

<a name="WCF"></a>

### <a name="windows-communication-foundation"></a>Windows Communication Foundation

In .NET Framework 4.6.2, Windows Communication Foundation è stato ottimizzato nelle aree seguenti:

**Supporto della sicurezza del trasporto WCF per i certificati archiviati usando CNG**

La sicurezza del trasporto WCF supporta i certificati archiviati usando la libreria di crittografia di Windows (CNG). In .NET Framework 4.6.2 questo supporto è limitato all'utilizzo dei certificati con una chiave pubblica che ha un esponente di lunghezza non superiore a 32 bit. Quando un'applicazione ha come destinazione .NET Framework 4.6.2, questa funzionalità è attivata per impostazione predefinita.

Per le applicazioni destinate a .NET Framework 4.6.1 e versioni precedenti ma in esecuzione nel .NET Framework 4.6.2, questa funzionalità può essere abilitata aggiungendo la riga seguente alla [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) sezione del file di app.config o web.config.

```xml
<AppContextSwitchOverrides
    value="Switch.System.ServiceModel.DisableCngCertificates=false"
/>
```

L'operazione può essere eseguita anche a livello di codice nel modo seguente:

```csharp
private const string DisableCngCertificates = @"Switch.System.ServiceModel.DisableCngCertificates";
AppContext.SetSwitch(disableCngCertificates, false);
```

```vb
Const DisableCngCertificates As String = "Switch.System.ServiceModel.DisableCngCertificates"
AppContext.SetSwitch(disableCngCertificates, False)
```

**Miglioramento del supporto per più regole di regolazione dell'ora legale con la classe DataContractJsonSerializer**

I clienti possono usare un'impostazione di configurazione dell'applicazione per determinare se la classe <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> supporta più regole di regolazione per un singolo fuso orario. È una funzionalità che prevede il consenso esplicito. Per abilitarla aggiungere la seguente impostazione nel file di configurazione dell'applicazione:

```xml
<runtime>
     <AppContextSwitchOverrides value="Switch.System.Runtime.Serialization.DoNotUseTimeZoneInfo=false" />
</runtime>
```

Quando questa funzionalità è abilitata, un oggetto <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> usa il tipo <xref:System.TimeZoneInfo> anziché il tipo <xref:System.TimeZone> per deserializzare i dati di data e ora. <xref:System.TimeZoneInfo> supporta più regole di regolazione, quindi consente di lavorare con i dati cronologici relativi al fuso orario, al contrario di <xref:System.TimeZone>.

Per altre informazioni sulla struttura di <xref:System.TimeZoneInfo> e sulle regolazioni per il fuso orario, vedere [Panoramica sul fuso orario](../../standard/datetime/time-zone-overview.md).

**Ricerca più accurata con NetNamedPipeBinding**

WCF offre una nuova impostazione di applicazione che può essere specificata sulle applicazioni client in modo da assicurare che si connettano sempre al servizio in ascolto sull'URI che meglio corrisponde a quello richiesto. Con questa impostazione impostata su `false` (impostazione predefinita), i client che usano <xref:System.ServiceModel.NetNamedPipeBinding> sono in grado di tentare la connessione a un servizio in ascolto su un URI che è una sottostringa dell'URI richiesto.

Ad esempio, un client tenta di connettersi a un servizio in ascolto su `net.pipe://localhost/Service1`, ma un altro servizio in esecuzione nello stesso computer con privilegi di amministratore è in ascolto su `net.pipe://localhost`. Con l'impostazione di applicazione impostata su `false`, il client tenterebbe di connettersi al servizio errato. Dopo aver impostato l'impostazione di applicazione su `true`, il client si connetterà sempre al servizio più pertinente.

> [!NOTE]
> I client che usano <xref:System.ServiceModel.NetNamedPipeBinding> trovano i servizi basati sull'indirizzo di base del servizio, se esiste, anziché sull'indirizzo completo dell'endpoint. Per assicurarsi che l'impostazione funzioni sempre, il servizio deve usare un indirizzo di base univoco.

Per abilitare questa modifica, aggiungere la seguente impostazione di applicazione al file di configurazione dell'applicazione o del Web dell'applicazione client:

```xml
<configuration>
    <appSettings>
        <add key="wcf:useBestMatchNamedPipeUri" value="true" />
    </appSettings>
</configuration>
```

**SSL 3.0 non è un protocollo predefinito**

Quando si usa NetTcp con la sicurezza del trasporto e un tipo di certificato con credenziali, SSL 3.0 non è più un protocollo predefinito usato per negoziare una connessione protetta. Nella maggior parte dei casi non vi sarà alcun impatto sulle applicazioni esistenti, poiché TLS 1.0 è incluso nell'elenco di protocolli per NetTcp. Tutti i client esistenti devono essere in grado di negoziare una connessione usando almeno TLS 1.0. Se è necessario il protocollo Ssl3, usare uno dei meccanismi di configurazione seguenti per aggiungerlo all'elenco dei protocolli negoziati.

- Proprietà <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols%2A?displayProperty=nameWithType>

- Proprietà <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=nameWithType>

- [\<transport>](../configure-apps/file-schema/wcf/transport-of-nettcpbinding.md)Sezione della [\<netTcpBinding>](../configure-apps/file-schema/wcf/nettcpbinding.md) sezione

- [\<sslStreamSecurity>](../configure-apps/file-schema/wcf/sslstreamsecurity.md)Sezione della [\<customBinding>](../configure-apps/file-schema/wcf/custombinding.md) sezione

<a name="WPF462"></a>

### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)

In .NET Framework 4.6.2, Windows Presentation Foundation è stato ottimizzato nelle aree seguenti:

**Ordinamento dei gruppi**

Un'applicazione che usa un oggetto <xref:System.Windows.Data.CollectionView> per raggruppare i dati ora puoi dichiarare esplicitamente in che modo ordinare i gruppi. L'ordinamento esplicito risolve il problema dell'ordinamento non intuitivo che si verifica quando un'applicazione aggiunge o rimuove in modo dinamico i gruppi o quando modifica il valore delle proprietà dell'elemento interessate dal raggruppamento. Può anche migliorare le prestazioni del processo di creazione dei gruppi spostando i confronti delle proprietà di raggruppamento dall'ordinamento della raccolta completa all'ordinamento dei gruppi.

Per supportare l'ordinamento dei gruppi, le nuove proprietà <xref:System.ComponentModel.GroupDescription.SortDescriptions%2A?displayProperty=nameWithType> e <xref:System.ComponentModel.GroupDescription.CustomSort%2A?displayProperty=nameWithType> descrivono come ordinare la raccolta di gruppi generata dall'oggetto <xref:System.ComponentModel.GroupDescription>. Questo comportamento è analogo al modo in cui le proprietà <xref:System.Windows.Data.ListCollectionView> omonime descrivono come ordinare gli elementi di dati.

Due nuove proprietà statiche della classe <xref:System.Windows.Data.PropertyGroupDescription>, <xref:System.Windows.Data.PropertyGroupDescription.CompareNameAscending%2A> e <xref:System.Windows.Data.PropertyGroupDescription.CompareNameDescending%2A>, possono essere utilizzate per la maggior parte dei casi.

Ad esempio, il seguente XAML raggruppa i dati in base all'età, ordina i gruppi di età in ordine crescente e raggruppa gli elementi all'interno di ogni gruppo di età in base al cognome.

```xaml
<GroupDescriptions>
     <PropertyGroupDescription
         PropertyName="Age"
         CustomSort=
              "{x:Static PropertyGroupDescription.CompareNamesAscending}"/>
     </PropertyGroupDescription>
</GroupDescriptions>

<SortDescriptions>
     <SortDescription PropertyName="LastName"/>
</SortDescriptions>
```

**Supporto tastiera touch**

Il supporto per la tastiera touch consente di rilevare lo stato attivo nelle applicazioni WPF richiamando e rimuovendo automaticamente la tastiera touch in Windows 10 quando l'input tocco viene ricevuto da un controllo che può assumere input testuale.

Nelle versioni precedenti di .NET Framework, le applicazioni WPF non possono optare per il rilevamento dello stato attivo senza disabilitare il supporto per i movimenti di penna/tocco WPF. Di conseguenza, le applicazioni WPF devono scegliere tra il supporto completo WPF per il tocco e la promozione del mouse di Windows.

**DPI per monitor**

Per supportare la recente proliferazione di ambienti ad alta risoluzione e risoluzione ibrida per le applicazioni WPF, WPF in .NET Framework 4.6.2 abilita la sensibilità ai valori DPI del monitor. Per altre informazioni su come abilitare l'app WPF per la sensibilità ai valori DPI del monitor, vedere gli [esempi e la guida per gli sviluppatori](https://github.com/Microsoft/WPF-Samples/tree/master/PerMonitorDPI) su GitHub.

Nelle versioni precedenti di .NET Framework, le applicazioni WPF sono compatibili con i valori DPI del sistema. In altre parole, l'interfaccia utente dell'applicazione viene adeguata in modo appropriato dal sistema operativo, in base alla risoluzione del monitor in cui viene eseguito il rendering dell'applicazione.

Per le app in esecuzione nel .NET Framework 4.6.2, è possibile disabilitare le modifiche dei valori DPI per monitor nelle app WPF aggiungendo un'istruzione di configurazione alla [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) sezione del file di configurazione dell'applicazione, come indicato di seguito:

```xml
<runtime>
   <AppContextSwitchOverrides value="Switch.System.Windows.DoNotScaleForDpiChanges=false"/>
</runtime>
```

<a name="WF462"></a>

### <a name="windows-workflow-foundation-wf"></a>Windows Workflow Foundation (WF)

In .NET Framework 4.6.2, Windows Workflow Foundation è stato ottimizzato nell'area seguente:

**Supporto per le espressioni C# e IntelliSense nella finestra di progettazione WF riallocata**

A partire da .NET Framework 4,5, WF supporta le espressioni C# sia nella finestra di progettazione di Visual Studio che nei flussi di lavoro di codice. Il Progettazione flussi di lavoro riallocato è una funzionalità chiave di WF che consente al Progettazione flussi di lavoro di trovarsi in un'applicazione all'esterno di Visual Studio (ad esempio, in WPF).  Windows Workflow Foundation offre la possibilità di supportare le espressioni C# e IntelliSense nella Progettazione flussi di lavoro riallocata. Per altre informazioni, vedere il [blog di Windows Workflow Foundation](https://docs.microsoft.com/archive/blogs/workflowteam/building-c-expressions-support-and-intellisense-in-the-rehosted-workflow-designer).

`Availability of IntelliSense when a customer rebuilds a workflow project from Visual Studio`Nelle versioni del .NET Framework precedenti a 4.6.2, la funzionalità IntelliSense di progettazione WF viene interruppe quando un cliente ricompila un progetto di flusso di lavoro da Visual Studio. Anche se la compilazione del progetto ha esito positivo, i tipi di flusso di lavoro non vengono trovati nell'utilità di progettazione e vengono visualizzati alcuni avvisi di IntelliSense per i tipi di flusso di lavoro mancanti nella finestra **Elenco errori**. .NET Framework 4.6.2 risolve questo problema e rende disponibile IntelliSense.

**Le applicazioni flusso di lavoro versione 1 con tracciabilità del flusso di lavoro vengono ora eseguite in modalità FIPS**

I computer con modalità di compatibilità FIPS abilitata ora sono in grado di eseguire correttamente un'applicazione di flusso di lavoro tipo versione 1 con tracciabilità del flusso di lavoro attivata. Per abilitare questo scenario, è necessario apportare le modifiche seguenti al file di configurazione dell'applicazione:

```xml
<add key="microsoft:WorkflowRuntime:FIPSRequired" value="true" />
```

Se questo scenario non è abilitato, eseguire l'applicazione continua a generare un'eccezione con il messaggio "Questa implementazione non fa parte degli algoritmi crittografici convalidati per Windows Platform FIPS".

**Miglioramenti apportati ai flussi di lavoro quando si usa l'aggiornamento dinamico con Progettazione flussi di lavoro di Visual Studio**

Progettazione flussi di lavoro, ActivityDesigner Diagramma di flusso e altre utilità di progettazione delle attività dei flussi di lavoro ora caricano e visualizzano correttamente i flussi di lavoro che sono stati salvati dopo la chiamata del metodo <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType>. Nelle versioni di .NET Framework precedenti a .NET Framework 4.6.2 il caricamento di un file XAML in Visual Studio per un flusso di lavoro salvato dopo la chiamata di <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType> può causare i problemi seguenti:

- Progettazione flussi di lavoro non è in grado di caricare correttamente il file XAML se <xref:System.Activities.Presentation.ViewState.ViewStateData.Id%2A?displayProperty=nameWithType> si trova alla fine della riga.

- ActivityDesigner Diagramma di flusso o altri ActivityDesigner del flusso di lavoro possono visualizzare tutti gli oggetti nei propri percorsi predefiniti anziché i valori della proprietà associata.

<a name="clickonce-1"></a>

### <a name="clickonce"></a>ClickOnce

ClickOnce è stato aggiornato per supportare TLS 1.1 e TLS 1.2 oltre al protocollo 1.0 che supporta già. ClickOnce rileva automaticamente il protocollo richiesto e non sono necessarie altre operazioni nell'applicazione ClickOnce per abilitare il supporto per TLS 1.1 e 1.2.

<a name="UWPConvert"></a>

### <a name="converting-windows-forms-and-wpf-apps-to--uwp-apps"></a>Conversione di Windows Form e applicazioni WPF in applicazioni UWP

Windows ora offre funzionalità che consentono di portare le applicazioni desktop Windows esistenti, incluse le applicazioni WPF e Windows Form, sulla piattaforma UWP (Universal Windows Platform). Questa tecnologia funge da ponte e consente di eseguire gradualmente la migrazione della codebase esistente a UWP, rendendo in tal modo l'applicazione disponibile in tutti i dispositivi Windows 10.

Le applicazioni desktop convertite ottengono un'identità di applicazione simile a quella delle applicazioni UWP e in questo modo le API UWP diventano accessibili per abilitare funzionalità come i riquadri animati e le notifiche. L'applicazione continua a comportarsi come in precedenza e viene eseguita come applicazione con attendibilità totale. Dopo avere convertito l'applicazione, è possibile aggiungere un processo contenitore di applicazioni al processo di attendibilità totale esistente per aggiungere un'interfaccia utente adattiva. Quando tutte le funzionalità vengono spostate nel processo contenitore di applicazioni, il processo di attendibilità totale può essere rimosso e la nuova applicazione UWP può essere resa disponibile per tutti i dispositivi Windows 10.

<a name="Debug462"></a>

### <a name="debugging-improvements"></a>Miglioramenti apportati al debug

L'*API di debug non gestito* è stata ottimizzata in .NET Framework 4.6.2 per l'esecuzione di un'ulteriore analisi quando viene generata un'eccezione <xref:System.NullReferenceException>, in modo che sia possibile determinare quale variabile in una singola riga di codice sorgente è `null`.   A supporto di questo scenario, le API seguenti sono state aggiunte all'API di debug non gestito.

- Interfacce [ICorDebugCode4](../unmanaged-api/debugging/icordebugcode4-interface.md), [ICorDebugVariableHome](../unmanaged-api/debugging/icordebugvariablehome-interface.md) e [ICorDebugVariableHomeEnum](../unmanaged-api/debugging/icordebugvariablehomeenum-interface.md), che espongono le posizioni native delle variabili gestite. Questo consente ai debugger di effettuare alcune analisi del flusso di codice quando si verifica un <xref:System.NullReferenceException> e di lavorare con le versioni precedenti per determinare la variabile gestita che corrisponde alla posizione nativa che era `null`.

- Il metodo [ICorDebugType2::GetTypeID](../unmanaged-api/debugging/icordebugtype2-gettypeid-method.md) fornisce un mapping per ICorDebugType a [COR_TYPEID](../unmanaged-api/debugging/cor-typeid-structure.md), che permette al debugger di ottenere un oggetto [COR_TYPEID](../unmanaged-api/debugging/cor-typeid-structure.md) senza un'istanza di ICorDebugType. È quindi possibile usare le API esistenti in [COR_TYPEID](../unmanaged-api/debugging/cor-typeid-structure.md) per determinare il layout di classe del tipo.

<a name="v461"></a>

## <a name="whats-new-in-net-framework-461"></a>Novità di .NET Framework 4.6.1

.NET Framework 4.6.1 include nuove funzionalità nelle aree seguenti:

- [Crittografia](#Crypto)

- [ADO.NET](#ADO.NET461)

- [Windows Presentation Foundation (WPF)](#WPF461)

- [Windows Workflow Foundation](#WWF461)

- [Profilatura](#Profile461)

- [NGen](#NGEN461)

Per altre informazioni su .NET Framework 4.6.1, vedere gli argomenti seguenti:

- [Elenco delle modifiche di .NET Framework 4.6.1](https://github.com/Microsoft/dotnet/blob/master/releases/net461/dotnet461-changes.md)

- [Compatibilità delle applicazioni nella versione 4.6.1](../migration-guide/application-compatibility.md)

- [Differenza tra API di .NET Framework](https://github.com/Microsoft/dotnet/blob/master/releases/net461/dotnet461-api-changes.md) (su GitHub)

<a name="Crypto"></a>

### <a name="cryptography-support-for-x509-certificates-containing-ecdsa"></a>Crittografia: supporto di certificati X509 contenenti ECDSA

In .NET Framework 4.6 è stato aggiunto il supporto RSACng per i certificati X509. .NET Framework 4.6.1 aggiunge il supporto di certificati X509 con ECDSA (Elliptic Curve Digital Signature Algorithm).

Offrendo prestazioni migliori e trattandosi di un algoritmo di crittografia più sicuro rispetto a RSA, ECDSA rappresenta un'ottima scelta per ambienti in cui la scalabilità e le prestazioni TLS (Transport Layer Security) sono fattori importanti. L'implementazione di .NET Framework esegue il wrapping delle chiamate nelle funzionalità di Windows esistenti.

L'esempio di codice seguente illustra quanto sia semplice generare una firma per un flusso di byte usando il nuovo supporto dei certificati X509 ECDSA incluso in .NET Framework 4.6.1.

[!code-csharp[whatsnew.461.crypto#1](~/samples/snippets/csharp/VS_Snippets_CLR/whatsnew.461.crypto/cs/Code46.cs#1)]
[!code-vb[whatsnew.461.crypto#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.461.crypto/vb/Code461.vb#1)]

Emerge una netta differenza rispetto al codice necessario per generare una firma in .NET Framework 4.6.

[!code-csharp[whatsnew.461.crypto#2](~/samples/snippets/csharp/VS_Snippets_CLR/whatsnew.461.crypto/cs/Code46.cs#2)]
[!code-vb[whatsnew.461.crypto#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.461.crypto/vb/Code46.vb#2)]

<a name="ADO.NET461"></a>

### <a name="adonet"></a>ADO.NET

In ADO.NET è stato aggiunto quanto segue:

**Supporto di Crittografia sempre attiva per le chiavi hardware protette**

ADO.NET ora supporta l'archiviazione nativa delle chiavi master di colonna con Crittografia sempre attiva nei moduli di protezione hardware. Grazie a questo supporto, i clienti possono usare le chiavi asimmetriche archiviate nei moduli di protezione hardware senza dover scrivere provider dell'archivio chiavi master di colonna personalizzati e senza doverli registrare nelle applicazioni.

I clienti devono installare il provider CSP fornito dal fornitore dei moduli di protezione hardware o i provider dell'archivio chiavi CNG nei server applicazioni o nei computer client per accedere ai dati con Crittografia sempre attiva protetti con le chiavi master di colonna archiviate in un modulo di protezione hardware.

**Miglioramento <xref:System.Data.SqlClient.SqlConnectionStringBuilder.MultiSubnetFailover%2A> del comportamento di connessione per AlwaysOn**

SqlClient ora offre automaticamente connessioni più veloci a un gruppo di disponibilità AlwaysOn. Rileva in modo trasparente se l'applicazione si connette a un gruppo di disponibilità AlwaysOn su una subnet diversa e individua rapidamente il server attivo corrente e gli fornisce una connessione. Prima di questa versione, un'applicazione doveva impostare la stringa di connessione in modo da includere `"MultisubnetFailover=true"` per indicare che era connessa a un gruppo di disponibilità AlwaysOn. Senza impostare la parola chiave di connessione su `true`, potrebbe verificarsi un timeout durante la connessione di un'applicazione a un gruppo di disponibilità AlwaysOn. In questa versione *non* è più necessario che un'applicazione imposti <xref:System.Data.SqlClient.SqlConnectionStringBuilder.MultiSubnetFailover%2A> su `true`. Per altre informazioni sul supporto SqlClient per gruppi di disponibilità Always On, vedere [Supporto SqlClient per disponibilità elevata, ripristino di emergenza](../data/adonet/sql/sqlclient-support-for-high-availability-disaster-recovery.md).

<a name="WPF461"></a>

### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)

Windows Presentation Foundation include molti miglioramenti e cambiamenti.

**Miglioramento delle prestazioni**

Il ritardo di attivazione degli eventi tocco è stato risolto in .NET Framework 4.6.1. Inoltre, l'inserimento di un controllo <xref:System.Windows.Controls.RichTextBox> non blocca più il thread di rendering durante l'input veloce.

**Miglioramenti di controllo ortografico**

Il controllo ortografico in WPF è stato aggiornato in Windows 8.1 e versioni successive per sfruttare il supporto di altre lingue per il controllo ortografico offerto dal sistema operativo.  La funzionalità non è stata modificata nelle versioni di Windows precedenti a Windows 8.1.

Come nelle versioni precedenti di .NET Framework, la lingua per un controllo <xref:System.Windows.Controls.TextBox> o un blocco <xref:System.Windows.Controls.RichTextBox> viene rilevata cercando le informazioni nell'ordine seguente:

- `xml:lang`, se presente.

- Lingua di input corrente.

- Impostazioni cultura del thread corrente.

Per ulteriori informazioni sul supporto delle lingue in WPF, vedere il [post di Blog WPF sulle funzionalità di .NET Framework 4.6.1](https://devblogs.microsoft.com/wpf/wpf-in-net-4-6-1/).

**Supporto aggiuntivo per i dizionari personalizzati per utente**

In .NET Framework 4.6.1, WPF riconosce i dizionari personalizzati che sono registrati a livello globale. Questa funzionalità si aggiunge alla possibilità di registrarli a livello di controllo.

Nelle versioni precedenti di WPF, i dizionari personalizzati non riconoscono le parole escluse e gli elenchi di correzione automatica. Sono supportati in Windows 8.1 e Windows 10 mediante l'uso di file che possono essere inseriti nella directory `%AppData%\Microsoft\Spelling\<language tag>`.  A questi file si applicano le regole seguenti:

- I file devono avere estensione dic (per le parole aggiunte), exc (per le parole escluse) o acl (per la correzione automatica).

- I file devono essere in testo normale UTF-16 LE che inizia con l'indicatore dell'ordine dei byte (BOM, Byte Order Mark).

- Ogni riga deve essere costituita da una parola, negli elenchi di parole aggiunte ed escluse, o da una coppia della correzione automatica con le parole separate da una barra verticale ("&#124;"), nell'elenco di parole della correzione automatica.

- Questi file sono considerati di sola lettura e non vengono modificati dal sistema.

> [!NOTE]
> Questi nuovi formati di file non sono supportati direttamente dalle API di controllo ortografico WPF e i dizionari personalizzati forniti a WPF nelle applicazioni devono continuare a usare i file con estensione lex.

**Esempi**

Sono disponibili numerosi esempi di WPF nel repository GitHub [Microsoft/WPF-Samples](https://github.com/Microsoft/WPF-Samples). Per aiutare Microsoft a migliorare gli esempi, inviare una richiesta di pull o segnalare un [problema di GitHub](https://github.com/Microsoft/WPF-Samples/issues).

**Estensioni DirectX**

WPF include un [pacchetto NuGet](https://www.nuget.org/packages/Microsoft.Wpf.Interop.DirectX-x86/) che offre nuove implementazioni di <xref:System.Windows.Interop.D3DImage>, le quali semplificano l'interazione con il contenuto DX10 e Dx11. Il codice per questo pacchetto è stato reso open source ed è disponibile su [GitHub](https://github.com/Microsoft/WPFDXInterop).

<a name="WWF461"></a>

### <a name="windows-workflow-foundation-transactions"></a>Windows Workflow Foundation: Transazioni

Il metodo <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A?displayProperty=nameWithType> ora può usare un gestore di transazioni distribuite diverso da MSDTC per alzare di livello la transazione. A questo scopo, specificare un identificatore del promotore della transazione GUID nel nuovo overload <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%28System.Transactions.IPromotableSinglePhaseNotification%2CSystem.Guid%29?displayProperty=nameWithType>. Se l'operazione riesce, le funzionalità della transazione sono soggette a limitazioni. Quando viene integrato un promotore di transazione non MSDTC, i metodi seguenti generano un'eccezione <xref:System.Transactions.TransactionPromotionException> perché questi metodi richiedono l'innalzamento di livello a MSDTC:

- <xref:System.Transactions.Transaction.EnlistDurable%2A?displayProperty=nameWithType>

- <xref:System.Transactions.TransactionInterop.GetDtcTransaction%2A?displayProperty=nameWithType>

- <xref:System.Transactions.TransactionInterop.GetExportCookie%2A?displayProperty=nameWithType>

- <xref:System.Transactions.TransactionInterop.GetTransmitterPropagationToken%2A?displayProperty=nameWithType>

Quando viene integrato un promotore di transazione non MSDTC, occorre usarlo per le future integrazioni durevoli usando i protocolli che definisce. L'oggetto <xref:System.Guid> del promotore di transazione può essere ottenuto mediante la proprietà <xref:System.Transactions.Transaction.PromoterType%2A>. Quando la transazione viene alzata di livello, il promotore di transazione fornisce una matrice <xref:System.Byte> che rappresenta il token alzato di livello. Un'applicazione può ottenere il token alzato di livello per una transazione non MSDTC alzata di livello con il metodo <xref:System.Transactions.Transaction.GetPromotedToken%2A>.

Gli utenti del nuovo overload <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%28System.Transactions.IPromotableSinglePhaseNotification%2CSystem.Guid%29?displayProperty=nameWithType> devono seguire una specifica sequenza di chiamate affinché l'operazione di promozione venga completata correttamente. Queste regole sono descritte nella documentazione relativa al metodo.

<a name="Profile461"></a>

### <a name="profiling"></a>Profilatura

L'API di profilatura non gestita è stata migliorata nel modo seguente:

- Supporto migliorato per l'accesso ai PDB nell'interfaccia [ICorProfilerInfo7](../unmanaged-api/profiling/icorprofilerinfo7-interface.md).

  In ASP.NET Core è sempre più comune che gli assembly vengano compilati in memoria mediante Roslyn. Per gli sviluppatori che creano strumenti di profilatura, ciò significa che i PDB che in passato erano serializzati sul disco potrebbero non essere più presenti. Gli strumenti profiler spesso usano PDB per rimappare il codice alle righe di origine per attività come il code coverage o l'analisi delle prestazioni riga per riga. L'interfaccia [ICorProfilerInfo7](../unmanaged-api/profiling/icorprofilerinfo7-interface.md) include ora due nuovi metodi, [ICorProfilerInfo7::GetInMemorySymbolsLength](../unmanaged-api/profiling/icorprofilerinfo7-getinmemorysymbolslength-method.md) e [ICorProfilerInfo7::ReadInMemorySymbols](../unmanaged-api/profiling/icorprofilerinfo7-readinmemorysymbols.md), per fornire a questi strumenti profiler l'accesso ai dati dei PDB in memoria. Usando le nuove API, un profiler può ottenere il contenuto di un PDB in memoria come matrice di byte e quindi elaborarlo o serializzarlo su disco.

- Strumentazione migliore con l'interfaccia ICorProfiler.

  I profiler che usano la funzionalità ReJit dell'API `ICorProfiler` per la strumentazione dinamica ora possono modificare alcuni metadati. In precedenza quegli strumenti potevano instrumentare IL in qualsiasi momento, ma i metadati potevano essere modificati solo in fase di caricamento del modulo. Poiché IL fa riferimento ai metadati, questo limitava i tipi di strumentazione possibile. Alcuni di questi limiti sono stati rimossi aggiungendo il metodo [ICorProfilerInfo7:: ApplyMetaData](../unmanaged-api/profiling/icorprofilerinfo7-applymetadata-method.md) per supportare un subset di modifiche dei metadati dopo il caricamento del modulo, in particolare aggiungendo nuovi record,,,, `AssemblyRef` `TypeRef` `TypeSpec` `MemberRef` `MemberSpec` e `UserString` . Questa modifica rende possibile una gamma più ampia di strumentazioni immediate.

<a name="NGEN461"></a>

### <a name="native-image-generator-ngen-pdbs"></a>PDB del generatore di immagini native (NGEN)

La traccia eventi tra computer consente ai clienti di profilare un programma sul Computer A e osservare i dati di profilatura con mapping della riga di origine sul Computer B. Nelle versioni precedenti di .NET Framework, l'utente copiava tutti i moduli e le immagini native dalla macchina profilata alla macchina di analisi contenente il PDB IL per creare il mapping sorgente-nativo. Anche se questo processo può funzionare bene quando i file sono relativamente piccoli, ad esempio per le applicazioni telefoniche, i file possono avere dimensioni molto grandi sui sistemi desktop e la copia può richiedere molto tempo.

Con i PDB Ngen, NGen può creare un PDB che contiene il mapping da IL a nativo senza una dipendenza dal PDB IL. In questo scenario di traccia eventi in più computer, è sufficiente copiare il PDB di immagine nativa generato dal Computer A nel Computer B e usare le [API di accesso all'interfaccia di debug](/visualstudio/debugger/debug-interface-access/debug-interface-access-sdk-reference) per leggere il mapping da codice sorgente a codice IL del PDB IL e il mapping da codice IL a codice nativo del PDB di immagine nativa. La combinazione di entrambi i mapping fornisce un mapping da codice sorgente a codice nativo. Poiché il PDB di immagine nativa è molto più piccolo rispetto a tutti i moduli e alle immagini native, il processo di copia dal Computer A al Computer B è molto più veloce.

<a name="v46"></a>

## <a name="whats-new-in-net-2015"></a>Novità di .NET 2015

.NET 2015 introduce .NET Framework 4.6 e .NET Core. Alcune nuove funzionalità sono valide per entrambi, mentre altre sono specifiche di .NET Framework 4.6 o .NET Core.

- **ASP.NET Core**

  .NET 2015 include ASP.NET Core, un'implementazione di .NET snella per lo sviluppo di app moderne basate su cloud. ASP.NET Core è modulare e consente quindi di includere solo le funzionalità necessarie nell'applicazione. Può essere ospitata su IIS o in modo indipendente in un processo personalizzato ed è possibile eseguire app con diverse versioni di .NET Framework nello stesso server. Include un nuovo sistema di configurazione dell'ambiente progettato per la distribuzione cloud.

  MVC, API Web e pagine Web sono riunite in un unico framework denominato MVC 6. Le app ASP.NET Core vengono compilate mediante gli strumenti in Visual Studio 2015 o versione successiva. Le applicazioni esistenti funzioneranno nel nuovo .NET Framework ma per compilare un'app che usa MVC 6 o SignalR 3 è necessario usare il sistema di progetto in Visual Studio 2015 o versione successiva.

  Per informazioni, vedere [ASP.NET Core](/aspnet/core/).

- **Aggiornamenti di ASP.NET**

  - **API basata su attività per lo scaricamento asincrono delle risposte**

    ASP.NET ora fornisce <xref:System.Web.HttpResponse.FlushAsync%2A?displayProperty=nameWithType>, una semplice API basata sulle attività che consente di scaricare le risposte asincrone con il supporto `async/await` del linguaggio usato.

  - **L'associazione di modelli supporta i metodi che restituiscono attività**

    In .NET Framework 4.5, ASP.NET ha aggiunto la funzionalità di associazione di modelli che ha reso possibile un approccio estendibile, focalizzato sul codice, per le operazioni di dati basate su CRUD nelle pagine Web Form e nei controlli utente. Il sistema di associazione di modelli ora supporta metodi di associazione di modelli con restituzione di <xref:System.Threading.Tasks.Task>. Questa funzionalità consente agli sviluppatori di Web Form di ottenere i vantaggi di scalabilità di async con la facilità del sistema di associazione dati quando usano versioni più recenti di ORM, tra cui Entity Framework.

    L'associazione di modelli async è controllata dall'impostazione di configurazione `aspnet:EnableAsyncModelBinding`.

    ```xml
    <appSettings>
        <add key=" aspnet:EnableAsyncModelBinding" value="true|false" />
    </appSettings>
    ```

    Per le app destinate a .NET Framework 4.6, l'impostazione predefinita è `true`. Per le app in esecuzione su .NET Framework 4.6 e che sono destinate a una versione precedente di .NET Framework, è `false` per impostazione predefinita. Può essere abilitata impostando l'impostazione di configurazione su `true`.

  - **Supporto HTTP/2 (Windows 10)**

    [HTTP/2](https://www.wikipedia.org/wiki/HTTP/2) è una nuova versione del protocollo HTTP che permette un utilizzo molto migliore della connessione, con meno round trip tra client e server, offrendo una latenza minore per il caricamento delle pagine Web per gli utenti.  Le pagine Web (a differenza dei servizi) traggono maggiori vantaggi dal protocollo HTTP/2, poiché ottimizza più elementi richiesti come parte di un'esperienza unica. Il supporto HTTP/2 è stato aggiunto ad ASP.NET in .NET Framework 4.6. Poiché la funzionalità di rete esiste a più livelli, si sono rese necessarie nuove funzionalità in Windows, IIS e ASP.NET per abilitare HTTP/2. È necessario eseguire Windows 10 per usare HTTP/2 con ASP.NET.

    HTTP/2 è anche supportato e attivato per impostazione predefinita per le app di Windows 10 Universal Windows Platform (UWP) che usano l'API <xref:System.Net.Http.HttpClient?displayProperty=nameWithType>.

    Per consentire l'uso della funzionalità [PUSH_PROMISE](https://http2.github.io/http2-spec/#PUSH_PROMISE) nelle applicazioni ASP.NET, è stato aggiunto un nuovo metodo con due overload, <xref:System.Web.HttpResponse.PushPromise%28System.String%29> e <xref:System.Web.HttpResponse.PushPromise%28System.String%2CSystem.String%2CSystem.Collections.Specialized.NameValueCollection%29>, alla classe <xref:System.Web.HttpResponse>.

    > [!NOTE]
    > Mentre ASP.NET Core supporta HTTP/2, il supporto della funzionalità PUSH PROMISE non è ancora stato aggiunto.

    Il browser e il server Web (IIS su Windows) eseguono tutte le operazioni. Gli utenti non dovranno eseguire alcuna operazione impegnativa.

    Poiché la maggior parte dei [principali browser supporta HTTP/2](https://www.wikipedia.org/wiki/HTTP/2), è probabile che gli utenti trarranno vantaggio dal supporto HTTP/2, se supportato dal server in uso.

  - **Supporto per Token Binding Protocol**

    Microsoft e Google stanno collaborando a un nuovo approccio all'autenticazione, chiamato [Token Binding Protocol](https://github.com/TokenBinding/Internet-Drafts). Il presupposto è che i token di autenticazione (nella cache del browser) possono essere rubati e usati dai criminali per accedere a risorse altrimenti sicure (ad esempio, il conto bancario) senza richiedere la password o altre informazioni riservate. L'obiettivo del nuovo protocollo è attenuare questo problema.

    Il Token Binding Protocol verrà implementato in Windows 10 come funzionalità del browser. Le app ASP.NET parteciperanno al protocollo, in modo che sia convalidata la legittimità dei token di autenticazione. Le implementazioni di client e server stabiliscono la protezione end-to-end specificata dal protocollo.

  - **Algoritmi hash casuali per le stringhe**

    In .NET Framework 4.5 è stato introdotto un [algoritmo hash casuale per le stringhe](../configure-apps/file-schema/runtime/userandomizedstringhashalgorithm-element.md). Tuttavia, non era supportato da ASP.NET perché alcune funzionalità ASP.NET dipendevano da un codice hash stabile. In .NET Framework 4.6 gli algoritmi di hash della stringa casuale sono ora supportati. Per abilitare questa funzionalità, usare l'impostazione di configurazione `aspnet:UseRandomizedStringHashAlgorithm`.

    ```xml
    <appSettings>
        <add key="aspnet:UseRandomizedStringHashAlgorithm" value="true|false" />
    </appSettings>
    ```

- **ADO.NET**

  ADO .NET supporta ora la funzionalità Crittografia sempre attiva disponibile in SQL Server 2016 Community Technology Preview 2 (CTP2). Con Always Encrypted, SQL Server possibile eseguire operazioni sui dati crittografati e la chiave di crittografia risiede con l'applicazione all'interno dell'ambiente attendibile del cliente e non nel server. La funzionalità Crittografia sempre attiva protegge i dati dei clienti, in modo che gli amministratori del database non abbiano accesso ai dati di testo normale. La crittografia e la decrittografia dei dati avvengono in modo trasparente a livello di driver, riducendo al minimo le modifiche che è necessario apportare alle applicazioni esistenti. Per informazioni dettagliate, vedere [Crittografia sempre attiva (motore di database)](/sql/relational-databases/security/encryption/always-encrypted-database-engine) e [Crittografia sempre attiva (sviluppo client)](/sql/relational-databases/security/encryption/always-encrypted-client-development).

- **Compilatore JIT a 64 bit per il codice gestito**

  .NET Framework 4.6 presenta una nuova versione del compilatore JIT a 64 bit (il cui nome in codice iniziale è RyuJIT). Il nuovo compilatore a 64 bit offre miglioramenti significativi delle prestazioni rispetto al compilatore JIT a 64 bit esistente. Il nuovo compilatore a 64 bit è abilitato per i processi a 64 bit in esecuzione su NET Framework 4.6. L'app verrà eseguita in un processo a 64 bit se è compilata come 64 bit o AnyCPU e se viene eseguita su un sistema operativo a 64 bit. Nonostante si sia cercato di rendere il più possibile trasparente la transizione al nuovo compilatore, potrebbero verificarsi cambiamenti del comportamento.

  Il nuovo compilatore JIT a 64 bit include anche funzionalità di accelerazione SIMD hardware quando è associato a tipi abilitati per SIMD nello spazio dei nomi <xref:System.Numerics>, con conseguente ottimizzazione delle prestazioni.

- **Miglioramenti apportati al caricatore di assembly**

  Il caricatore di assembly usa la memoria in modo più efficiente scaricando gli assembly IL dopo il caricamento di un'immagine NGEN corrispondente. Questa modifica riduce la memoria virtuale, aspetto particolarmente utile per app a 32 bit di grandi dimensioni (ad esempio Visual Studio) e consente anche di risparmiare memoria fisica.

- **Modifiche apportate alla libreria di classi base**

  Sono state aggiunte molte nuove API a .NET Framework 4.6 per abilitare gli scenari principali. Sono incluse le modifiche e le aggiunte seguenti:

  - **\<T>Implementazioni IReadOnlyCollection**

    Altre raccolte implementano <xref:System.Collections.Generic.IReadOnlyCollection%601>, ad esempio <xref:System.Collections.Generic.Queue%601> e <xref:System.Collections.Generic.Stack%601>.

  - **CultureInfo.CurrentCulture e CultureInfo.CurrentUICulture**

    Le proprietà <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> e <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType> ora sono di lettura/scrittura anziché di sola lettura. Se si assegna un nuovo oggetto <xref:System.Globalization.CultureInfo> a queste proprietà, cambiano anche le impostazioni cultura del thread corrente definite dalla proprietà `Thread.CurrentThread.CurrentCulture` e le impostazioni cultura del thread UI corrente definite dalle proprietà `Thread.CurrentThread.CurrentUICulture`.

  - **Miglioramenti a Garbage Collection (GC)**

    La classe <xref:System.GC> ora include i metodi <xref:System.GC.TryStartNoGCRegion%2A> e <xref:System.GC.EndNoGCRegion%2A> che consentono di disabilitare le operazioni di Garbage Collection durante l'esecuzione di un percorso critico.

    Un nuovo overload del metodo <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%2CSystem.Boolean%2CSystem.Boolean%29?displayProperty=nameWithType> consente di controllare se l'heap oggetti piccoli e l'heap oggetti grandi vengono entrambi sottoposti a sweep e compattati o solo sottoposti a sweep.

  - **Tipi abilitati per SIMD**

    Lo spazio dei nomi <xref:System.Numerics> ora include numerosi tipi abilitati per SIMD, ad esempio <xref:System.Numerics.Matrix3x2>, <xref:System.Numerics.Matrix4x4>, <xref:System.Numerics.Plane>, <xref:System.Numerics.Quaternion>, <xref:System.Numerics.Vector2>, <xref:System.Numerics.Vector3> e <xref:System.Numerics.Vector4>.

    Il nuovo compilatore JIT a 64 bit include anche funzionalità di accelerazione SIMD hardware, quindi le prestazioni migliorano notevolmente quando si usano i tipi abilitati per SIMD con il nuovo compilatore JIT a 64 bit.

  - **Aggiornamenti della crittografia**

    L'API <xref:System.Security.Cryptography?displayProperty=nameWithType> è in fase di aggiornamento per supportare le [API di crittografia CNG di Windows](/windows/desktop/SecCNG/cng-reference). Le versioni precedenti di .NET Framework si basavano interamente su una [versione precedente delle API di crittografia Windows](/windows/desktop/SecCrypto/cryptography-portal) per l'implementazione di <xref:System.Security.Cryptography?displayProperty=nameWithType>. Microsoft ha ricevuto alcune richieste relative all'aggiunta del supporto per l'API CNG, perché questa supporta [algoritmi di crittografia moderni](/windows/desktop/SecCNG/cng-features#suite-b-support), che sono importanti per determinate categorie di app.

    .NET Framework 4.6 include i nuovi miglioramenti seguenti per supportare le API di crittografia di CNG di Windows:

    - Un set di metodi di estensione per certificati X509, `System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)` e `System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)`, che restituiscono, quando possibile, un'implementazione basata su CNG invece di un'implementazione basata su CAPI. Ad esempio, alcune smart card richiedono comunque CAPI e le API gestiscono il fallback.

    - La classe <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType>, che fornisce un'implementazione CNG dell'algoritmo RSA.

    - Miglioramenti all'API RSA in modo che le azioni comuni non richiedano più il cast. Ad esempio, la crittografia dei dati eseguita con un oggetto <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> richiede codice simile al seguente nelle versioni precedenti di .NET Framework.

      [!code-csharp[WhatsNew.Casting#1](~/samples/snippets/csharp/VS_Snippets_CLR/whatsnew.casting/cs/program.cs#1)]
      [!code-vb[WhatsNew.Casting#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.casting/vb/module1.vb#1)]

      Il codice che usa le nuove API di crittografia in Framework .NET 4.6 può essere riscritto nel modo seguente per evitare il cast.

      [!code-csharp[WhatsNew.Casting#2](~/samples/snippets/csharp/VS_Snippets_CLR/whatsnew.casting/cs/program.cs#2)]
      [!code-vb[WhatsNew.Casting#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.casting/vb/module1.vb#2)]

  - **Supporto per la conversione di date e ore verso o dall'ora di Unix**

    Sono stati aggiunti i nuovi metodi seguenti alla struttura <xref:System.DateTimeOffset> per supportare la conversione di valori di data e ora da o verso l'ora di Unix:

    - <xref:System.DateTimeOffset.FromUnixTimeSeconds%2A?displayProperty=nameWithType>

    - <xref:System.DateTimeOffset.FromUnixTimeMilliseconds%2A?displayProperty=nameWithType>

    - <xref:System.DateTimeOffset.ToUnixTimeSeconds%2A?displayProperty=nameWithType>

    - <xref:System.DateTimeOffset.ToUnixTimeMilliseconds%2A?displayProperty=nameWithType>

  - **Opzioni di compatibilità**

    La <xref:System.AppContext> classe aggiunge una nuova funzionalità di compatibilità che consente agli autori di librerie di fornire un meccanismo uniforme per il rifiuto esplicito per nuove funzionalità per gli utenti. Stabilisce un contratto a regime di controllo libero tra i componenti per comunicare una richiesta di rifiuto esplicito. Questa funzionalità è importante in genere quando viene apportata una modifica alle funzionalità esistenti. Al contrario, esiste già un consenso esplicito per la nuova funzionalità.

    Con <xref:System.AppContext>, le librerie definiscono ed espongono le opzioni di compatibilità, mentre il codice che dipende dalle librerie può impostare tali opzioni in modo da influire sul comportamento della libreria. Per impostazione predefinita, le librerie forniscono la nuova funzionalità e la modificano (cioè offrono la funzionalità precedente) solo se l'opzione è impostata.

    Un'applicazione (o una libreria) può dichiarare il valore di un'opzione (che è sempre un valore <xref:System.Boolean>) definito da una libreria dipendente. L'opzione è sempre implicitamente `false`. Impostare l'opzione su `true` la abilita. Impostare in modo esplicito l'opzione su `false` fornisce il nuovo comportamento.

    ```csharp
    AppContext.SetSwitch("Switch.AmazingLib.ThrowOnException", true);
    ```

    ```vb
    AppContext.SetSwitch("Switch.AmazingLib.ThrowOnException", True)
    ```

    La libreria deve controllare se un consumer è dichiarato il valore dell'opzione e si comporta in modo appropriato in base ad essa.

    ```csharp
    if (!AppContext.TryGetSwitch("Switch.AmazingLib.ThrowOnException", out shouldThrow))
    {
        // This is the case where the switch value was not set by the application.
        // The library can choose to get the value of shouldThrow by other means.
        // If no overrides nor default values are specified, the value should be 'false'.
        // A false value implies the latest behavior.
    }

    // The library can use the value of shouldThrow to throw exceptions or not.
    if (shouldThrow)
    {
        // old code
    }
    else
    {
        // new code
    }
    ```

    ```vb
    If Not AppContext.TryGetSwitch("Switch.AmazingLib.ThrowOnException", shouldThrow) Then
        ' This is the case where the switch value was not set by the application.
        ' The library can choose to get the value of shouldThrow by other means.
        ' If no overrides nor default values are specified, the value should be 'false'.
        ' A false value implies the latest behavior.
    End If

    ' The library can use the value of shouldThrow to throw exceptions or not.
    If shouldThrow Then
        ' old code
    Else
        ' new code
    End If
    ```

    È opportuno usare un formato coerente per le opzioni, poiché si tratta di un contratto formale esposto da una libreria. Di seguito sono riportati due formati ovvi.

    - *Opzione*.*spaziodeinomi*.*nomeopzione*

    - *Opzione*.*libreria*.*nomeopzione*

  - **Modifiche apportate al modello asincrono basato su attività**

    Per le app destinate a NET Framework 4.6, gli oggetti <xref:System.Threading.Tasks.Task> e <xref:System.Threading.Tasks.Task%601> ereditano le impostazioni cultura e le impostazioni cultura dell'interfaccia utente del thread chiamante. Questo non incide sul comportamento delle app per versioni precedenti di .NET Framework o non destinate a una versione specifica di .NET Framework. Per altre informazioni, vedere la sezione dedicata alle impostazioni cultura e alle operazioni asincrone basate su attività nell'argomento relativo alla classe <xref:System.Globalization.CultureInfo>.

    La classe <xref:System.Threading.AsyncLocal%601?displayProperty=nameWithType> consente di rappresentare i dati di ambiente locali rispetto a un flusso di controllo asincrono specificato, ad esempio un metodo `async`. Può essere usato per rendere persistenti i dati tra thread. È anche possibile definire un metodo di callback che riceve una notifica ogni volta che i dati di ambiente subiscono una modifica perché la proprietà <xref:System.Threading.AsyncLocal%601.Value%2A?displayProperty=nameWithType> è stata modificata in modo esplicito oppure perché il thread ha rilevato una transizione di contesto.

    Tre metodi pratici, <xref:System.Threading.Tasks.Task.CompletedTask%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Task.FromCanceled%2A?displayProperty=nameWithType> e <xref:System.Threading.Tasks.Task.FromException%2A?displayProperty=nameWithType>, sono stati aggiunti al modello asincrono basato su attività (TAP) per restituire le attività completate in un determinato stato.

    La classe <xref:System.IO.Pipes.NamedPipeClientStream> ora supporta la comunicazione asincrona con il nuovo <xref:System.IO.Pipes.NamedPipeClientStream.ConnectAsync%2A>. ProcessOnStatus.

  - **EventSource supporta ora la scrittura nel registro eventi**

    Ora è possibile usare la classe <xref:System.Diagnostics.Tracing.EventSource> per registrare messaggi amministrativi o operativi nel registro eventi, oltre a tutte le sessioni ETW create nel computer. In passato era necessario usare il pacchetto Microsoft.Diagnostics.Tracing.EventSource NuGet per questa funzionalità. Questa funzionalità è ora integrata in .NET Framework 4.6.

    Sia il pacchetto NuGet sia .NET Framework 4.6 sono stati aggiornati con le funzionalità seguenti:

    - **Eventi dinamici**

      Consente eventi definiti al momento senza creare metodi di eventi.

    - **Payload avanzati**

      Consente di passare classi e matrici attribuite in modo specifico nonché tipi primitivi come un payload

    - **Rilevamento attività**

      Comporta l'applicazione di tag di eventi tra gli eventi Start e Stop con un ID che rappresenta tutte le attività attualmente attive.

    Per supportare queste funzionalità, il metodo <xref:System.Diagnostics.Tracing.EventSource.Write%2A> di overload è stato aggiunto alla classe <xref:System.Diagnostics.Tracing.EventSource>.

- **Windows Presentation Foundation (WPF)**

  - **Miglioramenti di HDPI**

    Il supporto di HDPI in WPF è stato migliorato in .NET Framework 4.6. Sono state apportate modifiche all'arrotondamento del layout per ridurre le istanze di ritaglio nei controlli con bordi. Per impostazione predefinita, questa funzionalità è abilitata solo se <xref:System.Runtime.Versioning.TargetFrameworkAttribute> è impostato su .NET 4.6.  Le applicazioni destinate a versioni precedenti del Framework ma in esecuzione nel .NET Framework 4,6 possono acconsentire esplicitamente al nuovo comportamento aggiungendo la riga seguente alla [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) sezione del file di app.config:

    ```xml
    <AppContextSwitchOverrides
    value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false"
    />
    ```

    Le finestre WPF che si estendono su più monitor con impostazioni DPI diverse (configurazione di più DPI) sono ora visualizzate completamente senza aree nere. È possibile rifiutare esplicitamente questo comportamento disabilitandolo con l'aggiunta della riga seguente alla sezione `<appSettings>` del file di configurazione dell'app:

    ```xml
    <add key="EnableMultiMonitorDisplayClipping" value="true"/>
    ```

    Il supporto per il caricamento automatico del cursore appropriato in base all'impostazione DPI è stato aggiunto a <xref:System.Windows.Input.Cursor?displayProperty=nameWithType>.

  - **Miglioramento della funzionalità touch**

    I clienti hanno segnalato su [Connect](https://connect.microsoft.com/VisualStudio/feedback/details/903760/) che il comportamento imprevedibile della funzionalità touch è stato risolto in .NET Framework 4.6. La soglia relativa al doppio tocco per le app di Windows Store e le applicazioni WPF ora è lo stesso in Windows 8.1 e versioni successive.

  - **Supporto per finestre figlio trasparenti**

    WPF in .NET Framework 4.6 supporta le finestre figlio trasparenti in Windows 8.1 e versioni successive. Ciò consente di creare finestre figlio non rettangolari e trasparenti nelle finestre di primo livello. È possibile abilitare questa funzionalità impostando la proprietà <xref:System.Windows.Interop.HwndSourceParameters.UsesPerPixelTransparency%2A?displayProperty=nameWithType> su `true`.

- **Windows Communication Foundation (WCF)**

  - **Supporto di SSL**

    WCF ora supporta la versione SSL TLS 1.1 e TLS 1.2, oltre a SSL 3.0 e TLS 1.0, quando si usa NetTcp con la sicurezza del trasporto e l'autenticazione client. Ora è possibile selezionare il protocollo da usare o disabilitare i protocolli precedenti, che sono meno sicuri. A tale scopo, è possibile impostare la proprietà <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A> o aggiungere il codice seguente a un file di configurazione.

    ```xml
    <netTcpBinding>
        <binding>
          <security mode= "None|Transport|Message|TransportWithMessageCredential" >
              <transport clientCredentialType="None|Windows|Certificate"
                        protectionLevel="None|Sign|EncryptAndSign"
                        sslProtocols="Ssl3|Tls1|Tls11|Tls12">
                </transport>
          </security>
        </binding>
    </netTcpBinding>
    ```

  - **Invio di messaggi tramite connessioni HTTP diverse**

    WCF ora consente agli utenti di garantire l'invio di determinati messaggi usando diverse connessioni HTTP sottostanti. A questo scopo è possibile procedere in due modi:

    - **Uso di un prefisso del nome del gruppo di connessione**

      Gli utenti possono specificare una stringa che WCF userà come prefisso per il nome del gruppo di connessione. Due messaggi con prefissi diversi vengono inviati usando diverse connessioni HTTP sottostanti. Per impostare il prefisso, aggiungere una coppia chiave/valore alla proprietà <xref:System.ServiceModel.Channels.Message.Properties%2A?displayProperty=nameWithType> del messaggio. La chiave è "HttpTransportConnectionGroupNamePrefix", mentre il valore è il prefisso desiderato.

    - **Uso di channel factory diverse**

      Gli utenti possono anche attivare una funzionalità che assicura che i messaggi inviati con i canali creati da channel factory diverse useranno connessioni HTTP sottostanti diverse. Per abilitare questa funzionalità, gli utenti devono impostare `appSetting` su `true`:

      ```xml
      <appSettings>
          <add key="wcf:httpTransportBinding:useUniqueConnectionPoolPerFactory" value="true" />
      </appSettings>
      ```

- **Windows Workflow Foundation (WWF)**

  Ora è possibile specificare il numero di secondi che un servizio di flusso di lavoro attenderà per una richiesta di operazione non ordinata quando esiste un segnalibro "non protocollo" in attesa prima del timeout della richiesta. Un segnalibro "non protocollo" è un segnalibro che non è correlato alle attività di ricezione in attesa. Alcune attività creano segnalibri non protocollo all'interno della propria implementazione, quindi potrebbe non essere evidente che un segnalibro non protocollo esista. Sono incluse le attività relative allo stato e alla selezione. Pertanto, se si ha un servizio del flusso di lavoro implementato con una macchina a stati o contenente un'attività di selezione, probabilmente si avranno segnalibri non protocollo. Specificare l'intervallo aggiungendo una riga simile alla seguente alla sezione `appSettings` del file di configurazione dell'app:

  ```xml
  <add key="microsoft:WorkflowServices:FilterResumeTimeoutInSeconds" value="60"/>
  ```

  Il valore predefinito è 60 secondi. Se `value` è impostato su 0, le richieste non ordinate vengono immediatamente rifiutate con un messaggio di errore simile al seguente:

  ```console
  Operation 'Request3|{http://tempuri.org/}IService' on service instance with identifier '2b0667b6-09c8-4093-9d02-f6c67d534292' cannot be performed at this time. Please ensure that the operations are performed in the correct order and that the binding in use provides ordered delivery guarantees.
  ```

  Si tratta dello stesso messaggio che viene visualizzato se si riceve un messaggio di operazione non ordinato e non sono presenti segnalibri non protocollo.

  Se il valore dell'elemento `FilterResumeTimeoutInSeconds` è diverso da zero, sono presenti segnalibri non protocollo, l'intervallo di timeout scade e l'operazione ha esito negativo con un messaggio di timeout.

- **Transazioni**

  Ora è possibile includere l'identificatore di transazione distribuita per la transazione che ha generato un'eccezione derivata da <xref:System.Transactions.TransactionException>. A questo scopo, aggiungere la chiave seguente alla sezione `appSettings` del file di configurazione dell'app:

  ```xml
  <add key="Transactions:IncludeDistributedTransactionIdInExceptionMessage" value="true"/>
  ```

  Il valore predefinito è `false`.

- **Rete**

  - **Riutilizzo di socket**

    Windows 10 include un nuovo algoritmo di rete ad alta scalabilità che consente di migliorare l'uso delle risorse del computer riutilizzando porte locali per le connessioni TCP in uscita. .NET Framework 4.6 supporta il nuovo algoritmo, consentendo alle app .NET di sfruttare il nuovo comportamento. Nelle versioni precedenti di Windows era presente un limite di connessioni simultanee artificiali (in genere 16.384, la dimensione predefinita dell'intervallo di porte dinamiche), che poteva limitare la scalabilità di un servizio causando l'esaurimento delle porte quando sono sotto carico.

    In .NET Framework 4,6 sono state aggiunte due API per abilitare il riutilizzo delle porte, che rimuove in modo efficace il limite di 64 KB per le connessioni simultanee:

    - Il valore di enumerazione <xref:System.Net.Sockets.SocketOptionName?displayProperty=nameWithType>.

    - La proprietà <xref:System.Net.ServicePointManager.ReusePort%2A?displayProperty=nameWithType>.

    Per impostazione predefinita, la proprietà <xref:System.Net.ServicePointManager.ReusePort%2A?displayProperty=nameWithType> è `false`, a meno che il valore `HWRPortReuseOnSocketBind` della chiave del registro di sistema `HKLM\SOFTWARE\Microsoft\.NETFramework\v4.0.30319` sia impostato su 0x1. Per abilitare il riutilizzo delle porte locali su connessioni HTTP, impostare la proprietà <xref:System.Net.ServicePointManager.ReusePort%2A?displayProperty=nameWithType> su `true`. In questo modo tutte le connessioni socket TCP in uscita da <xref:System.Net.Http.HttpClient> e <xref:System.Net.HttpWebRequest> usano la nuova opzione di socket di Windows 10, [SO_REUSE_UNICASTPORT](/windows/desktop/WinSock/sol-socket-socket-options), che consente il riutilizzo delle porte locali.

    Gli sviluppatori che scrivono un'applicazione solo socket possono specificare l'opzione <xref:System.Net.Sockets.SocketOptionName?displayProperty=nameWithType> quando si chiama un metodo come <xref:System.Net.Sockets.Socket.SetSocketOption%2A?displayProperty=nameWithType> in modo che i socket in uscita riutilizzino le porte locali durante l'associazione.

  - **Supporto dei nomi di dominio internazionali e di PunyCode**

    Una nuova proprietà, <xref:System.Uri.IdnHost%2A>, è stata aggiunta alla classe <xref:System.Uri> per migliorare il supporto dei nomi di dominio internazionali e di PunyCode.

- **Ridimensionamento nei controlli Windows Form**

  Questa funzionalità è stata estesa in .NET Framework 4.6 per includere i tipi <xref:System.Windows.Forms.DomainUpDown>, <xref:System.Windows.Forms.NumericUpDown>, <xref:System.Windows.Forms.DataGridViewComboBoxColumn>, <xref:System.Windows.Forms.DataGridViewColumn> e <xref:System.Windows.Forms.ToolStripSplitButton>, nonché il rettangolo specificato dalla proprietà <xref:System.Drawing.Design.PaintValueEventArgs.Bounds%2A> usato per disegnare un oggetto <xref:System.Drawing.Design.UITypeEditor>.

  È una funzionalità che prevede il consenso esplicito. Per attivarla, impostare l'elemento `EnableWindowsFormsHighDpiAutoResizing` su `true` nel file di configurazione dell'applicazione (app.config):

  ```xml
  <appSettings>
      <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />
  </appSettings>
  ```

- **Supporto delle codifiche della tabella codici**

  .NET Core supporta principalmente le codifiche Unicode e per impostazione predefinita offre un supporto limitato per le codifiche della tabella codici. È possibile aggiungere il supporto delle codifiche della tabella codici disponibili in .NET Framework, ma non supportate in .NET Core registrando le codifiche della tabella codici con il metodo <xref:System.Text.Encoding.RegisterProvider%2A?displayProperty=nameWithType>. Per altre informazioni, vedere <xref:System.Text.CodePagesEncodingProvider?displayProperty=nameWithType>.

- **.NET Native**

  Le app di Windows per Windows 10 destinate a .NET Core e scritte in C# o Visual Basic ora possono avvalersi di una nuova tecnologia che compila le app in codice nativo anziché IL. Producono app caratterizzate da maggiore rapidità di avvio ed esecuzione. Per altre informazioni, vedere [Compilazione di app con .NET Native](../net-native/index.md). Per una panoramica di .NET Native che esamina le differenze rispetto alla compilazione JIT e NGEN e descrive tutti i vantaggi per il codice, vedere [Compilazione e .NET Native](../net-native/net-native-and-compilation.md).

  Le app vengono compilate in codice nativo per impostazione predefinita quando si compilano con Visual Studio 2015 o versione successiva. Per altre informazioni, vedere [Introduzione a .NET Native](../net-native/getting-started-with-net-native.md).

  Per supportare il debug di app .NET Native, è stata aggiunta una serie di nuove interfacce ed enumerazioni all'API di debug non gestito. Per altre informazioni, vedere l'argomento [Debug (riferimenti alle API non gestite)](../unmanaged-api/debugging/index.md).

- **Pacchetti .NET Framework open source**

  I pacchetti .NET Core come le raccolte non modificabili, le [API SIMD](https://www.nuget.org/packages/Microsoft.Bcl.Simd)e le API di rete come quelle disponibili nello <xref:System.Net.Http> spazio dei nomi sono ora disponibili come pacchetti Open Source su [GitHub](https://github.com/). Per accedere al codice, vedere [.NET su GitHub](https://github.com/dotnet/runtime). Per altre informazioni e indicazioni su come contribuire a questi pacchetti, vedere [Componenti di base e open source di .NET](../get-started/net-core-and-open-source.md) e la [home page di .NET su GitHub](https://github.com/dotnet/home).

<a name="v452"></a>

## <a name="whats-new-in-net-framework-452"></a>Novità di .NET Framework 4.5.2

- **Nuove API per app ASP.NET** I nuovi metodi <xref:System.Web.HttpResponse.AddOnSendingHeaders%2A?displayProperty=nameWithType> e <xref:System.Web.HttpResponseBase.AddOnSendingHeaders%2A?displayProperty=nameWithType> consentono di esaminare e modificare le intestazioni di risposta e il codice di stato mentre la risposta viene scaricata sull'app client. Considerare l'uso di questi metodi invece degli eventi <xref:System.Web.HttpApplication.PreSendRequestHeaders> e <xref:System.Web.HttpApplication.PreSendRequestContent>, poiché sono più efficienti e affidabili.

  Il metodo <xref:System.Web.Hosting.HostingEnvironment.QueueBackgroundWorkItem%2A?displayProperty=nameWithType> consente di pianificare piccoli elementi di lavoro in background. ASP.NET tiene traccia di questi elementi e impedisce a IIS di chiudere improvvisamente il processo di lavoro finché non saranno stati completati tutti gli elementi di lavoro in background. Non è possibile chiamare questo metodo all'esterno del dominio dell'app gestita di ASP.NET.

  Le nuove proprietà <xref:System.Web.HttpResponse.HeadersWritten?displayProperty=nameWithType> e <xref:System.Web.HttpResponseBase.HeadersWritten?displayProperty=nameWithType> restituiscono valori booleani che indicano che le intestazioni di risposta sono state scritte. È possibile usare queste proprietà per accertarsi che le chiamate alle API come <xref:System.Web.HttpResponse.StatusCode%2A?displayProperty=nameWithType> (che genera eccezioni se le intestazioni sono state scritte) abbiano esito positivo.

- **Ridimensionamento nei controlli Windows Form** Questa funzionalità è stata ampliata. È ora possibile usare l'impostazione DPI di sistema per ridimensionare i componenti dei seguenti controlli aggiuntivi (ad esempio, la freccia a discesa nelle caselle combinate):

  - <xref:System.Windows.Forms.ComboBox>
  - <xref:System.Windows.Forms.ToolStripComboBox>
  - <xref:System.Windows.Forms.ToolStripMenuItem>
  - <xref:System.Windows.Forms.Cursor>
  - <xref:System.Windows.Forms.DataGridView>
  - <xref:System.Windows.Forms.DataGridViewComboBoxColumn>

  È una funzionalità che prevede il consenso esplicito. Per attivarla, impostare l'elemento `EnableWindowsFormsHighDpiAutoResizing` su `true` nel file di configurazione dell'applicazione (app.config):

  ```xml
  <appSettings>
      <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />
  </appSettings>
  ```

- **Nuova funzionalità per il flusso di lavoro.** Una funzionalità di gestione risorse che usa il metodo <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A> (e che quindi implementa l'interfaccia <xref:System.Transactions.IPromotableSinglePhaseNotification>) può usare il nuovo metodo <xref:System.Transactions.Transaction.PromoteAndEnlistDurable%2A?displayProperty=nameWithType> per richiedere quanto segue:

  - Promozione della transazione in transazione MSDTC (Microsoft Distributed Transaction Coordinator).

  - Sostituire <xref:System.Transactions.IPromotableSinglePhaseNotification> con una<xref:System.Transactions.ISinglePhaseNotification>, cioè un'integrazione durevole che supporta i commit monofase.

  È possibile eseguire questa operazione nello stesso dominio dell'app; inoltre, non è necessario altro codice non gestito che interagisca con MSDTC per eseguire la promozione. Questo nuovo metodo può essere chiamato solo quando esiste una chiamata in attesa da <xref:System.Transactions?displayProperty=nameWithType> al metodo <xref:System.Transactions.IPromotableSinglePhaseNotification> di `Promote` implementata dall'integrazione promuovibile.

- **Miglioramenti della profilatura.** Le seguenti nuove API di profilatura non gestite offrono funzioni di profilatura più solide:

  - [Struttura COR_PRF_ASSEMBLY_REFERENCE_INFO](../unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md)
  - [Enumerazione COR_PRF_HIGH_MONITOR](../unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md)
  - [Metodo GetAssemblyReferences](../unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)
  - [Metodo GetEventMask2](../unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md)
  - [Metodo SetEventMask2](../unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)
  - [Metodo AddAssemblyReference](../unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)

  Le precedenti implementazioni di `ICorProfiler` supportavano il caricamento differito degli assembly dipendenti. Le nuove API di profilatura richiedono assembly dipendenti inseriti dal profiler per il caricamento immediato, invece di essere caricato dopo la completa inizializzazione dell'app. Questa modifica non incide sugli utenti delle API `ICorProfiler` esistenti.

- **Miglioramenti al debug.** Le seguenti nuove API di debug non gestite offrono una migliore integrazione con un profiler. È ora possibile accedere ai metadati inseriti dal profiler oltre alle variabili e al codice locali prodotti dalle richieste ReJIT del compilatore durante il debug di dump.

  - [Metodo SetWriteableMetadataUpdateMode](../unmanaged-api/debugging/icordebugprocess7-setwriteablemetadataupdatemode-method.md)
  - [Metodo EnumerateLocalVariablesEx](../unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md)
  - [Metodo GetLocalVariableEx](../unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md)
  - [Metodo GetCodeEx](../unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md)
  - [Metodo GetActiveReJitRequestILCode](../unmanaged-api/debugging/icordebugfunction3-getactiverejitrequestilcode-method.md)
  - [Metodo GetInstrumentedILMap](../unmanaged-api/debugging/icordebugilcode2-getinstrumentedilmap-method.md)

- **Modifiche della traccia eventi.** .NET Framework 4.5.2 consente di eseguire attività out-of-process basate su Event Tracing for Windows (ETW) per una superficie di attacco maggiore. Ciò consente ai fornitori di Advanced Power Management (APM) di offrire strumenti semplici che tengono accuratamente traccia dei costi delle singole richieste e attività cross-thread.  Questi eventi vengono generati solo quando sono abilitati dai controller ETW; di conseguenza, le modifiche non influiscono sul codice ETW scritto in precedenza oppure sul codice eseguito con ETW disattivato.

- **Promozione di una transazione e relativa conversione in integrazione durevole**

  <xref:System.Transactions.Transaction.PromoteAndEnlistDurable%2A?displayProperty=nameWithType> è una nuova API aggiunta a .NET Framework 4.5.2 e 4.6:

  ```csharp
  [System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name = "FullTrust")]
  public Enlistment PromoteAndEnlistDurable(Guid resourceManagerIdentifier,
                                            IPromotableSinglePhaseNotification promotableNotification,
                                            ISinglePhaseNotification enlistmentNotification,
                                            EnlistmentOptions enlistmentOptions)
  ```

  ```vb
  <System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust")>
  public Function PromoteAndEnlistDurable(resourceManagerIdentifier As Guid,
                                          promotableNotification As IPromotableSinglePhaseNotification,
                                          enlistmentNotification As ISinglePhaseNotification,
                                          enlistmentOptions As EnlistmentOptions) As Enlistment
  ```

  Il metodo può essere usato da un elenco creato in precedenza da <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A?displayProperty=nameWithType> in risposta al metodo <xref:System.Transactions.ITransactionPromoter.Promote%2A?displayProperty=nameWithType>. Chiede a `System.Transactions` di alzare la transazione al livello di transazione MSDTC e di "convertire" l'elenco promuovibile in un elenco durevole. Dopo il completamento di questo metodo, l'interfaccia <xref:System.Transactions.IPromotableSinglePhaseNotification> non sarà più usata come riferimento da `System.Transactions` e le eventuali notifiche future arriveranno all'interfaccia <xref:System.Transactions.ISinglePhaseNotification> fornita. L'elenco in questione deve agire come un elenco durevole, supportando la registrazione e il ripristino delle transazioni. Vedere <xref:System.Transactions.Transaction.EnlistDurable%2A?displayProperty=nameWithType> per informazioni dettagliate. Inoltre, l'elenco deve supportare <xref:System.Transactions.ISinglePhaseNotification>.  Questo metodo può essere chiamato *solo* durante l'elaborazione di una chiamata <xref:System.Transactions.ITransactionPromoter.Promote%2A?displayProperty=nameWithType>. Diversamente, viene generata un'eccezione <xref:System.Transactions.TransactionException>.

<a name="v451"></a>

## <a name="whats-new-in-net-framework-451"></a>Novità di .NET Framework 4.5.1

**Aggiornamenti di aprile 2014**:

- [Visual Studio 2013 Update 2](https://go.microsoft.com/fwlink/p/?LinkId=393658) include alcuni aggiornamenti ai modelli di libreria di classi portabile per supportare questi scenari:

  - È possibile usare le API di Windows Runtime in librerie portabili destinate a Windows 8.1, Windows Phone 8.1 e Windows Phone Silverlight 8.1.

  - È possibile includere XAML (tipi Windows.UI.XAML) nelle librerie portabili quando la destinazione è Windows 8.1 o Windows Phone 8.1. Sono supportati i modelli XAML seguenti: Pagina vuota, Dizionario risorse, Controllo basato su modelli e Controllo utente.

  - È possibile creare una componente Windows Runtime portabile (.winmd file) da usare in app di Windows Store destinate a Windows 8.1 e Windows Phone 8.1.

  - È possibile cambiare associazione a una libreria di classi Windows Store o Windows Phone Store come una Libreria di classi portabile.

  Per altre informazioni su queste modifiche, vedere [Libreria di classi portabile](../../standard/cross-platform/cross-platform-development-with-the-portable-class-library.md).

- Il set di contenuti di .NET Framework ora include la documentazione relativa a .NET Native, una tecnologia di precompilazione per la creazione e la distribuzione di app di Windows. .NET Native compila le app direttamente in codice nativo piuttosto che in linguaggio intermedio (IL), per ottenere migliori prestazioni. Per informazioni dettagliate, vedere [Compilazione di app con .NET Native](../net-native/index.md).

- [Reference Source per .NET Framework](https://referencesource.microsoft.com/) offre una nuova esperienza di esplorazione e funzionalità migliorate. È ora possibile esplorare il codice sorgente di .NET Framework online, [scaricare i riferimenti](https://referencesource.microsoft.com/download.html) per la visualizzazione offline ed eseguire le origini (inclusi aggiornamenti e patch) durante il debug. Per altre informazioni, vedere il post di blog relativo al [nuovo aspetto di Reference Source per .NET](https://devblogs.microsoft.com/dotnet/a-new-look-for-net-reference-source/).

Le nuove funzionalità e i miglioramenti nelle classi di base di .NET Framework 4.5.1 includono:

- Reindirizzamento di associazione automatico per assembly. A partire da Visual Studio 2013, quando si compila un'app destinata a .NET Framework 4.5.1, è possibile aggiungere reindirizzamenti di associazione al file di configurazione dell'app se quest'ultima o i relativi componenti fanno riferimento a più versioni dello stesso assembly. È inoltre possibile abilitare questa funzionalità per i progetti destinati a versioni precedenti di .NET Framework. Per altre informazioni, vedere [Procedura: abilitare e disabilitare il reindirizzamento di associazione automatico](../configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md).

- Possibilità di raccogliere informazioni di diagnostica che consentono agli sviluppatori di migliorare le prestazioni delle applicazioni server e cloud. Per altre informazioni, vedere i metodi <xref:System.Diagnostics.Tracing.EventSource.WriteEventWithRelatedActivityId%2A> e <xref:System.Diagnostics.Tracing.EventSource.WriteEventWithRelatedActivityIdCore%2A> nella classe <xref:System.Diagnostics.Tracing.EventSource>.

- Capacità di compattare in modo esplicito gli heap di oggetti grandi durante la Garbage Collection. Per altre informazioni, vedere la proprietà <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=nameWithType>.

- Altri miglioramenti alle prestazioni, quali la sospensione di app ASP.NET, i miglioramenti JIT multicore e un avvio più rapido delle app in seguito a un aggiornamento di .NET Framework. Per informazioni dettagliate, vedere l'[annuncio di .NET Framework 4.5.1](https://devblogs.microsoft.com/dotnet/announcing-the-net-framework-4-5-1-preview/) e il post di blog sulla [sospensione di app ASP.NET](https://devblogs.microsoft.com/dotnet/asp-net-app-suspend-responsive-shared-net-web-hosting/).

I miglioramenti di Windows Form includono:

- Ridimensionamento nei controlli Windows Form. È possibile usare l'impostazione DPI per ridimensionare i componenti dei controlli (ad esempio, le icone visualizzate in una griglia delle proprietà) scegliendo una voce nel file di configurazione dell'applicazione (app.config) relativo alla propria app. Questa funzionalità è attualmente supportata nei seguenti controlli Windows Form:

  - <xref:System.Windows.Forms.PropertyGrid>
  - <xref:System.Windows.Forms.TreeView>
  -     Alcuni aspetti di <xref:System.Windows.Forms.DataGridView> (per gli altri controlli supportati, vedere le [nuove funzionalità nella versione 4.5.2](#v452))

  Per abilitare questa funzionalità, aggiungere un nuovo \<appSettings> elemento al file di configurazione (app.config) e impostare l' `EnableWindowsFormsHighDpiAutoResizing` elemento su `true` :

  ```xml
  <appSettings>
      <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />
  </appSettings>
  ```

I miglioramenti durante il debug delle app .NET Framework in Visual Studio 2013 includono:

- Valori restituiti nel debugger di Visual Studio. Quando si esegue il debug di un'app gestita in Visual Studio 2013, nella finestra Auto vengono restituiti tipi e valori per i metodi. Queste informazioni sono disponibili per applicazioni desktop, Windows Store e Windows Phone. Per altre informazioni, vedere [Esaminare i valori restituiti dalle chiamate di metodo](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/dn323257(v=vs.120)).

- Modifica e continua per app a 64 bit. In Visual Studio 2013 è supportata la funzionalità Modifica e continuazione per le applicazioni gestite a 64 bit per desktop, Windows Store e Windows Phone. Le limitazioni esistenti restano valide per le app a 32 bit e a 64 bit. Vedere l'ultima sezione dell'articolo [Modifiche al codice supportate (C#)](/visualstudio/debugger/supported-code-changes-csharp).

- Debug asincrono. Per semplificare il debug delle app asincrone in Visual Studio 2013, lo stack di chiamate nasconde il codice dell'infrastruttura fornito dai compilatori per supportare la programmazione asincrona e inoltre si concatena nei frame padre logici, in modo da poter seguire più chiaramente l'esecuzione logica del programma. La finestra Attività in parallelo è stata sostituita da una finestra Attività, contenente le attività correlate a uno specifico punto di interruzione e qualsiasi altra attività attualmente attiva o pianificata nell'app. Informazioni su questa funzionalità sono disponibili nella sezione relativa al debug asincrono nell'[annuncio di .NET Framework 4.5.1](https://devblogs.microsoft.com/dotnet/announcing-the-net-framework-4-5-1-preview/).

- Supporto avanzato delle eccezioni per i componenti Windows Runtime. In Windows 8.1 le eccezioni generate dalle app di Windows Store conservano le informazioni sull'errore che ha generato l'eccezione, anche oltre i limiti di linguaggio. Informazioni su questa funzionalità sono disponibili nella sezione relativa allo sviluppo di app di Windows Store nell'[annuncio di .NET Framework 4.5.1](https://devblogs.microsoft.com/dotnet/announcing-the-net-framework-4-5-1-preview/).

A partire da Visual Studio 2013, è possibile usare lo strumento [Mpgo.exe (Managed Profile Guided Optimization)](../tools/mpgo-exe-managed-profile-guided-optimization-tool.md) per ottimizzare le app di Windows 8.x Store e quelle desktop.

Per le nuove funzionalità in ASP.NET 4.5.1, vedere [Note sulla versione di ASP.NET and Web Tools per Visual Studio 2013](/aspnet/visual-studio/overview/2013/release-notes).

<a name="v45"></a>

## <a name="whats-new-in-net-framework-45"></a>Novità di .NET Framework 4.5

### <a name="base-classes"></a>Classi di base

- Possibilità di ridurre i riavvii di sistema rilevando e chiudendo le applicazioni .NET Framework 4 durante la distribuzione. Vedere [Riduzione dei riavvii del sistema durante le installazioni di .NET Framework 4.5](../deployment/reducing-system-restarts.md).

- Supporto per le matrici di dimensioni maggiori di 2 GB nelle piattaforme a 64 bit. Questa funzionalità può essere abilitata nel file di configurazione dell'applicazione. Vedere l' [ \<gcAllowVeryLargeObjects> elemento](../configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md), che elenca anche altre restrizioni sulle dimensioni degli oggetti e le dimensioni della matrice.

- Miglioramento delle prestazioni tramite Garbage Collection in background per server. Se si usa la funzionalità di Garbage Collection del server in .NET Framework 4.5, verrà automaticamente abilità la Garbage Collection in background. Vedere la sezione "Operazione di Garbage Collection in background per server" nell'argomento [Principi fondamentali di Garbage Collection](../../standard/garbage-collection/fundamentals.md).

- Compilazione JIT in background, eventualmente disponibile nei processori multicore per migliorare le prestazioni delle applicazioni. Vedere <xref:System.Runtime.ProfileOptimization>.

- Possibilità di limitare il tempo durante il quale il motore delle espressioni regolari tenterà di risolvere un'espressione regolare prima del timeout. Vedere la <xref:System.Text.RegularExpressions.Regex.MatchTimeout%2A?displayProperty=nameWithType> Proprietà.

- Possibilità di definire le impostazioni cultura predefinite per un dominio di applicazione. Vedere la classe <xref:System.Globalization.CultureInfo>.

- Supporto della console per la codifica Unicode (UTF-16). Vedere la classe <xref:System.Console>.

- Supporto per il controllo delle versioni dei dati di confronto e ordinamento delle stringhe di impostazioni cultura. Vedere la classe <xref:System.Globalization.SortVersion>.

- Miglioramento delle prestazioni in fase di recupero di risorse. Vedere [Creazione del pacchetto e distribuzione delle risorse in applicazioni desktop](../resources/packaging-and-deploying-resources-in-desktop-apps.md).

- Miglioramenti delle compressioni ZIP per ridurre la dimensione di un file compresso. Vedere lo spazio dei nomi <xref:System.IO.Compression?displayProperty=nameWithType>.

- Possibilità di personalizzare un contesto di reflection per eseguire l'override del comportamento di reflection predefinito tramite la classe <xref:System.Reflection.Context.CustomReflectionContext>.

- Supporto per la versione 2008 dello standard IDNA (International Domain Names in Applications) quando la <xref:System.Globalization.IdnMapping?displayProperty=nameWithType> classe viene utilizzata in Windows 8.

- Delega del confronto tra stringhe al sistema operativo, che effettua l'implementazione di Unicode 6.0, quando .NET Framework viene usato in Windows 8. Quando è in esecuzione in altre piattaforme, .NET Framework include i propri dati di confronto tra stringhe, che effettua l'implementazione di Unicode 5.x. Vedere la classe <xref:System.String> e la sezione Note della classe <xref:System.Globalization.SortVersion>.

- Possibilità di calcolare i codici hash per le stringhe in base al dominio dell'applicazione. Vedere l' [ \<UseRandomizedStringHashAlgorithm> elemento](../configure-apps/file-schema/runtime/userandomizedstringhashalgorithm-element.md).

- Il supporto per la reflection dei tipi è stato suddiviso tra le classi <xref:System.Type> e <xref:System.Reflection.TypeInfo>. Vedere [Reflection in .NET Framework per app di Windows Store](../reflection-and-codedom/reflection-for-windows-store-apps.md).

### <a name="managed-extensibility-framework-mef"></a>Managed Extensibility Framework (MEF)

In .NET Framework 4.5 la libreria Managed Extensibility Framework (MEF) offre le seguenti nuove funzionalità:

- Supporto per tipi generici.

- Modello di programmazione basato su convenzioni che consente di creare parti basate sulle convenzioni di denominazione, anziché sugli attributi.

- Più ambiti.

- Subset di MEF che è possibile usare in fase di creazione delle app di Windows 8.x Store. Questo subset è disponibile come [pacchetto scaricabile](https://www.nuget.org/packages/Microsoft.Composition) dalla raccolta NuGet. Per installare il pacchetto, aprire il progetto in Visual Studio, scegliere **Gestisci pacchetti NuGet** dal menu **Progetto** ed eseguire una ricerca online del pacchetto `Microsoft.Composition`.

Per altre informazioni, vedere [Managed Extensibility Framework (MEF)](../mef/index.md).

### <a name="asynchronous-file-operations"></a>Operazioni asincrone sui file.

In .NET Framework 4.5 sono state aggiunte nuove funzionalità asincrone nei linguaggi C# e Visual Basic. Con queste funzionalità viene introdotto un modello basato su attività per eseguire operazioni asincrone. Per impiegare questo nuovo modello, usare i metodi asincroni nelle classi I/O. Vedere [I/O di file asincrono](../../standard/io/asynchronous-file-i-o.md).

<a name="tools"></a>

### <a name="tools"></a>Strumenti

In .NET Framework 4.5 il generatore di file di risorse (Resgen.exe) consente di creare un file con estensione resw per l'uso nelle app di Windows 8.x Store da un file con estensione resources incorporato in un assembly .NET Framework. Per altre informazioni, vedere [Resgen.exe (generatore di file di risorse)](../tools/resgen-exe-resource-file-generator.md).

L'ottimizzazione PGO gestita (Mpgo.exe) consente di migliorare i tempi di avvio delle applicazioni, l'uso della memoria (dimensione del working set) e la velocità effettiva attraverso l'ottimizzazione degli assembly di immagini nativi. Lo strumento da riga di comando genera dati di profilo per assembly di applicazioni di immagini nativi. Vedere [Strumento Mpgo.exe (Managed Profile Guided Optimization)](../tools/mpgo-exe-managed-profile-guided-optimization-tool.md). A partire da Visual Studio 2013, è possibile usare Mpgo.exe per ottimizzare le app di Windows 8.x Store e quelle desktop.

<a name="parallel"></a>

### <a name="parallel-computing"></a>Elaborazione parallela

In .NET Framework 4.5 vengono forniti diversi miglioramenti e nuove funzionalità per il calcolo parallelo. Alcuni esempi: miglioramento delle prestazioni, maggiore controllo, supporto avanzato per la programmazione asincrona, una nuova libreria di flussi di dati e un miglioramento del supporto per il debug parallelo e l'analisi delle prestazioni. Vedere la voce [relativa alle novità del parallelismo in .net 4,5](https://devblogs.microsoft.com/pfxteam/whats-new-for-parallelism-in-net-4-5/) nel Blog sulla programmazione parallela con .NET.

<a name="web"></a>

### <a name="web"></a>Web

In ASP.NET 4.5 e 4.5.1 vengono aggiunti associazione di modelli per Web Form, supporto di WebSocket, gestori asincroni, miglioramenti delle prestazioni e molte altre funzionalità. Per altre informazioni, vedere le risorse seguenti:

- [ASP.NET 4.5 e Visual Studio 2012](https://docs.microsoft.com/previous-versions/aspnet/hh420390(v=vs.110))

- [Note sulla versione di ASP.NET and Web Tools per Visual Studio 2013](/aspnet/visual-studio/overview/2013/release-notes)

### <a name="networking"></a>Rete <a name="networking"></a>

In .NET Framework 4.5 viene fornita una nuova interfaccia di programmazione per applicazioni HTTP. Per altre informazioni, vedere i nuovi spazi dei nomi <xref:System.Net.Http?displayProperty=nameWithType> e <xref:System.Net.Http.Headers?displayProperty=nameWithType>.

È inoltre incluso il supporto per una nuova interfaccia di programmazione per l'accettazione e l'interazione con una connessione WebSocket usando l'oggetto <xref:System.Net.HttpListener> esistente e le classi correlate. Per altre informazioni, vedere il nuovo spazio dei nomi <xref:System.Net.WebSockets> e la classe <xref:System.Net.HttpListener>.

In .NET Framework 4.5 sono inclusi anche i seguenti miglioramenti di rete:

- Supporto URI conforme a RFC. Per altre informazioni, vedere <xref:System.Uri> e le classi correlate.

- Supporto per l'analisi IDN (Internationalized Domain Name). Per altre informazioni, vedere <xref:System.Uri> e le classi correlate.

- Supporto per EAI (Email Address Internationalization). Per altre informazioni, vedere lo spazio dei nomi <xref:System.Net.Mail>.

- Supporto IPv6 avanzato. Per altre informazioni, vedere lo spazio dei nomi <xref:System.Net.NetworkInformation>.

- Supporto per socket dual mode. Per altre informazioni, vedere le classi <xref:System.Net.Sockets.Socket> e <xref:System.Net.Sockets.TcpListener>.

<a name="client"></a>

### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)

In .NET Framework 4.5, Windows Presentation Foundation (WPF) include miglioramenti e modifiche nelle aree seguenti:

- Nuovo controllo <xref:System.Windows.Controls.Ribbon.Ribbon>, che consente di implementare l'interfaccia utente di una barra multifunzione che ospita una barra di accesso rapido, menu di applicazione e schede.

- Nuova interfaccia <xref:System.ComponentModel.INotifyDataErrorInfo>, che supporta la convalida sincrona e asincrona dei dati.

- Nuove funzionalità per le classi <xref:System.Windows.Controls.VirtualizingPanel> e <xref:System.Windows.Threading.Dispatcher>.

- Miglioramento delle prestazioni durante la visualizzazione di grandi set di dati raggruppati e mediante l'accesso alle raccolte in thread non dell'interfaccia utente.

- Associazione di dati a proprietà statiche, associazione di dati a tipi personalizzati che implementano l'interfaccia <xref:System.Reflection.ICustomTypeProvider> e recupero di informazioni sull'associazione dati da un'espressione di associazione.

- Riposizionamento di dati contestuale alla modifica dei valori (shaping attivo).

- Possibilità di controllare se il contesto dei dati per un contenitore di elementi è disconnesso.

- Possibilità di impostare la quantità di tempo che deve trascorrere tra le modifiche alle proprietà e gli aggiornamenti delle origini dati.

- Supporto avanzato per l'implementazione di modelli di eventi deboli. Inoltre, gli eventi possono ora accettare estensioni di markup.

<a name="windows_communication_foundation"></a>

### <a name="windows-communication-foundation-wcf"></a>Windows Communication Foundation (WCF)

In .NET Framework 4.5 le seguenti funzionalità sono state aggiunte per semplificare la scrittura e la gestione di applicazioni Windows Communication Foundation (WCF):

- Semplificazione dei file di configurazione generati.

- Supporto per lo sviluppo con priorità al contratto ("contract-first").

- Possibilità di configurare la modalità di compatibilità ASP.NET in modo più semplice.

- Modifiche ai valori predefiniti delle proprietà di trasporto per ridurre la probabilità di doverli impostare.

- Aggiornamenti alla classe <xref:System.Xml.XmlDictionaryReaderQuotas> per ridurre le probabilità di dover configurare manualmente le quote per i reader del dizionario XML.

- Convalida dei file di configurazione WCF da parte di Visual Studio nell'ambito del processo di compilazione, in modo da poter rilevare errori di configurazione prima di eseguire l'applicazione.

- Nuovo supporto per lo streaming asincrono.

- Nuovo mapping del protocollo HTTPS per semplificare l'esposizione di un endpoint su HTTPS con Internet Information Services (IIS).

- Possibilità di generare metadati in un singolo documento WSDL aggiungendo `?singleWSDL` all'URL del servizio.

- Supporto di WebSocket per consentire un'effettiva comunicazione bidirezionale sulle porte 80 e 443 con caratteristiche di prestazioni simili al trasporto TCP.

- Supporto per la configurazione dei servizi nel codice.

- Descrizioni comando dell'editor XML.

- Supporto per la memorizzazione nella cache di <xref:System.ServiceModel.ChannelFactory>.

- Supporto della compressione del codificatore binario.

- Supporto per un trasporto UDP che consente agli sviluppatori di scrivere servizi che usano la messaggistica di tipo "Fire and Forget". Un client invia un messaggio a un servizio e non prevede alcuna risposta dal servizio.

- Possibilità di supportare più modalità di autenticazione in un singolo endpoint WCF quando si usa il trasporto HTTP e la sicurezza del trasporto.

- Supporto per servizi WCF che usano IDN (Internationalized Domain Name).

Per altre informazioni, vedere [Novità di Windows Communication Foundation](../wcf/whats-new.md).

<a name="windows_workflow_foundation"></a>

### <a name="windows-workflow-foundation-wf"></a>Windows Workflow Foundation (WF)

In .NET Framework 4.5 sono state introdotte numerose nuove funzionalità in Windows Workflow Foundation (WF), tra cui:

- Flussi di lavoro della macchina a stati, introdotti per la prima volta in .NET Framework 4.0.1 ([.NET Framework 4 Platform Update 1](https://docs.microsoft.com/archive/blogs/endpoint/microsoft-net-framework-4-platform-update-1)). In questo aggiornamento erano incluse diverse nuove classi e attività che consentivano agli sviluppatori di creare flussi di lavoro macchina a stati. Queste classi e attività sono state aggiornate per .NET Framework 4.5 al fine di includere:

  - Possibilità di impostare punti di interruzione negli stati.

  - Possibilità di copiare e incollare transizioni in Workflow Designer.

  - Supporto della finestra di progettazione per la creazione di transizioni con trigger condivisi.

  - Attività per creare flussi di lavoro macchina a stati, tra cui: <xref:System.Activities.Statements.StateMachine>, <xref:System.Activities.Statements.State> e <xref:System.Activities.Statements.Transition>.

- Funzionalità avanzate di Workflow Designer, tra cui:

  - Funzionalità avanzate di ricerca di flussi di lavoro in Visual Studio, tra cui **Ricerca veloce** e **Cerca nei file**.

  - Possibilità di creare automaticamente un'attività Sequence quando viene aggiunta una seconda attività figlio a un'attività del contenitore e di includere entrambe le attività nell'attività Sequence.

  - Supporto per panoramica, che consente di modificare la parte visibile di un flusso di lavoro senza ricorrere a barre di scorrimento.

  - Nuova visualizzazione **Struttura documento** che mostra i componenti di un flusso di lavoro in una visualizzazione in stile albero e permette di selezionare un componente nella visualizzazione **Struttura documento**.

  - Possibilità di aggiungere annotazioni alle attività.

  - Capacità di definire e usare delegati di attività mediante Workflow Designer.

  - Connessione e inserimento automatici per attività e transizioni nei flussi di lavoro macchina a stati e del diagramma di flusso.

- Archiviazione di informazioni sullo stato di visualizzazione per un flusso di lavoro in un singolo elemento nel file XAML, in modo da poter individuare e modificare agevolmente tali informazioni.

- Attività del contenitore NoPersistScope per impedire la conservazione delle attività figlio.

- Supporto per espressioni C#:

  - I progetti di flusso di lavoro che usano Visual Basic impiegheranno espressioni Visual Basic, mentre i progetti di flusso di lavoro C# useranno espressioni C#.

  - I progetti di flusso di lavoro C# creati in Visual Studio 2010 e con espressioni Visual Basic sono compatibili con i progetti di flusso di lavoro C# che usano espressioni C#.

- Miglioramenti del controllo delle versioni:

  - Nuova classe <xref:System.Activities.WorkflowIdentity>, che fornisce un mapping tra un'istanza di flusso di lavoro persistente e la relativa definizione.

  - Esecuzione affiancata di più versioni del flusso di lavoro nello stesso host, tra cui <xref:System.ServiceModel.Activities.WorkflowServiceHost>.

  - In Aggiornamento dinamico, capacità di modificare la definizione di un'istanza di flusso di lavoro persistente.

- Sviluppo di flussi di lavoro con priorità al contratto ("contract-first"), che fornisce supporto per generare automaticamente attività in modo da soddisfare un contratto di servizio esistente.

Per altre informazioni, vedere [Novità di Windows Workflow Foundation](../windows-workflow-foundation/whats-new-in-wf-in-dotnet.md).

<a name="tailored"></a>

### <a name="net-for-windows-8x-store-apps"></a>.NET per app di Windows 8.x Store

Le app di WIndows 8.x Store sono progettate per fattori di forma specifici e sfruttano la potenza del sistema operativo Windows. Un subset di .NET Framework 4.5 o 4.5.1 è disponibile per la compilazione di app per Windows 8.x Store usando C# o Visual Basic. Questo subset è denominato .NET per le app di Windows 8. x Store e viene descritto in una [Panoramica](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140)).

### <a name="portable-class-libraries"></a>Librerie di classi portabili <a name="portable"></a>

Il progetto Libreria di classi portabile in Visual Studio 2012 (e versioni successive) consente di scrivere e compilare assembly gestiti compatibili con più piattaforme .NET Framework. Usando un progetto libreria di classi portabile, si scelgono le piattaforme (ad esempio Windows Phone e .NET per le app di Windows 8. x Store) per la destinazione. I tipi e i membri disponibili nel progetto sono automaticamente limitati a tipi e membri comuni in queste piattaforme. Per altre informazioni, vedere [Libreria di classi portabile](../../standard/cross-platform/cross-platform-development-with-the-portable-class-library.md).

## <a name="see-also"></a>Vedere anche

- [.NET Framework e rilascio fuori programma](../get-started/the-net-framework-and-out-of-band-releases.md)
- [Nuove funzionalità di accessibilità in .NET Framework](whats-new-in-accessibility.md)
- [Novità di Visual Studio 2017](/visualstudio/ide/whats-new-visual-studio-2017)
- [Novità di Visual Studio 2019](/visualstudio/ide/whats-new-visual-studio-2019)
- [ASP.NET](/aspnet)
- [Novità di C++ in Visual Studio](/cpp/what-s-new-for-visual-cpp-in-visual-studio)
