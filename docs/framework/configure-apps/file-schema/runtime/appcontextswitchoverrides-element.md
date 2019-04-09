---
title: <AppContextSwitchOverrides> Elemento
ms.custom: updateeachrelease
ms.date: 03/07/2019
helpviewer_keywords:
- AppContextSwitchOverrides
- compatibility switches
- configuration switches
- configuration
ms.assetid: 4ce07f47-7ddb-4d91-b067-501bd8b88752
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1bc4cd94d3acd37244e1d5b882612e4b1da91b90
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136461"
---
# <a name="appcontextswitchoverrides-element"></a>\<AppContextSwitchOverrides > elemento
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
|`value`|Attributo obbligatorio.<br /><br /> Definisce uno o più nomi di opzione e i relativi valori booleani associate.|  
  
### <a name="value-attribute"></a>valore attributo  
  
|Value|Descrizione|  
|-----------|-----------------|  
|"name=value"|Un nome di parametro predefinito insieme al relativo valore (`true` o `false`). Più coppie nome/valore di opzione sono separate da punti e virgola (";"). Per un elenco di nomi di parametro predefiniti supportati da .NET Framework, vedere la sezione Osservazioni.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.|  
  
## <a name="remarks"></a>Note  
 A partire da .NET Framework 4.6, il `<AppContextSwitchOverrides>` elemento in un file di configurazione consente ai chiamanti di un'API per determinare se l'app può sfruttare i vantaggi delle nuove funzionalità o mantenere la compatibilità con le versioni precedenti di una libreria. Se, ad esempio, il comportamento di un'API è stato modificato tra due versioni di una libreria, il `<AppContextSwitchOverrides>` elemento consente ai chiamanti di quell'API per rifiutare esplicitamente il nuovo comportamento nelle versioni della libreria che supportano le nuove funzionalità. Per le app che chiamano le API in .NET Framework, il `<AppContextSwitchOverrides>` elemento può anche consentire ai chiamanti di App come destinazione una versione precedente di .NET Framework per consentire a nuove funzionalità, se l'app è in esecuzione su una versione di .NET Framework che include tale funzionalità.  
  
 Il `value` attributo del `<AppContextSwitchOverrides>` elemento è costituito da una singola stringa costituita da uno o più coppie nome/valore delimitata da punti e virgola.  Ogni nome identifica un'opzione di compatibilità e il relativo valore corrispondente è un valore booleano (`true` o `false`) che indica se l'opzione è impostata. Per impostazione predefinita, l'opzione è `false`, e le librerie forniscono la nuova funzionalità. Forniscono la funzionalità precedente solo se il cambio viene impostato (vale a dire, il relativo valore è `true`). Ciò consente alle librerie di fornire di nuovo comportamento per un'API esistente, consentendo ai chiamanti che dipendono dal comportamento precedente per rifiutare esplicitamente la nuova funzionalità.  
  
 .NET Framework supporta le seguenti opzioni:  
  
