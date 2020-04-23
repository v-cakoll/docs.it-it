---
title: AppContextSwitchOverrides Elemento
ms.custom: updateeachrelease
ms.date: 04/18/2019
helpviewer_keywords:
- AppContextSwitchOverrides
- compatibility switches
- configuration switches
- configuration
ms.assetid: 4ce07f47-7ddb-4d91-b067-501bd8b88752
ms.openlocfilehash: 8d5cd73bb9393533cb669581420e24297cb5ff71
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102931"
---
# <a name="appcontextswitchoverrides-element"></a>\<AppContextSwitchOverrides>elemento

Definisce una o più opzioni di compatibilità usate dalla classe <xref:System.AppContext> per fornire un meccanismo di rifiuto esplicito per la nuova funzionalità.

[**\<>di configurazione**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>di runtime**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<AppContextSwitchOverrides>**

## <a name="syntax"></a>Sintassi

```xml
<AppContextSwitchOverrides value="name1=value1[[;name2=value2];...]" />
```

## <a name="attributes-and-elements"></a>Attributi ed elementi
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.

### <a name="attributes"></a>Attributes

|Attributo|Descrizione|
|---------------|-----------------|
|`value`|Attributo obbligatorio.<br /><br /> Definisce uno o più nomi di switch e i relativi valori booleani associati.|

### <a name="value-attribute"></a>Attributo value

|valore|Descrizione|
|-----------|-----------------|
|"nome/valore"|Un nome di switch predefinito`true` insieme `false`al relativo valore ( o ). Più coppie nome/valore dell'opzione sono separate da punto e virgola (";"). Per un elenco dei nomi di opzioni predefiniti supportati da .NET Framework, vedere la sezione Osservazioni.|

### <a name="child-elements"></a>Elementi figlio
 No.

### <a name="parent-elements"></a>Elementi padre

|Elemento|Descrizione|
|-------------|-----------------|
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|
|`runtime`|Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.|

## <a name="remarks"></a>Osservazioni
 A partire da .NET Framework `<AppContextSwitchOverrides>` 4.6, l'elemento in un file di configurazione consente ai chiamanti di un'API di determinare se l'app può sfruttare le nuove funzionalità o mantenere la compatibilità con le versioni precedenti di una libreria. Ad esempio, se il comportamento di un'API è `<AppContextSwitchOverrides>` cambiato tra due versioni di una libreria, l'elemento consente ai chiamanti di tale API di rifiutare esplicitamente il nuovo comportamento nelle versioni della libreria che supportano la nuova funzionalità. Per le app che chiamano API in `<AppContextSwitchOverrides>` .NET Framework, l'elemento può anche consentire ai chiamanti le cui app sono destinate a una versione precedente di .NET Framework di scegliere una nuova funzionalità se l'app è in esecuzione su una versione di .NET Framework che include tale funzionalità.

 `value` L'attributo `<AppContextSwitchOverrides>` dell'elemento è costituito da una singola stringa costituita da una o più coppie nome/valore delimitate da punto e virgola.  Ogni nome identifica un'opzione di compatibilità`true` e `false`il valore corrispondente è un valore booleano ( o ) che indica se l'opzione è impostata. Per impostazione predefinita, l'opzione è `false`, e le librerie forniscono la nuova funzionalità. Forniscono la funzionalità precedente solo se è impostata `true`l'opzione, ovvero il relativo valore è . Ciò consente alle librerie di fornire un nuovo comportamento per un'API esistente, consentendo ai chiamanti che dipendono dal comportamento precedente di rifiutare esplicitamente la nuova funzionalità.

.NET Framework supporta le opzioni seguenti:

|Nome switch|Descrizione|Presentare|
|-----------------|-----------------|----------------|
|`Switch.MS.Internal.`<br/>`DoNotApplyLayoutRoundingToMarginsAndBorderThickness`|Controlla se Windows Presentation Foundation utilizza un algoritmo legacy per il layout dei controlli. Per altre informazioni, vedere [Mitigazione: Layout WPF](../../../migration-guide/mitigation-wpf-layout.md).|.NET Framework 4.6|
|`Switch.MS.Internal.`<br/>`UseSha1AsDefaultHashAlgorithmForDigitalSignatures`|Controlla se l'algoritmo predefinito utilizzato per firmare parti di un pacchetto da PackageDigitalSignatureManager è SHA1 o SHA256.<br>A causa di problemi di conflitto con SHA1, Microsoft consiglia SHA256.|.NET Framework 4.7.1|
|`Switch.System.Activities.`<br/>`UseMD5CryptoServiceProviderForWFDebugger`|Se impostato `false`su , consente il debug di progetti flusso di lavoro basati su XAML con Visual Studio quando FIPS è abilitato. Senza di <xref:System.NullReferenceException> essa, viene generata un viene generata nelle chiamate ai metodi nell'assembly System.Activities.|.NET Framework 4.7|
|`Switch.System.Activities.`<br/>`UseMD5ForWFDebugger`|Controlla se il checksum per un'istanza del flusso di lavoro nel debugger utilizza MD5 o SHA1. | .NET Framework 4.7|
|`Switch.System.Activities.`<br/>`UseSHA1HashForDebuggerSymbols`|Controlla se l'hash checksum del flusso di lavoro utilizza l'algoritmo`true`SHA1 introdotto come predefinito in .NET Framework 4.7 (`false`) o se utilizza l'algoritmo SHA256 predefinito introdotto come predefinito in .NET Framework 4.8 ( ).<br>A causa di problemi di conflitto con SHA1, Microsoft consiglia SHA256.|.NET Framework 4.8|
|`Switch.System.Diagnostics.`<br/>`IgnorePortablePDBsInStackTraces`|Controlla se le tracce dello stack vengono ottenute quando si utilizzano file PDB portabili possono includere informazioni sul file di origine e sulla riga. `false`per includere informazioni sul file di origine e sulla riga; in `true`caso contrario, .|.NET Framework 4.7.2|
|`Switch.System.Drawing.`<br/>`DontSupportPngFramesInIcons`|Controlla se <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> il metodo genera <xref:System.Drawing.Icon> un'eccezione quando un oggetto dispone di frame PNG. Per altre informazioni, vedere [Mitigazione: Frame PNG in oggetti icona](../../../migration-guide/mitigation-png-frames-in-icon-objects.md).|.NET Framework 4.6|
|`Switch.System.Drawing.Text.`<br/>`DoNotRemoveGdiFontsResourcesFromFontCollection`|Determina <xref:System.Drawing.Text.PrivateFontCollection?displayProperty=nameWithType> se gli oggetti vengono eliminati correttamente <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)?displayProperty=nameWithType> quando vengono aggiunti alla raccolta dal metodo . `true`per mantenere il comportamento legacy; `false` per eliminare tutti gli oggetti font privati. |.NET Framework 4.7.2|
|`Switch.System.Drawing.Printing.`<br>`OptimizePrintPreview`|Controlla se le <xref:System.Windows.Forms.PrintPreviewDialog> prestazioni del file sono ottimizzate per le stampanti di rete. Per ulteriori informazioni, vedere [Cenni preliminari sul controllo PrintPreviewDialog](../../../winforms/controls/printpreviewdialog-control-overview-windows-forms.md).|.NET Framework 4.6|
|`Switch.System.Globalization.EnforceJapaneseEraYearRanges`|Controlla se vengono applicati i controlli dell'intervallo dell'anno per le ere del calendario giapponese. `true`per applicare i controlli `false` dell'intervallo degli anni e disabilitarli (comportamento predefinito). Per ulteriori informazioni, vedere [Utilizzo dei calendari](../../../../standard/datetime/working-with-calendars.md).|.NET Framework 4.6|
|`Switch.System.Globalization.EnforceLegacyJapaneseDateParsing`|Controlla se solo "1" viene riconosciuto come primo anno di un'era del calendario giapponese nelle operazioni di analisi. `true`riconoscere solo "1"; `false` riconoscere "1" o Gannen (comportamento predefinito). Per ulteriori informazioni, vedere [Utilizzo dei calendari](../../../../standard/datetime/working-with-calendars.md).|.NET Framework 4.6|
|`Switch.System.Globalization.FormatJapaneseFirstYearAsANumber`|Controlla se il primo anno di un'era del calendario giapponese è rappresentato come "1" o Gannen nelle operazioni di formattazione. `true`per formattare il primo anno dell'era come "1"; `false` per formattarlo come Gannen (comportamento predefinito). Per ulteriori informazioni, vedere [Utilizzo dei calendari](../../../../standard/datetime/working-with-calendars.md).|.NET Framework 4.6|
|`Switch.System.Globalization.NoAsyncCurrentCulture`|Controlla se le operazioni asincrone non scorrono dal contesto del thread chiamante. Per ulteriori informazioni, vedere [CurrentCulture e CurrentUICulture tra le attività](../../../migration-guide/retargeting/4.5.2-4.6.md#currentculture-and-currentuiculture-flow-across-tasks).|.NET Framework 4.6|
|`Switch.System.IdentityModel.`<br/>`DisableMultipleDNSEntriesInSANCertificate`|Controlla se <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> il metodo tenta di associare il tipo di attestazione solo con l'ultima voce DNS. Per altre informazioni, vedere [Mitigazione: Metodo X509CertificateClaimSet.FindClaims](../../../migration-guide/mitigation-x509certificateclaimset-findclaims-method.md).|.NET Framework 4.6.1|
|`Switch.System.IdentityModel.`<br/>`EnableCachedEmptyDefaultAuthorizationContext`|Controlla se consentire a AuthorizationContext.Empty di restituire un oggetto modificabile.|.NET Framework 4.6|
|`Switch.System.IO.BlockLongPaths`|Controlla se i `MAX_PATH` percorsi più lunghi <xref:System.IO.PathTooLongException>di (260 caratteri) generano un ' Per ulteriori informazioni, vedere [Supporto di percorsi lunghi](../../../migration-guide/retargeting/4.6.1-4.6.2.md#long-path-support).|.NET Framework 4.6.2|
|`Switch.System.IO.Compression.`<br/>`DoNotUseNativeZipLibraryForDecompression`|Controlla se le routine OS native vengono <xref:System.IO.Compression.DeflateStream> utilizzate per la decompressione dalla classe. `false`per utilizzare le API native; `true` per utilizzare <xref:System.IO.Compression.DeflateStream> l'implementazione.|.NET Framework 4.7.2|
|`Switch.System.IO.Compression.ZipFile.`<br/>`UseBackslash`|Utilizza la barra\\rovesciata (" ") anziché la barra <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=nameWithType> ("/") come separatore di percorso nella proprietà. Per ulteriori informazioni, vedere [Mitigazione: Separatore percorso nomecompleto..FullName](../../../migration-guide/mitigation-ziparchiveentry-fullname-path-separator.md).|.NET Framework 4.6.1|
|`Switch.System.IO.Ports.`<br/>`DoNotCatchSerialStreamThreadExceptions`|Controlla se le eccezioni del sistema operativo <xref:System.IO.Ports.SerialPort> generate nei thread in background creati con flussi terminano il processo.|.NET Framework 4.7.1|
|`Switch.System.IO.`<br/>`UseLegacyPathHandling`|Controlla se viene utilizzata la normalizzazione dei <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> percorsi legacy e i percorsi URI sono supportati dai metodi e <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> . Per ulteriori informazioni, vedere [Mitigazione: normalizzazione](../../../migration-guide/mitigation-path-normalization.md) e [attenuazione del percorso: controlli del colon](../../../migration-guide/mitigation-path-colon-checks.md)del percorso .|.NET Framework 4.6.2|
|`Switch.System.`<br/>`MemberDescriptorEqualsReturnsFalseIfEquivalent`|Controlla se un test di <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=nameWithType> uguaglianza confronta <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=nameWithType> la proprietà di un oggetto con la proprietà del secondo oggetto. Per ulteriori informazioni, vedere [Implementazione non corretta di MemberDescriptor.Equals](../../../migration-guide/retargeting/4.6.1-4.6.2.md#incorrect-implementation-of-memberdescriptorequals).|.NET Framework 4.6.2|
 `Switch.System.Net.`<br/>`DontCheckCertificateEKUs`|Disabilita la convalida dell'identificatore di oggetto (OID) dell'utilizzo chiavi avanzato del certificato. Un'estensione di utilizzo chiavi avanzato (EKU) è una raccolta di identificatori di oggetto (OID) che indica le applicazioni che usano la chiave.|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchSendAuxRecord`|Disabilita l'attenuazione TLS1.0 Browser Exploit Against SSL/TLS (BEAST) disabilitando l'uso di SCH_SEND_AUX_RECORD.|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchUseStrongCrypto`|Controlla se <xref:System.Net.ServicePointManager?displayProperty=nameWithType> <xref:System.Net.Security.SslStream?displayProperty=nameWithType> le classi e possono utilizzare il protocollo SSL 3.0. Per altre informazioni, vedere [Mitigazione: Protocolli TLS](../../../migration-guide/mitigation-tls-protocols.md).|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSystemDefaultTlsVersions`|Disabilita SystemDefault tls versioni ripristinare un valore predefinito di Tls12, Tls11, Tls.|.NET Framework 4.7|
|`Switch.System.Net.`<br/>`DontEnableTlsAlerts`|Disabilita gli avvisi lato server TLS SslStream.|.NET Framework 4.7|
|`Switch.System.Runtime.InteropServices.`<br/>`DoNotMarshalOutByrefSafeArrayOnInvoke`|Controlla se i parametri ByRef SafeArray sugli eventi`false`di interoperabilità COM eseguono il`true`marshalling al codice nativo ( ) o se il marshalling al codice nativo è disabilitato ( ).|.NET Framework 4.8|
|`Switch.System.Runtime.Serialization.`<br/>`DoNotUseECMAScriptV6EscapeControlCharacter` |Controlla se [DataContractJsonSerializer](xref:System.Runtime.Serialization.Json.DataContractJsonSerializer) serializza alcuni caratteri di controllo in base agli standard ECMAScript V6 e V8. Per altre informazioni, vedere [Mitigazione: Serializzazione dei caratteri di controllo con DataContractJsonSerializer](../../../migration-guide/mitigation-serialization-control-characters.md)| .NET Framework 4.7 |
|`Switch.System.Runtime.Serialization.`<br/>`DoNotUseTimeZoneInfo`|Controlla se <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> supporta più regolazioni o solo una singola regolazione per un fuso orario. Se `true`, utilizza <xref:System.TimeZoneInfo> il tipo per serializzare e deserializzare i dati di data e ora; in caso contrario, viene utilizzato il <xref:System.TimeZone> tipo, che non supporta più regole di regolazione.|.NET Framework 4.6.2|
|`Switch.System.Runtime.Serialization.UseNewMaxArraySize`|Controlla <xref:System.Runtime.Serialization.ObjectManager?displayProperty=nameWithType> se utilizza una dimensione della matrice maggiore durante la serializzazione e la deserializzazione degli oggetti. Impostare questa `true` opzione su per migliorare le prestazioni di serializzazione <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>e deserializzazione di oggetti grafici di grandi dimensioni in base a tipi quali . |.NET Framework 4.7.2|
|`Switch.System.Security.ClaimsIdentity.`<br/>`SetActorAsReferenceWhenCopyingClaimsIdentity`|Controlla se <xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29> il costruttore imposta <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=nameWithType> la proprietà del nuovo oggetto con un riferimento all'oggetto esistente. Per altre informazioni, vedere [Mitigazione: Costruttore ClaimsIdentity](../../../migration-guide/retargeting/4.6.1-4.6.2.md).|.NET Framework 4.6.2|
|`Switch.System.Security.Cryptography.`<br/>`AesCryptoServiceProvider.DontCorrectlyResetDecryptor`|Controlla se il tentativo <xref:System.Security.Cryptography.AesCryptoServiceProvider> di riutilizzare <xref:System.Security.Cryptography.CryptographicException>un decryptor genera un'eccezione . Per ulteriori informazioni, vedere [Decrittografia AesCryptoServiceProvider fornisce una trasformazione riutilizzabile.](../../../migration-guide/retargeting/4.6.1-4.6.2.md#aescryptoserviceprovider-decryptor-provides-a-reusable-transform)|.NET Framework 4.6.2|
|`Switch.System.Security.Cryptography.`<br/>`DoNotAddrOfCspParentWindowHandle`|Controlla se il valore della [proprietà CspParameters.ParentWindowHandle](xref:System.Security.Cryptography.CspParameters.ParentWindowHandle) è un [IntPtr](xref:System.IntPtr) che rappresenta la posizione di memoria di un handle di finestra o se è un handle di finestra (un HWND). Per altre informazioni, vedere [Mitigazione: CspParameters.ParentWindowHandle prevede un HWND](../../../migration-guide/retargeting/4.6.2-4.7.md#cspparametersparentwindowhandle-now-expects-hwnd-value). |.NET Framework 4.7|
|`Switch.System.Security.Cryptography.`<br/>`UseLegacyFipsThrow`|Controlla se l'utilizzo di classi di crittografia <xref:System.Security.Cryptography.CryptographicException> gestite in modalità FIPS genera un (`true`) o si basa sull'implementazione delle librerie di sistema ( ).`false`|.NET Framework 4.8|
|`Switch.System.Security.Cryptography.Pkcs.`<br/>`UseInsecureHashAlgorithms`|Determina se l'impostazione predefinita per alcune operazioni SignedCMS è SHA1 o SHA256.<br>A causa di problemi di conflitto con SHA1, Microsoft consiglia SHA256.|.NET Framework 4.7.1|
|`Switch.System.Security.Cryptography.X509Certificates.`<br/>`ECDsaCertificateExtensions.UseLegacyPublicKeyReader`|Controlla se <xref:System.Security.Cryptography.X509Certificates.ECDsaCertificateExtensions.GetECDsaPublicKey%2A?displayProperty=nameWithType> il metodo gestisce correttamente tutte`false`le curve denominate supportate dal sistema operativo ( ) o ripristina il comportamento legacy.|.NET Framework 4.8|
|`Switch.System.Security.Cryptography.Xml.`<br/>`UseInsecureHashAlgorithms`|Determina se l'impostazione predefinita per alcune operazioni SignedXML è SHA1 o SHA256.<br>A causa di problemi di conflitto con SHA1, Microsoft consiglia SHA256.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`AllowUnsignedToHeader`|Determina se `TransportWithMessageCredential` la modalità di sicurezza consente i messaggi con un'intestazione "a" non firmata. Si tratta di un interruttore di consenso esplicito. Per ulteriori informazioni, vedere Modifiche di [runtime in .NET Framework 4.6.1](../../../migration-guide/runtime/4.5.2-4.6.1.md#windows-communication-foundation-wcf).|.NET Framework 4.6.1|
|`Switch.System.ServiceModel.`<br/>`DisableAddressHeaderCollectionValidation`>|Controlla se <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> il costruttore genera un <xref:System.ArgumentException> `null`if uno degli elementi è .|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br />`DisableCngCertificates`|Determina se il tentativo di utilizzare certificati X509 con un provider di archiviazione chiavi CSG genera un'eccezione. Per altre informazioni, vedere [Sicurezza del trasporto WCF supporta i certificati archiviati tramite CNG](../../../migration-guide/retargeting/4.6.1-4.6.2.md#wcf-transport-security-supports-certificates-stored-using-cng).|.NET Framework 4.6.1|
|`Switch.System.ServiceModel.`<br/>`DisableExplicitConnectionCloseHeader`|Quando si usa il trasporto HTTP con un servizio `true` self-hosted, l'impostazione di questo valore in modo che WCF ignori un'applicazione che aggiunge l'intestazione `Connection: close` alle intestazioni di risposta per una richiesta. L'impostazione `false` di `Connection: close` questo valore su consente di aggiungere l'intestazione alle intestazioni di risposta, che comporta la chiusura del socket di richiesta dopo l'invio di una risposta.|.NET Framework 4.6|
|`Switch.System.ServiceModel.`<br/>`DisableOperationContextAsyncFlow`|Gestisce i deadlock che derivano dalla limitazione delle istanze di un servizio rientrante a un singolo thread di esecuzione alla volta.|.NET Framework 4.6.2|
|`Switch.System.ServiceModel.`<br/>`DisableUsingServicePointManagerSecurityProtocols`|Insieme `Switch.System.Net.DontEnableSchUseStrongCrypto`a , determina se la sicurezza dei messaggi WCF utilizza TLS 1.1 e TLS 1.2.|.NET Framework 4.7 |
|`Switch.System.ServiceModel.`<br/>`DontEnableSystemDefaultTlsVersions`|Il valore `false` di imposta la configurazione predefinita per consentire al sistema operativo di scegliere il protocollo. Il valore `true` di imposta il valore predefinito sul protocollo più alto disponibile. (Disponibile anche nel ramo di manutenzione delle versioni precedenti del framework)|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`UseSha1InMsmqEncryptionAlgorithm`|Determina se l'algoritmo di firma dei messaggi predefinito per i messaggi MSMQ in WCF è SHA1 o SHA256.<br>A causa di problemi di conflitto con SHA1, Microsoft consiglia SHA256.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`UseSha1InPipeConnectionGetHashAlgorithm`|Controlla se WCF utilizza un SHA1 o un hash SHA256 per generare nomi casuali per named pipe.<br>A causa di problemi di conflitto con SHA1, Microsoft consiglia SHA256.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.Internals`<br/>`IncludeNullExceptionMessageInETWTrace`|Controlla se generare [un'eccezione NullReferenceException](xref:System.NullReferenceException) quando il messaggio di eccezione è null.|.NET Framework 4.7|
|`Switch.System.ServiceProcess.`<br/>`DontThrowExceptionsOnStart`|Controlla se le eccezioni generate all'avvio del <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType> servizio vengono propagate al chiamante del metodo.|.NET Framework 4.7.1|
|`Switch.System.Threading.UseNetCoreTimer`|Controlla <xref:System.Threading.Timer> se le istanze sfruttano i miglioramenti delle prestazioni per gli ambienti con scalabilità elevata. Se `true`, i miglioramenti delle prestazioni sono abilitati; se `false` (il valore predefinito), sono disabilitati.|.NET Framework 4.8|
|`Switch.System.Uri.`<br/>`DontEnableStrictRFC3986ReservedCharacterSets`|Determina se alcuni caratteri con codifica percentuale che a volte sono stati decodificati vengono ora codificati in modo coerente. Se `true`, vengono decodificati; in `false`caso contrario, .|.NET Framework 4.7.2|
|`Switch.System.Uri.`<br/>`DontKeepUnicodeBidiFormattingCharacters`|Determina la gestione dei caratteri bidirezionali Unicode negli URI. `true`per rimuoverli dagli URI; `false` per conservarli e codificarli percento.|.NET Framework 4.7.2|
|`Switch.System.Windows.Controls.Grid.`<br/>`StarDefinitionsCanExceedAvailableSpace` |Determina se Windows Presentation Foundation`true`applica un algoritmo`false`precedente ( ) \*o un nuovo algoritmo ( ) nell'allocazione dello spazio a -colonne. Per altre informazioni, vedere [Mitigazione: Allocazione dello spazio di controllo della griglia alle colonne a stella](../../../migration-guide/retargeting/4.6.2-4.7.md#wpf-grid-allocation-of-space-to-star-columns). |.NET Framework 4.7 |
|`Switch.System.Windows.Controls.TabControl.`<br/>`SelectionPropertiesCanLagBehindSelectionChangedEvent`|Controlla se un selettore o un controllo struttura a schede aggiorna sempre il valore della proprietà del valore selezionata prima di generare l'evento di selezione modificato.|.NET Framework 4.7.1|
|`Switch.System.Windows.Controls.Text.`<br/>`UseAdornerForTextboxSelectionRendering`|Determina se il rendering della selezione non <xref:System.Windows.Controls.TextBox> basato su Adorner è disponibile per i controlli e <xref:System.Windows.Controls.PasswordBox> per impedire il testo occluso (`false`) o se viene eseguito il rendering del testo solo nel livello Adorner (`true`).|.NET Framework 4.7.2|
|`Switch.System.Windows.Data.Binding.`<br/>`IListIndexerHidesCustomIndexer`|Controlla se gli indicizzatori IList`true`personalizzati vengono`false`utilizzati <xref:System.Windows.Data.Binding?displayProperty=nameWithType> in modo non corretto ( ) o correttamente ( ) dalla classe .|.NET Framework 4.8|
|`Switch.System.Windows.DoNotScaleForDpiChanges`|Determina se le modifiche DPI si verificano `false`in base al sistema (valore di ) o per monitor (valore di `true`).|.NET Framework 4.6.2|
|`Switch.System.Windows.`<br/>`DoNotUsePresentationDpiCapabilityTier2OrGreater`|Controlla se i miglioramenti apportati <xref:System.Windows.Interop.HwndHost?displayProperty=nameWithType> al ridimensionamento dei controlli in un`true`oggetto in`false`cui WPFWPF viene eseguito in modalità di monitoraggio per monitor sono disabilitati ( ) o abilitati ( ).|.NET Framework 4.8|
|`Switch.System.Windows.Forms.`<br/>`DomainUpDown.UseLegacyScrolling`|Determina se lo sviluppatore <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> deve gestire in modo speciale l'azione quando è presente il testo del controllo. `true`per gestire <xref:System.Windows.Forms.DomainUpDown.UpButton> l'azione; `false` per <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> le <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> azioni e per essere correttamente sincronizzati.|.NET Framework 4.7.2|
|`Switch.System.Windows.Forms.`<br />`DontSupportReentrantFilterMessage`|Disattiva il codice che consente <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> a un'implementazione personalizzata di <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> filtrare in modo sicuro i messaggi senza generare un'eccezione quando viene chiamato il metodo. Per altre informazioni, vedere [Mitigazione: Implementazioni IMessageFilter.PreFilterMessage personalizzate](../../../migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).|.NET Framework 4.6.1|
|`Switch.System.Windows.Forms.`<br/>`UseLegacyContextMenuStripSourceControlValue`|Determina se <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> la proprietà restituisce il controllo del <xref:System.Windows.Forms.ToolStripMenuItem> codice sorgente quando l'utente apre il menu da un controllo annidato. `true`per `null`restituire , il comportamento legacy; `false` per restituire il controllo del codice sorgente.|.NET Framework 4.7.2|
|`Switch.System.Windows.Forms.UseLegacyToolTipDisplay`|Controlla se il supporto per`true`la chiamata`false`della descrizione comandi è disabilitato ( ) o abilitato ( ). L'abilitazione del supporto per la `Switch.UseLegacyAccessibilityFeatures` `Switch.UseLegacyAccessibilityFeatures.2`chiamata `Switch.UseLegacyAccessibilityFeatures.3` delle descrizioni comandi `false`richiede inoltre funzionalità di accessibilità legacy definite da , e tutte disabilitate (impostate su ).|.NET Framework 4.8|
|`Switch.System.Windows.Input.Stylus.`<br/>`EnablePointerSupport`|Determina se `WM_POINTER`uno stack tocco/stilo basato su facoltativo è abilitato nelle applicazioni WPFWPF. Per altre informazioni, vedere [Mitigazione: supporto di tocco e stilo basato su puntatoreFor more information, see Mitigation: Pointer-based Touch and Stylus Support](../../../migration-guide/mitigation-pointer-based-touch-and-stylus-support.md)|.NET Framework 4.7|
|`Switch.System.Windows.Markup.`<br/>`DoNotUseSha256ForMarkupCompilerChecksumAlgorithm`|Determina se l'algoritmo hash predefinito utilizzato per i`false`checksum è`true`SHA256 ( ) o SHA1 ( ).<br>A causa di problemi di conflitto con SHA1, Microsoft consiglia SHA256.|.NET Framework 4.7.2|
|`Switch.System.Windows.Media.ImageSourceConverter.`<br/>`OverrideExceptionWithNullReferenceException`|Controlla se viene generata un'eccezione [NullReferenceException](xref:System.NullReferenceException) legacy anziché l'eccezione che indica in modo più specifico la causa dell'eccezione, ad esempio [Un'eccezione DirectoryNotFoundException](xref:System.IO.DirectoryNotFoundException) o [fileNotFoundException](xref:System.IO.FileNotFoundException). È destinato all'utilizzo da parte di codice che dipende dalla gestione di [NullReferenceException](xref:System.NullReferenceException). | .NET Framework 4.7 |
|`Switch.System.Workflow.ComponentModel.`<br/>`UseLegacyHashForXomlFileChecksum`|Controlla se l'hashing di checksum dei file XOML nelle`true`compilazioni di progetto per flussi di lavoro utilizza l'algoritmo MD5 ( ) o se utilizzano l'algoritmo SHA256 introdotto come predefinito in .NET Framework 4.8.<br>A causa di problemi di collisione con MD5, Microsoft consiglia SHA256.|.NET Framework 4.8|
|`Switch.System.Workflow.Runtime.`<br/>`UseLegacyHashForSqlTrackingCacheKey`|Controlla se l'hashing del checksum da parte`true`di SqlTrackingService utilizza l'algoritmo MD5 ( ) per le stringhe memorizzate nella cache o se utilizza l'algoritmo SHA256 introdotto come predefinito in .NET Framework 4.8.<br>A causa di problemi di collisione con MD5, Microsoft consiglia SHA256.|.NET Framework 4.8|
|`Switch.System.Workflow.Runtime.`<br/>`UseLegacyHashForWorkflowDefinitionDispenserCacheKey`|Controlla se l'hashing del checksum da parte`true`del runtime del flusso di lavoro utilizza l'algoritmo MD5 ( ) per le definizioni del flusso di lavoro memorizzate nella cache o se utilizza l'algoritmo SHA256 introdotto come predefinito in .NET Framework 4.8.<br>A causa di problemi di collisione con MD5, Microsoft consiglia SHA256.|.NET Framework 4.8|
|`Switch.UseLegacyAccessibilityFeatures`|Controlla se le funzionalità di accessibilità disponibili a partire da .NET Framework 4.7.1 sono abilitate o disabilitate. | .NET Framework 4.7.1 |
|`Switch.UseLegacyAccessibilityFeatures.2`|Controlla se le funzionalità di accessibilità disponibili in .NET Framework 4.7.2 sono abilitate (`false`) o disabilitate (`true`). Se `true` `Switch.UseLegacyAccessibilityFeatures` , è `true` necessario essere necessario abilitare le funzionalità di accessibilità di .NET Framework 4.7.1.|.NET Framework 4.7.2|
|`Switch.UseLegacyAccessibilityFeatures.3`|Controlla se le funzionalità di accessibilità introdotte`false`in .NET`true`Framework 4.8 sono abilitate ( ) o disabilitate ( ). Se `true` `Switch.UseLegacyAccessibilityFeatures` , `Switch.UseLegacyAccessibilityFeatures.2` e `true`deve anche essere .|.NET Framework 4.8|
|`Switch.UseLegacyToolTipDisplay`|Controlla se le descrizioni comandi vengono visualizzate quando un utente`true`passa il cursore del mouse su un controllo`false`WPF ( ) o se vengono visualizzate sia sullo stato attivo della tastiera che tramite il tasto di scelta rapida ( , il comportamento predefinito). Per le applicazioni in esecuzione in .NET Framework 4.8 ma destinate a versioni `Switch.UseLegacyAccessibilityFeatures`precedenti `Switch.UseLegacyAccessibilityFeatures.2`di `Switch.UseLegacyAccessibilityFeatures.3` .NET `false`Framework, l'abilitazione dello stato attivo della tastiera e del supporto dei tasti di scelta rapida richiede che , e tutti siano impostati su .|.NET Framework 4.8|
|`Switch.System.Xml.`<br />`IgnoreEmptyKeySequences`|Controlla se le sequenze di chiavi vuote nelle chiavi composte vengono ignorate dalla convalida dello schema XSD. Per ulteriori informazioni, vedere [Mitigazione: convalida XML Schema](../../../migration-guide/mitigation-xml-schema-validation.md).|.NET Framework 4.6|

> [!NOTE]
> Invece di `AppContextSwitchOverrides` aggiungere un elemento a un file di configurazione dell'applicazione, è anche possibile impostare le opzioni a livello di codice chiamando il `static` (in C ) o `Shared` (in Visual Basic) <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> metodo.

 Gli sviluppatori di librerie possono anche definire opzioni personalizzate per consentire ai chiamanti di rifiutare esplicitamente le funzionalità modificate introdotte nelle versioni successive delle librerie. Per altre informazioni, vedere la classe <xref:System.AppContext>.

## <a name="switches-in-aspnet-apps"></a>Opzioni nelle app ASP.NET

È possibile configurare un'applicazione ASP.NET [ \<](../appsettings/add-element-for-appsettings.md) per l'utilizzo delle impostazioni di compatibilità aggiungendo un elemento Aggiungi>alla sezione [ \<appSettings>](../appsettings/index.md) del file web.config.

Nell'esempio seguente `<add>` viene utilizzato l'elemento per aggiungere due impostazioni alla `<appSettings>` sezione di un file web.config:

```xml
<appSettings>
  <add key="AppContext.SetSwitch:Switch.System.Globalization.NoAsyncCurrentCulture" value="true" />
  <add key="AppContext.SetSwitch:Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets" value="true" />
</appSettings>
```

## <a name="example"></a>Esempio

 Nell'esempio seguente `AppContextSwitchOverrides` viene utilizzato l'elemento `Switch.System.Globalization.NoAsyncCurrentCulture`per definire una singola opzione di compatibilità dell'applicazione, , che impedisce il flusso delle impostazioni cultura tra i thread nelle chiamate asincrone al metodo.

```xml
<configuration>
   <runtime>
      <AppContextSwitchOverrides value="Switch.System.Globalization.NoAsyncCurrentCulture=true" />
   </runtime>
</configuration>
```

 Nell'esempio riportato di seguito viene utilizzato l'elemento `AppContextSwitchOverrides` per definire due opzioni di compatibilità delle applicazioni `Switch.System.Globalization.NoAsyncCurrentCulture` e `Switch.System.IO.BlockLongPaths`. Un punto e virgola separa le due coppie nome/valore.

```xml
<configuration>
    <runtime>
       <AppContextSwitchOverrides
          value="Switch.System.Globalization.NoAsyncCurrentCulture=true;Switch.System.IO.BlockLongPaths=true" />
    </runtime>
</configuration>
```

## <a name="see-also"></a>Vedere anche

- [Ridurre i nuovi comportamenti in .NET Framework 4.6 e versioni successive](../../../migration-guide/mitigations.md)
- <xref:System.AppContext?displayProperty=nameWithType>
- [\<Elemento> di runtime](runtime-element.md)
- [\<Elemento> configurazione](../configuration-element.md)
