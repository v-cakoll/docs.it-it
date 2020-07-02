---
ms.openlocfilehash: 0024b2a53444319788b8cdd312d537f994070b5e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614512"
---
### <a name="sslstream-supports-tls-alerts"></a>SslStream supporta avvisi TLS

#### <a name="details"></a>Dettagli

Dopo un handshake TLS non riuscito, verrà generata una <xref:System.IO.IOException?displayProperty=fullName> con eccezione <xref:System.ComponentModel.Win32Exception?displayProperty=fullName> interna dalla prima operazione di lettura/scrittura di I/O. Il <xref:System.ComponentModel.Win32Exception.NativeErrorCode?displayProperty=fullName> codice per il <xref:System.ComponentModel.Win32Exception?displayProperty=fullName> può essere mappato all'avviso TLS dalla parte remota usando i [codici di errore Schannel per gli avvisi TLS e SSL](https://docs.microsoft.com/windows/desktop/SecAuthN/schannel-error-codes-for-tls-and-ssl-alerts). Per altre informazioni, vedere [RFC 2246: Section 7.2.2 Error Alerts](https://tools.ietf.org/html/rfc2246#section-7.2.2). <br/>Il comportamento in .NET Framework 4.6.2 e versioni precedenti corrisponde al timeout del canale di trasporto (in genere una connessione TCP) durante la scrittura o la lettura se l'altra entità non è riuscita a effettuare l'handshake e subito dopo ha rifiutato la connessione.

#### <a name="suggestion"></a>Suggerimento

Le applicazioni che chiamano API I/O di rete, ad esempio <xref:System.IO.Stream.Read(System.Byte[],System.Int32,System.Int32)>/<xref:System.IO.Stream.Write(System.Byte[],System.Int32,System.Int32)>, devono gestire <xref:System.IO.IOException> o <xref:System.TimeoutException?displayProperty=fullName>.<br/>La funzionalità relativa agli avvisi TLS è abilitata per impostazione predefinita a partire da .NET Framework 4.7. Nelle applicazioni destinate alle versioni di .NET Framework da 4.0 a 4.6.2 e in esecuzione in un sistema .NET Framework 4.7 o superiore, la funzionalità è disabilitata per mantenere la compatibilità. <br/>L'API di configurazione seguente è disponibile per abilitare o disabilitare la funzionalità per le applicazioni .NET Framework 4.6 e versioni successive in esecuzione in .NET Framework 4.7 o versioni successive.

- A livello di codice: deve essere la prima operazione eseguita dall'applicazione poiché ServicePointManager verrà inizializzato una sola volta:

    ```csharp
    AppContext.SetSwitch("TestSwitch.LocalAppContext.DisableCaching", true);

    // Set to 'false' to enable the feature in .NET Framework 4.6 - 4.6.2.
    AppContext.SetSwitch("Switch.System.Net.DontEnableTlsAlerts", true);
    ```

- AppConfig:

    ```xml
    <runtime>
      <AppContextSwitchOverrides value="Switch.System.Net.DontEnableTlsAlerts=true"/>
      <!-- Set to 'false' to enable the feature in .NET Framework 4.6 - 4.6.2. -->
    </runtime>
    ```

- Chiave del registro di sistema (computer globale): impostare il valore su `false` per abilitare la funzionalità in .NET Framework 4,6-4.6.2.

    ```ini
    Key: HKLM\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\AppContext\Switch.System.Net.DontEnableTlsAlerts
    - Type: String
    - Value: "true"
    ```

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| Version | 4.7         |
| Type    | Ridestinazione |

#### <a name="affected-apis"></a>API interessate

- <xref:System.Net.Security.SslStream?displayProperty=nameWithType>
- <xref:System.Net.WebRequest?displayProperty=nameWithType>
- <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>
- <xref:System.Net.FtpWebRequest?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Http?displayProperty=nameWithType>
