---
ms.openlocfilehash: 0024b2a53444319788b8cdd312d537f994070b5e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614512"
---
### <a name="sslstream-supports-tls-alerts"></a><span data-ttu-id="5e93d-101">SslStream supporta avvisi TLS</span><span class="sxs-lookup"><span data-stu-id="5e93d-101">SslStream supports TLS Alerts</span></span>

#### <a name="details"></a><span data-ttu-id="5e93d-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="5e93d-102">Details</span></span>

<span data-ttu-id="5e93d-103">Dopo un handshake TLS non riuscito, verrà generata una <xref:System.IO.IOException?displayProperty=fullName> con eccezione <xref:System.ComponentModel.Win32Exception?displayProperty=fullName> interna dalla prima operazione di lettura/scrittura di I/O.</span><span class="sxs-lookup"><span data-stu-id="5e93d-103">After a failed TLS handshake, an <xref:System.IO.IOException?displayProperty=fullName> with an inner <xref:System.ComponentModel.Win32Exception?displayProperty=fullName> exception will be thrown by the first I/O Read/Write operation.</span></span> <span data-ttu-id="5e93d-104">Il <xref:System.ComponentModel.Win32Exception.NativeErrorCode?displayProperty=fullName> codice per il <xref:System.ComponentModel.Win32Exception?displayProperty=fullName> può essere mappato all'avviso TLS dalla parte remota usando i [codici di errore Schannel per gli avvisi TLS e SSL](https://docs.microsoft.com/windows/desktop/SecAuthN/schannel-error-codes-for-tls-and-ssl-alerts). Per altre informazioni, vedere [RFC 2246: Section 7.2.2 Error Alerts](https://tools.ietf.org/html/rfc2246#section-7.2.2).</span><span class="sxs-lookup"><span data-stu-id="5e93d-104">The <xref:System.ComponentModel.Win32Exception.NativeErrorCode?displayProperty=fullName> code for the <xref:System.ComponentModel.Win32Exception?displayProperty=fullName> can be mapped to the TLS Alert from the remote party using the [Schannel error codes for TLS and SSL alerts](https://docs.microsoft.com/windows/desktop/SecAuthN/schannel-error-codes-for-tls-and-ssl-alerts).For more information, see [RFC 2246: Section 7.2.2 Error alerts](https://tools.ietf.org/html/rfc2246#section-7.2.2).</span></span> <br/><span data-ttu-id="5e93d-105">Il comportamento in .NET Framework 4.6.2 e versioni precedenti corrisponde al timeout del canale di trasporto (in genere una connessione TCP) durante la scrittura o la lettura se l'altra entità non è riuscita a effettuare l'handshake e subito dopo ha rifiutato la connessione.</span><span class="sxs-lookup"><span data-stu-id="5e93d-105">The behavior in .NET Framework 4.6.2 and earlier is that the transport channel (usually TCP connection) will timeout during either Write or Read if the other party failed the handshake and immediately afterwards rejected the connection.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="5e93d-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="5e93d-106">Suggestion</span></span>

<span data-ttu-id="5e93d-107">Le applicazioni che chiamano API I/O di rete, ad esempio <xref:System.IO.Stream.Read(System.Byte[],System.Int32,System.Int32)>/<xref:System.IO.Stream.Write(System.Byte[],System.Int32,System.Int32)>, devono gestire <xref:System.IO.IOException> o <xref:System.TimeoutException?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="5e93d-107">Applications calling network I/O APIs such as <xref:System.IO.Stream.Read(System.Byte[],System.Int32,System.Int32)>/<xref:System.IO.Stream.Write(System.Byte[],System.Int32,System.Int32)> should handle <xref:System.IO.IOException> or <xref:System.TimeoutException?displayProperty=fullName>.</span></span><br/><span data-ttu-id="5e93d-108">La funzionalità relativa agli avvisi TLS è abilitata per impostazione predefinita a partire da .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="5e93d-108">The TLS Alerts feature is enabled by default starting with .NET Framework 4.7.</span></span> <span data-ttu-id="5e93d-109">Nelle applicazioni destinate alle versioni di .NET Framework da 4.0 a 4.6.2 e in esecuzione in un sistema .NET Framework 4.7 o superiore, la funzionalità è disabilitata per mantenere la compatibilità.</span><span class="sxs-lookup"><span data-stu-id="5e93d-109">Applications targeting versions of the .NET Framework from 4.0 through 4.6.2 running on a .NET Framework 4.7 or higher system will have the feature disabled to preserve compatibility.</span></span> <br/><span data-ttu-id="5e93d-110">L'API di configurazione seguente è disponibile per abilitare o disabilitare la funzionalità per le applicazioni .NET Framework 4.6 e versioni successive in esecuzione in .NET Framework 4.7 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="5e93d-110">The following configuration API is available to enable or disable the feature for .NET Framework 4.6 and later applications running on .NET Framework 4.7 or later.</span></span>