|Nome del commutatore|Descrizione|Introdotto|  
|-----------------|-----------------|----------------|  
|`Switch.MS.Internal.`<br/>`DoNotApplyLayoutRoundingToMarginsAndBorderThickness`|Controlla se Windows Presentation Foundation Usa un algoritmo legacy per il layout dei controlli. Per altre informazioni, vedere [Mitigazione: Layout WPF](../../../migration-guide/mitigation-wpf-layout.md).|.NET Framework 4.6|  
|`Switch.MS.Internal.`<br/>`UseSha1AsDefaultHashAlgorithmForDigitalSignatures`|Controlla se l'algoritmo predefinito utilizzato per firmare le parti di un pacchetto da PackageDigitalSignatureManager è SHA1 o SHA256.<br>A causa di problemi di conflitto con SHA1, Microsoft consiglia SHA256.|.NET Framework 4.7.1|
|`Switch.System.Activities.`<br/>`UseMD5CryptoServiceProviderForWFDebugger`|Se impostato su `false`, consente il debug di progetti di flusso di lavoro basato su XAML con Visual Studio quando è abilitato FIPS. In caso contrario, un <xref:System.NullReferenceException> viene generata un'eccezione in chiamate a metodi nell'assembly System. Activities.|.NET Framework 4.7|
|`Switch.System.Activities.`<br/>`UseMD5ForWFDebugger`|Controlla se il valore di checksum per un'istanza del flusso di lavoro nel debugger Usa MD5 o SHA1. | .NET Framework 4.7|
|`Switch.System.Activities.`<br/>`UseSHA1HashForDebuggerSymbols`|Controlla se l'hash del checksum del flusso di lavoro Usa l'algoritmo SHA1 introdotto come impostazione predefinita in .NET Framework 4.7 (`true`), o se Usa l'algoritmo SHA256 predefinito introdotto come l'impostazione predefinita in .NET Framework 4.8 (`false`).<br>A causa di problemi di conflitto con SHA1, Microsoft consiglia SHA256.|.NET Framework 4.8|
|`Switch.System.Diagnostics.`<br/>`IgnorePortablePDBsInStackTraces`|Controlla se le analisi dello stack ottenuti quando si usano file PDB portatili possono includere informazioni sulla riga e file di origine. `false` Per includere informazioni; file e righe di origine in caso contrario, `true`.|.NET Framework 4.7.2|
|`Switch.System.Drawing.`<br/>`DontSupportPngFramesInIcons`|Controlli se il <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> metodo genera un'eccezione quando un <xref:System.Drawing.Icon> oggetto presenta frame PNG. Per altre informazioni, vedere [Mitigazione: Frame PNG in oggetti icona](../../../migration-guide/mitigation-png-frames-in-icon-objects.md).|.NET Framework 4.6|
|`Switch.System.Drawing.Text.`<br/>`DoNotRemoveGdiFontsResourcesFromFontCollection`|Determina se <xref:System.Drawing.Text.PrivateFontCollection?displayProperty=nameWithType> gli oggetti vengono eliminati correttamente quando aggiunto alla raccolta in base al <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)?displayProperty=nameWithType> (metodo). `true` Per mantenere il comportamento legacy. `false` per l'eliminazione di tutti gli oggetti di tipo di carattere privato. |.NET Framework 4.7.2|
|`Switch.System.Drawing.Printing.`<br>`OptimizePrintPreview`|Controlli se le prestazioni dei <xref:System.Windows.Forms.PrintPreviewDialog> è ottimizzato per le stampanti di rete. Per altre informazioni, vedere [Cenni preliminari sul controllo PrintPreviewDialog](../../../winforms/controls/printpreviewdialog-control-overview-windows-forms.md).|.NET Framework 4.6|
|`Switch.System.Globalization.EnforceJapaneseEraYearRanges`|Se Controlla intervallo di anni di calendario giapponese vengono applicate le ere. `true` Per imporre l'intervallo di anni i controlli, e `false` per disabilitarli (comportamento predefinito). Per altre informazioni, vedere [utilizzo di calendari](../../../../standard/datetime/working-with-calendars.md).|.NET Framework 4.6|
|`Switch.System.Globalization.EnforceLegacyJapaneseDateParsing`|Consente di controllare se solo "1" è riconosciuto come il primo anno dell'era calendario giapponese nelle operazioni di analisi. `true` per riconoscere solo "1". `false` riconoscere "1" o Gannen (comportamento predefinito). Per altre informazioni, vedere [utilizzo di calendari](../../../../standard/datetime/working-with-calendars.md).|.NET Framework 4.6| 
|`Switch.System.Globalization.FormatJapaneseFirstYearAsANumber`|Controlla se il primo anno dell'era calendario giapponese è rappresentato come "1" o Gannen nelle operazioni di formattazione. `true` Per formattare l'anno prima dell'era come "1". `false` formattarle come Gannen (comportamento predefinito). Per altre informazioni, vedere [utilizzo di calendari](../../../../standard/datetime/working-with-calendars.md).|.NET Framework 4.6|
|`Switch.System.Globalization.NoAsyncCurrentCulture`|Controlla se le operazioni asincrone non passano dal contesto del thread chiamante. Per altre informazioni, vedere [CurrentCulture e CurrentUICulture vengono propagate tra attività](../../../migration-guide/retargeting/4.5.2-4.6.md#currentculture-and-currentuiculture-flow-across-tasks).|.NET Framework 4.6|  
|`Switch.System.IdentityModel.`<br/>`DisableMultipleDNSEntriesInSANCertificate`|Controlli se il <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> metodo tenta di ottenere il tipo di attestazione solo con l'ultima voce DNS. Per altre informazioni, vedere [Mitigazione: Metodo X509CertificateClaimSet.FindClaims](../../../migration-guide/mitigation-x509certificateclaimset-findclaims-method.md).|.NET Framework 4.6.1|  
|`Switch.System.IdentityModel.`<br/>`EnableCachedEmptyDefaultAuthorizationContext`|Controlla se si desidera consentire AuthorizationContext.Empty restituire un oggetto modificabile.|.NET Framework 4.6|  
|`Switch.System.IO.BlockLongPaths`|Controlli se percorsi che contengono più `MAX_PATH` ovvero 260 caratteri, generare un <xref:System.IO.PathTooLongException>. Per altre informazioni, vedere [supporto del percorso lungo](../../../migration-guide/retargeting/4.6.1-4.6.2.md#long-path-support).|.NET Framework 4.6.2|  
|`Switch.System.IO.Compression.`<br/>`DoNotUseNativeZipLibraryForDecompression`|Controlla se le routine del sistema operativo native vengono utilizzate per la decompressione dal <xref:System.IO.Compression.DeflateStream> classe. `false` usare le API native; `true` usare il <xref:System.IO.Compression.DeflateStream> implementazione.|.NET Framework 4.7.2|
|`Switch.System.IO.Compression.ZipFile.`<br/>`UseBackslash`|Usa la barra rovesciata ("\\") anziché la barra rovesciata ("/") come separatore di percorso nel <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=nameWithType> proprietà. Per altre informazioni, vedere [mitigazione: Separatore di percorsi ZipArchiveEntry. FullName](../../../migration-guide/mitigation-ziparchiveentry-fullname-path-separator.md).|.NET Framework 4.6.1|  
|`Switch.System.IO.Ports.`<br/>`DoNotCatchSerialStreamThreadExceptions`|Controlla se operativo eccezioni di sistema che vengono generate nel thread in background creati con <xref:System.IO.Ports.SerialPort> flussi terminano il processo.|.NET Framework 4.7.1| 
|`Switch.System.IO.`<br/>`UseLegacyPathHandling`|Controlla se viene usata la normalizzazione percorso legacy e percorsi URI sono supportati per il <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> e <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> metodi. Per altre informazioni, vedere [Mitigazione: Normalizzazione del percorso](../../../migration-guide/mitigation-path-normalization.md) e [mitigazione: Percorso i controlli della presenza](../../../migration-guide/mitigation-path-colon-checks.md).|.NET Framework 4.6.2|
|`Switch.System.`<br/>`MemberDescriptorEqualsReturnsFalseIfEquivalent`|Controlla se un test per verificarne l'uguaglianza confronta la <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=nameWithType> proprietà di un oggetto con il <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=nameWithType> proprietà del secondo oggetto. Per altre informazioni, vedere [implementazione non corretta di MemberDescriptor. Equals](../../../migration-guide/retargeting/4.6.1-4.6.2.md#incorrect-implementation-of-memberdescriptorequals).|.NET Framework 4.6.2|  
 `Switch.System.Net.`<br/>`DontCheckCertificateEKUs`|Disattiva la convalida dell'identificatore (OID) Utilizzo chiavi avanzato (EKU) oggetto del certificato. Un'estensione di utilizzo chiavi avanzato (EKU) è una raccolta di identificatori di oggetto (OID) che indica le applicazioni che usano la chiave.|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchSendAuxRecord`|Disabilita la mitigazione dei rischi TLS1.0 Browser Exploit con SSL/TLS (BEAST), disabilitare l'utilizzo di SCH_SEND_AUX_RECORD.|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchUseStrongCrypto`|Controlli se il <xref:System.Net.ServicePointManager?displayProperty=nameWithType> e <xref:System.Net.Security.SslStream?displayProperty=nameWithType> le classi possono utilizzare il protocollo SSL 3.0. Per altre informazioni, vedere [Mitigazione: Protocolli TLS](../../../migration-guide/mitigation-tls-protocols.md).|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSystemDefaultTlsVersions`|Disabilita le versioni di TLS SystemDefault eseguendo il ripristino di un valore predefinito di Tls12, Tls11, Tls.|.NET Framework 4.7|
|`Switch.System.Net.`<br/>`DontEnableTlsAlerts`|Disabilita gli avvisi sul lato server TLS SslStream.|.NET Framework 4.7|
|`Switch.System.Runtime.Serialization.`<br/>`DoNotUseECMAScriptV6EscapeControlCharacter` |Controlli se il [DataContractJsonSerializer](xref:System.Runtime.Serialization.Json.DataContractJsonSerializer) serializza alcuni caratteri di controllo basati sugli standard ECMAScript V6 e V8. Per altre informazioni, vedere [Mitigazione: Serializzazione dei caratteri di controllo con DataContractJsonSerializer](../../../migration-guide/mitigation-serialization-control-characters.md)| .NET Framework 4.7 |
|`Switch.System.Runtime.Serialization.`<br/>`DoNotUseTimeZoneInfo`|Controlli se il <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> supporta solo una regolazione singola o più modifiche per un fuso orario. Se `true`, Usa le <xref:System.TimeZoneInfo> tipo da serializzare e deserializzare i dati di data e ora; in caso contrario, viene utilizzato il <xref:System.TimeZone> tipo, che non supporta più regole di regolazione.|.NET Framework 4.6.2|
|`Switch.System.Runtime.Serialization.UseNewMaxArraySize`|Controlli se <xref:System.Runtime.Serialization.ObjectManager?displayProperty=nameWithType> utilizza una dimensione della matrice di dimensioni maggiori durante la serializzazione degli oggetti e la deserializzazione. Impostare questa opzione su `true` per migliorare le prestazioni di serializzazione e deserializzazione dei grafici di oggetti di grandi dimensioni dai tipi, ad esempio <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>. |.NET Framework 4.7.2|
|`Switch.System.Security.ClaimsIdentity.`<br/>`SetActorAsReferenceWhenCopyingClaimsIdentity`|Controlli se il <xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29?displayProperty=nameWithType> costruttore imposta il nuovo oggetto <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=nameWithType> proprietà con un riferimento all'oggetto esistente. Per altre informazioni, vedere [Mitigazione: Costruttore ClaimsIdentity](../../../migration-guide/mitigation-claimsidentity-constructor.md).|.NET Framework 4.6.2|  
|`Switch.System.Security.Cryptography.`<br/>`AesCryptoServiceProvider.DontCorrectlyResetDecryptor`|Controlli se il tentativo di riusare un' <xref:System.Security.Cryptography.AesCryptoServiceProvider> decrittografia genera un <xref:System.Security.Cryptography.CryptographicException>. Per altre informazioni, vedere [componente di decrittografia AesCryptoServiceProvider fornisce una trasformazione riutilizzabile](../../../migration-guide/retargeting/4.6.1-4.6.2.md#aescryptoserviceprovider-decryptor-provides-a-reusable-transform).|.NET Framework 4.6.2|
|`Switch.System.Security.Cryptography.`<br/>`DoNotAddrOfCspParentWindowHandle`|Controlli se il valore della [CspParameters. Parentwindowhandle](xref:System.Security.Cryptography.CspParameters.ParentWindowHandle) proprietà è un [IntPtr](xref:System.IntPtr) che rappresenta la posizione di memoria di una finestra di gestione, oppure se si tratta di un handle di finestra (HWND). Per altre informazioni, vedere [Mitigazione: CspParameters. Parentwindowhandle prevede un HWND](../../../migration-guide/retargeting/4.6.2-4.7.md#cspparametersparentwindowhandle-now-expects-hwnd-value). |.NET Framework 4.7|   
|`Switch.System.Security.Cryptography.Pkcs.`<br/>`UseInsecureHashAlgorithms`|Determina se il valore predefinito per alcune operazioni SignedCMS SHA1 o SHA256.<br>A causa di problemi di conflitto con SHA1, Microsoft consiglia SHA256.|.NET Framework 4.7.1|
|`Switch.System.Security.Cryptography.Xml.`<br/>`UseInsecureHashAlgorithms`|Determina se il valore predefinito per alcune operazioni di SignedXML SHA1 o SHA256.<br>A causa di problemi di conflitto con SHA1, Microsoft consiglia SHA256.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`AllowUnsignedToHeader`|Determina se il `TransportWithMessageCredential` modalità di sicurezza consente messaggi con un unsigned "intestazione to". Si tratta di un commutatore di consenso. Per altre informazioni, vedere [modifiche al Runtime in .NET Framework 4.6.1](../../../migration-guide/runtime/4.5.2-4.6.1.md#windows-communication-foundation-wcf).|.NET Framework 4.6.1| 
|`Switch.System.ServiceModel.`<br/>`DisableAddressHeaderCollectionValidation`>|Controlli se il <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> costruttore genera un <xref:System.ArgumentException> se uno degli elementi è `null`.|.NET Framework 4.7.1| 
|`Switch.System.ServiceModel.`<br />`DisableCngCertificates`|Determina che se il tentativo di usare X509 i certificati con un provider di archiviazione chiavi CSG genera un'eccezione. Per altre informazioni, vedere [protezione del trasporto WCF supporta i certificati archiviati usando CNG](../../../migration-guide/retargeting/4.6.1-4.6.2.md#wcf-transport-security-supports-certificates-stored-using-cng).|.NET Framework 4.6.1|
|`Switch.System.ServiceModel.`<br/>`DisableExplicitConnectionCloseHeader`|Quando si usa il trasporto HTTP con un servizio indipendente, impostare questo valore su `true` fa sì che WCF ignorare l'aggiunta di un'applicazione di `Connection: close` intestazione per le intestazioni di risposta per una richiesta. Impostando questo valore su `false` consente l'aggiunta di `Connection: close` intestazione per le intestazioni di risposta, con conseguente chiusura del socket di richiesta dopo aver inviata una risposta.|.NET Framework 4.6|
|`Switch.System.ServiceModel.`<br/>`DisableOperationContextAsyncFlow`|Gestisce i deadlock che derivano da limitare le istanze di un servizio rientrante a un singolo thread di esecuzione alla volta.|.NET Framework 4.6.2|
|`Switch.System.ServiceModel.`<br/>`DisableUsingServicePointManagerSecurityProtocols`|Insieme a `Switch.System.Net.DontEnableSchUseStrongCrypto`, determina se la protezione dei messaggi WCF Usa TLS 1.1 e TLS 1.2.|.NET Framework 4.7 |    
|`Switch.System.ServiceModel.`<br/>`DontEnableSystemDefaultTlsVersions`|Un valore di `false` imposta la configurazione predefinita per consentire al sistema operativo di scegliere il protocollo. Un valore di `true` imposta il valore predefinito per il protocollo più alto disponibile. (Disponibile anche nel ramo di versioni precedenti di framework di manutenzione)|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`UseSha1InMsmqEncryptionAlgorithm`|Determina se il messaggio predefinito per i messaggi MSMQ in WCF algoritmo di firma SHA1 o SHA256.<br>A causa di problemi di conflitto con SHA1, Microsoft consiglia SHA256.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`UseSha1InPipeConnectionGetHashAlgorithm`|Controlla se WCF Usa un SHA1 o un hash SHA256 per generare nomi casuali per le named pipe.<br>A causa di problemi di conflitto con SHA1, Microsoft consiglia SHA256.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.Internals`<br/>`IncludeNullExceptionMessageInETWTrace`|Controlla se generare una [NullReferenceException](xref:System.NullReferenceException) quando il messaggio di eccezione è null.|.NET Framework 4.7|  
|`Switch.System.ServiceProcess.`<br/>`DontThrowExceptionsOnStart`|Controlla se le eccezioni generate all'avvio del servizio vengono propagate al chiamante del <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType> (metodo).|.NET Framework 4.7.1|
|`Switch.System.Uri.`<br/>`DontEnableStrictRFC3986ReservedCharacterSets`|Determina se alcuni caratteri codificati in percentuale casi apparivano ora sono codificate in modo uniforme. Se `true`, vengono decodificati; in caso contrario, `false`.|.NET Framework 4.7.2|
|`Switch.System.Uri.`<br/>`DontKeepUnicodeBidiFormattingCharacters`|Determina la gestione dei caratteri bidirezionali Unicode negli URI. `true` per rimuoverli dall'URI. `false` per mantenere e percentuale-codificare tali funzioni.|.NET Framework 4.7.2|
|`Switch.System.Windows.Controls.Grid.`<br/>`StarDefinitionsCanExceedAvailableSpace` |Determina se Windows Presentation Foundation si applica un algoritmo precedente (`true`) o un nuovo algoritmo (`false`) per l'allocazione dello spazio a \*-colonne. Per altre informazioni, vedere [Mitigazione: Allocazione dello spazio di controllo della griglia alle colonne a stella a](../../../migration-guide/retargeting/4.6.2-4.7.md#wpf-grid-allocation-of-space-to-star-columns). |.NET Framework 4.7 |
|`Switch.System.Windows.Controls.TabControl.`<br/>`SelectionPropertiesCanLagBehindSelectionChangedEvent`|Indica se un selettore o una scheda controllano sempre aggiorna il valore della relativa proprietà value selezionato prima di generare la selezione di controlli dell'evento modificato.|.NET Framework 4.7.1|
|`Switch.System.Windows.Controls.Text.`<br/>`UseAdornerForTextboxSelectionRendering`|Determina se è disponibile per il rendering non dello strumento decorativo visuale di selezione in base il <xref:System.Windows.Controls.TextBox> e <xref:System.Windows.Controls.PasswordBox> controlla per impedire testo bloccato (`false`), o se viene eseguito rendering del testo solo al livello dell'Adorner (`true`).|.NET Framework 4.7.2|
|`Switch.System.Windows.Data.Binding.`<br/>`IListIndexerHidesCustomIndexer`|Controlla se gli indicizzatori di IList personalizzati vengono utilizzati in modo non corretto (`false`) o in modo corretto (`true`) per il <xref:System.Windows.Data.Binding?displayProperty=nameWithtype> classe.|.NET Framework 4.8|
|`Switch.System.Windows.DoNotScaleForDpiChanges`|Determina se si verificano modifiche DPI in base al sistema (un valore pari `false`) base di monitor o (valore `true`).|.NET Framework 4.6.2|
|`Switch.System.Windows.`<br/>`DoNotUsePresentationDpiCapabilityTier2OrGreater`|Controlli se miglioramenti nel ridimensionamento di controlli in una <xref:System.Windows.Interop.HwndHost?displayProperty=nameWithType> quando WPF viene eseguito in modo che riconoscano monitor sono disabilitate (`true`) o abilitato (`false`).|.NET Framework 4.8|
|`Switch.System.Windows.Forms.`<br/>`DomainUpDown.UseLegacyScrolling`|Determina se lo sviluppatore deve gestire in modo specifico la <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> azione quando è presente testo del controllo. `true` per gestire il <xref:System.Windows.Forms.DomainUpDown.UpButton> azione; `false` per il <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> e <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> azioni per essere correttamente sincronizzato.|.NET Framework 4.7.2|
|`Switch.System.Windows.Forms.`<br />`DontSupportReentrantFilterMessage`|Rifiuta esplicitamente il codice che consente a un oggetto personalizzato <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> implementazione di filtrare in modo sicuro i messaggi senza generare un'eccezione quando il <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> viene chiamato il metodo. Per altre informazioni, vedere [Mitigazione: Le implementazioni IMessageFilter. PreFilterMessage personalizzate](../../../migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).|.NET Framework 4.6.1|  
|`Switch.System.Windows.Forms.`<br/>`UseLegacyContextMenuStripSourceControlValue`|Determina se il <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> proprietà restituisce il controllo del codice sorgente quando l'utente apre il menu di scelta da nidificato <xref:System.Windows.Forms.ToolStripMenuItem> controllo. `true` per restituire `null`, il comportamento legacy. `false` per restituire il controllo del codice sorgente.|.NET Framework 4.7.2|
|`Switch.System.Windows.Forms.UseLegacyToolTipDisplay`|Controlla se il supporto di chiamata della descrizione comando è disabilitato (`true`) o abilitato (`false`). Abilitazione del supporto di chiamata della descrizione comando richiede anche le funzionalità di accessibilità legacy definite da `Switch.UseLegacyAccessibilityFeatures`, `Switch.UseLegacyAccessibilityFeatures.2`, e `Switch.UseLegacyAccessibilityFeatures.3` tutti essere disabilitati (impostato su `false`).|.NET Framework 4.8|
|`Switch.System.Windows.Input.Stylus.`<br/>`EnablePointerSupport`|Determina se facoltativo `WM_POINTER`-stack di tocco/stilo basato su è abilitato nelle applicazioni WPF. Per altre informazioni, vedere [Mitigazione: Basato su puntatore supporto di tocco e stilo](../../../migration-guide/mitigation-pointer-based-touch-and-stylus-support.md)|.NET Framework 4.7|
|`Switch.System.Windows.Markup.`<br/>`DoNotUseSha256ForMarkupCompilerChecksumAlgorithm`|Determina se l'algoritmo hash predefinito usato per i valori di checksum SHA256 (`false`) o SHA1 (`true`).<br>A causa di problemi di conflitto con SHA1, Microsoft consiglia SHA256.|.NET Framework 4.7.2|
|`Switch.System.Windows.Media.ImageSourceConverter.`<br/>`OverrideExceptionWithNullReferenceException`|Controlla se un legacy [NullReferenceException](xref:System.NullReferenceException) generata anziché dell'eccezione che indica in modo più specifico la causa dell'eccezione (ad esempio un [DirectoryNotFoundException](xref:System.IO.DirectoryNotFoundException) o un' [ FileNotFoundException](xref:System.IO.FileNotFoundException). È destinato da codice che dipende dalla gestione di [NullReferenceException](xref:System.NullReferenceException). | .NET Framework 4.7 |
|`Switch.System.Workflow.ComponentModel.`<br/>`UseLegacyHashForXomlFileChecksum`|I controlli se hash del checksum dei file XOML del flusso di lavoro progetto compila utilizzano l'algoritmo MD5 (`true`), o se usare l'algoritmo SHA256 introdotto come l'impostazione predefinita in .NET Framework 4.8.<br>A causa di problemi di conflitto con MD5, è consigliabile SHA256.|.NET Framework 4.8|
|`Switch.System.Workflow.Runtime.`<br/>`UseLegacyHashForSqlTrackingCacheKey`|Controlla se l'hash del checksum per SqlTrackingService Usa l'algoritmo MD5 (`true`) per le stringhe memorizzati nella cache, oppure se utilizza l'algoritmo SHA256 introdotto come l'impostazione predefinita in .NET Framework 4.8.<br>A causa di problemi di conflitto con MD5, è consigliabile SHA256.|.NET Framework 4.8|
|`Switch.System.Workflow.Runtime.`<br/>`UseLegacyHashForWorkflowDefinitionDispenserCacheKey`|Controlla se l'hash del checksum dal Runtime del flusso di lavoro Usa l'algoritmo MD5 (`true`) per le definizioni del flusso di lavoro memorizzata nella cache, oppure se utilizza l'algoritmo SHA256 introdotto come l'impostazione predefinita in .NET Framework 4.8.<br>A causa di problemi di conflitto con MD5, è consigliabile SHA256.|.NET Framework 4.8|
|`Switch.UseLegacyAccessibilityFeatures`|Controlli se la funzionalità di accessibilità, disponibile a partire da .NET Framework 4.7.1 vengono abilitati o disabilitati. | .NET Framework 4.7.1 |
|`Switch.UseLegacyAccessibilityFeatures.2`|Controlli di funzionalità disponibili in .NET Framework 4.7.2 di accessibilità sono abilitate (`false`) o disabilitato (`true`). Se `true`, `Switch.UseLegacyAccessibilityFeatures` deve anche essere `true` per abilitare le funzionalità di accessibilità di .NET Framework 4.7.1.|.NET Framework 4.7.2|
|`Switch.UseLegacyAccessibilityFeatures.3`|Indica se le funzionalità di accessibilità introdotta in .NET Framework 4.8 sono abilitati i controlli (`false`) o disabilitato (`true`). Se `true`, `Switch.UseLegacyAccessibilityFeatures` e `Switch.UseLegacyAccessibilityFeatures.2` deve essere anche `true`.|.NET Framework 4.8|
|`Switch.UseLegacyToolTipDisplay`|Controlli se le descrizioni comando sono displaed quando l'utente posiziona il cursore del mouse su un controllo WPF (`true`), o se vengono visualizzate sia in stato attivo della tastiera e tramite il tasto di scelta rapida da tastiera (`false`, il comportamento predefinito). Per abilitare entrambe le applicazioni in esecuzione in .NET Framework 4.8 ma destinate a versioni precedenti di .NET Framework, lo stato attivo e il supporto di tasti di scelta rapida richiede che `Switch.UseLegacyAccessibilityFeatures`, `Switch.UseLegacyAccessibilityFeatures.2`, e `Switch.UseLegacyAccessibilityFeatures.3` tutti impostati su `false`.|.NET Framework 4.8|
|`System.Xml.`<br /><br /> `IgnoreEmptyKeySequences`|Controlla se le sequenze di tasti vuote nelle chiavi composte vengono ignorate dalla convalida dello schema XSD. Per altre informazioni, vedere [Mitigazione: Convalida di XML Schema](../../../migration-guide/mitigation-xml-schema-validation.md).|.NET Framework 4.6|  
  
> [!NOTE]
>  Invece di aggiungere un `AppContextSwitchOverrides` elemento da un file di configurazione dell'applicazione, è anche possibile impostare le opzioni a livello di codice chiamando il `static` (in c#) o `Shared` (in Visual Basic) <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> (metodo).  
  
 Gli sviluppatori di librerie è anche possono definire opzioni personalizzate per consentire ai chiamanti di rifiutare esplicitamente la funzionalità modificate introdotte nelle versioni più recenti delle librerie. Per altre informazioni, vedere la classe <xref:System.AppContext>.  
  
## <a name="switches-in-aspnet-applications"></a>Opzioni nelle applicazioni ASP.NET

È possibile configurare un'applicazione ASP.NET di usare le impostazioni di compatibilità mediante l'aggiunta di un [ \<Aggiungi >](../../../configure-apps/file-schema/appsettings/add-element-for-appsettings.md) elemento per il [ \<appSettings >](../../../configure-apps/file-schema/appsettings/index.md) sezione del file Web. config. 

L'esempio seguente usa il `<add>` elemento a cui aggiungere le due impostazioni per il `<appSettings>` sezione di un file Web. config:

```xml
<appSettings>
  <add key="AppContext.SetSwitch:Switch.System.Globalization.NoAsyncCurrentCulture" value="true" />
  <add key="AppContext.SetSwitch:Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets" value="true" />
</appSettings>
```

## <a name="example"></a>Esempio

 L'esempio seguente usa il `AppContextSwitchOverrides` elemento per definire un'opzione di compatibilità delle applicazioni singolo, `Switch.System.Globalization.NoAsyncCurrentCulture`, che impedisce le impostazioni cultura che passano attraverso i thread nelle chiamate al metodo asincrona.  
  
```xml  
<configuration>  
   <runtime>  
      <AppContextSwitchOverrides value="Switch.System.Globalization.NoAsyncCurrentCulture=true" />  
   </runtime>  
</configuration>  
```  
  
 L'esempio seguente usa il `AppContextSwitchOverrides` elemento due opzioni di compatibilità dell'applicazione, definire `Switch.System.Globalization.NoAsyncCurrentCulture` e `Switch.System.IO.BlockLongPaths`. Si noti che un punto e virgola separa le due coppie nome/valore.  
  
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
- [\<runtime > elemento](runtime-element.md)
- [\<configurazione > elemento](../configuration-element.md)
