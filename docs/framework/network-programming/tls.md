---
title: Transport Layer Security (TLS) le procedure consigliate con .NET Framework
description: Descrive le procedure consigliate usando Transport Layer Security (TLS) con .NET Framework
ms.date: 03/15/2018
ms.prod: .net-framework
ms.topic: article
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
author: blowdart
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 64829eee5b21a44acb18cbec9b901d77d49cab90
ms.sourcegitcommit: 3eea47bff3201ae5d3395b0c7947806c2faca255
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/16/2018
---
# <a name="transport-layer-security-tls-best-practices-with-the-net-framework"></a>Transport Layer Security (TLS) le procedure consigliate con .NET Framework

Il protocollo Transport Layer Security (TLS) è uno standard del settore progettata per proteggere la riservatezza delle informazioni comunicate tramite Internet. [TLS 1.2](https://tools.ietf.org/html/rfc5246) è lo standard rilasciato più recente e fornisce miglioramenti della sicurezza rispetto alle versioni precedenti. TLS 1.2 verrà sostituita da [TLS 1.3](https://tools.ietf.org/html/draft-ietf-tls-tls13-22). In questo articolo offre delle raccomandazioni per proteggere le applicazioni .NET Framework che usano il protocollo TLS.

Per garantire le applicazioni .NET Framework rimangano sicura, TLS versione dovrebbe **non** essere hardcoded. Le applicazioni .NET framework devono utilizzare la versione TLS che supporta il sistema operativo (sistema operativo).

Questo documento è destinata agli sviluppatori che sono:

- Direttamente tramite il <xref:System.Net> API (ad esempio <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> e <xref:System.Net.Security.SslStream?displayProperty=nameWithType>).
- Utilizzare direttamente i client WCF e servizi che usano il <xref:System.ServiceModel?displayProperty=nameWithType> dello spazio dei nomi.
- Utilizzo [servizi Cloud di Azure](https://azure.microsoft.com/services/cloud-services/) ruoli Web e di lavoro per ospitare ed eseguire l'applicazione. Vedere la [servizi Cloud di Azure](#azure-cloud-services) sezione.

È consigliabile che è:

- .NET Framework 4.7 o versioni successive nelle app di destinazione. .NET Framework di destinazione 4.7.1 o versioni successive nelle App WCF.
- Non si specifica la versione TLS. Configurare il codice per consentire il sistema operativo a decidere in TLS versione.
- Esecuzione di un controllo di codice completo per verificare che non si specifica una versione TLS o SSL.

Quando l'app consente il sistema operativo sceglie TLS versione:

- Automaticamente sfrutta di nuovi protocolli aggiunto in futuro, ad esempio TLS 1.3.
- Il sistema operativo consente di bloccare i protocolli che vengono individuati non deve essere protetta.

La sezione [il controllo del codice e apportare modifiche al codice](#audit-your-code-and-make-code-changes) riguarda il controllo e aggiornamento del codice.

In questo articolo viene illustrato come abilitare il livello di protezione disponibile per la versione di .NET Framework che l'app ha come destinazione e viene eseguito in. Quando un'applicazione imposta in modo esplicito un protocollo di sicurezza e la versione, Rifiuta esplicitamente di qualsiasi altra alternativa e rifiuta esplicitamente il comportamento predefinito di .NET Framework e del sistema operativo. Se si vuole che l'app in grado di negoziare una connessione TLS 1.2, impostare in modo esplicito a una versione inferiore TLS impedisce una connessione TLS 1.2.

Se non è possibile evitare una versione del protocollo a livello di codice, è consigliabile specificare TLS 1.2. Per informazioni dettagliate sull'identificazione e rimozione di dipendenze di TLS 1.0, scaricare il [risoluzione del problema di TLS 1.0](https://www.microsoft.com/download/details.aspx?id=55266) white paper.

WCF supporta TLS1.0, 1.1 e 1.2 come impostazione predefinita in .NET Framework 4.7. A partire da .NET Framework 4.7.1, valori predefiniti WCF per il sistema operativo configurato versione. Se un'applicazione è configurata in modo esplicito con `SslProtocols.None`, WCF utilizza l'impostazione predefinita del sistema operativo quando si utilizza il trasporto NetTcp.

È possibile porre domande su questo documento il problema di GitHub [consigliate Transport Layer Security (TLS) con .NET Framework](https://github.com/dotnet/docs/issues/4675).

## <a name="audit-your-code-and-make-code-changes"></a>Il controllo del codice e apportare modifiche al codice

Per le applicazioni ASP.NET, controllare la `<system.web><httpRuntime targetFramework>` elemento di _Web. config_ per verificare la versione desiderata di .NET Framework in uso.

Per Windows Form e altre applicazioni, vedere [procedura: destinare una versione di .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).

Usare le sezioni seguenti per verificare che non si usa una versione specifica di TLS o SSL.

## <a name="if-your-app-targets-net-framework-47-or-later-versions"></a>Se l'app è destinata a .NET Framework 4.7 o versioni successive

Nelle sezioni seguenti viene illustrato come verificare che non si usa una versione specifica di TLS o SSL.

### <a name="for-http-networking"></a>Per la rete HTTP

<xref:System.Net.ServicePointManager>, utilizzando .NET Framework 4.7 e versioni successive, per impostazione predefinita il sistema operativo scegliendo il protocollo di protezione ottimale e la versione. Per ottenere la scelta migliore del sistema operativo predefinita, se possibile, non impostare un valore per il <xref:System.Net.ServicePointManager.SecurityProtocol> proprietà. In caso contrario, impostarlo su <xref:System.Net.SecurityProtocolType.SystemDefault>.

Il resto di questo articolo non è pertinente quando la destinazione è .NET Framework 4.7 o versioni successive per la rete HTTP.

### <a name="for-tcp-sockets-networking"></a>Per i socket TCP di rete

<xref:System.Net.Security.SslStream>, utilizzando .NET Framework 4.7 e versioni successive, per impostazione predefinita il sistema operativo scegliendo il protocollo di protezione ottimale e la versione. Per ottenere la scelta migliore del sistema operativo predefinita, se possibile, non utilizzare l'overload del metodo di <xref:System.Net.Security.SslStream> che accetta un oggetto esplicito <xref:System.Security.Authentication.SslProtocols> parametro. In caso contrario, passare <xref:System.Security.Authentication.SslProtocols.None?displayProperty=nameWithType>. È consigliabile non utilizzare <xref:System.Security.Authentication.SslProtocols.Default>; impostazione `SslProtocols.Default` impone l'utilizzo di SSL 3.0 /TLS 1.0 ed evitare TLS 1.2.

Non impostare un valore per il <xref:System.Net.ServicePointManager.SecurityProtocol> proprietà (per il collegamento in rete HTTP).

Non utilizzare l'overload del metodo di <xref:System.Net.Security.SslStream> che accetta un oggetto esplicito <xref:System.Security.Authentication.SslProtocols> parametro (per i socket TCP networking). Quando si Ridestina l'app per .NET Framework 4.7 o versioni successive, è possibile che si sarà seguendo la procedura consigliata.

Il resto di questo argomento non è pertinente quando destinato a .NET Framework 4.7 o versioni successive per TCP socket di rete.

<a name="wcf-tcp-cert"></a>

### <a name="for-wcf-tcp-transport-using-transport-security-with-certificate-credentials"></a>Per TCP WCF di trasporto tramite la sicurezza del trasporto con le credenziali del certificato

WCF Usa lo stesso stack di rete del resto di .NET Framework.

Se la destinazione è 4.7.1, WCF è configurato per consentire al sistema operativo di scegliere il protocollo di protezione ottimale per impostazione predefinita, a meno che non configurata in modo esplicito:

- Nel file di configurazione dell'applicazione.
- **O**, nell'applicazione in uso nel codice sorgente.

Per impostazione predefinita, .NET Framework 4.7 e versioni successive è configurato per l'utilizzo di TLS 1.2 e consente le connessioni che utilizzano TLS 1.1 o TLS 1.0. Configurare WCF per consentire al sistema operativo di scegliere il protocollo di sicurezza ottimale configurando l'associazione da utilizzare <xref:System.Security.Authentication.SslProtocols.None?displayProperty=nameWithType>. Può essere impostata su <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols>. `SslProtocols.None` è possibile accedere da <xref:System.ServiceModel.NetTcpSecurity.Transport>. `NetTcpSecurity.Transport` è possibile accedere da <xref:System.ServiceModel.NetTcpBinding.Security>.

Se si utilizza un'associazione personalizzata:

- Configurare WCF per consentire al sistema operativo di scegliere il protocollo di sicurezza ottimale impostando <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols> da utilizzare <xref:System.Security.Authentication.SslProtocols.None?displayProperty=nameWithType>.
- **O** configurare il protocollo utilizzato con il percorso di configurazione `system.serviceModel/bindings/customBinding/binding/sslStreamSecurity:sslProtocols`.

Se si **non** utilizzando un'associazione personalizzata **e** si imposta il binding WCF utilizzando la configurazione, impostare il protocollo utilizzato con il percorso di configurazione `system.serviceModel/bindings/netTcpBinding/binding/security/transport:sslProtocols`.

### <a name="for-wcf-message-security-with-certificate-credentials"></a>Per la sicurezza dei messaggi WCF con le credenziali del certificato

.NET framework 4.7 e versioni successive per impostazione predefinita viene utilizzato il protocollo specificato nella <xref:System.Net.ServicePointManager.SecurityProtocol> proprietà. Quando il [AppContextSwitch](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) `Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols` è impostata su `true`, WCF sceglie il protocollo ottimale, fino a TLS 1.0.

## <a name="if-your-app-targets-a-net-framework-version-earlier-than-47"></a>Se l'app è destinata una versione di .NET Framework precedenti a 4.7

Controllo del codice per verificare che non si sta impostando una versione specifica di TLS o SSL utilizzando le sezioni seguenti:

### <a name="for-net-framework-46---462-and-not-wfc"></a>Per .NET Framework 4.6 - 4.6.2 e non WFC

Impostare il `DontEnableSystemDefaultTlsVersions` `AppContext` passa a `false`. Vedere [configurazione della protezione tramite commutatori AppContext](#configuring-security-via-appcontext-switches).

### <a name="for-wcf-using-net-framework-46---462-using-tcp-transport-security-with-certificate-credentials"></a>Per WCF utilizzando .NET Framework 4.6 - 4.6.2 utilizzando sicurezza del trasporto TCP con le credenziali del certificato

È necessario installare la patch più recente del sistema operativo. Vedere [gli aggiornamenti della sicurezza](#security-updates).

Il framework WCF sceglie automaticamente il protocollo più alto disponibile fino a TLS 1.2, a meno che non è configurato in modo esplicito una versione del protocollo. Per altre informazioni, vedere la sezione precedente [trasporto per TCP WCF utilizzando la sicurezza del trasporto con le credenziali del certificato](#wcf-tcp-cert).

### <a name="for-net-framework-35---451-and-not-wcf"></a>Per .NET Framework 3.5 - 4.5.1 e non WCF

È consigliabile che aggiornare l'app a .NET Framework 4.7 o versioni successive. Se non è possibile aggiornare, procedere come segue. A un certo punto in futuro, l'applicazione potrebbe non riuscire finché l'aggiornamento a .NET Framework 4.7 o versioni successive.

Impostare il [SchUseStrongCrypto](#schusestrongcrypto) e [SystemDefaultTlsVersions](#systemdefaulttlsversions) le chiavi del Registro di sistema su 1. Vedere [configurazione della protezione tramite il Registro di sistema di Windows](#configuring-security-via-the-windows-registry). .NET Framework versione 3.5 supporta il `SchUseStrongCrypto` flag solo quando viene passato un valore esplicito di TLS.

Se si eseguono in .NET Framework 3.5, è necessario installare una patch a caldo in modo che TLS 1.2 possono essere specificate tramite il programma:

| [KB3154518](https://support.microsoft.com/kb/3154518) | Affidabilità Rollup delle risorse Umane-1605 - supporto per le versioni predefinite di sistema TLS incluso in .NET Framework 3.5.1 in Windows 7 SP1 e Server 2008 R2 SP1 |
| --- | --- |
| [KB3154519](https://support.microsoft.com/kb/3154519) | Affidabilità Rollup delle risorse Umane-1605 - supporto per TLS predefinito versioni del sistema incluso in .NET Framework 3.5 in Windows Server 2012 |
| [KB3154520](https://support.microsoft.com/kb/3154520) | Affidabilità Rollup delle risorse Umane-1605 - supporto per le versioni predefinite di sistema TLS incluso in .NET Framework 3.5 in Windows 8.1 e Windows Server 2012 R2 |
| [KB3156421](https://support.microsoft.com/kb/3156421) | 1605 Hotfix rollup 3154521 per .NET Framework 4.5.2 e 4.5.1 in Windows |

### <a name="for-wcf-using-net-framework-35---452-using-tcp-transport-security-with-certificate-credentials"></a>Per WCF utilizzando .NET Framework 3.5 - 4.5.2 utilizzando sicurezza del trasporto TCP con le credenziali del certificato

Queste versioni di framework WCF sono hardcoded per utilizzare valori SSL 3.0 e TLS 1.0. Non è possibile modificare questi valori. È necessario aggiornare e Ridestina a NET Framework 4.6 o versioni successive usare TLS 1.1 e 1.2.

## <a name="if-your-app-targets-net-framework-35"></a>Se l'app è destinata a .NET Framework 3.5

Se è necessario impostare esplicitamente un protocollo di sicurezza anziché consentire a .NET framework o la selezione del sistema operativo il protocollo di sicurezza, aggiungere `SecurityProtocolTypeExtensions` e `SslProtocolsExtension` enumerazioni al codice. `SecurityProtocolTypeExtensions` e `SslProtocolsExtension` includono i valori per `Tls12`, `Tls11`e il `SystemDefault` valore. Vedere [supporto per TLS predefinito versioni del sistema incluso in .NET Framework 3.5 in Windows 8.1 e Windows Server 2012 R2](https://support.microsoft.com/help/3154520/support-for-tls-system-default-versions-included-in-the--net-framework).

<a name="configuring-security-via-appcontext-switches"></a>

## <a name="configuring-security-via-appcontext-switches-for-net-framework-46-or-later-versions"></a>Configurazione della protezione tramite AppContext cambi (per .NET Framework 4.6 o versioni successive)

Il [AppContext](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) opzioni descritte in questa sezione sono rilevanti se l'app sia destinata a, o viene eseguita in .NET Framework 4.6 o versioni successive. Se per impostazione predefinita, oppure impostarle in modo esplicito, le opzioni devono essere `false` se possibile. Se si desidera configurare la sicurezza tramite uno o più commutatori, non specificare un valore del protocollo di sicurezza nel codice. In tal modo sostituirebbe gli switch.

I parametri hanno lo stesso effetto se si sta eseguendo operazioni in rete HTTP (<xref:System.Net.ServicePointManager>) o TCP socket di rete (<xref:System.Net.Security.SslStream>).

### <a name="switchsystemnetdontenableschusestrongcrypto"></a>Switch.System.Net.DontEnableSchUseStrongCrypto

Il valore `false` per `Switch.System.Net.DontEnableSchUseStrongCrypto` fa sì che l'app da usare la crittografia avanzata. Il valore `false` per `DontEnableSchUseStrongCrypto` utilizza protocolli di rete più sicuri (TLS 1.2, TLS 1.1 e TLS 1.0) e blocca i protocolli che non sono protette. Per ulteriori informazioni, vedi [flag SCH_USE_STRONG_CRYPTO il](#the-schusestrongcrypto-flag). Il valore `true` disabilita la crittografia avanzata per l'app.

Se l'app è destinata a .NET Framework 4.6 o versioni successive, questa opzione è attivata per impostazione predefinita `false`. Che è un valore predefinito sicuro, è consigliabile. Se l'app viene eseguita su .NET Framework 4.6, ma ha come destinazione una versione precedente, il commutatore predefinito `true`. In tal caso, è consigliabile impostare in modo esplicito tale `false`.

`DontEnableSchUseStrongCrypto` deve contenere solo un valore di `true` se si desidera connettersi a servizi legacy che non supportano la crittografia avanzata e non possono essere aggiornati.

### <a name="switchsystemnetdontenablesystemdefaulttlsversions"></a>Switch.System.Net.DontEnableSystemDefaultTlsVersions

Il valore `false` per `Switch.System.Net.DontEnableSystemDefaultTlsVersions` fa sì che l'app consentire al sistema operativo scegliere il protocollo. Il valore `true` fa sì che l'app può usare i protocolli selezionati da .NET Framework.

Se l'app è destinata a .NET Framework 4.7 o versioni successive, questa opzione è attivata per impostazione predefinita `false`. Che è un valore predefinito sicuro che è consigliabile. Se l'app viene eseguita in .NET Framework 4.7 o versioni successive, ma ha come destinazione una versione precedente, il commutatore predefinito `true`. In tal caso, è consigliabile impostare in modo esplicito tale `false`.

### <a name="switchsystemservicemodeldisableusingservicepointmanagersecurityprotocols"></a>Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols

Il valore `false` per `Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols` fa sì che l'applicazione per utilizzare il valore definito `ServicePointManager.SecurityProtocols` per la sicurezza dei messaggi con le credenziali del certificato. Il valore `true` utilizza il protocollo più alto disponibile, fino a TLS1.0

Per le applicazioni destinate a .NET Framework 4.7 e versioni successive, il valore predefinito `false`. Per applicazioni destinate a .NET Framework 4.6.2 e versioni precedenti, il valore predefinito `true`.

### <a name="switchsystemservicemodeldontenablesystemdefaulttlsversions"></a>Switch.System.ServiceModel.DontEnableSystemDefaultTlsVersions

Il valore `false` per `Switch.System.ServiceModel.DontEnableSystemDefaultTlsVersions` imposta la configurazione predefinita per consentire al sistema operativo scegliere il protocollo. Il valore `true` imposta il valore predefinito per il protocollo più alto disponibile, fino a TLS1.2.

Per le applicazioni destinate a .NET Framework 4.7.1 e versioni successive, il valore predefinito `false`. Per applicazioni destinate a .NET Framework 4,7 e versioni precedenti, il valore predefinito per `true`.

Per ulteriori informazioni sui protocolli TLS, vedere [mitigazione: protocolli TLS](../migration-guide/mitigation-tls-protocols.md). Per ulteriori informazioni `AppContext` commutatori, vedere [ `<AppContextSwitchOverrides> Element` ](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).

## <a name="configuring-security-via-the-windows-registry"></a>Configurazione della protezione tramite il Registro di sistema di Windows

Se l'impostazione di uno o entrambi `AppContext` le opzioni non sono un'opzione, è possibile controllare i protocolli di sicurezza utilizzato dall'app con le chiavi del Registro di sistema di Windows descritte in questa sezione. Potrebbe non essere in grado di utilizzare uno o entrambi i `AppContext` passa l'app è destinata una versione di .NET Framework precedenti a 4.6, se non è possibile modificare il file di configurazione. Se si desidera configurare la sicurezza del Registro di sistema, non specificare un valore del protocollo di sicurezza nel codice. tale operazione così sostituirebbe il Registro di sistema.

I nomi delle chiavi del Registro di sistema sono simili a quelli dei corrispondenti `AppContext` passa ma senza un `DontEnable` anteposto al nome. Ad esempio, il `AppContext` switch `DontEnableSchUseStrongCrypto` è la chiave del Registro di sistema denominata [SchUseStrongCrypto](#schusestrongcrypto).

Queste chiavi sono disponibili in tutte le versioni di .NET Framework per cui è disponibile una recente patch di sicurezza. Vedere [gli aggiornamenti della sicurezza](#security-updates).

Tutte le chiavi del Registro di sistema descritte di seguito hanno lo stesso effetto se si sta eseguendo operazioni in rete HTTP (<xref:System.Net.ServicePointManager>) o TCP socket di rete (<xref:System.Net.Security.SslStream>).

### <a name="schusestrongcrypto"></a>SchUseStrongCrypto

Il `HKEY_LOCAL_MACHINE\SOFTWARE\[Wow6432Node\]Microsoft\.NETFramework\<VERSION>: SchUseStrongCrypto` chiave del Registro di sistema ha un valore di tipo DWORD. Un valore pari a 1, dell'app per usare la crittografia avanzata. La crittografia avanzata utilizza protocolli di rete più sicuri (TLS 1.2, TLS 1.1 e TLS 1.0) e blocca i protocolli che non sono protette. Un valore pari a 0 disabilita la crittografia avanzata. Per altre informazioni, vedere [flag SCH_USE_STRONG_CRYPTO il](#the-schusestrongcrypto-flag).

Se l'app è destinata a .NET Framework 4.6 o versioni successive, questa chiave impostazione predefinita su un valore pari a 1. Che è un valore predefinito sicuro che è consigliabile. Se l'app viene eseguita su .NET Framework 4.6, ma ha come destinazione una versione precedente, quindi la chiave di valore predefinito è 0. In tal caso, è necessario impostare esplicitamente il relativo valore su 1.

Questa chiave deve avere solo un valore pari a 0 se si desidera connettersi a servizi legacy che non supportano la crittografia avanzata e non possono essere aggiornati.

### <a name="systemdefaulttlsversions"></a>SystemDefaultTlsVersions

Il `HKEY_LOCAL_MACHINE\SOFTWARE\[Wow6432Node\]Microsoft\.NETFramework\<VERSION>: SystemDefaultTlsVersions` chiave del Registro di sistema ha un valore di tipo DWORD. Un valore pari a 1 fa sì che l'app consentire al sistema operativo scegliere il protocollo. Un valore pari a 0 fa sì che l'app può usare i protocolli selezionati da .NET Framework.

`<VERSION>` deve essere v4.0.30319 (per .NET Framework 4 e versioni successive) o v2.0.50727 (per .NET Framework 3.5).

Se l'app è destinata a .NET Framework 4.7 o versioni successive, questa chiave sarà un valore pari a 1. Che è un valore predefinito sicuro che è consigliabile. Se l'app viene eseguita in .NET Framework 4.7 o versioni successive, ma ha come destinazione una versione precedente, la chiave di valore predefinito è 0. In tal caso, è necessario impostare esplicitamente il relativo valore su 1.

Per ulteriori informazioni, vedi [Cumulative Update per Windows 10 versione 1511 e Windows Server 2016 Technical Preview 4: 10 maggio 2016](https://support.microsoft.com/help/3156421/cumulative-update-for-windows-10-version-1511-and-windows-server-2016).

Per altre informazioni con .NET framework 3.5.1, vedere [supporto per TLS predefinito versioni del sistema incluso in .NET Framework 3.5.1 in Windows 7 SP1 e Server 2008 R2 SP1](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the--net-framework).

Nell'esempio _. REG_ file imposta le chiavi del Registro di sistema e dalle relative varianti in base ai valori più sicuro:

```
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

## <a name="configuring-schannel-protocols-in-the-windows-registry"></a>Configurazione dei protocolli Schannel nel Registro di sistema Windows

È possibile utilizzare il Registro di sistema per un controllo accurato i protocolli che negozia l'app client e/o server. Funzionalità di rete dell'app passa attraverso Schannel (ovvero un nome diverso per [Secure Channel](https://msdn.microsoft.com/library/windows/desktop/aa380123). Configurando `Schannel`, è possibile configurare il comportamento dell'app.

Iniziare con il `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols` chiave del Registro di sistema. In tale chiave è possibile creare tutte le sottochiavi nel set `SSL 2.0`, `SSL 3.0`, `TLS 1.0`, `TLS 1.1`, e `TLS 1.2`. In ognuno di tali sottochiavi, è possibile creare sottochiavi `Client` e/o `Server`. Sotto `Client` e `Server`, è possibile creare valori DWORD `DisabledByDefault` (0 o 1) e `Enabled` (0 o 0xFFFFFFFF).

## <a name="the-schusestrongcrypto-flag"></a>Il flag SCH_USE_STRONG_CRYPTO

Quando è abilitata (per impostazione predefinita, da un `AppContext` cambiare, o dal Registro di sistema Windows), .NET Framework Usa il `SCH_USE_STRONG_CRYPTO` flag quando l'app richiede un protocollo di sicurezza TLS. Il `SCH_USE_STRONG_CRYPTO` flag può essere abilitata per impostazione predefinita, con la `AppContext` tornare, o il Registro di sistema. Il sistema operativo passa il flag su `Schannel`per fare in modo che disabilita algoritmi di crittografia vulnerabili noti, pacchetti di crittografia Suite e versioni del protocollo TLS/SSL che potrebbero essere attivate in caso contrario, per una migliore interoperabilità. Per altre informazioni, vedere:

- [Canale sicuro](https://msdn.microsoft.com/library/windows/desktop/aa380123)
- [Struttura SCHANNEL_CRED](https://msdn.microsoft.com/library/windows/desktop/aa379810)

Il `SCH_USE_STRONG_CRYPTO` flag viene passato anche a `Schannel` quando si utilizza in modo esplicito il `Tls` (TLS 1.0), `Tls11`, o `Tls12` dei valori enumerati <xref:System.Net.SecurityProtocolType> o <xref:System.Security.Authentication.SslProtocols>.

## <a name="security-updates"></a>Aggiornamenti della sicurezza

Le procedure consigliate in questo articolo dipendono dal recenti aggiornamenti della sicurezza in fase di installazione. Questi aggiornamenti includono la possibilità di usare avanzate .NET Framework 4.7 e le funzionalità di versioni successive. Aggiornamenti recenti sono importanti se l'app viene eseguita in .NET Framework 4.7 e versioni successive (anche se è destinato a una versione precedente).

Per aggiornare .NET Framework per consentire al sistema operativo scegliere la versione migliore di TLS da usare, è necessario installare almeno:

- Il [anteprima di agosto 2017 .NET Framework di qualità Rollup](https://blogs.msdn.microsoft.com/dotnet/2017/08/16/net-framework-august-2017-preview-of-quality-rollup).
- **O** il [Rollup qualità e sicurezza di .NET Framework 2017 settembre](https://blogs.msdn.microsoft.com/dotnet/2017/09/12/net-framework-september-2017-security-and-quality-rollup).

Vedere anche:

- [Versioni di .NET framework e dipendenze](../migration-guide/versions-and-dependencies.md)
- [Procedura: determinare quali versioni di .NET Framework installate](../migration-guide/how-to-determine-which-versions-are-installed.md).

## <a name="support-for-tls-12"></a>Supporto per TLS 1.2

Per l'app per la negoziazione di TLS 1.2, il sistema operativo e la versione di .NET Framework sia da supportare TLS 1.2.

**Requisiti del sistema operativo per il supporto di TLS 1.2**

Per attivare o riattivare TLS 1.2 e/o TLS 1.1 in un sistema che li supporta, vedere [le impostazioni del Registro di sistema di sicurezza TLS (Transport Layer)](/windows-server/security/tls/tls-registry-settings).

| **OS** | **Supporto di TLS 1.2** |
| --- | --- |
| Windows 10</br>Windows Server 2016 | Supportato e attivato per impostazione predefinita. |
| Windows 8,1</br>Windows Server 2012 R2 | Supportato e attivato per impostazione predefinita. |
| Windows 8.0</br>Windows Server 2012 | Supportato e attivato per impostazione predefinita. |
| Windows 7 SP1</br>Windows Server 2008 R2 SP1 | Supportato, ma non abilitato per impostazione predefinita. Vedere la [le impostazioni del Registro di sistema di sicurezza TLS (Transport Layer)](/windows-server/security/tls/tls-registry-settings) pagina web per informazioni dettagliate su come abilitare TLS 1.2. |
| Windows Server 2008 | Supporto per TLS 1.1 e TLS 1.2 richiede un aggiornamento. Vedere [aggiornamento da aggiungere il supporto di TLS 1.1 e TLS 1.2 in Windows Server 2008 SP2](https://support.microsoft.com/help/4019276/update-to-add-support-for-tls-1-1-and-tls-1-2-in-windows-server-2008-s). |
| Windows Vista | Non supportato. |

Per informazioni su quali TLS/SSL protocolli siano abilitati per impostazione predefinita in ogni versione di Windows, vedere [i protocolli TLS/SSL (SSP Schannel)](https://msdn.microsoft.com/library/windows/desktop/mt808159).

**Requisiti per il supporto di TLS 1.2 con .NET Framework 3.5**

Questa tabella mostra l'aggiornamento del sistema operativo che è necessario supportare TLS 1.2 con .NET Framework 3.5. Si consiglia di che applicare tutti gli aggiornamenti del sistema operativo.

| **OS** | **Aggiornamento minimo necessario per supportare TLS 1.2 con .NET Framework 3.5** |
| --- | --- |
| Windows 10</br>Windows Server 2016 | [Aggiornamento cumulativo per Windows 10 versione 1511 e Windows Server 2016 Technical Preview 4: 10 maggio 2016](https://support.microsoft.com/help/3156421/cumulative-update-for-windows-10-version-1511-and-windows-server-2016) |
| Windows 8,1</br>Windows Server 2012 R2 | [Supporto per TLS predefinito versioni del sistema incluso in .NET Framework 3.5 in Windows 8.1 e Windows Server 2012 R2](https://support.microsoft.com/help/3154520/support-for-tls-system-default-versions-included-in-the--net-framework) |
| Windows 8.0</br>Windows Server 2012 | [Supporto per TLS predefinito versioni del sistema incluso in .NET Framework 3.5 in Windows Server 2012](https://support.microsoft.com/help/3154519/support-for-tls-system-default-versions-included-in-the--net-framework) |
| Windows 7 SP1</br>Windows Server 2008 R2 SP1 | [Supporto per TLS predefinito versioni del sistema incluso in .NET Framework 3.5.1 in Windows 7 SP1 e Server 2008 R2 SP1](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the--net-framework) |
| Windows Server 2008 | [Supporto per TLS predefinito versioni del sistema incluso in .NET Framework 2.0 SP2 in Windows Vista SP2 e Server 2008 SP2](https://support.microsoft.com/help/3154517/support-for-tls-system-default-versions-included-in-the--net-framework) |
| Windows Vista | Non supportato |

## <a name="azure-cloud-services"></a>Servizi Cloud di Azure

Se si utilizza [servizi Cloud di Azure](https://azure.microsoft.com/services/cloud-services/) ruoli Web e di lavoro per ospitare ed eseguire l'applicazione, esistono alcune considerazioni che è necessario prendere in considerazione per il supporto di TLS 1.2.

### <a name="net-framework-47-is-not-installed-on-azure-guest-os-by-default"></a>4.7 di .NET framework non è installato nel sistema operativo Guest Azure per impostazione predefinita

La versione più recente installata dell'ultima versione 5 di famiglia del sistema operativo Guest Azure (Windows Server 2016) è 4.6.2. Per individuare le versioni di .NET Framework installate in ogni sistema operativo Guest Azure, vedere la [rilasci del sistema operativo Guest Azure e matrice di compatibilità SDK](https://docs.microsoft.com/azure/cloud-services/cloud-services-guestos-update-matrix).

Se l'app è destinata a una versione di .NET Framework che non è disponibile nella versione del sistema operativo Guest Azure, è necessario installarlo manualmente. Vedere [installarvi i ruoli del servizio Cloud di Azure .NET](https://docs.microsoft.com/azure/cloud-services/cloud-services-dotnet-install-dotnet). Se l'installazione di framework richiede un riavvio, anche i ruoli del servizio venga riavviato prima di immettere stato pronto.

### <a name="azure-guest-os-registry-settings"></a>Impostazioni del Registro di sistema operativo Guest Azure

L'immagine del sistema operativo Guest Azure per [servizi Cloud di Azure](https://azure.microsoft.com/services/cloud-services/) esiste già il `SchUseStrongCrypto` chiave del Registro di sistema impostata su un valore pari a 1. Per altre informazioni, vedere [SchUseStrongCrypto](#schusestrongcrypto).

Impostare il [SystemDefaultTlsVersions](#systemdefaulttlsversions) chiave del Registro di sistema su 1. Vedere [configurazione della protezione tramite il Registro di sistema di Windows](#configuring-security-via-the-windows-registry).