- <span data-ttu-id="5e93d-111">A livello di codice: deve essere la prima operazione eseguita dall'applicazione poiché ServicePointManager verrà inizializzato una sola volta:</span><span class="sxs-lookup"><span data-stu-id="5e93d-111">Programmatically:   Must be the very first thing the application does since ServicePointManager will initialize only once:</span></span>

    ```csharp
    AppContext.SetSwitch("TestSwitch.LocalAppContext.DisableCaching", true);

    // Set to 'false' to enable the feature in .NET Framework 4.6 - 4.6.2.
    AppContext.SetSwitch("Switch.System.Net.DontEnableTlsAlerts", true);
    ```

- <span data-ttu-id="5e93d-112">AppConfig:</span><span class="sxs-lookup"><span data-stu-id="5e93d-112">AppConfig:</span></span>

    ```xml
    <runtime>
      <AppContextSwitchOverrides value="Switch.System.Net.DontEnableTlsAlerts=true"/>
      <!-- Set to 'false' to enable the feature in .NET Framework 4.6 - 4.6.2. -->
    </runtime>
    ```

- <span data-ttu-id="5e93d-113">Chiave del registro di sistema (computer globale): impostare il valore su `false` per abilitare la funzionalità in .NET Framework 4,6-4.6.2.</span><span class="sxs-lookup"><span data-stu-id="5e93d-113">Registry key (machine global):   Set the Value to `false` to enable the feature in .NET Framework 4.6 - 4.6.2.</span></span>

    ```ini
    Key: HKLM\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\AppContext\Switch.System.Net.DontEnableTlsAlerts
    - Type: String
    - Value: "true"
    ```

| <span data-ttu-id="5e93d-114">Nome</span><span class="sxs-lookup"><span data-stu-id="5e93d-114">Name</span></span>    | <span data-ttu-id="5e93d-115">Valore</span><span class="sxs-lookup"><span data-stu-id="5e93d-115">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="5e93d-116">Scope</span><span class="sxs-lookup"><span data-stu-id="5e93d-116">Scope</span></span>   | <span data-ttu-id="5e93d-117">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="5e93d-117">Edge</span></span>        |
| <span data-ttu-id="5e93d-118">Version</span><span class="sxs-lookup"><span data-stu-id="5e93d-118">Version</span></span> | <span data-ttu-id="5e93d-119">4.7</span><span class="sxs-lookup"><span data-stu-id="5e93d-119">4.7</span></span>         |
| <span data-ttu-id="5e93d-120">Type</span><span class="sxs-lookup"><span data-stu-id="5e93d-120">Type</span></span>    | <span data-ttu-id="5e93d-121">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="5e93d-121">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="5e93d-122">API interessate</span><span class="sxs-lookup"><span data-stu-id="5e93d-122">Affected APIs</span></span>

- <xref:System.Net.Security.SslStream?displayProperty=nameWithType>
- <xref:System.Net.WebRequest?displayProperty=nameWithType>
- <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>
- <xref:System.Net.FtpWebRequest?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Http?displayProperty=nameWithType>
