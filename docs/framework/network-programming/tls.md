---
title: Procedure consigliate per Transport Layer Security (TLS) con .NET Framework
description: Descrive le procedure consigliate per l'uso di Transport Layer Security (TLS) con .NET Framework
ms.date: 10/22/2018
helpviewer_keywords:
- sending data, Internet security
- protocols, Internet security
- Network security
- network resources, Internet security
- receiving data, Internet security
- authentication [.NET Framework], Internet security
- Internet, security
- security [.NET Framework], Internet
- permissions [.NET Framework], Internet
ms.openlocfilehash: d1218e5db2ee4fc0ec044c6e0aa16187390708b0
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134393"
---
# <a name="transport-layer-security-tls-best-practices-with-the-net-framework"></a>Procedure consigliate per Transport Layer Security (TLS) con .NET Framework

Il protocollo Transport Layer Security (TLS) è uno standard del settore progettato per proteggere la riservatezza delle informazioni comunicate tramite Internet. [TLS 1.2](https://tools.ietf.org/html/rfc5246) è uno standard che offre miglioramenti per la sicurezza rispetto alle versioni precedenti. TLS 1.2 verrà sostituito dalla versione più recente dello standard, [TLS 1.3](https://tools.ietf.org/html/rfc8446), più veloce e che offre maggiore sicurezza. Questo articolo presenta alcune raccomandazioni per proteggere le applicazioni .NET Framework che usano il protocollo TLS.

Per garantire la sicurezza delle applicazioni .NET Framework, la versione di TLS **non** deve essere hardcoded. Le applicazioni .NET Framework devono usare la versione di TLS supportata dal sistema operativo.

Questo documento è destinato agli sviluppatori che:

- Usano direttamente le API <xref:System.Net> (ad esempio <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> e <xref:System.Net.Security.SslStream?displayProperty=nameWithType>).
- Usano direttamente i client e i servizi WCF tramite lo spazio dei nomi <xref:System.ServiceModel?displayProperty=nameWithType>.

È consigliabile:

- Usare .NET Framework 4.7 o versioni successive come destinazione per le app. Usare .NET Framework 4.7.1 o versioni successive come destinazione per le app WCF.
- Non specificare la versione di TLS. Configurare il codice per consentire al sistema operativo di decidere la versione di TLS.
- Eseguire un controllo esaustivo del codice per assicurarsi che non venga specificata una versione di TLS o SSL.

Quando l'app consente al sistema operativo di scegliere la versione di TLS:

- L'app sfrutta automaticamente i nuovi protocolli aggiunti in futuro, ad esempio TLS 1.3.
- Il sistema operativo blocca i protocolli riscontrati come non sicuri.

La sezione [Controllare il codice e apportare modifiche al codice](#audit-your-code-and-make-code-changes) tratta il controllo e l'aggiornamento del codice.

Questo articolo spiega come abilitare il livello di sicurezza più alto disponibile per la versione di .NET Framework a cui è destinata l'app e in cui viene eseguita. Quando un'app imposta in modo esplicito un protocollo di sicurezza e una versione, rifiuta esplicitamente qualsiasi altra alternativa e il comportamento predefinito di .NET Framework e del sistema operativo. Se si vuole che l'app sia in grado di negoziare una connessione TLS 1.2, l'impostazione esplicita di una versione di TLS precedente impedisce una connessione TLS 1.2.

Se non è possibile evitare di usare una versione del protocollo hardcoded, è consigliabile specificare TLS 1.2. Per istruzioni sull'identificazione e la rimozione delle dipendenze TLS 1.0, scaricare il white paper [Risoluzione del problema TLS 1.0.](https://www.microsoft.com/download/details.aspx?id=55266)

WCF supporta TLS1.0, 1.1 e 1.2 come impostazione predefinita in .NET Framework 4.7. A partire da .NET Framework 4.7.1, WCF usa come predefinita la versione configurata dal sistema operativo. Se un'applicazione è configurata in modo esplicito con `SslProtocols.None`, WCF usa l'impostazione predefinita del sistema operativo quando si usa il trasporto NetTcp.

È possibile porre domande su questo documento nel problema di GitHub [Transport Layer Security (TLS) best practices with the .NET Framework](https://github.com/dotnet/docs/issues/4675) (Procedure consigliate per Transport Layer Security (TLS) con .NET Framework).

## <a name="audit-your-code-and-make-code-changes"></a>Controllare il codice e apportare modifiche al codice

Per le applicazioni ASP.NET, controllare l'elemento `<system.web><httpRuntime targetFramework>` di _Web.config_ per verificare di usare la versione prevista di .NET Framework.

Per Windows Forms e altre applicazioni, vedere [Procedura: Scegliere una versione di .NET Framework di destinazione](/visualstudio/ide/visual-studio-multi-targeting-overview).

Usare le sezioni seguenti per verificare che non sia in uso una versione specifica di TLS o SSL.

## <a name="if-your-app-targets-net-framework-47-or-later-versions"></a>Se l'app è destinata a .NET Framework 4.7 o versioni successive

Le sezioni seguenti illustrano come verificare che non sia in uso una versione specifica di TLS o SSL.

### <a name="for-http-networking"></a>Per reti HTTP

<xref:System.Net.ServicePointManager>, utilizzando .NET Framework 4.7 e versioni successive, verrà utilizzato il protocollo di protezione predefinito configurato nel sistema operativo. Per ottenere l'opzione predefinita del sistema operativo, se <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType> possibile, non impostare un valore per la proprietà, che per impostazione predefinita è <xref:System.Net.SecurityProtocolType.SystemDefault?displayProperty=nameWithType>.

Poiché <xref:System.Net.SecurityProtocolType.SystemDefault?displayProperty=nameWithType> l'impostazione fa sì che l'utilizzo <xref:System.Net.ServicePointManager> del protocollo di protezione predefinito configurato dal sistema operativo, l'applicazione potrebbe essere eseguita in modo diverso in base al sistema operativo in cui viene eseguito. Ad esempio, Windows 7 SP1 utilizza TLS 1.0 mentre Windows 8 e Windows 10 usano TLS 1.2.

Il resto di questo articolo non è pertinente se la destinazione è .NET Framework 4.7 o versioni successive per le reti HTTP.

### <a name="for-tcp-sockets-networking"></a>Per reti TCP Sockets

<xref:System.Net.Security.SslStream>, quando si usano .NET Framework 4.7 e versioni successive, per impostazione predefinita delega al sistema operativo la scelta del protocollo di sicurezza e della versione ottimali. Per ottenere la scelta migliore del sistema operativo predefinita, se possibile, non usare overload di metodo di <xref:System.Net.Security.SslStream> che accettano un parametro <xref:System.Security.Authentication.SslProtocols> esplicito. In caso contrario, passare <xref:System.Security.Authentication.SslProtocols.None?displayProperty=nameWithType>. È consigliabile non usare <xref:System.Security.Authentication.SslProtocols.Default>. L'impostazione `SslProtocols.Default` impone l'uso di SSL 3.0/TLS 1.0 e impedisce l'uso di TLS 1.2.

Non impostare un valore per la proprietà <xref:System.Net.ServicePointManager.SecurityProtocol> (per le reti HTTP).

Non usare overload di metodo di <xref:System.Net.Security.SslStream> che accettano un parametro <xref:System.Security.Authentication.SslProtocols> esplicito (per le reti TCP Sockets). Quando si ridestina l'app a .NET Framework 4.7 o versioni successive, si seguiranno le procedure consigliate.

Il resto di questo argomento non è pertinente se la destinazione è .NET Framework 4.7 o versioni successive per le reti TCP Sockets.

<a name="wcf-tcp-cert"></a>

### <a name="for-wcf-tcp-transport-using-transport-security-with-certificate-credentials"></a>Per il trasporto TCP WCF con sicurezza del trasporto con credenziali del certificato

WCF usa lo stesso stack di rete del resto di .NET Framework.

Se la destinazione è 4.7.1, WCF viene configurato per consentire al sistema operativo di scegliere il protocollo di sicurezza ottimale per impostazione predefinita, a meno che non venga configurato in modo esplicito:

- Nel file di configurazione dell'applicazione.
- **Oppure** nell'applicazione nel codice sorgente.

Per impostazione predefinita, .NET Framework 4.7 e versioni successive sono configurati per l'uso di TLS 1.2 e consentono connessioni tramite TLS 1.1 o TLS 1.0. Configurare WCF per consentire al sistema operativo di scegliere il protocollo di sicurezza ottimale configurando il binding per l'uso di <xref:System.Security.Authentication.SslProtocols.None?displayProperty=nameWithType>. Questa impostazione può essere eseguita in <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols>. `SslProtocols.None` è accessibile da <xref:System.ServiceModel.NetTcpSecurity.Transport>. `NetTcpSecurity.Transport` è accessibile da <xref:System.ServiceModel.NetTcpBinding.Security>.

Se si usa un binding personalizzato:

- Configurare WCF per consentire al sistema operativo di scegliere il protocollo di sicurezza ottimale impostando <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols> per l'uso di <xref:System.Security.Authentication.SslProtocols.None?displayProperty=nameWithType>.
- **Oppure** configurare il protocollo usato con il percorso di configurazione `system.serviceModel/bindings/customBinding/binding/sslStreamSecurity:sslProtocols`.

Se **non** si usa un binding personalizzato **e** si imposta il binding WCF tramite la configurazione, impostare il protocollo usato con il percorso di configurazione `system.serviceModel/bindings/netTcpBinding/binding/security/transport:sslProtocols`.

### <a name="for-wcf-message-security-with-certificate-credentials"></a>Per la sicurezza dei messaggi WCF con le credenziali del certificato

.NET Framework 4.7 e versioni successive usano per impostazione predefinita il protocollo specificato nella proprietà <xref:System.Net.ServicePointManager.SecurityProtocol>. Quando [AppContextSwitch](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) `Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols` è impostato su `true`, WCF sceglie il protocollo ottimale, fino a TLS 1.0.

## <a name="if-your-app-targets-a-net-framework-version-earlier-than-47"></a>Se l'app è destinata a una versione di .NET Framework precedente alla 4.7

Controllare il codice per assicurarsi di non impostare una versione specifica di TLS o SSL usando le sezioni seguenti:

### <a name="for-net-framework-46---462-and-not-wcf"></a>Per .NET Framework 4.6 - 4.6.2 e non WCF

Impostare `DontEnableSystemDefaultTlsVersions` `AppContext` l'interruttore su `false`. Vedere [Configurazione della sicurezza tramite opzioni di AppContext](#configuring-security-via-appcontext-switches).

### <a name="for-wcf-using-net-framework-46---462-using-tcp-transport-security-with-certificate-credentials"></a>Per WCF con .NET Framework 4.6 - 4.6.2 e la sicurezza del trasporto TCP con credenziali del certificato

È necessario installare le patch più recenti del sistema operativo. Vedere [Aggiornamenti della sicurezza](#security-updates).

Il framework WCF sceglie automaticamente il protocollo più alto disponibile fino a TLS 1.2, a meno che non si configuri in modo esplicito una versione del protocollo. Per altre informazioni, vedere la sezione precedente [Per il trasporto TCP WCF con sicurezza del trasporto con credenziali del certificato](#wcf-tcp-cert).

### <a name="for-net-framework-35---452-and-not-wcf"></a>Per .NET Framework 3.5 - 4.5.2 e non WCF

È consigliabile aggiornare l'app a .NET Framework 4.7 o versioni successive. Se non è possibile eseguire l'aggiornamento, procedere come segue.

Impostare le chiavi del Registro di sistema [SchUseStrongCrypto](#schusestrongcrypto) e [SystemDefaultTlsVersions](#systemdefaulttlsversions) su 1. Vedere [Configurazione della sicurezza tramite il Registro di sistema di Windows](#configuring-security-via-the-windows-registry). .NET Framework versione 3.5 supporta il flag `SchUseStrongCrypto` solo quando viene passato un valore esplicito di TLS.

Se l'app è in esecuzione in .NET Framework 3.5, è necessario installare una patch a caldo in modo che TLS 1.2 possa essere specificato dal programma:

| [KB3154518](https://support.microsoft.com/kb/3154518) | Aggiornamento cumulativo per l'affidabilità HR-1605 - Supporto per le versioni predefinite del sistema TLS incluso in .NET Framework 3.5.1 in Windows 7 SP1 e Windows Server 2008 R2 SP1 |
| --- | --- |
| [KB3154519](https://support.microsoft.com/kb/3154519) | Aggiornamento cumulativo per l'affidabilità HR-1605 - Supporto per le versioni predefinite del sistema TLS incluso in .NET Framework 3.5 in Windows Server 2012 |
| [KB3154520](https://support.microsoft.com/kb/3154520) | Aggiornamento cumulativo per l'affidabilità HR-1605 - Supporto per le versioni predefinite del sistema TLS incluso in .NET Framework 3.5 in Windows 8.1 e Windows Server 2012 R2 |
| [KB3156421](https://support.microsoft.com/kb/3156421) | Aggiornamento cumulativo hotfix 1605 3154521 per .NET Framework 4.5.2 e 4.5.1 in Windows |

### <a name="for-wcf-using-net-framework-35---452-using-tcp-transport-security-with-certificate-credentials"></a>Per WCF con .NET Framework 3.5 - 4.5.2 e la sicurezza del trasporto TCP con credenziali del certificato

Queste versioni del framework WCF sono hardcoded per l'uso dei valori SSL 3.0 e TLS 1.0. Questi valori non sono modificabili. È necessario aggiornare e ridestinare a NET Framework 4.6 o versioni successive per l'uso di TLS 1.1 e 1.2.

## <a name="if-your-app-targets-net-framework-35"></a>Se l'app è destinata a .NET Framework 3.5

Se è necessario impostare in modo esplicito un protocollo di sicurezza `SecurityProtocolTypeExtensions` `SslProtocolsExtension` anziché consentire a .NET o al sistema operativo di scegliere il protocollo di sicurezza, aggiungere ed enumerazioni al codice. `SecurityProtocolTypeExtensions` e `SslProtocolsExtension` includono i valori per `Tls12`, `Tls11` e il valore `SystemDefault`. Per ulteriori informazioni, vedere Supporto per le versioni predefinite di [sistema TLS incluse in .NET Framework 3.5 in Windows 8.1 e Windows Server 2012 R2.](https://support.microsoft.com/help/3154520/support-for-tls-system-default-versions-included-in-the--net-framework)

<a name="configuring-security-via-appcontext-switches"></a>

## <a name="configuring-security-via-appcontext-switches-for-net-framework-46-or-later-versions"></a>Configurazione della sicurezza tramite le opzioni di AppContext (per .NET Framework 4.6 o versioni successive)

Le opzioni di [AppContext](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) descritte in questa sezione sono rilevanti se l'app è destinata a, o viene eseguita in .NET Framework 4.6 o versioni successive. Le opzioni devono essere `false` se possibile, per impostazione predefinita o impostandole in modo esplicito. Se si vuole configurare la sicurezza tramite una o entrambe le opzioni, non specificare un valore del protocollo di sicurezza nel codice, perché avrebbe la precedenza rispetto alle opzioni.

Le opzioni hanno lo stesso effetto sia per le reti HTTP (<xref:System.Net.ServicePointManager>) che per le reti TCP Sockets (<xref:System.Net.Security.SslStream>).

### <a name="switchsystemnetdontenableschusestrongcrypto"></a>Switch.System.Net.DontEnableSchUseStrongCrypto

Il valore `false` per `Switch.System.Net.DontEnableSchUseStrongCrypto` imposta l'uso della crittografia avanzata per l'app. Il valore `false` per `DontEnableSchUseStrongCrypto` usa protocolli di rete più sicuri (TLS 1.2, TLS 1.1 e TLS 1.0) e blocca i protocolli non sicuri. Per altre informazioni, vedere [Flag SCH_USE_STRONG_CRYPTO](#the-sch_use_strong_crypto-flag). Il valore `true` disabilita la crittografia avanzata per l'app.

Se l'app è destinata a .NET Framework 4.6 o versioni successive, l'impostazione predefinita di questa opzione è `false`. Si tratta di un'impostazione predefinita sicura, consigliata. Se l'app viene eseguita in .NET Framework 4.6, ma è destinata a una versione precedente, l'impostazione predefinita dell'opzione è `true`. In questo caso, è consigliabile impostarla in modo esplicito su `false`.

`DontEnableSchUseStrongCrypto` deve avere il valore `true` solo se è necessario connettersi a servizi legacy che non supportano la crittografia avanzata e non possono essere aggiornati.

### <a name="switchsystemnetdontenablesystemdefaulttlsversions"></a>Switch.System.Net.DontEnableSystemDefaultTlsVersions

Il valore `false` per `Switch.System.Net.DontEnableSystemDefaultTlsVersions` fa sì che l'app consenta al sistema operativo di scegliere il protocollo. Il valore `true` fa sì che l'app usi i protocolli selezionati da .NET Framework.

Se l'app è destinata a .NET Framework 4.7 o versioni successive, l'impostazione predefinita di questa opzione è `false`. Si tratta di un'impostazione predefinita sicura, consigliata. Se l'app viene eseguita in .NET Framework 4.7 o versioni successive, ma è destinata a una versione precedente, l'impostazione predefinita dell'opzione è `true`. In questo caso, è consigliabile impostarla in modo esplicito su `false`.

### <a name="switchsystemservicemodeldisableusingservicepointmanagersecurityprotocols"></a>Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols

Il valore `false` per `Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols` fa sì che l'applicazione usi il valore definito in `ServicePointManager.SecurityProtocols` per la sicurezza dei messaggi con le credenziali del certificato. Il valore `true` usa il protocollo più alto disponibile, fino a TLS 1.0

Per le applicazioni destinate a .NET Framework 4.7 e versioni successive, l'impostazione predefinita di questo valore è `false`. Per le applicazioni destinate a .NET Framework 4.6.2 e versioni precedenti, l'impostazione predefinita di questo valore è `true`.

### <a name="switchsystemservicemodeldontenablesystemdefaulttlsversions"></a>Switch.System.ServiceModel.DontEnableSystemDefaultTlsVersions

Il valore `false` per `Switch.System.ServiceModel.DontEnableSystemDefaultTlsVersions` imposta la configurazione predefinita per consentire al sistema operativo di scegliere il protocollo. Il valore `true` imposta il valore predefinito sul protocollo più alto disponibile, fino a TLS 1.2.

Per le applicazioni destinate a .NET Framework 4.7.1 e versioni successive, l'impostazione predefinita di questo valore è `false`. Per le applicazioni destinate a .NET Framework 4.7 e versioni precedenti, l'impostazione predefinita di questo valore è `true`.

Per altre informazioni sui protocolli TLS, vedere [Mitigazione: Protocolli TLS](../migration-guide/mitigation-tls-protocols.md). Per ulteriori `AppContext` informazioni sulle [`<AppContextSwitchOverrides> Element`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)opzioni, vedere .

## <a name="configuring-security-via-the-windows-registry"></a>Configurazione della sicurezza tramite il Registro di sistema di Windows

> [!WARNING]
> L'impostazione delle chiavi del Registro di sistema influisce su tutte le applicazioni nel sistema. Usare questa opzione solo se si ha il controllo completo del computer ed è possibile controllare le modifiche apportate al Registro di sistema.

Se l'impostazione di una o entrambe le opzioni di `AppContext` non è praticabile, è possibile controllare i protocolli di sicurezza usati dall'app con le chiavi del Registro di sistema di Windows descritte in questa sezione. L'uso di una o entrambe le opzioni di `AppContext` potrebbe non essere possibile se l'app viene eseguita in .NET Framework 4.5.2 o versioni precedenti oppure se non è possibile modificare il file di configurazione. Se si vuole configurare la sicurezza con il Registro di sistema, non specificare un valore del protocollo di sicurezza nel codice, perché ha la precedenza rispetto all'impostazione del Registro di sistema.

I nomi delle chiavi del Registro di sistema sono simili a quelli delle opzioni `AppContext` corrispondenti, ma senza il prefisso `DontEnable` nel nome. Ad esempio, l'opzione di `AppContext``DontEnableSchUseStrongCrypto` corrisponde alla chiave del Registro di sistema denominata [SchUseStrongCrypto](#schusestrongcrypto).

Queste chiavi sono disponibili in tutte le versioni di .NET Framework per cui è disponibile una patch di sicurezza recente. Vedere [Aggiornamenti della sicurezza](#security-updates).

Tutte le chiavi del Registro di sistema descritte di seguito hanno lo stesso effetto sia per le reti HTTP (<xref:System.Net.ServicePointManager>) che per le reti TCP Sockets (<xref:System.Net.Security.SslStream>).

### <a name="schusestrongcrypto"></a>SchUseStrongCrypto

Il valore della chiave del Registro di sistema `HKEY_LOCAL_MACHINE\SOFTWARE\[Wow6432Node\]Microsoft\.NETFramework\<VERSION>: SchUseStrongCrypto` è di tipo DWORD. Il valore 1 imposta l'uso della crittografia avanzata per l'app. La crittografia avanzata usa protocolli di rete più sicuri (TLS 1.2, TLS 1.1 e TLS 1.0) e blocca i protocolli non sicuri. Un valore pari a 0 disabilita la crittografia avanzata. Per altre informazioni, vedere [Flag SCH_USE_STRONG_CRYPTO](#the-sch_use_strong_crypto-flag).

Se l'app è destinata a .NET Framework 4.6 o versioni successive, il valore predefinito di questa chiave è 1. Si tratta di un'impostazione predefinita sicura, consigliata. Se l'app è destinata a .NET Framework 4.5.2 o versioni precedenti, il valore predefinito della chiave è 0.If your app targets .NET Framework 4.5.2 or earlier versions, the key defaults to 0. In questo caso, è consigliabile impostarla in modo esplicito su 1.

Questa chiave deve avere il valore 0 solo se è necessario connettersi a servizi legacy che non supportano la crittografia avanzata e non possono essere aggiornati.

### <a name="systemdefaulttlsversions"></a>SystemDefaultTlsVersions

Il valore della chiave del Registro di sistema `HKEY_LOCAL_MACHINE\SOFTWARE\[Wow6432Node\]Microsoft\.NETFramework\<VERSION>: SystemDefaultTlsVersions` è di tipo DWORD. Il valore 1 fa sì che l'app consenta al sistema operativo di scegliere il protocollo. Il valore 0 fa sì che l'app usi i protocolli selezionati da .NET Framework.

`<VERSION>` deve essere v4.0.30319 (per .NET Framework 4 e versioni successive) o v2.0.50727 (per .NET Framework 3.5).

Se l'app è destinata a .NET Framework 4.7 o versioni successive, il valore predefinito di questa chiave è 1. Si tratta di un'impostazione predefinita sicura, consigliata. Se l'app è destinata a .NET Framework 4.6.1 o versioni precedenti, il valore predefinito della chiave è 0.If your app targets .NET Framework 4.6.1 or earlier versions, the key defaults to 0. In questo caso, è consigliabile impostarla in modo esplicito su 1.

Per altre informazioni, vedere [Aggiornamento cumulativo per Windows 10 versione 1511 e Windows Server 2016 Technical Preview 4: 10 maggio 2016](https://support.microsoft.com/help/3156421/cumulative-update-for-windows-10-version-1511-and-windows-server-2016).

Per ulteriori informazioni su .NET Framework 3.5.1, vedere Supporto per le versioni predefinite di [sistema TLS incluse in .NET Framework 3.5.1 in Windows 7 SP1 e Server 2008 R2 SP1.](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the--net-framework)

Il file _.REG_ seguente imposta le chiavi del Registro di sistema e le relative varianti sui valori più sicuri:

```text
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\.NETFramework\v2.0.50727]
"SystemDefaultTlsVersions"=dword:00000001
"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\.NETFramework\v4.0.30319]
"SystemDefaultTlsVersions"=dword:00000001
"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v2.0.50727]
"SystemDefaultTlsVersions"=dword:00000001
"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v4.0.30319]
"SystemDefaultTlsVersions"=dword:00000001
"SchUseStrongCrypto"=dword:00000001
```

## <a name="configuring-schannel-protocols-in-the-windows-registry"></a>Configurazione dei protocolli Schannel nel Registro di sistema di Windows

È possibile usare il Registro di sistema per un controllo dettagliato dei protocolli negoziati dall'app client e/o server. Le funzionalità di rete dell'app passano attraverso Schannel (ovvero un nome diverso per [canale sicuro](/windows/desktop/SecAuthN/secure-channel)). Configurando `Schannel` è possibile configurare il comportamento dell'app.

Iniziare con la chiave del Registro di sistema `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols`. In tale chiave è possibile creare qualsiasi sottochiave nel set `SSL 2.0`, `SSL 3.0`, `TLS 1.0`, `TLS 1.1` e `TLS 1.2`. In ognuna di queste sottochiavi, è possibile creare sottochiavi `Client` e/o `Server`. In `Client` e `Server`, è possibile creare valori DWORD `DisabledByDefault` (0 o 1) e `Enabled` (0 o 0xFFFFFFFF).

## <a name="the-sch_use_strong_crypto-flag"></a><a name="the-sch_use_strong_crypto-flag"></a>Flag SCH_USE_STRONG_CRYPTO

Quando è abilitato (per impostazione predefinita, tramite un'opzione di `AppContext` o con il Registro di sistema Windows), .NET Framework usa il flag `SCH_USE_STRONG_CRYPTO` quando l'app richiede un protocollo di sicurezza TLS. Il flag `SCH_USE_STRONG_CRYPTO` può essere abilitato per impostazione predefinita, con l'opzione `AppContext` o con il Registro di sistema. Il sistema operativo passa il flag a `Schannel` per richiedere la disabilitazione degli algoritmi di crittografia vulnerabili noti, dei pacchetti di crittografia e delle versioni del protocollo TLS/SSL che potrebbero essere abilitati in caso contrario, per una migliore interoperabilità. Per altre informazioni, vedere:

- [Canale sicuro](/windows/desktop/SecAuthN/secure-channel)
- [Struttura SCHANNEL_CRED](/windows/win32/api/schannel/ns-schannel-schannel_cred)

Il flag `SCH_USE_STRONG_CRYPTO` viene anche passato a `Schannel` quando si usano in modo esplicito i valori enumerati `Tls` (TLS 1.0), `Tls11` o `Tls12` di <xref:System.Net.SecurityProtocolType> o <xref:System.Security.Authentication.SslProtocols>.

## <a name="security-updates"></a>Aggiornamenti per la sicurezza

Le procedure consigliate in questo articolo dipendono dagli aggiornamenti della sicurezza installati. Questi aggiornamenti includono la possibilità di usare funzionalità avanzate di .NET Framework 4.7 e versioni successive. Gli aggiornamenti della sicurezza recenti sono importanti se l'app viene eseguita in .NET Framework 4.7 e versioni successive (anche se è destinata a una versione precedente).

Per aggiornare .NET Framework per consentire al sistema operativo scegliere la versione migliore di TLS da usare, è necessario installare almeno:

- [.NET Framework August 2017 Preview of Quality Rollup](https://devblogs.microsoft.com/dotnet/net-framework-august-2017-preview-of-quality-rollup/) (Aggiornamento cumulativo per la qualità in anteprima di .NET Framework agosto 2017).
- **Oppure**[.NET Framework September 2017 Security and Quality Rollup](https://devblogs.microsoft.com/dotnet/net-framework-september-2017-security-and-quality-rollup/) (Aggiornamento cumulativo per la sicurezza e la qualità di .NET Framework settembre 2017).

Vedere anche la pagina relativa alla

- [Versioni e dipendenze di .NET Framework](../migration-guide/versions-and-dependencies.md)
- [Procedura: determinare quali versioni di .NET Framework sono installate.](../migration-guide/how-to-determine-which-versions-are-installed.md)

## <a name="support-for-tls-12"></a>Supporto per TLS 1.2

Per consentire all'app di negoziare TLS 1.2, il sistema operativo e la versione di .NET Framework devono entrambi supportare TLS 1.2.

**Requisiti del sistema operativo per il supporto di TLS 1.2**

Per abilitare o riabilitare TLS 1.2 e/o TLS 1.1 in un sistema che li supporta, vedere [Impostazioni del Registro di sistema di Transport Layer Security (TLS)](/windows-server/security/tls/tls-registry-settings).

| **Os** | **Supporto tls 1.2** |
| --- | --- |
| Windows 10<br>Windows Server 2016 | Supportato e abilitato per impostazione predefinita. |
| Windows 8.1<br>Windows Server 2012 R2 | Supportato e abilitato per impostazione predefinita. |
| Windows 8.0<br>Windows Server 2012 | Supportato e abilitato per impostazione predefinita. |
| Windows 7 SP1<br>Windows Server 2008 R2 SP1 | Supportato ma non abilitato per impostazione predefinita. Vedere la pagina Web [Impostazioni del Registro di sistema di Transport Layer Security (TLS)](/windows-server/security/tls/tls-registry-settings) per informazioni dettagliate su come abilitare TLS 1.2. |
| Windows Server 2008 | Il supporto per TLS 1.1 e TLS 1.2 richiede un aggiornamento. Vedere [Aggiornamento per aggiungere il supporto per TLS 1.1 e TLS 1.2 in Windows Server 2008 SP2](https://support.microsoft.com/help/4019276/update-to-add-support-for-tls-1-1-and-tls-1-2-in-windows-server-2008-s). |
| Windows Vista | Non supportato. |

Per informazioni su quali protocolli TLS/SSL sono abilitati per impostazione predefinita in ogni versione di Windows, vedere [Protocols in TLS/SSL (Schannel SSP)](/windows/desktop/SecAuthN/protocols-in-tls-ssl--schannel-ssp-) (Protocolli in TLS/SSL - Schannel SSP).

**Requisiti per il supporto di TLS 1.2 con .NET Framework 3.5**

Questa tabella mostra l'aggiornamento del sistema operativo che è necessario per il supporto di TLS 1.2 con .NET Framework 3.5. Si consiglia di applicare tutti gli aggiornamenti del sistema operativo.

| **Os** | **Aggiornamento minimo necessario per supportare TLS 1.2 con .NET Framework 3.5** |
| --- | --- |
| Windows 10<br>Windows Server 2016 | [Aggiornamento cumulativo per Windows 10 versione 1511 e Windows Server 2016 Technical Preview 4: 10 maggio 2016](https://support.microsoft.com/help/3156421/cumulative-update-for-windows-10-version-1511-and-windows-server-2016) |
| Windows 8.1<br>Windows Server 2012 R2 | [Supporto per le versioni predefinite del sistema TLS incluso in .NET Framework 3.5 in Windows 8.1 e Windows Server 2012 R2](https://support.microsoft.com/help/3154520/support-for-tls-system-default-versions-included-in-the--net-framework) |
| Windows 8.0<br>Windows Server 2012 | [Supporto per le versioni predefinite del sistema TLS incluso in .NET Framework 3.5 in Windows Server 2012](https://support.microsoft.com/help/3154519/support-for-tls-system-default-versions-included-in-the--net-framework) |
| Windows 7 SP1<br>Windows Server 2008 R2 SP1 | [Supporto per le versioni predefinite del sistema TLS incluso in .NET Framework 3.5.1 in Windows 7 SP1 e Windows Server 2008 R2 SP1](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the--net-framework) |
| Windows Server 2008 | [Supporto per le versioni predefinite del sistema TLS incluso in .NET Framework 2.0 SP2 in Windows Vista SP2 e Windows Server 2008 SP2](https://support.microsoft.com/help/3154517/support-for-tls-system-default-versions-included-in-the--net-framework) |
| Windows Vista | Non supportate |
