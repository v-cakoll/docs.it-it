---
title: Elemento AppContextSwitchOverrides
ms.custom: updateeachrelease
ms.date: 04/18/2019
helpviewer_keywords:
- AppContextSwitchOverrides
- compatibility switches
- configuration switches
- configuration
ms.assetid: 4ce07f47-7ddb-4d91-b067-501bd8b88752
ms.openlocfilehash: 2495ddbc89caf0b72cfc0e6a1647e8f2da291778
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347192"
---
# <a name="appcontextswitchoverrides-element"></a>\<elemento > AppContextSwitchOverrides

Definisce una o più opzioni di compatibilità usate dalla classe <xref:System.AppContext> per fornire un meccanismo di rifiuto esplicito per la nuova funzionalità.

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<runtime >** ](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<AppContextSwitchOverrides>**

## <a name="syntax"></a>Sintassi

```xml
<AppContextSwitchOverrides value="name1=value1[[;name2=value2];...]" />
```

## <a name="attributes-and-elements"></a>Attributi ed elementi
 Le sezioni seguenti descrivono gli attributi, gli elementi figlio e gli elementi padre.

### <a name="attributes"></a>Attributi

|Attributo|Descrizione|
|---------------|-----------------|
|`value`|Attributo obbligatorio.<br /><br /> Definisce uno o più nomi di commutioni e i valori booleani associati.|

### <a name="value-attribute"></a>Attributo value

|Valore|Descrizione|
|-----------|-----------------|
|"nome = valore"|Nome di opzione predefinito insieme al relativo valore (`true` o `false`). Più coppie nome/valore del commutire sono separate da punti e virgola (";"). Per un elenco di nomi di opzioni predefiniti supportati dal .NET Framework, vedere la sezione Osservazioni.|

### <a name="child-elements"></a>Elementi figlio
 nessuna.

### <a name="parent-elements"></a>Elementi padre

|Elemento|Descrizione|
|-------------|-----------------|
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|
|`runtime`|Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.|

## <a name="remarks"></a>Note
 A partire da .NET Framework 4,6, l'elemento `<AppContextSwitchOverrides>` in un file di configurazione consente ai chiamanti di un'API di determinare se l'app può sfruttare le nuove funzionalità o mantenere la compatibilità con le versioni precedenti di una libreria. Se, ad esempio, il comportamento di un'API è cambiato tra due versioni di una libreria, l'elemento `<AppContextSwitchOverrides>` consente ai chiamanti di tale API di rifiutare esplicitamente il nuovo comportamento nelle versioni della libreria che supportano la nuova funzionalità. Per le app che chiamano le API nel .NET Framework, l'elemento `<AppContextSwitchOverrides>` può anche consentire ai chiamanti le cui app sono destinate a una versione precedente del .NET Framework di scegliere una nuova funzionalità se l'app è in esecuzione in una versione del .NET Framework che include tale funzionalità.

 L'attributo `value` dell'elemento `<AppContextSwitchOverrides>` è costituito da una singola stringa costituita da una o più coppie nome/valore delimitate da punti e virgola.  Ogni nome identifica un'opzione di compatibilità e il valore corrispondente è un valore booleano (`true` o `false`) che indica se l'opzione è impostata. Per impostazione predefinita, l'opzione è `false`e le librerie forniscono la nuova funzionalità. Forniscono solo la funzionalità precedente se è impostata l'opzione (ovvero, il valore è `true`). Questo consente alle librerie di fornire un nuovo comportamento per un'API esistente, consentendo ai chiamanti che dipendono dal comportamento precedente di rifiutare esplicitamente la nuova funzionalità.

 Il .NET Framework supporta le opzioni seguenti:

|Nome dell'opzione|Descrizione|Introdotte|
|-----------------|-----------------|----------------|
|`Switch.MS.Internal.`<br/>`DoNotApplyLayoutRoundingToMarginsAndBorderThickness`|Controlla se Windows Presentation Foundation usa un algoritmo legacy per il layout del controllo. Per altre informazioni, vedere [Mitigazione: Layout WPF](../../../migration-guide/mitigation-wpf-layout.md).|.NET Framework 4.6|
|`Switch.MS.Internal.`<br/>`UseSha1AsDefaultHashAlgorithmForDigitalSignatures`|Controlla se l'algoritmo predefinito utilizzato per firmare parti di un pacchetto da PackageDigitalSignatureManager è SHA1 o SHA256.<br>A causa di problemi di conflitto con SHA1, Microsoft consiglia SHA256.|.NET Framework 4.7.1|
|`Switch.System.Activities.`<br/>`UseMD5CryptoServiceProviderForWFDebugger`|Quando è impostato su `false`, consente il debug di progetti di flusso di lavoro basati su XAML con Visual Studio quando FIPS è abilitato. Senza di esso, viene generata un'<xref:System.NullReferenceException> nelle chiamate ai metodi nell'assembly System. Activities.|.NET Framework 4.7|
|`Switch.System.Activities.`<br/>`UseMD5ForWFDebugger`|Controlla se il checksum per un'istanza del flusso di lavoro nel debugger usa MD5 o SHA1. | .NET Framework 4.7|
|`Switch.System.Activities.`<br/>`UseSHA1HashForDebuggerSymbols`|Controlla se l'hashing del checksum del flusso di lavoro usa l'algoritmo SHA1 introdotto come valore predefinito in .NET Framework 4,7 (`true`) o se usa l'algoritmo predefinito SHA256 introdotto come valore predefinito in .NET Framework 4,8 (`false`).<br>A causa di problemi di conflitto con SHA1, Microsoft consiglia SHA256.|.NET Framework 4.8|
|`Switch.System.Diagnostics.`<br/>`IgnorePortablePDBsInStackTraces`|Controlla se le analisi dello stack ottengono quando si usano PDB portatili possono includere informazioni su file di origine e righe. `false` includere le informazioni sulla riga e sul file di origine; in caso contrario, `true`.|.NET Framework 4.7.2|
|`Switch.System.Drawing.`<br/>`DontSupportPngFramesInIcons`|Controlla se il metodo <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> genera un'eccezione quando un oggetto <xref:System.Drawing.Icon> dispone di frame PNG. Per altre informazioni, vedere [Mitigazione: Frame PNG in oggetti icona](../../../migration-guide/mitigation-png-frames-in-icon-objects.md).|.NET Framework 4.6|
|`Switch.System.Drawing.Text.`<br/>`DoNotRemoveGdiFontsResourcesFromFontCollection`|Determina se gli oggetti <xref:System.Drawing.Text.PrivateFontCollection?displayProperty=nameWithType> vengono eliminati correttamente quando vengono aggiunti alla raccolta dal metodo <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)?displayProperty=nameWithType>. `true` per mantenere il comportamento legacy; `false` eliminare tutti gli oggetti carattere privati. |.NET Framework 4.7.2|
|`Switch.System.Drawing.Printing.`<br>`OptimizePrintPreview`|Controlla se le prestazioni dell'<xref:System.Windows.Forms.PrintPreviewDialog> sono ottimizzate per le stampanti di rete. Per ulteriori informazioni, vedere [Cenni preliminari sul controllo PrintPreviewDialog](../../../winforms/controls/printpreviewdialog-control-overview-windows-forms.md).|.NET Framework 4.6|
|`Switch.System.Globalization.EnforceJapaneseEraYearRanges`|Controlla se vengono applicati i controlli dell'intervallo di anno per le ere del calendario giapponese. `true` per applicare i controlli intervallo anno e `false` per disabilitarli (comportamento predefinito). Per ulteriori informazioni, vedere [utilizzo dei calendari](../../../../standard/datetime/working-with-calendars.md).|.NET Framework 4.6|
|`Switch.System.Globalization.EnforceLegacyJapaneseDateParsing`|Controlla se solo "1" viene riconosciuto come primo anno di un'era del calendario giapponese nelle operazioni di analisi. `true` riconoscere solo "1"; `false` per riconoscere "1" o Gannen (comportamento predefinito). Per ulteriori informazioni, vedere [utilizzo dei calendari](../../../../standard/datetime/working-with-calendars.md).|.NET Framework 4.6|
|`Switch.System.Globalization.FormatJapaneseFirstYearAsANumber`|Controlla se il primo anno di un'era del calendario giapponese è rappresentato come "1" o Gannen nelle operazioni di formattazione. `true` formattare il primo anno dell'era come "1"; `false` per formattarlo come Gannen (comportamento predefinito). Per ulteriori informazioni, vedere [utilizzo dei calendari](../../../../standard/datetime/working-with-calendars.md).|.NET Framework 4.6|
|`Switch.System.Globalization.NoAsyncCurrentCulture`|Controlla se le operazioni asincrone non vengono propagate dal contesto del thread chiamante. Per ulteriori informazioni, vedere [CurrentCulture e CurrentUICulture scorrono tra le attività](../../../migration-guide/retargeting/4.5.2-4.6.md#currentculture-and-currentuiculture-flow-across-tasks).|.NET Framework 4.6|
|`Switch.System.IdentityModel.`<br/>`DisableMultipleDNSEntriesInSANCertificate`|Controlla se il metodo di <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> tenta di trovare la corrispondenza con il tipo di attestazione solo con l'ultima voce DNS. Per altre informazioni, vedere [Mitigazione: Metodo X509CertificateClaimSet.FindClaims](../../../migration-guide/mitigation-x509certificateclaimset-findclaims-method.md).|.NET Framework 4.6.1|
|`Switch.System.IdentityModel.`<br/>`EnableCachedEmptyDefaultAuthorizationContext`|Determina se consentire AuthorizationContext. Empty per restituire un oggetto modificabile.|.NET Framework 4.6|
|`Switch.System.IO.BlockLongPaths`|Controlla se i percorsi più lunghi di `MAX_PATH` (260 caratteri) generano una <xref:System.IO.PathTooLongException>. Per ulteriori informazioni, vedere [supporto per percorsi lunghi](../../../migration-guide/retargeting/4.6.1-4.6.2.md#long-path-support).|.NET Framework 4.6.2|
|`Switch.System.IO.Compression.`<br/>`DoNotUseNativeZipLibraryForDecompression`|Controlla se le routine del sistema operativo native vengono usate per la decompressione da parte della classe <xref:System.IO.Compression.DeflateStream>. `false` usare API native; `true` per utilizzare l'implementazione di <xref:System.IO.Compression.DeflateStream>.|.NET Framework 4.7.2|
|`Switch.System.IO.Compression.ZipFile.`<br/>`UseBackslash`|Usa la barra rovesciata ("\\") anziché la barra ("/") come separatore di percorso nella proprietà <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=nameWithType>. Per ulteriori informazioni, vedere [mitigazione: separatore di percorsi ZipArchiveEntry. FullName](../../../migration-guide/mitigation-ziparchiveentry-fullname-path-separator.md).|.NET Framework 4.6.1|
|`Switch.System.IO.Ports.`<br/>`DoNotCatchSerialStreamThreadExceptions`|Controlla se le eccezioni del sistema operativo generate sui thread in background creati con <xref:System.IO.Ports.SerialPort> flussi terminano il processo.|.NET Framework 4.7.1|
|`Switch.System.IO.`<br/>`UseLegacyPathHandling`|Controlla se viene utilizzata la normalizzazione del percorso legacy e se i percorsi URI sono supportati dai metodi <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> e <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType>. Per altre informazioni, vedere [mitigazione: normalizzazione dei percorsi](../../../migration-guide/mitigation-path-normalization.md) e [mitigazione: controlli dei due punti del percorso](../../../migration-guide/mitigation-path-colon-checks.md).|.NET Framework 4.6.2|
|`Switch.System.`<br/>`MemberDescriptorEqualsReturnsFalseIfEquivalent`|Controlla se un test di uguaglianza confronta la proprietà <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=nameWithType> di un oggetto con la proprietà <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=nameWithType> del secondo oggetto. Per ulteriori informazioni, vedere [implementazione non corretta di MemberDescriptor. Equals](../../../migration-guide/retargeting/4.6.1-4.6.2.md#incorrect-implementation-of-memberdescriptorequals).|.NET Framework 4.6.2|
 `Switch.System.Net.`<br/>`DontCheckCertificateEKUs`|Disabilita la convalida dell'identificatore di oggetto (OID) di utilizzo chiavi avanzato (EKU) del certificato. Un'estensione di utilizzo chiavi avanzato (EKU) è una raccolta di identificatori di oggetto (OID) che indica le applicazioni che usano la chiave.|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchSendAuxRecord`|Disabilita l'exploit del browser TLS 1.0 contro la mitigazione SSL/TLS (BEAST) disabilitando l'uso di SCH_SEND_AUX_RECORD.|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchUseStrongCrypto`|Controlla se le classi <xref:System.Net.ServicePointManager?displayProperty=nameWithType> e <xref:System.Net.Security.SslStream?displayProperty=nameWithType> possono usare il protocollo SSL 3,0. Per altre informazioni, vedere [Mitigazione: Protocolli TLS](../../../migration-guide/mitigation-tls-protocols.md).|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSystemDefaultTlsVersions`|Disabilita le versioni di TLS di SystemDefault ripristinando il valore predefinito Tls12, Tls11 e TLS.|.NET Framework 4.7|
|`Switch.System.Net.`<br/>`DontEnableTlsAlerts`|Disabilita gli avvisi lato server di SslStream TLS.|.NET Framework 4.7|
|`Switch.System.Runtime.InteropServices.`<br/>`DoNotMarshalOutByrefSafeArrayOnInvoke`|Controlla se i parametri ByRef SafeArray negli eventi di interoperabilità COM eseguono il marshalling al codice nativo (`false`) o se il marshalling al codice nativo è disabilitato (`true`).|.NET Framework 4.8|
|`Switch.System.Runtime.Serialization.`<br/>`DoNotUseECMAScriptV6EscapeControlCharacter` |Controlla se [DataContractJsonSerializer](xref:System.Runtime.Serialization.Json.DataContractJsonSerializer) serializza alcuni caratteri di controllo in base agli standard ECMAScript V6 e V8. Per altre informazioni, vedere [Mitigazione: Serializzazione dei caratteri di controllo con DataContractJsonSerializer](../../../migration-guide/mitigation-serialization-control-characters.md)| .NET Framework 4.7 |
|`Switch.System.Runtime.Serialization.`<br/>`DoNotUseTimeZoneInfo`|Controlla se il <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> supporta più regolazioni o solo una singola regolazione per un fuso orario. Se `true`, usa il tipo di <xref:System.TimeZoneInfo> per serializzare e deserializzare i dati di data e ora; in caso contrario, viene utilizzato il tipo <xref:System.TimeZone>, che non supporta più regole di regolazione.|.NET Framework 4.6.2|
|`Switch.System.Runtime.Serialization.UseNewMaxArraySize`|Controlla se <xref:System.Runtime.Serialization.ObjectManager?displayProperty=nameWithType> utilizza una dimensione della matrice maggiore durante la serializzazione e la deserializzazione dell'oggetto. Impostare questa opzione su `true` per migliorare le prestazioni della serializzazione e della deserializzazione di oggetti grafici di grandi dimensioni in base ai tipi, ad esempio <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>. |.NET Framework 4.7.2|
|`Switch.System.Security.ClaimsIdentity.`<br/>`SetActorAsReferenceWhenCopyingClaimsIdentity`|Controlla se il costruttore <xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29?displayProperty=nameWithType> imposta la proprietà di <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=nameWithType> del nuovo oggetto con un riferimento a un oggetto esistente. Per altre informazioni, vedere [Mitigazione: Costruttore ClaimsIdentity](../../../migration-guide/retargeting/4.6.1-4.6.2.md).|.NET Framework 4.6.2|
|`Switch.System.Security.Cryptography.`<br/>`AesCryptoServiceProvider.DontCorrectlyResetDecryptor`|Controlla se il tentativo di riutilizzare un decrittografia <xref:System.Security.Cryptography.AesCryptoServiceProvider> genera un'<xref:System.Security.Cryptography.CryptographicException>. Per ulteriori informazioni, vedere [AesCryptoServiceProvider Decryptor fornisce una trasformazione riutilizzabile](../../../migration-guide/retargeting/4.6.1-4.6.2.md#aescryptoserviceprovider-decryptor-provides-a-reusable-transform).|.NET Framework 4.6.2|
|`Switch.System.Security.Cryptography.`<br/>`DoNotAddrOfCspParentWindowHandle`|Controlla se il valore della proprietà [CspParameters. ParentWindowHandle](xref:System.Security.Cryptography.CspParameters.ParentWindowHandle) è un elemento [IntPtr](xref:System.IntPtr) che rappresenta la posizione di memoria di un handle di finestra o se è un handle di finestra (HWND). Per altre informazioni, vedere [Mitigazione: CspParameters.ParentWindowHandle prevede un HWND](../../../migration-guide/retargeting/4.6.2-4.7.md#cspparametersparentwindowhandle-now-expects-hwnd-value). |.NET Framework 4.7|
|`Switch.System.Security.Cryptography.`<br/>`UseLegacyFipsThrow`|Controlla se l'uso di classi di crittografia gestite in modalità FIPS genera un <xref:System.Security.Cryptography.CryptographicException> (`true`) o si basa sull'implementazione delle librerie di sistema (`false`).|.NET Framework 4.8|
|`Switch.System.Security.Cryptography.Pkcs.`<br/>`UseInsecureHashAlgorithms`|Determina se l'impostazione predefinita per alcune operazioni SignedCMS è SHA1 o SHA256.<br>A causa di problemi di conflitto con SHA1, Microsoft consiglia SHA256.|.NET Framework 4.7.1|
|`Switch.System.Security.Cryptography.X509Certificates.`<br/>`ECDsaCertificateExtensions.UseLegacyPublicKeyReader`|Controlla se il metodo <xref:System.Security.Cryptography.X509Certificates.ECDsaCertificateExtensions.GetECDsaPublicKey%2A?displayProperty=nameWithType> gestisce correttamente tutte le curve denominate supportate dal sistema operativo (`false`) o Ripristina il comportamento legacy.|.NET Framework 4.8|
|`Switch.System.Security.Cryptography.Xml.`<br/>`UseInsecureHashAlgorithms`|Determina se l'impostazione predefinita per alcune operazioni SignedXML è SHA1 o SHA256.<br>A causa di problemi di conflitto con SHA1, Microsoft consiglia SHA256.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`AllowUnsignedToHeader`|Determina se la modalità di sicurezza `TransportWithMessageCredential` consente messaggi con un'intestazione "to" senza segno. Si tratta di un'opzione di consenso esplicito. Per ulteriori informazioni, vedere [modifiche di runtime nel .NET Framework 4.6.1](../../../migration-guide/runtime/4.5.2-4.6.1.md#windows-communication-foundation-wcf).|.NET Framework 4.6.1|
|`Switch.System.ServiceModel.`<br/>`DisableAddressHeaderCollectionValidation`>|Controlla se il costruttore <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> genera un'<xref:System.ArgumentException> se uno degli elementi è `null`.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br />`DisableCngCertificates`|Determina se il tentativo di usare i certificati X509 con un provider di archiviazione chiavi CSG genera un'eccezione. Per ulteriori informazioni, vedere la pagina relativa alla [sicurezza del trasporto WCF supporta i certificati archiviati tramite CNG](../../../migration-guide/retargeting/4.6.1-4.6.2.md#wcf-transport-security-supports-certificates-stored-using-cng).|.NET Framework 4.6.1|
|`Switch.System.ServiceModel.`<br/>`DisableExplicitConnectionCloseHeader`|Quando si usa il trasporto HTTP con un servizio indipendente, impostando questo valore su `true` fa in modo che WCF ignori un'applicazione che aggiunge l'intestazione `Connection: close` alle intestazioni della risposta per una richiesta. Impostando questo valore su `false` è possibile aggiungere l'intestazione `Connection: close` alle intestazioni della risposta, con conseguente chiusura del socket della richiesta dopo l'invio di una risposta.|.NET Framework 4.6|
|`Switch.System.ServiceModel.`<br/>`DisableOperationContextAsyncFlow`|Gestisce i deadlock derivanti dalla restrizione delle istanze di un servizio rientrante a un singolo thread di esecuzione alla volta.|.NET Framework 4.6.2|
|`Switch.System.ServiceModel.`<br/>`DisableUsingServicePointManagerSecurityProtocols`|Insieme a `Switch.System.Net.DontEnableSchUseStrongCrypto`, determina se la sicurezza dei messaggi WCF utilizza TLS 1,1 e TLS 1,2.|.NET Framework 4.7 |
|`Switch.System.ServiceModel.`<br/>`DontEnableSystemDefaultTlsVersions`|Il valore `false` imposta la configurazione predefinita per consentire al sistema operativo di scegliere il protocollo. Il valore `true` imposta il valore predefinito sul protocollo più alto disponibile. (Disponibile anche nel ramo di manutenzione delle versioni precedenti del Framework)|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`UseSha1InMsmqEncryptionAlgorithm`|Determina se l'algoritmo di firma del messaggio predefinito per i messaggi MSMQ in WCF è SHA1 o SHA256.<br>A causa di problemi di conflitto con SHA1, Microsoft consiglia SHA256.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`UseSha1InPipeConnectionGetHashAlgorithm`|Controlla se WCF utilizza un hash SHA1 o SHA256 per generare nomi casuali per le named pipe.<br>A causa di problemi di conflitto con SHA1, Microsoft consiglia SHA256.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.Internals`<br/>`IncludeNullExceptionMessageInETWTrace`|Determina se generare un'eccezione [NullReferenceException](xref:System.NullReferenceException) quando il messaggio di eccezione è null.|.NET Framework 4.7|
|`Switch.System.ServiceProcess.`<br/>`DontThrowExceptionsOnStart`|Controlla se le eccezioni generate all'avvio del servizio vengono propagate al chiamante del metodo <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType>.|.NET Framework 4.7.1|
|`Switch.System.Threading.UseNetCoreTimer`|Controlla se <xref:System.Threading.Timer> istanze di sfruttano i vantaggi offerti dai miglioramenti delle prestazioni per gli ambienti a scalabilità elevata. Se `true`, i miglioramenti delle prestazioni sono abilitati. Se `false` (valore predefinito), sono disabilitati.|.NET Framework 4.8|
|`Switch.System.Uri.`<br/>`DontEnableStrictRFC3986ReservedCharacterSets`|Determina se alcuni caratteri codificati in percentuale a volte decodificati sono ora codificati in modo coerente. Se `true`, vengono decodificati. in caso contrario, `false`.|.NET Framework 4.7.2|
|`Switch.System.Uri.`<br/>`DontKeepUnicodeBidiFormattingCharacters`|Determina la gestione dei caratteri bidirezionali Unicode negli URI. `true` per rimuoverli dagli URI; `false` per mantenere e codificare in percentuale i componenti.|.NET Framework 4.7.2|
|`Switch.System.Windows.Controls.Grid.`<br/>`StarDefinitionsCanExceedAvailableSpace` |Determina se Windows Presentation Foundation applica un algoritmo precedente (`true`) o un nuovo algoritmo (`false`) nell'allocazione dello spazio alle colonne \*. Per altre informazioni, vedere [Mitigazione: Allocazione dello spazio di controllo della griglia alle colonne a stella](../../../migration-guide/retargeting/4.6.2-4.7.md#wpf-grid-allocation-of-space-to-star-columns). |.NET Framework 4.7 |
|`Switch.System.Windows.Controls.TabControl.`<br/>`SelectionPropertiesCanLagBehindSelectionChangedEvent`|Controlla se un selettore o un controllo struttura a schede Aggiorna sempre il valore della proprietà del valore selezionato prima di generare l'evento di modifica della selezione.|.NET Framework 4.7.1|
|`Switch.System.Windows.Controls.Text.`<br/>`UseAdornerForTextboxSelectionRendering`|Determina se è disponibile il rendering della selezione non basata su Adorner per la <xref:System.Windows.Controls.TextBox> e <xref:System.Windows.Controls.PasswordBox> i controlli per impedire il testo nascosto (`false`) o se il rendering del testo viene eseguito solo nel livello dello strumento decorativo (`true`).|.NET Framework 4.7.2|
|`Switch.System.Windows.Data.Binding.`<br/>`IListIndexerHidesCustomIndexer`|Controlla se gli indicizzatori IList personalizzati vengono usati in modo errato (`true`) o correttamente (`false`) dalla classe <xref:System.Windows.Data.Binding?displayProperty=nameWithType>.|.NET Framework 4.8|
|`Switch.System.Windows.DoNotScaleForDpiChanges`|Determina se le modifiche DPI si verificano in un sistema (valore `false`) o in base al monitoraggio (valore di `true`).|.NET Framework 4.6.2|
|`Switch.System.Windows.`<br/>`DoNotUsePresentationDpiCapabilityTier2OrGreater`|Controlla se i miglioramenti apportati al ridimensionamento dei controlli in un <xref:System.Windows.Interop.HwndHost?displayProperty=nameWithType> quando WPF viene eseguito in modalità di rilevamento per monitoraggio sono disabilitati (`true`) o abilitati (`false`).|.NET Framework 4.8|
|`Switch.System.Windows.Forms.`<br/>`DomainUpDown.UseLegacyScrolling`|Determina se lo sviluppatore deve gestire in modo specifico l'azione <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> quando è presente il testo del controllo. `true` per gestire l'azione <xref:System.Windows.Forms.DomainUpDown.UpButton>; `false` per sincronizzare correttamente le azioni <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> e <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType>.|.NET Framework 4.7.2|
|`Switch.System.Windows.Forms.`<br />`DontSupportReentrantFilterMessage`|Esclude il codice che consente a un'implementazione di <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> personalizzata di filtrare in modo sicuro i messaggi senza generare un'eccezione quando viene chiamato il metodo <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType>. Per altre informazioni, vedere [Mitigazione: Implementazioni IMessageFilter.PreFilterMessage personalizzate](../../../migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).|.NET Framework 4.6.1|
|`Switch.System.Windows.Forms.`<br/>`UseLegacyContextMenuStripSourceControlValue`|Determina se la proprietà <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> restituisce il controllo del codice sorgente quando l'utente apre il menu da un controllo <xref:System.Windows.Forms.ToolStripMenuItem> annidato. `true` per restituire `null`, il comportamento legacy; `false` per restituire il controllo del codice sorgente.|.NET Framework 4.7.2|
|`Switch.System.Windows.Forms.UseLegacyToolTipDisplay`|Controlla se il supporto della chiamata della descrizione comando è disabilitato (`true`) o abilitato (`false`). L'abilitazione del supporto della chiamata della descrizione comando richiede inoltre funzionalità di accessibilità legacy definite da `Switch.UseLegacyAccessibilityFeatures`, `Switch.UseLegacyAccessibilityFeatures.2`e `Switch.UseLegacyAccessibilityFeatures.3` tutte disabilitate (impostate su `false`).|.NET Framework 4.8|
|`Switch.System.Windows.Input.Stylus.`<br/>`EnablePointerSupport`|Determina se uno stack di tocco/stilo basato su `WM_POINTER`facoltativo è abilitato nelle applicazioni WPF. Per altre informazioni, vedere [mitigazione: supporto per tocco e stilo basato su puntatore](../../../migration-guide/mitigation-pointer-based-touch-and-stylus-support.md)|.NET Framework 4.7|
|`Switch.System.Windows.Markup.`<br/>`DoNotUseSha256ForMarkupCompilerChecksumAlgorithm`|Determina se l'algoritmo hash predefinito utilizzato per i checksum è SHA256 (`false`) o SHA1 (`true`).<br>A causa di problemi di conflitto con SHA1, Microsoft consiglia SHA256.|.NET Framework 4.7.2|
|`Switch.System.Windows.Media.ImageSourceConverter.`<br/>`OverrideExceptionWithNullReferenceException`|Controlla se viene generata un'eccezione [NullReferenceException](xref:System.NullReferenceException) legacy anziché l'eccezione che indica più specificamente la provocazione dell'eccezione, ad esempio [DirectoryNotFoundException](xref:System.IO.DirectoryNotFoundException) o [FileNotFoundException](xref:System.IO.FileNotFoundException). È destinata all'utilizzo da parte del codice che dipende dalla gestione dell' [eccezione NullReferenceException](xref:System.NullReferenceException). | .NET Framework 4.7 |
|`Switch.System.Workflow.ComponentModel.`<br/>`UseLegacyHashForXomlFileChecksum`|Controlla se l'hashing di checksum dei file XOML nelle compilazioni di progetti flusso di lavoro usa l'algoritmo MD5 (`true`) o se usa l'algoritmo SHA256 introdotto come valore predefinito in .NET Framework 4,8.<br>A causa di problemi di collisione con MD5, Microsoft consiglia SHA256.|.NET Framework 4.8|
|`Switch.System.Workflow.Runtime.`<br/>`UseLegacyHashForSqlTrackingCacheKey`|Controlla se l'hashing di checksum da SqlTrackingService usa l'algoritmo MD5 (`true`) per le stringhe memorizzate nella cache o se usa l'algoritmo SHA256 introdotto come valore predefinito in .NET Framework 4,8.<br>A causa di problemi di collisione con MD5, Microsoft consiglia SHA256.|.NET Framework 4.8|
|`Switch.System.Workflow.Runtime.`<br/>`UseLegacyHashForWorkflowDefinitionDispenserCacheKey`|Controlla se l'hashing di checksum da parte del runtime del flusso di lavoro usa l'algoritmo MD5 (`true`) per le definizioni del flusso di lavoro memorizzato nella cache o se usa l'algoritmo SHA256 introdotto come valore predefinito in .NET Framework 4,8.<br>A causa di problemi di collisione con MD5, Microsoft consiglia SHA256.|.NET Framework 4.8|
|`Switch.UseLegacyAccessibilityFeatures`|Controlla se le funzionalità di accessibilità disponibili a partire da .NET Framework 4.7.1 sono abilitate o disabilitate. | .NET Framework 4.7.1 |
|`Switch.UseLegacyAccessibilityFeatures.2`|Controlla se le funzionalità di accessibilità disponibili in .NET Framework 4.7.2 sono abilitate (`false`) o disabilitate (`true`). Se `true`, è necessario `true` anche `Switch.UseLegacyAccessibilityFeatures` per abilitare le funzionalità di accessibilità .NET Framework 4.7.1.|.NET Framework 4.7.2|
|`Switch.UseLegacyAccessibilityFeatures.3`|Controlla se le funzionalità di accessibilità introdotte in .NET Framework 4,8 sono abilitate (`false`) o disabilitate (`true`). Se `true`, è necessario `true`anche `Switch.UseLegacyAccessibilityFeatures` e `Switch.UseLegacyAccessibilityFeatures.2`.|.NET Framework 4.8|
|`Switch.UseLegacyToolTipDisplay`|Controlla se le descrizioni comandi vengono visualizzate quando un utente posiziona il cursore del mouse su un controllo WPF (`true`) o se viene visualizzato sullo stato attivo della tastiera e tramite il tasto di scelta rapida (`false`, il comportamento predefinito). Per le applicazioni in esecuzione in .NET Framework 4,8 ma destinate a versioni precedenti del .NET Framework, l'abilitazione del supporto per lo stato attivo e il tasto di scelta rapida richiede che `Switch.UseLegacyAccessibilityFeatures`, `Switch.UseLegacyAccessibilityFeatures.2`e `Switch.UseLegacyAccessibilityFeatures.3` siano impostate su `false`.|.NET Framework 4.8|
|`Switch.System.Xml.`<br />`IgnoreEmptyKeySequences`|Controlla se le sequenze di chiavi vuote nelle chiavi composte vengono ignorate dalla convalida dello schema XSD. Per ulteriori informazioni, vedere [mitigazione: convalida di XML Schema](../../../migration-guide/mitigation-xml-schema-validation.md).|.NET Framework 4.6|

> [!NOTE]
> Invece di aggiungere un elemento `AppContextSwitchOverrides` a un file di configurazione dell'applicazione, è anche possibile impostare le opzioni a livello di codice chiamando il C#metodo di `static` (in) o `Shared` (in Visual Basic) <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>.

 Gli sviluppatori di librerie possono anche definire opzioni personalizzate per consentire ai chiamanti di rifiutare esplicitamente le funzionalità modificate introdotte nelle versioni successive delle librerie. Per altre informazioni, vedere la classe <xref:System.AppContext>.

## <a name="switches-in-aspnet-applications"></a>Opzioni nelle applicazioni ASP.NET

È possibile configurare un'applicazione ASP.NET per l'utilizzo delle impostazioni di compatibilità aggiungendo un [\<aggiungere >](../appsettings/add-element-for-appsettings.md) elemento alla sezione [\<appSettings >](../appsettings/index.md) del file Web. config.

Nell'esempio seguente viene usato l'elemento `<add>` per aggiungere due impostazioni alla sezione `<appSettings>` di un file Web. config:

```xml
<appSettings>
  <add key="AppContext.SetSwitch:Switch.System.Globalization.NoAsyncCurrentCulture" value="true" />
  <add key="AppContext.SetSwitch:Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets" value="true" />
</appSettings>
```

## <a name="example"></a>Esempio

 Nell'esempio seguente viene usato l'elemento `AppContextSwitchOverrides` per definire una singola opzione di compatibilità dell'applicazione, `Switch.System.Globalization.NoAsyncCurrentCulture`, che impedisce la propagazione delle impostazioni cultura tra i thread nelle chiamate asincrone al metodo.

```xml
<configuration>
   <runtime>
      <AppContextSwitchOverrides value="Switch.System.Globalization.NoAsyncCurrentCulture=true" />
   </runtime>
</configuration>
```

 Nell'esempio seguente viene usato l'elemento `AppContextSwitchOverrides` per definire due opzioni di compatibilità delle applicazioni, `Switch.System.Globalization.NoAsyncCurrentCulture` e `Switch.System.IO.BlockLongPaths`. Un punto e virgola separa le due coppie nome/valore.

```xml
<configuration>
    <runtime>
       <AppContextSwitchOverrides
          value="Switch.System.Globalization.NoAsyncCurrentCulture=true;Switch.System.IO.BlockLongPaths=true" />
    </runtime>
</configuration>
```

## <a name="see-also"></a>Vedere anche

- <xref:System.AppContext?displayProperty=nameWithType>
- [\<elemento > Runtime](runtime-element.md)
- [Elemento \<configuration>](../configuration-element.md)
