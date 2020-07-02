---
ms.openlocfilehash: c996dafcf65b1fd428be908be346de603ead6e0b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615680"
---
### <a name="certificate-eku-oid-validation"></a><span data-ttu-id="8ef3f-101">Convalida dell'OID EKU del certificato</span><span class="sxs-lookup"><span data-stu-id="8ef3f-101">Certificate EKU OID validation</span></span>

#### <a name="details"></a><span data-ttu-id="8ef3f-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="8ef3f-102">Details</span></span>

<span data-ttu-id="8ef3f-103">A partire da .NET Framework 4.6, le classi <xref:System.Net.Security.SslStream> o <xref:System.Net.ServicePointManager> eseguono la convalida dell'oggetto identificatore (OID) dell'utilizzo chiavi avanzato (EKU).</span><span class="sxs-lookup"><span data-stu-id="8ef3f-103">Starting with .NET Framework 4.6, the <xref:System.Net.Security.SslStream> or <xref:System.Net.ServicePointManager> classes perform enhanced key use (EKU) object identifier (OID) validation.</span></span> <span data-ttu-id="8ef3f-104">Un'estensione di utilizzo chiavi avanzato (EKU) è una raccolta di identificatori di oggetto (OID) che indica le applicazioni che usano la chiave.</span><span class="sxs-lookup"><span data-stu-id="8ef3f-104">An enhanced key usage (EKU) extension is a collection of object identifiers (OIDs) that indicate the applications that use the key.</span></span> <span data-ttu-id="8ef3f-105">La convalida dell'OID EKU usa callback del certificato remoto per assicurarsi che il certificato remoto abbia gli OID corretti per lo scopo previsto.</span><span class="sxs-lookup"><span data-stu-id="8ef3f-105">EKU OID validation uses remote certificate callbacks to ensure that the remote certificate has the correct OIDs for the intended purpose.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="8ef3f-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="8ef3f-106">Suggestion</span></span>

<span data-ttu-id="8ef3f-107">Se questa modifica è indesiderata, è possibile disabilitare la convalida dell'OID EKU del certificato aggiungendo l'opzione seguente al [\<AppContextSwitchOverrides>](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) nella [\`](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del file di configurazione dell'app:</span><span class="sxs-lookup"><span data-stu-id="8ef3f-107">If this change is undesirable, you can disable certificate EKU OID validation by adding the following switch to the [\<AppContextSwitchOverrides>](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) in the [\`](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) of your app configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Net.DontCheckCertificateEKUs=true" />
</runtime>
```

> [!IMPORTANT]
> <span data-ttu-id="8ef3f-108">Questa impostazione è disponibile solo per la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="8ef3f-108">This setting is provided for backward compatibility only.</span></span> <span data-ttu-id="8ef3f-109">Il suo uso non è altrimenti consigliato.</span><span class="sxs-lookup"><span data-stu-id="8ef3f-109">Its use is otherwise not recommended.</span></span>

| <span data-ttu-id="8ef3f-110">Nome</span><span class="sxs-lookup"><span data-stu-id="8ef3f-110">Name</span></span>    | <span data-ttu-id="8ef3f-111">Valore</span><span class="sxs-lookup"><span data-stu-id="8ef3f-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="8ef3f-112">Scope</span><span class="sxs-lookup"><span data-stu-id="8ef3f-112">Scope</span></span>   | <span data-ttu-id="8ef3f-113">Minorenne</span><span class="sxs-lookup"><span data-stu-id="8ef3f-113">Minor</span></span>       |
| <span data-ttu-id="8ef3f-114">Version</span><span class="sxs-lookup"><span data-stu-id="8ef3f-114">Version</span></span> | <span data-ttu-id="8ef3f-115">4.6</span><span class="sxs-lookup"><span data-stu-id="8ef3f-115">4.6</span></span>         |
| <span data-ttu-id="8ef3f-116">Type</span><span class="sxs-lookup"><span data-stu-id="8ef3f-116">Type</span></span>    | <span data-ttu-id="8ef3f-117">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="8ef3f-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="8ef3f-118">API interessate</span><span class="sxs-lookup"><span data-stu-id="8ef3f-118">Affected APIs</span></span>

- <xref:System.Net.Security.SslStream?displayProperty=nameWithType>
- <xref:System.Net.ServicePointManager?displayProperty=nameWithType>
- <xref:System.Net.Http.HttpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>
- <xref:System.Net.FtpWebRequest?displayProperty=nameWithType>
