---
title: <AppContextSwitchOverrides> Elemento
ms.custom: updateeachrelease
ms.date: 04/18/2019
helpviewer_keywords:
- AppContextSwitchOverrides
- compatibility switches
- configuration switches
- configuration
ms.assetid: 4ce07f47-7ddb-4d91-b067-501bd8b88752
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5a71277c6e5183f855ef07a6fc3a20e29b06998f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920917"
---
# <a name="appcontextswitchoverrides-element"></a>\<Elemento > AppContextSwitchOverrides
Definisce una o più opzioni di compatibilità usate dalla classe <xref:System.AppContext> per fornire un meccanismo di rifiuto esplicito per la nuova funzionalità.  
  
 \<configuration>  
 \<runtime>  
\<AppContextSwitchOverrides>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<AppContextSwitchOverrides value="name1=value1[[;name2=value2];...]" />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`value`|Attributo obbligatorio.<br /><br /> Definisce uno o più nomi di commutioni e i valori booleani associati.|  
  
### <a name="value-attribute"></a>Attributo value  
  
|Value|Descrizione|  
|-----------|-----------------|  
|"nome = valore"|Nome di opzione predefinito insieme al relativo valore (`true` o `false`). Più coppie nome/valore del commutire sono separate da punti e virgola (";"). Per un elenco di nomi di opzioni predefiniti supportati dal .NET Framework, vedere la sezione Osservazioni.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.|  
  
## <a name="remarks"></a>Note  
 A partire da .NET Framework 4,6, l' `<AppContextSwitchOverrides>` elemento in un file di configurazione consente ai chiamanti di un'API di determinare se l'app può sfruttare le nuove funzionalità o mantenere la compatibilità con le versioni precedenti di una libreria. Se, ad esempio, il comportamento di un'API è cambiato tra due versioni di una libreria, `<AppContextSwitchOverrides>` l'elemento consente ai chiamanti di tale API di rifiutare esplicitamente il nuovo comportamento nelle versioni della libreria che supportano la nuova funzionalità. Per le app che chiamano le API nel .NET Framework, `<AppContextSwitchOverrides>` l'elemento può anche consentire ai chiamanti le cui app sono destinate a una versione precedente del .NET Framework per acconsentire esplicitamente alla nuova funzionalità se l'app è in esecuzione in una versione del .NET Framework che include funzionalità.  
  
 L' `value` attributo`<AppContextSwitchOverrides>` dell'elemento è costituito da una singola stringa costituita da una o più coppie nome/valore delimitate da punti e virgola.  Ogni nome identifica un'opzione di compatibilità e il valore corrispondente è un valore booleano `false`(`true` o) che indica se l'opzione è impostata. Per impostazione predefinita, l'opzione `false`è e le librerie forniscono la nuova funzionalità. Forniscono solo la funzionalità precedente se è impostata l'opzione (ovvero il valore è `true`). Questo consente alle librerie di fornire un nuovo comportamento per un'API esistente, consentendo ai chiamanti che dipendono dal comportamento precedente di rifiutare esplicitamente la nuova funzionalità.  
  
 Il .NET Framework supporta le opzioni seguenti:  
  
