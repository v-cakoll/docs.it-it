---
title: Migrazione dell'app di Windows Store a .NET Native
ms.date: 03/30/2017
ms.assetid: 4153aa18-6f56-4a0a-865b-d3da743a1d05
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a316cd8ed82f9833b23fe313b8f4c4903bd0a433
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="migrating-your-windows-store-app-to-net-native"></a>Migrazione dell'app di Windows Store a .NET Native
[!INCLUDE[net_native](../../../includes/net-native-md.md)] fornisce la compilazione statica di applicazioni in Windows Store o sul computer dello sviluppatore. Ciò differisce dalla compilazione dinamica eseguita per applicazioni Windows Store dal compilatore just-in-time (JIT) o il [Native Image Generator (Ngen.exe)](../../../docs/framework/tools/ngen-exe-native-image-generator.md) sul dispositivo. Nonostante le differenze, [!INCLUDE[net_native](../../../includes/net-native-md.md)] prova a mantenere la compatibilità con [.NET per applicazioni Windows Store](http://msdn.microsoft.com/library/windows/apps/br230302.aspx). Nella maggior parte dei casi, ciò che funziona sulle app .NET per Windows Store funziona anche con [!INCLUDE[net_native](../../../includes/net-native-md.md)].  Tuttavia, in alcuni casi, è possibile riscontrare differenze di comportamento. In questo documento vengono illustrate le differenze tra .NET per applicazioni Windows Store standard e [!INCLUDE[net_native](../../../includes/net-native-md.md)] nelle seguenti aree:  
  
-   [Differenze generali di runtime](#Runtime)  
  
-   [Differenze di programmazione dinamica](#Dynamic)  
  
-   [Altre differenze correlate alla reflection](#Reflection)  
  
-   [Scenari e API non supportati](#Unsupported)  
  
-   [Differenze di Visual Studio](#VS)  
  
<a name="Runtime"></a>   
## <a name="general-runtime-differences"></a>Differenze generali di runtime  
  
-   Eccezioni, ad esempio <xref:System.TypeLoadException>, che vengono generate dal compilatore JIT quando un'applicazione eseguita su Common Language Runtime (CLR), in genere producono errori in fase di compilazione quando vengono elaborate da [!INCLUDE[net_native](../../../includes/net-native-md.md)].  
  
-   Non chiamare il metodo <xref:System.GC.WaitForPendingFinalizers%2A?displayProperty=nameWithType> da un thread UI dell'app. Ciò può causare un deadlock in [!INCLUDE[net_native](../../../includes/net-native-md.md)].  
  
-   Non fare affidamento sull'ordine di chiamata del costruttore di classe statica. In [!INCLUDE[net_native](../../../includes/net-native-md.md)], l'ordine di chiamata è diverso dall'ordine di runtime standard (anche con il runtime standard, non è consigliabile fare affidamento sull'ordine di esecuzione dei costruttori di classe statici).  
  
-   Un ciclo infinito senza eseguire una chiamata (ad esempio, `while(true);`) su qualsiasi thread può comportare l'arresto dell'applicazione. Allo stesso modo, attese lunghe o infinite possono portare all'arresto dell'applicazione.  
  
-   Alcuni cicli di inizializzazione generici non generano eccezioni in [!INCLUDE[net_native](../../../includes/net-native-md.md)]. Ad esempio, il codice seguente genera un'eccezione <xref:System.TypeLoadException> sul CLR standard, mentre in [!INCLUDE[net_native](../../../includes/net-native-md.md)]ciò non accade.  
  
     [!code-csharp[ProjectN#8](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat1.cs#8)]  
  
-   In alcuni casi, [!INCLUDE[net_native](../../../includes/net-native-md.md)] fornisce implementazioni diverse di librerie di classi .NET Framework. Un oggetto restituito da un metodo implementerà sempre i membri del tipo restituito. Tuttavia, poiché l'implementazione di supporto è diversa, potrebbe non essere possibile eseguire il cast per la stessa raccolta di tipi come su altre piattaforme di.NET Framework. Ad esempio, in alcuni casi, potrebbe non essere possibile eseguire il cast dell'oggetto di interfaccia <xref:System.Collections.Generic.IEnumerable%601> restituito da metodi quali <xref:System.Reflection.TypeInfo.DeclaredMembers%2A?displayProperty=nameWithType> o <xref:System.Reflection.TypeInfo.DeclaredProperties%2A?displayProperty=nameWithType> a `T[]`.  
  
-   La cache di WinINet non è abilitata per impostazione predefinita su .NET per applicazioni Windows Store, ma lo è su [!INCLUDE[net_native](../../../includes/net-native-md.md)]. Questo migliora le prestazioni, ma ha implicazioni sul working set. Non è necessaria alcuna azione da parte dello sviluppatore.  
  
<a name="Dynamic"></a>   
## <a name="dynamic-programming-differences"></a>Differenze di programmazione dinamica  
 [!INCLUDE[net_native](../../../includes/net-native-md.md)] collega in modo statico il codice da .NET Framework per rendere il codice app-local e ottenere prestazioni ottimali. Tuttavia, le dimensioni binarie devono rimanere ridotte, in modo da non consentire il passaggio dell'intero.NET Framework. Il compilatore di [!INCLUDE[net_native](../../../includes/net-native-md.md)] risolve questa limitazione usando un riduttore di dipendenza che rimuove i riferimenti al codice non usato. Tuttavia, [!INCLUDE[net_native](../../../includes/net-native-md.md)] può non gestire o generare alcune informazioni sul tipo e il codice quando tali informazioni non possono essere dedotte in modo statico in fase di compilazione, ma al contrario vengono recuperate in modo dinamico in fase di esecuzione.  
  
 [!INCLUDE[net_native](../../../includes/net-native-md.md)] non attiva la reflection e la programmazione dinamica. Tuttavia, non tutti i tipi possono essere contrassegnati per la reflection, perché ciò rende eccessive le dimensioni del codice generato (soprattutto perché la reflection sulle API pubbliche in .NET Framework è supportata). Il compilatore di [!INCLUDE[net_native](../../../includes/net-native-md.md)] opera scelte intelligenti su quali tipi devono supportare la reflection e mantiene i metadati generando il codice solo per i tipi.  
  
 Ad esempio, il data binding richiede che un'applicazione possa eseguire il mapping dei nomi di proprietà alle funzioni. In .NET per applicazioni Windows Store, Common Language Runtime usa automaticamente la reflection per fornire questa funzionalità per i tipi gestiti e i tipi nativi disponibili al pubblico. In [!INCLUDE[net_native](../../../includes/net-native-md.md)], il compilatore include automaticamente i metadati per i tipi a cui associare i dati.  
  
 Il compilatore di [!INCLUDE[net_native](../../../includes/net-native-md.md)] può anche gestire i tipi generici usati comunemente come <xref:System.Collections.Generic.List%601> e <xref:System.Collections.Generic.Dictionary%602>, che funzionano senza richiedere suggerimenti o direttive. È supportata anche la parola chiave [dinamica](~/docs/csharp/language-reference/keywords/dynamic.md) entro certi limiti.  
  
> [!NOTE]
>  È consigliabile verificare accuratamente tutti i percorsi di codice dinamico durante l'importazione dell'applicazione in [!INCLUDE[net_native](../../../includes/net-native-md.md)].  
  
 La configurazione predefinita per [!INCLUDE[net_native](../../../includes/net-native-md.md)] è sufficiente per la maggior parte degli sviluppatori, ma per alcuni sviluppatori potrebbe essere necessario ritoccare le relative configurazioni usando un file delle direttive di runtime (rd.xml). Inoltre, in alcuni casi, il compilatore [!INCLUDE[net_native](../../../includes/net-native-md.md)] non può determinare quali metadati devono essere disponibili per la reflection e si basa su suggerimenti, in particolare nei seguenti casi:  
  
-   Alcuni costrutti come <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> e <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A?displayProperty=nameWithType> non possono essere determinati staticamente.  
  
-   Poiché il compilatore non può determinare le istanze create, un tipo generico di cui si vuole effettuare la reflection deve essere specificato dalle direttive di runtime. Ciò non solo perché è necessario includere tutto il codice, ma anche perché la reflection sui tipi può creare un ciclo infinito (ad esempio, quando un metodo generico viene richiamato su un tipo generico).  
  
> [!NOTE]
>  Le direttive di runtime sono definite in un file nelle direttive di runtime (rd.xml). Per informazioni generali sull'uso di questo file, vedere [Introduzione](../../../docs/framework/net-native/getting-started-with-net-native.md). Per informazioni sulle direttive di runtime, vedere [Runtime Directives (rd.xml) Configuration File Reference](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).  
  
 [!INCLUDE[net_native](../../../includes/net-native-md.md)] include anche strumenti di profilatura che consentono allo sviluppatore di determinare quali tipi all'esterno del set predefinito devono supportare la reflection.  
  
<a name="Reflection"></a>   
## <a name="other-reflection-related-differences"></a>Altre differenze correlate alla reflection  
 Esistono numerose altre differenze di comportamento relative alla reflection tra .NET per applicazioni Windows Store e [!INCLUDE[net_native](../../../includes/net-native-md.md)].  
  
 In [!INCLUDE[net_native](../../../includes/net-native-md.md)]:  
  
-   La reflection privata su tipi e membri della libreria di classi .NET Framework non è supportata. È tuttavia possibile riflettere sui propri tipi e membri privati, nonché sui tipi e membri nelle librerie di terze parti.  
  
-   La proprietà <xref:System.Reflection.ParameterInfo.HasDefaultValue%2A?displayProperty=nameWithType> restituisce correttamente `false` per un oggetto <xref:System.Reflection.ParameterInfo> che rappresenta un valore restituito. In .NET per applicazioni Windows Store, restituisce `true`. IL (Intermediate language) non supporta direttamente questa funzione, e quindi l'interpretazione viene lasciata al linguaggio.  
  
-   I membri pubblici sulle strutture <xref:System.RuntimeFieldHandle> e <xref:System.RuntimeMethodHandle> non sono supportati. Questi tipi sono supportati solo per LINQ, gli alberi delle espressioni e l'inizializzazione di matrice statica.  
  
-   <xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeProperties%2A?displayProperty=nameWithType> e <xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeEvents%2A?displayProperty=nameWithType> includono membri nascosi in classi di base e perciò potrebbero essere sottoposti a override esplicito. Ciò vale anche per gli altri metodi [RuntimeReflectionExtensions.GetRuntime*](http://msdn.microsoft.com/library/system.reflection.runtimereflectionextensions_methods.aspx) .  
  
-   <xref:System.Type.MakeArrayType%2A?displayProperty=nameWithType> e <xref:System.Type.MakeByRefType%2A?displayProperty=nameWithType> non hanno esito negativo quando si prova a creare determinate combinazioni (ad esempio, una matrice di ByRef).  
  
-   Non è possibile usare la reflection per richiamare i membri con parametri di puntatore.  
  
-   Non è possibile usare la reflection per ottenere o impostare un campo del puntatore.  
  
-   Quando il numero di argomenti è errato e il tipo di uno degli argomenti non è corretto, [!INCLUDE[net_native](../../../includes/net-native-md.md)] genera una <xref:System.ArgumentException> invece di una <xref:System.Reflection.TargetParameterCountException>.  
  
-   In genere la serializzazione binaria delle eccezioni non è supportata. Di conseguenza, è possibile aggiungere gli oggetti non serializzabili al dizionario <xref:System.Exception.Data%2A?displayProperty=nameWithType>.  
  
<a name="Unsupported"></a>   
## <a name="unsupported-scenarios-and-apis"></a>Scenari e API non supportati  
 Nelle sezioni seguenti vengono elencati gli scenari e le API non supportati per lo sviluppo generale, l'interoperabilità e le tecnologie, ad esempio HTTPClient e Windows Communication Foundation (WCF):  
  
-   [Sviluppo generale](#General)  
  
-   [HttpClient](#HttpClient)  
  
-   [Interoperabilità](#Interop)  
  
-   [API non supportate](#APIs)  
  
<a name="General"></a>   
### <a name="general-development-differences"></a>Differenze generali per lo sviluppo  
 **Tipi di valore**  
  
-   Se si esegue l'override dei metodi <xref:System.ValueType.Equals%2A?displayProperty=nameWithType> e <xref:System.ValueType.GetHashCode%2A?displayProperty=nameWithType> per un tipo di valore, non chiamare le implementazioni della classe di base. In .NET per applicazioni Windows Store, questi metodi si basano sulla reflection. In fase di compilazione, [!INCLUDE[net_native](../../../includes/net-native-md.md)] genera un'implementazione che non si basa sulla reflection di runtime. Ciò significa che se si non esegue l'override di questi due metodi, funzioneranno come previsto, perché [!INCLUDE[net_native](../../../includes/net-native-md.md)] genera l'implementazione in fase di compilazione. Tuttavia, se si esegue l'override di questi metodi, ma si chiama l'implementazione della classe base verrà generata un'eccezione.  
  
-   Non sono supportati i tipi di valore superiori a un megabyte.  
  
-   I tipi di valore non possono avere un costruttore predefinito in [!INCLUDE[net_native](../../../includes/net-native-md.md)] (C# e Visual Basic vietano i costruttori predefiniti sui tipi di valore. Tuttavia, è possibile crearli in IL).  
  
 **Matrici**  
  
-   Non sono supportate le matrici con limite inferiore diverso da zero. Solitamente, queste matrici vengono create chiamando l'overload di <xref:System.Array.CreateInstance%28System.Type%2CSystem.Int32%5B%5D%2CSystem.Int32%5B%5D%29?displayProperty=nameWithType>.  
  
-   Non è supportata la creazione dinamica di matrici multidimensionali. Tali matrici vengono in genere creata dalla chiamata di un overload del metodo <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> che include un parametro `lengths` oppure dalla chiamata del metodo <xref:System.Type.MakeArrayType%28System.Int32%29?displayProperty=nameWithType>.  
  
-   Le matrici multidimensionali con quattro o più dimensioni non sono supportate; vale a dire il relativo valore della proprietà <xref:System.Array.Rank%2A?displayProperty=nameWithType> è 4 o superiore. Usare invece le [matrici irregolari](~/docs/csharp/programming-guide/arrays/jagged-arrays.md) (una matrice di matrici). Ad esempio, `array[x,y,z]` non è valido, mentre `array[x][y][z]` è valido.  
  
-   La varianza per le matrici multidimensionali non è supportata e causa un'eccezione <xref:System.InvalidCastException> in fase di esecuzione.  
  
 **Generics**  
  
-   L'espansione di tipo generico infinito genera un errore del compilatore. Ad esempio, questo codice non viene compilato:  
  
     [!code-csharp[ProjectN#9](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat2.cs#9)]  
  
 **Pointers**  
  
-   Le matrici di puntatori non sono supportate.  
  
-   Non è possibile usare la reflection per ottenere o impostare un campo del puntatore.  
  
 **Serializzazione**  
  
 L'attributo <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.String%29> non è supportato. Usare piuttosto l'attributo <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.Type%29> .  
  
 **Risorse**  
  
 L'uso di risorse localizzate con la classe <xref:System.Diagnostics.Tracing.EventSource> non è supportato. La proprietà <xref:System.Diagnostics.Tracing.EventSourceAttribute.LocalizationResources%2A?displayProperty=nameWithType> non definisce le risorse localizzate.  
  
 **Delegati**  
  
 `Delegate.BeginInvoke` e `Delegate.EndInvoke` non sono supportati.  
  
 **Async**  
  
 La logica di threading negli overload di Task IAsync non è supportata.  
  
 **Varie API**  
  
-   La proprietà <xref:System.Reflection.TypeInfo.GUID%2A?displayProperty=nameWithType> genera un'eccezione <xref:System.PlatformNotSupportedException> se un attributo <xref:System.Runtime.InteropServices.GuidAttribute> non viene applicato al tipo. Il GUID viene usato principalmente per il supporto COM.  
  
-   Il metodo <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> analizza correttamente le stringhe che contengono date brevi in [!INCLUDE[net_native](../../../includes/net-native-md.md)]. Tuttavia, non mantiene la compatibilità con le modifiche nell'analisi di data e ora descritte negli articoli della Microsoft Knowledge Base [KB2803771](http://support.microsoft.com/kb/2803771) e [KB2803755](http://support.microsoft.com/kb/2803755).  
  
-   <xref:System.Numerics.BigInteger.ToString%2A?displayProperty=nameWithType> `("E")` è arrotondata correttamente in [!INCLUDE[net_native](../../../includes/net-native-md.md)]. In alcune versioni di CLR, la stringa di risultato viene troncata anziché arrotondata.  
  
<a name="HttpClient"></a>   
### <a name="httpclient-differences"></a>Differenze di HttpClient  
 In [!INCLUDE[net_native](../../../includes/net-native-md.md)]la classe <xref:System.Net.Http.HttpClientHandler> usa internamente WinINet (tramite la classe [HttpBaseProtocolFilter](http://msdn.microsoft.com/library/windows/apps/windows.web.http.filters.httpbaseprotocolfilter.aspx) ) anziché le classi <xref:System.Net.WebRequest> e <xref:System.Net.WebResponse> usate nella versione standard di .NET per applicazioni Windows Store.  WinINet non supporta tutte le opzioni di configurazione supportate dalla classe <xref:System.Net.Http.HttpClientHandler> .  Di conseguenza, si verifica quanto segue:  
  
-   Alcune delle proprietà di capacità su <xref:System.Net.Http.HttpClientHandler> restituiscono `false` su [!INCLUDE[net_native](../../../includes/net-native-md.md)], laddove restituiscono `true` in .NET per applicazioni Windows Store standard.  
  
-   Alcune delle le funzioni di accesso `get` della proprietà di configurazione restituisce sempre un valore fisso in [!INCLUDE[net_native](../../../includes/net-native-md.md)] , diverso da quello predefinito configurabile in .NET per applicazioni Windows Store.  
  
 Nelle sottosezioni riportate di seguito sono descritte alcune differenze di comportamento aggiuntive.  
  
 **Proxy**  
  
 La classe [HttpBaseProtocolFilter](http://msdn.microsoft.com/library/windows/apps/windows.web.http.filters.httpbaseprotocolfilter.aspx) non supporta la configurazione o l'override del proxy in base a ogni richiesta.  Ciò significa che tutte le richieste su [!INCLUDE[net_native](../../../includes/net-native-md.md)] usano il server proxy configurato dal sistema o nessun server proxy, a seconda del valore della proprietà <xref:System.Net.Http.HttpClientHandler.UseProxy%2A?displayProperty=nameWithType>.  In .NET per applicazioni Windows Store il server proxy viene definito dalla proprietà <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType>.  In [!INCLUDE[net_native](../../../includes/net-native-md.md)], l'impostazione di <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType> su un valore diverso da `null` genera un'eccezione <xref:System.PlatformNotSupportedException>.  La proprietà <xref:System.Net.Http.HttpClientHandler.SupportsProxy%2A?displayProperty=nameWithType> restituisce `false` su [!INCLUDE[net_native](../../../includes/net-native-md.md)], laddove restituisce `true` in .NET per applicazioni Windows Store standard.  
  
 **Reindirizzamento automatico**  
  
 La classe [HttpBaseProtocolFilter](http://msdn.microsoft.com/library/windows/apps/windows.web.http.filters.httpbaseprotocolfilter.aspx) non consente la configurazione del numero massimo di reindirizzamenti automatici.  Il valore della proprietà <xref:System.Net.Http.HttpClientHandler.MaxAutomaticRedirections%2A?displayProperty=nameWithType> è 50 per impostazione predefinita in .NET per applicazioni Windows Store standard e può essere modificato. In [!INCLUDE[net_native](../../../includes/net-native-md.md)], il valore di questa proprietà è 10 e se si prova a modificarlo viene generata un'eccezione <xref:System.PlatformNotSupportedException> .  La proprietà <xref:System.Net.Http.HttpClientHandler.SupportsRedirectConfiguration%2A?displayProperty=nameWithType> restituisce `false` su [!INCLUDE[net_native](../../../includes/net-native-md.md)], laddove restituisce `true` in .NET per applicazioni Windows Store.  
  
 **Decompressione automatica**  
  
 .NET per applicazioni Windows Store consente di impostare la proprietà <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A?displayProperty=nameWithType> su <xref:System.Net.DecompressionMethods.Deflate>, <xref:System.Net.DecompressionMethods.GZip>, sia <xref:System.Net.DecompressionMethods.Deflate> che <xref:System.Net.DecompressionMethods.GZip> o <xref:System.Net.DecompressionMethods.None>.  [!INCLUDE[net_native](../../../includes/net-native-md.md)] supporta solo <xref:System.Net.DecompressionMethods.Deflate> assieme a <xref:System.Net.DecompressionMethods.GZip>o <xref:System.Net.DecompressionMethods.None>.  Provare a impostare la proprietà <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A> su <xref:System.Net.DecompressionMethods.Deflate> o <xref:System.Net.DecompressionMethods.GZip> da soli comporta l'impostazione automatica su <xref:System.Net.DecompressionMethods.Deflate> e <xref:System.Net.DecompressionMethods.GZip>.  
  
 **Cookie**  
  
 La gestione dei cookie viene eseguita simultaneamente da <xref:System.Net.Http.HttpClient> e WinINet.  I cookie di <xref:System.Net.CookieContainer> vengono combinati con i cookie nella cache dei cookie di WinINet.  La rimozione di un cookie da <xref:System.Net.CookieContainer> impedisce a <xref:System.Net.Http.HttpClient> di inviarlo, ma se è già stato rilevato da WinINet, e i cookie non sono stati eliminati dall'utente, WinINet lo invia.  Non è possibile rimuovere a livello di codice un cookie da WinINet usando le API <xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.HttpClientHandler>o <xref:System.Net.CookieContainer> .  L'impostazione della proprietà <xref:System.Net.Http.HttpClientHandler.UseCookies%2A?displayProperty=nameWithType> su `false` fa solo sì che <xref:System.Net.Http.HttpClient> smetta di inviare cookie; WinINet potrebbe ancora includere i propri cookie nella richiesta.  
  
 **Credenziali**  
  
 In .NET per applicazioni Windows Store, le proprietà <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A?displayProperty=nameWithType> e <xref:System.Net.Http.HttpClientHandler.Credentials%2A?displayProperty=nameWithType> funzionano in maniera indipendente.  Inoltre, la proprietà <xref:System.Net.Http.HttpClientHandler.Credentials%2A> accetta qualsiasi oggetto che implementa l'interfaccia <xref:System.Net.ICredentials> .  In [!INCLUDE[net_native](../../../includes/net-native-md.md)], impostare la proprietà <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A> su `true` fa sì che la proprietà <xref:System.Net.Http.HttpClientHandler.Credentials%2A> diventi `null`.  Inoltre, la proprietà <xref:System.Net.Http.HttpClientHandler.Credentials%2A> può essere impostata solo su `null`, <xref:System.Net.CredentialCache.DefaultCredentials%2A>o un oggetto di tipo <xref:System.Net.NetworkCredential>.  L'assegnazione di qualsiasi altro oggetto <xref:System.Net.ICredentials> , il più popolare dei quali è <xref:System.Net.CredentialCache>, alla proprietà <xref:System.Net.Http.HttpClientHandler.Credentials%2A> genera una <xref:System.PlatformNotSupportedException>.  
  
 **Altre funzionalità non supportate o non configurabili**  
  
 In [!INCLUDE[net_native](../../../includes/net-native-md.md)]:  
  
-   Il valore della proprietà <xref:System.Net.Http.HttpClientHandler.ClientCertificateOptions%2A?displayProperty=nameWithType> è sempre <xref:System.Net.Http.ClientCertificateOption.Automatic>.  In .NET per applicazioni Windows Store, il valore predefinito è <xref:System.Net.Http.ClientCertificateOption.Manual>.  
  
-   La proprietà <xref:System.Net.Http.HttpClientHandler.MaxRequestContentBufferSize%2A?displayProperty=nameWithType> non è configurabile.  
  
-   La proprietà <xref:System.Net.Http.HttpClientHandler.PreAuthenticate%2A?displayProperty=nameWithType> è sempre `true`.  In .NET per applicazioni Windows Store, il valore predefinito è `false`.  
  
-   L'intestazione `SetCookie2` nelle risposte verrà ignorata come obsoleta.  
  
<a name="Interop"></a>   
### <a name="interop-differences"></a>Differenze di interoperabilità  
 **API deprecate**  
  
 Una serie di API usate con minore frequenza per l'interoperabilità con codice gestito è stata deprecata. Quando usate con [!INCLUDE[net_native](../../../includes/net-native-md.md)], queste API possono generare un'eccezione <xref:System.NotImplementedException> o <xref:System.PlatformNotSupportedException> oppure produrre un errore del compilatore. In .NET per applicazioni Windows Store, queste API vengono contrassegnate come obsolete, anche se la chiamata genera un avviso del compilatore invece di un errore del compilatore.  
  
 API deprecate per il marshalling di `VARIANT` :  
  
||  
|-|  
|<xref:System.Runtime.InteropServices.BStrWrapper?displayProperty=nameWithType>|  
|<xref:System.Runtime.InteropServices.CurrencyWrapper?displayProperty=nameWithType>|  
|<xref:System.Runtime.InteropServices.DispatchWrapper?displayProperty=nameWithType>|  
|<xref:System.Runtime.InteropServices.ErrorWrapper?displayProperty=nameWithType>|  
|<xref:System.Runtime.InteropServices.UnknownWrapper?displayProperty=nameWithType>|  
|<xref:System.Runtime.InteropServices.VariantWrapper?displayProperty=nameWithType>|  
|<xref:System.Runtime.InteropServices.UnmanagedType.IDispatch?displayProperty=nameWithType>|  
|<xref:System.Runtime.InteropServices.UnmanagedType.SafeArray?displayProperty=nameWithType>|  
|<xref:System.Runtime.InteropServices.VarEnum?displayProperty=nameWithType>|  
  
 <xref:System.Runtime.InteropServices.UnmanagedType.Struct?displayProperty=nameWithType> è supportato, ma genera un'eccezione in alcuni scenari, ad esempio quando viene usato con [IDispatch](http://msdn.microsoft.com/library/windows/apps/ms221608.aspx) o varianti di byref.  
  
 Le API deprecate per [IDispatch](http://msdn.microsoft.com/library/windows/apps/ms221608.aspx) supportano:  
  
|Tipo|Membro|  
|----------|------------|  
|<xref:System.Runtime.InteropServices.ClassInterfaceType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDispatch>|  
|<xref:System.Runtime.InteropServices.ClassInterfaceType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual>|  
|<xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute?displayProperty=nameWithType>|L'attributo non è supportato.|  
  
 API deprecate per eventi COM classici:  
  
||  
|-|  
|<xref:System.Runtime.InteropServices.ComEventsHelper?displayProperty=nameWithType>|  
|<xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute>|  
  
 API deprecate nell'interfaccia <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType>, che non è supportata in [!INCLUDE[net_native](../../../includes/net-native-md.md)]:  
  
|Tipo|Membro|  
|----------|------------|  
|<xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType>|Tutti i membri.|  
|<xref:System.Runtime.InteropServices.CustomQueryInterfaceMode?displayProperty=nameWithType>|Tutti i membri.|  
|<xref:System.Runtime.InteropServices.CustomQueryInterfaceResult?displayProperty=nameWithType>|Tutti i membri.|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.GetComInterfaceForObject%28System.Object%2CSystem.Type%2CSystem.Runtime.InteropServices.CustomQueryInterfaceMode%29?displayProperty=nameWithType>|  
  
 Altre funzionalità di interoperabilità non supportate:  
  
|Tipo|Membro|  
|----------|------------|  
|<xref:System.Runtime.InteropServices.ICustomAdapter?displayProperty=nameWithType>|Tutti i membri.|  
|<xref:System.Runtime.InteropServices.SafeBuffer?displayProperty=nameWithType>|Tutti i membri.|  
|<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.UnmanagedType.Currency>|  
|<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.UnmanagedType.VBByRefStr>|  
|<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.UnmanagedType.AnsiBStr>|  
|<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.UnmanagedType.AsAny>|  
|<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.UnmanagedType.CustomMarshaler>|  
  
 API di marshalling raramente usate:  
  
|Tipo|Member|  
|----------|------------|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.ReadByte%28System.Object%2CSystem.Int32%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.ReadInt16%28System.Object%2CSystem.Int32%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.ReadInt32%28System.Object%2CSystem.Int32%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.ReadInt64%28System.Object%2CSystem.Int32%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.ReadIntPtr%28System.Object%2CSystem.Int32%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.WriteByte%28System.Object%2CSystem.Int32%2CSystem.Byte%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.WriteInt16%28System.Object%2CSystem.Int32%2CSystem.Int16%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.WriteInt32%28System.Object%2CSystem.Int32%2CSystem.Int32%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.WriteInt64%28System.Object%2CSystem.Int32%2CSystem.Int64%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.WriteIntPtr%28System.Object%2CSystem.Int32%2CSystem.IntPtr%29>|  
  
 **Compatibilità platform invoke e interoperabilità COM**  
  
 La maggior parte dei scenari di platform invoke e interoperabilità COM sono ancora supportati in [!INCLUDE[net_native](../../../includes/net-native-md.md)]. In particolare, sono supportate tutte le API di interoperabilità con Windows Runtime (WinRT) e tutti i marshalling richiesti per Windows Runtime. Ciò include il supporto del marshalling per:  
  
-   Matrici (inclusa <xref:System.Runtime.InteropServices.UnmanagedType.ByValArray?displayProperty=nameWithType>)  
  
-   `BStr`  
  
-   Delegati  
  
-   Stringhe (Unicode, Ansi e HSTRING)  
  
-   Struct (`byref` e `byval`)  
  
-   Unioni  
  
-   Handle Win32  
  
-   Tutti i costrutti di WinRT  
  
-   Supporto parziale per il marshalling dei tipi variant. È supportato quanto segue:  
  
    -   <xref:System.Boolean>  
  
    -   <xref:System.Byte>  
  
    -   <xref:System.Decimal>  
  
    -   <xref:System.Double>  
  
    -   <xref:System.Int16>  
  
    -   <xref:System.Int32>  
  
    -   <xref:System.Int64>  
  
    -   <xref:System.SByte>  
  
    -   <xref:System.Single>  
  
    -   <xref:System.UInt16>  
  
    -   <xref:System.UInt32>  
  
    -   <xref:System.UInt64>  
  
    -   `BStr`  
  
    -   [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509.aspx)  
  
 Tuttavia, [!INCLUDE[net_native](../../../includes/net-native-md.md)] non supporta quanto segue:  
  
-   Utilizzo degli eventi COM classici  
  
-   Implementazione dell'interfaccia <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> su un tipo gestito  
  
-   Implementazione di [IDispatch](http://msdn.microsoft.com/library/windows/apps/ms221608.aspx) interfaccia su un tipo gestito tramite il <xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute?displayProperty=nameWithType> attributo. Notare tuttavia che non è possibile chiamare oggetti COM tramite `IDispatch`e l'oggetto gestito non può implementare `IDispatch`.  
  
 L'uso della reflection per richiamare un metodo platform invoke non è supportato. È possibile aggirare questa limitazione eseguendo il wrapping della chiamata al metodo in un altro metodo e usando la reflection per chiamare invece il wrapper.  
  
<a name="APIs"></a>   
### <a name="other-differences-from-net-apis-for-windows-store-apps"></a>Altre differenze rispetto alle API .NET per app di Windows Store  
 In questa sezione sono elencate le API rimanenti che non sono supportate in [!INCLUDE[net_native](../../../includes/net-native-md.md)]. Il set più grande di API non supportate è rappresentato dalle API di Windows Communication Foundation (WCF).  
  
 **DataAnnotations (System.ComponentModel.DataAnnotations)**  
  
 I tipi negli spazi dei nomi <xref:System.ComponentModel.DataAnnotations> e <xref:System.ComponentModel.DataAnnotations.Schema> non sono supportati in [!INCLUDE[net_native](../../../includes/net-native-md.md)]. Questi includono i seguenti tipi che sono presenti in .NET per applicazioni Windows Store per Windows 8:  
  
||  
|-|  
|<xref:System.ComponentModel.DataAnnotations.AssociationAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.ConcurrencyCheckAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.CustomValidationAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.DataType?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.DataTypeAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.DisplayAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.DisplayColumnAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.DisplayFormatAttribute>|  
|<xref:System.ComponentModel.DataAnnotations.EditableAttribute>|  
|<xref:System.ComponentModel.DataAnnotations.EnumDataTypeAttribute>|  
|<xref:System.ComponentModel.DataAnnotations.FilterUIHintAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.KeyAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.RangeAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.RegularExpressionAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.RequiredAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.StringLengthAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.TimestampAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.UIHintAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.ValidationContext?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.ValidationException?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.ValidationResult?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.Validator?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.Schema.DatabaseGeneratedAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.Schema.DatabaseGeneratedOption?displayProperty=nameWithType>|  
  
 **Visual Basic**  
  
 Visual Basic non è attualmente supportato in [!INCLUDE[net_native](../../../includes/net-native-md.md)]. I seguenti tipi negli spazi dei nomi <xref:Microsoft.VisualBasic> e <xref:Microsoft.VisualBasic.CompilerServices> non sono disponibili in [!INCLUDE[net_native](../../../includes/net-native-md.md)]:  
  
||  
|-|  
|<xref:Microsoft.VisualBasic.CallType?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.Constants?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.HideModuleNameAttribute?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.Strings?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.Conversions?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.DesignerGeneratedAttribute?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.IncompleteInitialization?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.NewLateBinding?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.ObjectFlowControl?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.ObjectFlowControl.ForLoopControl?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.Operators?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.OptionCompareAttribute?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.OptionTextAttribute?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.ProjectData?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.StandardModuleAttribute?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.StaticLocalInitFlag?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.Utils?displayProperty=nameWithType>|  
  
 **Contesto Reflection (spazio dei nomi System.Reflection.Context)**  
  
 La classe <xref:System.Reflection.Context.CustomReflectionContext?displayProperty=nameWithType> non è supportata in [!INCLUDE[net_native](../../../includes/net-native-md.md)].  
  
 **RTC (System.Net.Http.Rtc)**  
  
 La classe <xref:System.Net.Http.RtcRequestFactory?displayProperty=nameWithType> non è supportata in [!INCLUDE[net_native](../../../includes/net-native-md.md)].  
  
 **Windows Communication Foundation (WCF) (System.ServiceModel.\*)**  
  
 I tipi negli [spazi dei nomi System.ServiceModel.*](http://msdn.microsoft.com/library/gg145010.aspx) non sono supportati in [!INCLUDE[net_native](../../../includes/net-native-md.md)]. Sono inclusi i tipi seguenti:  
  
||  
|-|  
|<xref:System.ServiceModel.ActionNotSupportedException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.BasicHttpMessageCredentialType?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.BasicHttpSecurity?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.BasicHttpSecurityMode?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.CallbackBehaviorAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ClientBase%601.BeginOperationDelegate?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ClientBase%601.ChannelBase%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ClientBase%601.EndOperationDelegate?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ClientBase%601.InvokeAsyncCompletedEventArgs?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.CommunicationException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.CommunicationObjectAbortedException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.CommunicationObjectFaultedException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.CommunicationState?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.DataContractFormatAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.DnsEndpointIdentity?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.DuplexChannelFactory%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.DuplexClientBase%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.EndpointAddress?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.EndpointAddressBuilder?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.EndpointIdentity?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.EndpointNotFoundException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.EnvelopeVersion?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ExceptionDetail?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.FaultCode?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.FaultException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.FaultReason?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.FaultReasonText?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.HttpBindingBase?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.HttpClientCredentialType?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.HttpTransportSecurity?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ICommunicationObject?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.IContextChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.IDefaultCommunicationTimeouts?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.IExtensibleObject%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.IExtension%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.IExtensionCollection%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.InvalidMessageContractException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.MessageBodyMemberAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.MessageContractAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.MessageContractMemberAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.MessageCredentialType?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.MessageHeader%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.MessageHeaderException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.MessageParameterAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.MessageSecurityOverTcp?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.MessageSecurityVersion?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.NetHttpBinding?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.NetHttpMessageEncoding?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.NetTcpBinding?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.NetTcpSecurity?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.OperationContext?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.OperationContextScope?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.OperationContractAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.OperationFormatStyle?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ProtocolException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.QuotaExceededException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.SecurityMode?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ServerTooBusyException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ServiceActivationException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ServiceKnownTypeAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.SpnEndpointIdentity?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.TcpClientCredentialType?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.TcpTransportSecurity?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.TransferMode?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.UnknownMessageReceivedEventArgs?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.UpnEndpointIdentity?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.XmlSerializerFormatAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.AddressHeader?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.AddressHeaderCollection?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.AddressingVersion?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.ChannelManagerBase?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.ChannelParameterCollection?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.CommunicationObject?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.CompressionFormat?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.FaultConverter?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.HttpRequestMessageProperty?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.HttpResponseMessageProperty?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.HttpsTransportBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IChannelFactory?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IChannelFactory%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IDuplexChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IDuplexSession?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IDuplexSessionChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IHttpCookieContainerManager?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IInputChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IInputSession?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IInputSessionChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IMessageProperty?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IOutputChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IOutputSession?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IOutputSessionChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IRequestChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IRequestSessionChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.ISession?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.ISessionChannel%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.LocalClientSecuritySettings?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.Message?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageBuffer?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageEncoder?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageEncoderFactory?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageEncodingBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageFault?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageHeader?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageHeaderInfo?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageHeaders?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageProperties?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageState?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageVersion?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.RequestContext?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.SecurityBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.SecurityHeaderLayout?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.TcpConnectionPoolSettings?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.TcpTransportBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.TransportBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.TransportSecurityBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.WebSocketTransportSettings?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.WebSocketTransportUsage?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.ClientCredentials?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.ContractDescription?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.FaultDescription?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.FaultDescriptionCollection?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessageBodyDescription?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessageDescription?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessageDescriptionCollection?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessageDirection?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessageHeaderDescription?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessageHeaderDescriptionCollection?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessagePartDescription?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessagePartDescriptionCollection?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessagePropertyDescription?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessagePropertyDescriptionCollection?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.OperationDescription?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.OperationDescriptionCollection?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.ServiceEndpoint?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Dispatcher.ClientOperation?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Dispatcher.ClientRuntime?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Dispatcher.DispatchOperation?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Dispatcher.DispatchRuntime?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Dispatcher.EndpointDispatcher?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Dispatcher.IClientMessageFormatter?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Dispatcher.IClientOperationSelector?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.BasicSecurityProfileVersion?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.HttpDigestClientCredential?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.MessageSecurityException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.SecureConversationVersion?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.SecurityAccessDeniedException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.SecurityPolicyVersion?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.SecurityVersion?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.TrustVersion?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.UserNamePasswordClientCredential?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.WindowsClientCredential?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.Tokens.SecurityTokenParameters?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.Tokens.SupportingTokenParameters?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.Tokens.UserNameSecurityTokenParameters?displayProperty=nameWithType>|  
  
### <a name="differences-in-serializers"></a>Differenze nei serializzatori  
 Le differenze riportate di seguito riguardano la serializzazione e la deserializzazione con le classi <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>e <xref:System.Xml.Serialization.XmlSerializer> :  
  
-   In [!INCLUDE[net_native](../../../includes/net-native-md.md)], <xref:System.Runtime.Serialization.DataContractSerializer> e <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> non riescono a serializzare o deserializzare una classe derivata che ha un membro della classe di base il cui tipo non è un tipo di serializzazione radice. Ad esempio, nel codice seguente, il tentativo di serializzare o deserializzare `Y` genererà un errore:  
  
     [!code-csharp[ProjectN#10](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat3.cs#10)]  
  
     Il tipo `InnerType` non è noto al serializzatore, perché i membri della classe base non vengono attraversati durante la serializzazione.  
  
-   <xref:System.Runtime.Serialization.DataContractSerializer> e <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> non riescono a serializzare una classe o una struttura che implementa l'interfaccia <xref:System.Collections.Generic.IEnumerable%601> . Ad esempio, i seguenti tipi non riesco a serializzare o deserializzare:  
  
  
  
-   <xref:System.Xml.Serialization.XmlSerializer> non riesce a serializzare il valore dell'oggetto seguente, perché non conoscere il tipo esatto dell'oggetto da serializzare:  
  
  
  
-   <xref:System.Xml.Serialization.XmlSerializer> non riesce a serializzare o deserializzare se il tipo di oggetto serializzato è <xref:System.Xml.XmlQualifiedName>.  
  
-   Tutti i serializzatori (<xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> e <xref:System.Xml.Serialization.XmlSerializer>) non riescono a generare un codice di serializzazione per il tipo <xref:System.Xml.Linq.XElement?displayProperty=nameWithType> o per un tipo che contiene <xref:System.Xml.Linq.XElement>, visualizzando invece gli errori in fase di compilazione.  
  
-   Il funzionamento corretto dei seguenti costruttori dei tipi di serializzazione non è garantito:  
  
    -   <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29?displayProperty=nameWithType>  
  
    -   <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.Runtime.Serialization.DataContractSerializerSettings%29?displayProperty=nameWithType>  
  
    -   <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.String%2CSystem.String%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29?displayProperty=nameWithType>  
  
    -   <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.Xml.XmlDictionaryString%2CSystem.Xml.XmlDictionaryString%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29?displayProperty=nameWithType>  
  
    -   <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor%28System.Type%2CSystem.Runtime.Serialization.Json.DataContractJsonSerializerSettings%29?displayProperty=nameWithType>  
  
    -   <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor%28System.Type%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29?displayProperty=nameWithType>  
  
    -   <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.String%29?displayProperty=nameWithType>  
  
    -   <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Type%5B%5D%29?displayProperty=nameWithType>  
  
    -   <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Xml.Serialization.XmlAttributeOverrides%29?displayProperty=nameWithType>  
  
    -   <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Xml.Serialization.XmlRootAttribute%29?displayProperty=nameWithType>  
  
    -   <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Xml.Serialization.XmlAttributeOverrides%2CSystem.Type%5B%5D%2CSystem.Xml.Serialization.XmlRootAttribute%2CSystem.String%29?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Serialization.XmlSerializer> non riesce a generare il codice per un tipo che ha metodi con uno qualsiasi dei seguenti attributi:  
  
    -   <xref:System.Runtime.Serialization.OnSerializingAttribute>  
  
    -   <xref:System.Runtime.Serialization.OnSerializedAttribute>  
  
    -   <xref:System.Runtime.Serialization.OnDeserializingAttribute>  
  
    -   <xref:System.Runtime.Serialization.OnDeserializedAttribute>  
  
-   <xref:System.Xml.Serialization.XmlSerializer> non soddisfa l'interfaccia di serializzazione personalizzata di <xref:System.Xml.Serialization.IXmlSerializable> . Se si ha una classe che implementa questa interfaccia, <xref:System.Xml.Serialization.XmlSerializer> considera il tipo come un oggetto Plain Old CLR Object (POCO) di CLR e ne serializza solo le proprietà pubbliche.  
  
-   La serializzazione di un oggetto <xref:System.Exception> POCO, come il seguente, non ha esito positivo con <xref:System.Runtime.Serialization.DataContractSerializer> e <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>:  
  
  
  
<a name="VS"></a>   
## <a name="visual-studio-differences"></a>Differenze di Visual Studio  
 **Eccezioni e debug**  
  
 Quando si eseguono applicazioni compilate usando [!INCLUDE[net_native](../../../includes/net-native-md.md)] nel debugger, vengono abilitate le eccezioni first-chance per i seguenti tipi di eccezione:  
  
-   <xref:System.MemberAccessException>  
  
-   <xref:System.TypeAccessException>  
  
 **Creazione di applicazioni**  
  
 Usare gli strumenti di compilazione x86 usati per impostazione predefinita da Visual Studio. Non è consigliabile usare gli strumenti di MSBuild AMD64, disponibili in C:\Program Files (x86)\MSBuild\12.0\bin\amd64, perché possono creare problemi di compilazione.  
  
 **Profiler**  
  
-   Il profiler della CPU di Visual Studio e il profiler della memoria XAML non visualizzano Just My Code correttamente.  
  
-   Il profiler della memoria di XAML non visualizza in modo accurato i dati di heap gestito.  
  
-   Il profiler della CPU non identifica correttamente i moduli e consente di visualizzare i nomi di funzione con prefisso.  
  
 **Progetti di librerie unit test**  
  
 L'abilitazione di [!INCLUDE[net_native](../../../includes/net-native-md.md)] su una libreria unit test per un progetto di app di Windows Store non è supportata e produce la mancata compilazione del progetto.  
  
## <a name="see-also"></a>Vedere anche  
 [Introduzione](../../../docs/framework/net-native/getting-started-with-net-native.md)  
 [Informazioni di riferimento sul file di configurazione delle direttive di runtime (rd.xml)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [Panoramica di App .NET per Windows Store](http://msdn.microsoft.com/library/windows/apps/br230302.aspx)  
 [.NET Framework Support for Windows Store Apps and Windows Runtime](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md) (Supporto di .NET Framework per le app di Windows Store e Windows Runtime)
