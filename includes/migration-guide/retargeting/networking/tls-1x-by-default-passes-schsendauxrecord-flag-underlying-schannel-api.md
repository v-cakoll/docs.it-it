---
ms.openlocfilehash: 207dba9327cfd6debd15c5573697f8950b6c2c95
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86218389"
---
### <a name="tls-1x-by-default-passes-the-sch_send_aux_record-flag-to-the-underlying-schannel-api"></a><span data-ttu-id="8d2a1-101">TLS 1.x passa per impostazione predefinita il flag SCH_SEND_AUX_RECORD all'API SCHANNEL sottostante</span><span class="sxs-lookup"><span data-stu-id="8d2a1-101">TLS 1.x by default passes the SCH_SEND_AUX_RECORD flag to the underlying SCHANNEL API</span></span>

#### <a name="details"></a><span data-ttu-id="8d2a1-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="8d2a1-102">Details</span></span>

<span data-ttu-id="8d2a1-103">Quando si usa TLS 1.x, .NET Framework si basa sull'API SCHANNEL di Windows sottostante.</span><span class="sxs-lookup"><span data-stu-id="8d2a1-103">When using TLS 1.x, the .NET Framework relies on the underlying Windows SCHANNEL API.</span></span> <span data-ttu-id="8d2a1-104">A partire da .NET Framework 4.6, il flag [SCH_SEND_AUX_RECORD](https://docs.microsoft.com/windows/win32/api/schannel/ns-schannel-schannel_cred) viene passato per impostazione predefinita a SCHANNEL.</span><span class="sxs-lookup"><span data-stu-id="8d2a1-104">Starting with .NET Framework 4.6, the [SCH_SEND_AUX_RECORD](https://docs.microsoft.com/windows/win32/api/schannel/ns-schannel-schannel_cred) flag is passed by default to SCHANNEL.</span></span> <span data-ttu-id="8d2a1-105">SCHANNEL suddivide di conseguenza i dati da crittografare in due record separati, il primo come un singolo byte e il secondo come <em>n</em>-1 byte. In rari casi, ciò interrompe la comunicazione tra i client e i server esistenti che si basano sul presupposto che i dati risiedano in un singolo record.</span><span class="sxs-lookup"><span data-stu-id="8d2a1-105">This causes SCHANNEL to split data to be encrypted into two separate records, the first as a single byte and the second as <em>n</em>-1 bytes.In rare cases, this breaks communication between clients and existing servers that make the assumption that the data resides in a single record.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="8d2a1-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="8d2a1-106">Suggestion</span></span>

<span data-ttu-id="8d2a1-107">Se questa modifica interrompe la comunicazione con un server esistente, è possibile disabilitare l'invio del flag [SCH_SEND_AUX_RECORD](https://docs.microsoft.com/windows/win32/api/schannel/ns-schannel-schannel_cred) e ripristinare il comportamento precedente, che non prevede la suddivisione dei dati in record separati, aggiungendo l'opzione seguente all'elemento [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) nella sezione [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del file di configurazione dell'app:</span><span class="sxs-lookup"><span data-stu-id="8d2a1-107">If this change breaks communication with an existing server, you can disable sending the [SCH_SEND_AUX_RECORD](https://docs.microsoft.com/windows/win32/api/schannel/ns-schannel-schannel_cred) flag and restore the previous behavior of not splitting data into separate records by adding the following switch to the [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your app configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Net.DontEnableSchSendAuxRecord=true" />
</runtime>
```

> [!IMPORTANT]
> <span data-ttu-id="8d2a1-108">Questa impostazione è disponibile solo per la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="8d2a1-108">This setting is provided for backward compatibility only.</span></span> <span data-ttu-id="8d2a1-109">Il suo uso non è altrimenti consigliato.</span><span class="sxs-lookup"><span data-stu-id="8d2a1-109">Its use is otherwise not recommended.</span></span>

| <span data-ttu-id="8d2a1-110">Nome</span><span class="sxs-lookup"><span data-stu-id="8d2a1-110">Name</span></span>    | <span data-ttu-id="8d2a1-111">Valore</span><span class="sxs-lookup"><span data-stu-id="8d2a1-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="8d2a1-112">Ambito</span><span class="sxs-lookup"><span data-stu-id="8d2a1-112">Scope</span></span>   | <span data-ttu-id="8d2a1-113">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="8d2a1-113">Edge</span></span>        |
| <span data-ttu-id="8d2a1-114">Versione</span><span class="sxs-lookup"><span data-stu-id="8d2a1-114">Version</span></span> | <span data-ttu-id="8d2a1-115">4.6</span><span class="sxs-lookup"><span data-stu-id="8d2a1-115">4.6</span></span>         |
| <span data-ttu-id="8d2a1-116">Tipo</span><span class="sxs-lookup"><span data-stu-id="8d2a1-116">Type</span></span>    | <span data-ttu-id="8d2a1-117">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="8d2a1-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="8d2a1-118">API interessate</span><span class="sxs-lookup"><span data-stu-id="8d2a1-118">Affected APIs</span></span>

- <xref:System.Net.Security.SslStream?displayProperty=nameWithType>
- <xref:System.Net.ServicePointManager?displayProperty=nameWithType>
- <xref:System.Net.Http.HttpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>
- <xref:System.Net.FtpWebRequest?displayProperty=nameWithType>