|Nome dell'opzione|Descrizione|Introdotte|  
|-----------------|-----------------|----------------|  
|`Switch.MS.Internal.`<br/>`DoNotApplyLayoutRoundingToMarginsAndBorderThickness`|Controlla se Windows Presentation Foundation usa un algoritmo legacy per il layout del controllo. Per altre informazioni, vedere [Mitigazione: Layout](../../../migration-guide/mitigation-wpf-layout.md)WPF.|.NET Framework 4.6|  
|`Switch.MS.Internal.`<br/>`UseSha1AsDefaultHashAlgorithmForDigitalSignatures`|Controlla se l'algoritmo predefinito utilizzato per firmare parti di un pacchetto da PackageDigitalSignatureManager è SHA1 o SHA256.<br>A causa di problemi di conflitto con SHA1, Microsoft consiglia SHA256.|.NET Framework 4.7.1|
|`Switch.System.Activities.`<br/>`UseMD5CryptoServiceProviderForWFDebugger`|Quando è impostato `false`su, consente il debug di progetti di flusso di lavoro basati su XAML con Visual Studio quando FIPS è abilitato. Senza di esso, <xref:System.NullReferenceException> viene generata un'eccezione nelle chiamate ai metodi nell'assembly System. Activities.|.NET Framework 4.7|
|`Switch.System.Activities.`<br/>`UseMD5ForWFDebugger`|Controlla se il checksum per un'istanza del flusso di lavoro nel debugger usa MD5 o SHA1. | .NET Framework 4.7|
|`Switch.System.Activities.`<br/>`UseSHA1HashForDebuggerSymbols`|Controlla se l'hashing del checksum del flusso di lavoro usa l'algoritmo SHA1 introdotto come valore predefinito`true`in .NET Framework 4,7 () o se usa l'algoritmo predefinito SHA256 introdotto come valore predefinito in .NET Framework`false`4,8 ().<br>A causa di problemi di conflitto con SHA1, Microsoft consiglia SHA256.|.NET Framework 4.8|
|`Switch.System.Diagnostics.`<br/>`IgnorePortablePDBsInStackTraces`|Controlla se le analisi dello stack ottengono quando si usano PDB portatili possono includere informazioni su file di origine e righe. `false`per includere le informazioni su file di origine e riga; in caso `true`contrario,.|.NET Framework 4.7.2|
|`Switch.System.Drawing.`<br/>`DontSupportPngFramesInIcons`|Controlla se il <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> metodo genera un'eccezione quando un <xref:System.Drawing.Icon> oggetto presenta frame PNG. Per altre informazioni, vedere [Mitigazione: Frame PNG negli oggetti](../../../migration-guide/mitigation-png-frames-in-icon-objects.md)icona.|.NET Framework 4.6|
|`Switch.System.Drawing.Text.`<br/>`DoNotRemoveGdiFontsResourcesFromFontCollection`|Determina se <xref:System.Drawing.Text.PrivateFontCollection?displayProperty=nameWithType> gli oggetti vengono eliminati correttamente quando vengono aggiunti alla raccolta <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)?displayProperty=nameWithType> dal metodo. `true`per mantenere il comportamento legacy; `false` per eliminare tutti gli oggetti carattere privati. |.NET Framework 4.7.2|
|`Switch.System.Drawing.Printing.`<br>`OptimizePrintPreview`|Controlla se le prestazioni di <xref:System.Windows.Forms.PrintPreviewDialog> sono ottimizzate per le stampanti di rete. Per ulteriori informazioni, vedere [Cenni preliminari sul controllo PrintPreviewDialog](../../../winforms/controls/printpreviewdialog-control-overview-windows-forms.md).|.NET Framework 4.6|
|`Switch.System.Globalization.EnforceJapaneseEraYearRanges`|Controlla se vengono applicati i controlli dell'intervallo di anno per le ere del calendario giapponese. `true`per applicare i controlli di intervallo anno `false` e per disabilitarli (comportamento predefinito). Per ulteriori informazioni, vedere [utilizzo](../../../../standard/datetime/working-with-calendars.md)dei calendari.|.NET Framework 4.6|
|`Switch.System.Globalization.EnforceLegacyJapaneseDateParsing`|Controlla se solo "1" viene riconosciuto come primo anno di un'era del calendario giapponese nelle operazioni di analisi. `true`per riconoscere solo "1"; `false` per riconoscere "1" o Gannen (comportamento predefinito). Per ulteriori informazioni, vedere [utilizzo](../../../../standard/datetime/working-with-calendars.md)dei calendari.|.NET Framework 4.6| 
|`Switch.System.Globalization.FormatJapaneseFirstYearAsANumber`|Controlla se il primo anno di un'era del calendario giapponese è rappresentato come "1" o Gannen nelle operazioni di formattazione. `true`per formattare il primo anno dell'era come "1"; `false` per formattarlo come Gannen (comportamento predefinito). Per ulteriori informazioni, vedere [utilizzo](../../../../standard/datetime/working-with-calendars.md)dei calendari.|.NET Framework 4.6|
|`Switch.System.Globalization.NoAsyncCurrentCulture`|Controlla se le operazioni asincrone non vengono propagate dal contesto del thread chiamante. Per ulteriori informazioni, vedere [CurrentCulture e CurrentUICulture scorrono tra le attività](../../../migration-guide/retargeting/4.5.2-4.6.md#currentculture-and-currentuiculture-flow-across-tasks).|.NET Framework 4.6|  
|`Switch.System.IdentityModel.`<br/>`DisableMultipleDNSEntriesInSANCertificate`|Controlla se il <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> metodo tenta di trovare la corrispondenza con il tipo di attestazione solo con l'ultima voce DNS. Per altre informazioni, vedere [Mitigazione: Metodo](../../../migration-guide/mitigation-x509certificateclaimset-findclaims-method.md)X509CertificateClaimSet. FindClaims.|.NET Framework 4.6.1|  
|`Switch.System.IdentityModel.`<br/>`EnableCachedEmptyDefaultAuthorizationContext`|Determina se consentire AuthorizationContext. Empty per restituire un oggetto modificabile.|.NET Framework 4.6|  
|`Switch.System.IO.BlockLongPaths`|Controlla se i percorsi più `MAX_PATH` lunghi di (260 caratteri) <xref:System.IO.PathTooLongException>generano un'eccezione. Per ulteriori informazioni, vedere [supporto per percorsi lunghi](../../../migration-guide/retargeting/4.6.1-4.6.2.md#long-path-support).|.NET Framework 4.6.2|  
|`Switch.System.IO.Compression.`<br/>`DoNotUseNativeZipLibraryForDecompression`|Controlla se le routine del sistema operativo native vengono usate per la decompressione da parte della <xref:System.IO.Compression.DeflateStream> classe. `false`per usare le API native; per utilizzare l' <xref:System.IO.Compression.DeflateStream> implementazione di. `true`|.NET Framework 4.7.2|
|`Switch.System.IO.Compression.ZipFile.`<br/>`UseBackslash`|Usa la barra rovesciata\\("") anziché la barra ("/") come separatore <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=nameWithType> di percorso nella proprietà. Per ulteriori informazioni, vedere [mitigazione: Separatore](../../../migration-guide/mitigation-ziparchiveentry-fullname-path-separator.md)di percorso ZipArchiveEntry. FullName.|.NET Framework 4.6.1|  
|`Switch.System.IO.Ports.`<br/>`DoNotCatchSerialStreamThreadExceptions`|Controlla se le eccezioni del sistema operativo generate sui thread in background <xref:System.IO.Ports.SerialPort> creati con i flussi terminano il processo.|.NET Framework 4.7.1| 
|`Switch.System.IO.`<br/>`UseLegacyPathHandling`|Controlla se viene utilizzata la normalizzazione del percorso legacy e se i <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> percorsi URI sono supportati dai metodi e. <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> Per altre informazioni, vedere [Mitigazione: Normalizzazione](../../../migration-guide/mitigation-path-normalization.md) e [mitigazione dei percorsi: Controlli](../../../migration-guide/mitigation-path-colon-checks.md)di due punti del percorso.|.NET Framework 4.6.2|
|`Switch.System.`<br/>`MemberDescriptorEqualsReturnsFalseIfEquivalent`|Controlla se un test di uguaglianza confronta la <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=nameWithType> proprietà di un oggetto con la <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=nameWithType> proprietà del secondo oggetto. Per ulteriori informazioni, vedere [implementazione non corretta di MemberDescriptor. Equals](../../../migration-guide/retargeting/4.6.1-4.6.2.md#incorrect-implementation-of-memberdescriptorequals).|.NET Framework 4.6.2|  
 `Switch.System.Net.`<br/>`DontCheckCertificateEKUs`|Disabilita la convalida dell'identificatore di oggetto (OID) di utilizzo chiavi avanzato (EKU) del certificato. Un'estensione di utilizzo chiavi avanzato (EKU) è una raccolta di identificatori di oggetto (OID) che indica le applicazioni che usano la chiave.|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchSendAuxRecord`|Disabilita l'exploit del browser TLS 1.0 contro la mitigazione SSL/TLS (BEAST) disabilitando l'uso di SCH_SEND_AUX_RECORD.|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchUseStrongCrypto`|Controlla se le <xref:System.Net.ServicePointManager?displayProperty=nameWithType> classi <xref:System.Net.Security.SslStream?displayProperty=nameWithType> e possono usare il protocollo SSL 3,0. Per altre informazioni, vedere [Mitigazione: Protocolli TLS](../../../migration-guide/mitigation-tls-protocols.md).|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSystemDefaultTlsVersions`|Disabilita le versioni di TLS di SystemDefault ripristinando il valore predefinito Tls12, Tls11 e TLS.|.NET Framework 4.7|
|`Switch.System.Net.`<br/>`DontEnableTlsAlerts`|Disabilita gli avvisi lato server di SslStream TLS.|.NET Framework 4.7|
|`Switch.System.Runtime.InteropServices.`<br/>`DoNotMarshalOutByrefSafeArrayOnInvoke`|Controlla se i parametri SAFEARRAY ByRef sugli eventi di interoperabilità COM eseguono il`false`marshalling al codice nativo () o se il marshalling`true`al codice nativo è disabilitato ().|.NET Framework 4.8|
|`Switch.System.Runtime.Serialization.`<br/>`DoNotUseECMAScriptV6EscapeControlCharacter` |Controlla se [DataContractJsonSerializer](xref:System.Runtime.Serialization.Json.DataContractJsonSerializer) serializza alcuni caratteri di controllo in base agli standard ECMAScript V6 e V8. Per altre informazioni, vedere [Mitigazione: Serializzazione di caratteri di controllo con DataContractJsonSerializer](../../../migration-guide/mitigation-serialization-control-characters.md)| .NET Framework 4.7 |
|`Switch.System.Runtime.Serialization.`<br/>`DoNotUseTimeZoneInfo`|Controlla se <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> supporta più regolazioni o solo una singola regolazione per un fuso orario. Se `true`, usa il <xref:System.TimeZoneInfo> tipo per serializzare e deserializzare i dati di data e ora; in caso contrario <xref:System.TimeZone> , usa il tipo, che non supporta più regole di regolazione.|.NET Framework 4.6.2|
|`Switch.System.Runtime.Serialization.UseNewMaxArraySize`|Controlla se <xref:System.Runtime.Serialization.ObjectManager?displayProperty=nameWithType> utilizza una dimensione della matrice maggiore durante la serializzazione e la deserializzazione dell'oggetto. Impostare questa opzione su `true` per migliorare le prestazioni della serializzazione e della deserializzazione di oggetti grafici di grandi dimensioni in <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>base ai tipi come. |.NET Framework 4.7.2|
|`Switch.System.Security.ClaimsIdentity.`<br/>`SetActorAsReferenceWhenCopyingClaimsIdentity`|Controlla se il <xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29?displayProperty=nameWithType> costruttore imposta la <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=nameWithType> proprietà del nuovo oggetto con un riferimento a un oggetto esistente. Per altre informazioni, vedere [Mitigazione: Costruttore](../../../migration-guide/mitigation-claimsidentity-constructor.md)ClaimsIdentity.|.NET Framework 4.6.2|  
|`Switch.System.Security.Cryptography.`<br/>`AesCryptoServiceProvider.DontCorrectlyResetDecryptor`|Controlla se il tentativo di riutilizzare <xref:System.Security.Cryptography.AesCryptoServiceProvider> un decrittografia genera <xref:System.Security.Cryptography.CryptographicException>un'eccezione. Per ulteriori informazioni, vedere [AesCryptoServiceProvider Decryptor fornisce una trasformazione](../../../migration-guide/retargeting/4.6.1-4.6.2.md#aescryptoserviceprovider-decryptor-provides-a-reusable-transform)riutilizzabile.|.NET Framework 4.6.2|
|`Switch.System.Security.Cryptography.`<br/>`DoNotAddrOfCspParentWindowHandle`|Controlla se il valore della proprietà [CspParameters. ParentWindowHandle](xref:System.Security.Cryptography.CspParameters.ParentWindowHandle) è un elemento [IntPtr](xref:System.IntPtr) che rappresenta la posizione di memoria di un handle di finestra o se è un handle di finestra (HWND). Per altre informazioni, vedere [Mitigazione: CspParameters. ParentWindowHandle prevede un HWND](../../../migration-guide/retargeting/4.6.2-4.7.md#cspparametersparentwindowhandle-now-expects-hwnd-value). |.NET Framework 4.7|   
|`Switch.System.Security.Cryptography.`<br/>`UseLegacyFipsThrow`|Controlla se l'utilizzo di classi di crittografia gestite in modalità FIPS genera un' <xref:System.Security.Cryptography.CryptographicException> eccezione`true`() o si basa sull'implementazione delle librerie di sistema`false`().|.NET Framework 4.8|
|`Switch.System.Security.Cryptography.Pkcs.`<br/>`UseInsecureHashAlgorithms`|Determina se l'impostazione predefinita per alcune operazioni SignedCMS è SHA1 o SHA256.<br>A causa di problemi di conflitto con SHA1, Microsoft consiglia SHA256.|.NET Framework 4.7.1|
|`Switch.System.Security.Cryptography.X509Certificates.`<br/>`ECDsaCertificateExtensions.UseLegacyPublicKeyReader`|Controlla se il <xref:System.Security.Cryptography.X509Certificates.ECDsaCertificateExtensions.GetECDsaPublicKey%2A?displayProperty=nameWithType> metodo gestisce correttamente tutte le curve denominate supportate dal sistema`false`operativo () o Ripristina il comportamento legacy.|.NET Framework 4.8|
|`Switch.System.Security.Cryptography.Xml.`<br/>`UseInsecureHashAlgorithms`|Determina se l'impostazione predefinita per alcune operazioni SignedXML è SHA1 o SHA256.<br>A causa di problemi di conflitto con SHA1, Microsoft consiglia SHA256.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`AllowUnsignedToHeader`|Determina se la `TransportWithMessageCredential` modalità di sicurezza consente messaggi con un'intestazione "to" senza segno. Si tratta di un'opzione di consenso esplicito. Per ulteriori informazioni, vedere [modifiche di runtime nel .NET Framework 4.6.1](../../../migration-guide/runtime/4.5.2-4.6.1.md#windows-communication-foundation-wcf).|.NET Framework 4.6.1| 
|`Switch.System.ServiceModel.`<br/>`DisableAddressHeaderCollectionValidation`>|Controlla se il <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> costruttore genera un' <xref:System.ArgumentException> eccezione se uno degli elementi è `null`.|.NET Framework 4.7.1| 
|`Switch.System.ServiceModel.`<br />`DisableCngCertificates`|Determina se il tentativo di usare i certificati X509 con un provider di archiviazione chiavi CSG genera un'eccezione. Per ulteriori informazioni, vedere la pagina relativa alla [sicurezza del trasporto WCF supporta i certificati archiviati tramite CNG](../../../migration-guide/retargeting/4.6.1-4.6.2.md#wcf-transport-security-supports-certificates-stored-using-cng).|.NET Framework 4.6.1|
|`Switch.System.ServiceModel.`<br/>`DisableExplicitConnectionCloseHeader`|Quando si usa il trasporto HTTP con un servizio indipendente, l'impostazione di questo valore `true` su fa sì che WCF ignori un' `Connection: close` applicazione che aggiunge l'intestazione alle intestazioni della risposta per una richiesta. L'impostazione di questo `false` valore su consente `Connection: close` di aggiungere l'intestazione alle intestazioni della risposta, il che comporta la chiusura del socket della richiesta dopo l'invio di una risposta.|.NET Framework 4.6|
|`Switch.System.ServiceModel.`<br/>`DisableOperationContextAsyncFlow`|Gestisce i deadlock derivanti dalla restrizione delle istanze di un servizio rientrante a un singolo thread di esecuzione alla volta.|.NET Framework 4.6.2|
|`Switch.System.ServiceModel.`<br/>`DisableUsingServicePointManagerSecurityProtocols`|Insieme a `Switch.System.Net.DontEnableSchUseStrongCrypto`, determina se la sicurezza dei messaggi WCF utilizza TLS 1,1 e TLS 1,2.|.NET Framework 4.7 |    
|`Switch.System.ServiceModel.`<br/>`DontEnableSystemDefaultTlsVersions`|Il valore `false` imposta la configurazione predefinita per consentire al sistema operativo di scegliere il protocollo. Il valore `true` predefinito imposta il protocollo più alto disponibile. (Disponibile anche nel ramo di manutenzione delle versioni precedenti del Framework)|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`UseSha1InMsmqEncryptionAlgorithm`|Determina se l'algoritmo di firma del messaggio predefinito per i messaggi MSMQ in WCF è SHA1 o SHA256.<br>A causa di problemi di conflitto con SHA1, Microsoft consiglia SHA256.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`UseSha1InPipeConnectionGetHashAlgorithm`|Controlla se WCF utilizza un hash SHA1 o SHA256 per generare nomi casuali per le named pipe.<br>A causa di problemi di conflitto con SHA1, Microsoft consiglia SHA256.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.Internals`<br/>`IncludeNullExceptionMessageInETWTrace`|Determina se generare un'eccezione [NullReferenceException](xref:System.NullReferenceException) quando il messaggio di eccezione è null.|.NET Framework 4.7|  
|`Switch.System.ServiceProcess.`<br/>`DontThrowExceptionsOnStart`|Controlla se le eccezioni generate all'avvio del servizio vengono propagate al <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType> chiamante del metodo.|.NET Framework 4.7.1|
|`Switch.System.Threading.UseNetCoreTimer`|Controlla se <xref:System.Threading.Timer> le istanze di sfruttano i vantaggi offerti dai miglioramenti delle prestazioni per gli ambienti a scalabilità elevata. Se `true`, i miglioramenti delle prestazioni sono abilitati `false` ; se (valore predefinito), sono disabilitati.|.NET Framework 4.8|
|`Switch.System.Uri.`<br/>`DontEnableStrictRFC3986ReservedCharacterSets`|Determina se alcuni caratteri codificati in percentuale a volte decodificati sono ora codificati in modo coerente. Se `true`, vengono decodificati. in caso contrario `false`,.|.NET Framework 4.7.2|
|`Switch.System.Uri.`<br/>`DontKeepUnicodeBidiFormattingCharacters`|Determina la gestione dei caratteri bidirezionali Unicode negli URI. `true`per rimuoverle dagli URI; `false` per mantenere e codificare le percentuali.|.NET Framework 4.7.2|
|`Switch.System.Windows.Controls.Grid.`<br/>`StarDefinitionsCanExceedAvailableSpace` |Determina se Windows Presentation Foundation applica un algoritmo precedente (`true`) o un nuovo algoritmo (`false`) nell'allocazione di spazio \*alle colonne. Per altre informazioni, vedere [Mitigazione: Allocazione dello spazio del controllo griglia alle colonne](../../../migration-guide/retargeting/4.6.2-4.7.md#wpf-grid-allocation-of-space-to-star-columns)a stella. |.NET Framework 4.7 |
|`Switch.System.Windows.Controls.TabControl.`<br/>`SelectionPropertiesCanLagBehindSelectionChangedEvent`|Controlla se un selettore o un controllo struttura a schede Aggiorna sempre il valore della proprietà del valore selezionato prima di generare l'evento di modifica della selezione.|.NET Framework 4.7.1|
|`Switch.System.Windows.Controls.Text.`<br/>`UseAdornerForTextboxSelectionRendering`|Determina se il rendering della selezione basata su Adorner è disponibile per <xref:System.Windows.Controls.TextBox> i <xref:System.Windows.Controls.PasswordBox> controlli e per impedire il testo`false`bloccato () o se il rendering del testo viene eseguito solo nel livello`true`dello strumento decorativo ().|.NET Framework 4.7.2|
|`Switch.System.Windows.Data.Binding.`<br/>`IListIndexerHidesCustomIndexer`|Controlla se gli`false``true` indicizzatoriIListpersonalizzativengonousatiinmodoerrato()ocorrettamente(<xref:System.Windows.Data.Binding?displayProperty=nameWithType> ) dalla classe.|.NET Framework 4.8|
|`Switch.System.Windows.DoNotScaleForDpiChanges`|Determina se le modifiche DPI si verificano in un oggetto per sistema ( `false`valore) o per monitoraggio (valore di `true`).|.NET Framework 4.6.2|
|`Switch.System.Windows.`<br/>`DoNotUsePresentationDpiCapabilityTier2OrGreater`|Controlla se i miglioramenti apportati al ridimensionamento dei controlli in un oggetto <xref:System.Windows.Interop.HwndHost?displayProperty=nameWithType> quando WPF viene eseguito in modalità di rilevamento per monitoraggio sono disabilitati (`true`) o abilitati (`false`).|.NET Framework 4.8|
|`Switch.System.Windows.Forms.`<br/>`DomainUpDown.UseLegacyScrolling`|Determina se lo sviluppatore deve gestire in modo specifico <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> l'azione quando è presente il testo del controllo. `true`per gestire l' <xref:System.Windows.Forms.DomainUpDown.UpButton> azione; per sincronizzare <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> correttamente le azioni e <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType>. `false`|.NET Framework 4.7.2|
|`Switch.System.Windows.Forms.`<br />`DontSupportReentrantFilterMessage`|Esclude il codice che consente a un'implementazione personalizzata <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> di filtrare in modo sicuro i messaggi senza generare un'eccezione <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> quando viene chiamato il metodo. Per altre informazioni, vedere [Mitigazione: Implementazioni personalizzate di IMessageFilter.](../../../migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md)PreFilterMessage.|.NET Framework 4.6.1|  
|`Switch.System.Windows.Forms.`<br/>`UseLegacyContextMenuStripSourceControlValue`|Determina se la <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> proprietà restituisce il controllo del codice sorgente quando l'utente apre il menu da <xref:System.Windows.Forms.ToolStripMenuItem> un controllo annidato. `true`per restituire `null`, il comportamento legacy; `false` per restituire il controllo del codice sorgente.|.NET Framework 4.7.2|
|`Switch.System.Windows.Forms.UseLegacyToolTipDisplay`|Controlla se il supporto della chiamata della descrizione comando`true`è disabilitato (`false`) o abilitato (). L'abilitazione del supporto della chiamata della descrizione comando richiede anche `Switch.UseLegacyAccessibilityFeatures`le funzionalità di `Switch.UseLegacyAccessibilityFeatures.3` accessibilità legacy definite da, `false` `Switch.UseLegacyAccessibilityFeatures.2`e tutte disabilitate (impostate su).|.NET Framework 4.8|
|`Switch.System.Windows.Input.Stylus.`<br/>`EnablePointerSupport`|Determina se uno stack `WM_POINTER`di tocco/stilo basato su facoltativo è abilitato nelle applicazioni WPF. Per altre informazioni, vedere [Mitigazione: Supporto per tocco e stilo basato su puntatore](../../../migration-guide/mitigation-pointer-based-touch-and-stylus-support.md)|.NET Framework 4.7|
|`Switch.System.Windows.Markup.`<br/>`DoNotUseSha256ForMarkupCompilerChecksumAlgorithm`|Determina se l'algoritmo hash predefinito utilizzato per i checksum è SHA256 (`false`) o SHA1 (`true`).<br>A causa di problemi di conflitto con SHA1, Microsoft consiglia SHA256.|.NET Framework 4.7.2|
|`Switch.System.Windows.Media.ImageSourceConverter.`<br/>`OverrideExceptionWithNullReferenceException`|Controlla se viene generata un'eccezione [NullReferenceException](xref:System.NullReferenceException) legacy anziché l'eccezione che indica più specificamente la provocazione dell'eccezione, ad esempio [DirectoryNotFoundException](xref:System.IO.DirectoryNotFoundException) o [FileNotFoundException](xref:System.IO.FileNotFoundException). È destinata all'utilizzo da parte del codice che dipende dalla gestione dell' [eccezione NullReferenceException](xref:System.NullReferenceException). | .NET Framework 4.7 |
|`Switch.System.Workflow.ComponentModel.`<br/>`UseLegacyHashForXomlFileChecksum`|Controlla se l'hashing di checksum dei file XOML nelle compilazioni di progetti flusso di`true`lavoro usa l'algoritmo MD5 () o se usa l'algoritmo SHA256 introdotto come valore predefinito in .NET Framework 4,8.<br>A causa di problemi di collisione con MD5, Microsoft consiglia SHA256.|.NET Framework 4.8|
|`Switch.System.Workflow.Runtime.`<br/>`UseLegacyHashForSqlTrackingCacheKey`|Controlla se l'hashing di checksum da SqlTrackingService usa l'algoritmo MD5 (`true`) per le stringhe memorizzate nella cache o se usa l'algoritmo SHA256 introdotto come valore predefinito in .NET Framework 4,8.<br>A causa di problemi di collisione con MD5, Microsoft consiglia SHA256.|.NET Framework 4.8|
|`Switch.System.Workflow.Runtime.`<br/>`UseLegacyHashForWorkflowDefinitionDispenserCacheKey`|Controlla se l'hashing di checksum da parte del runtime del flusso di lavoro`true`usa l'algoritmo MD5 () per le definizioni dei flussi di lavoro memorizzati nella cache o se usa l'algoritmo SHA256 introdotto come valore predefinito in .NET Framework 4,8.<br>A causa di problemi di collisione con MD5, Microsoft consiglia SHA256.|.NET Framework 4.8|
|`Switch.UseLegacyAccessibilityFeatures`|Controlla se le funzionalità di accessibilità disponibili a partire da .NET Framework 4.7.1 sono abilitate o disabilitate. | .NET Framework 4.7.1 |
|`Switch.UseLegacyAccessibilityFeatures.2`|Controlla se le funzionalità di accessibilità disponibili in .NET Framework 4.7.2`false`sono abilitate (`true`) o disabilitate (). Se `true`, `Switch.UseLegacyAccessibilityFeatures` deve essere`true` anche per abilitare le funzionalità di accessibilità di .NET Framework 4.7.1.|.NET Framework 4.7.2|
|`Switch.UseLegacyAccessibilityFeatures.3`|Controlla se le funzionalità di accessibilità introdotte in .NET Framework 4,8`false`sono abilitate (`true`) o disabilitate (). Se `true`, `Switch.UseLegacyAccessibilityFeatures` e devono`Switch.UseLegacyAccessibilityFeatures.2` essere`true`anche.|.NET Framework 4.8|
|`Switch.UseLegacyToolTipDisplay`|Controlla se le descrizioni comandi vengono visualizzate quando un utente posiziona il cursore del mouse su un controllo WPF`true`() o se viene visualizzato sullo stato attivo della tastiera e tramite il tasto di scelta`false`rapida (, il comportamento predefinito). Per le applicazioni in esecuzione in .NET Framework 4,8 ma destinate a versioni precedenti del .NET Framework, `Switch.UseLegacyAccessibilityFeatures`l'abilitazione del supporto per `false`lo stato attivo `Switch.UseLegacyAccessibilityFeatures.2`e il `Switch.UseLegacyAccessibilityFeatures.3` tasto di scelta rapida richiede che, e siano tutti impostati su.|.NET Framework 4.8|
|`System.Xml.`<br /><br /> `IgnoreEmptyKeySequences`|Controlla se le sequenze di chiavi vuote nelle chiavi composte vengono ignorate dalla convalida dello schema XSD. Per altre informazioni, vedere [Mitigazione: Convalida](../../../migration-guide/mitigation-xml-schema-validation.md)di XML Schema.|.NET Framework 4.6|  
  
> [!NOTE]
> Invece di aggiungere un `AppContextSwitchOverrides` elemento a un file di configurazione dell'applicazione, è anche possibile impostare le opzioni a livello di `static` codice chiamando C#il metodo `Shared` (in) o <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> (in Visual Basic).  
  
 Gli sviluppatori di librerie possono anche definire opzioni personalizzate per consentire ai chiamanti di rifiutare esplicitamente le funzionalità modificate introdotte nelle versioni successive delle librerie. Per altre informazioni, vedere la classe <xref:System.AppContext>.  
  
## <a name="switches-in-aspnet-applications"></a>Opzioni nelle applicazioni ASP.NET

È possibile configurare un'applicazione ASP.NET per l' [ \<](../appsettings/index.md) uso delle impostazioni di compatibilità aggiungendo un [ \<elemento Add >](../appsettings/add-element-for-appsettings.md) alla sezione appSettings > del file Web. config. 

Nell'esempio seguente viene usato `<add>` l'elemento per aggiungere due impostazioni `<appSettings>` alla sezione di un file Web. config:

```xml
<appSettings>
  <add key="AppContext.SetSwitch:Switch.System.Globalization.NoAsyncCurrentCulture" value="true" />
  <add key="AppContext.SetSwitch:Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets" value="true" />
</appSettings>
```

## <a name="example"></a>Esempio

 Nell'esempio seguente viene utilizzato `AppContextSwitchOverrides` l'elemento per definire una singola opzione di compatibilità `Switch.System.Globalization.NoAsyncCurrentCulture`dell'applicazione,, che impedisce la visualizzazione delle impostazioni cultura tra i thread nelle chiamate asincrone al metodo.  
  
```xml  
<configuration>  
   <runtime>  
      <AppContextSwitchOverrides value="Switch.System.Globalization.NoAsyncCurrentCulture=true" />  
   </runtime>  
</configuration>  
```  
  
 Nell'esempio seguente viene usato `AppContextSwitchOverrides` l'elemento per definire due opzioni di compatibilità `Switch.System.Globalization.NoAsyncCurrentCulture` delle `Switch.System.IO.BlockLongPaths`applicazioni, e. Si noti che un punto e virgola separa le due coppie nome/valore.  
  
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
- [\<Elemento runtime >](runtime-element.md)
- [Elemento \<configuration>](../configuration-element.md)
