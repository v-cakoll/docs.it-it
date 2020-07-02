---
ms.openlocfilehash: 7d3568fef933758c40e47cefa86c24d31d4119fc
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620131"
---
### <a name="httprequestcontentencoding-property-prohibits-utf7"></a><span data-ttu-id="f8f7d-101">La proprietà HttpRequest.ContentEncoding non consente UTF7</span><span class="sxs-lookup"><span data-stu-id="f8f7d-101">HttpRequest.ContentEncoding property prohibits UTF7</span></span>

#### <a name="details"></a><span data-ttu-id="f8f7d-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="f8f7d-102">Details</span></span>

<span data-ttu-id="f8f7d-103">A partire da .NET Framework 4.5, la codifica UTF-7 non è consentita nel corpo di <xref:System.Web.HttpRequest?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="f8f7d-103">Beginning in .NET Framework 4.5, UTF-7 encoding is prohibited in <xref:System.Web.HttpRequest?displayProperty=fullName>s' bodies.</span></span> <span data-ttu-id="f8f7d-104">In alcuni casi i dati per le applicazioni che dipendono dai dati UTF-7 in ingresso non verranno decodificati correttamente.</span><span class="sxs-lookup"><span data-stu-id="f8f7d-104">Data for applications that depend on incoming UTF-7 data will not decode properly in some cases.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f8f7d-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="f8f7d-105">Suggestion</span></span>

<span data-ttu-id="f8f7d-106">È consigliabile aggiornare le applicazioni in modo da non usare la codifica UTF-7 in <xref:System.Web.HttpRequest?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="f8f7d-106">Ideally, applications should be updated to not use UTF-7 encoding in <xref:System.Web.HttpRequest?displayProperty=fullName>s.</span></span> <span data-ttu-id="f8f7d-107">In alternativa, è possibile ripristinare il comportamento legacy usando l'attributo <code>aspnet:AllowUtf7RequestContentEncoding</code> dell'elemento [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="f8f7d-107">Alternatively, legacy behavior can be restored by using the <code>aspnet:AllowUtf7RequestContentEncoding</code> attribute of the [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) element.</span></span>

| <span data-ttu-id="f8f7d-108">Nome</span><span class="sxs-lookup"><span data-stu-id="f8f7d-108">Name</span></span>    | <span data-ttu-id="f8f7d-109">Valore</span><span class="sxs-lookup"><span data-stu-id="f8f7d-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f8f7d-110">Scope</span><span class="sxs-lookup"><span data-stu-id="f8f7d-110">Scope</span></span>   |<span data-ttu-id="f8f7d-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="f8f7d-111">Edge</span></span>|
|<span data-ttu-id="f8f7d-112">Version</span><span class="sxs-lookup"><span data-stu-id="f8f7d-112">Version</span></span>|<span data-ttu-id="f8f7d-113">4.5</span><span class="sxs-lookup"><span data-stu-id="f8f7d-113">4.5</span></span>|
|<span data-ttu-id="f8f7d-114">Type</span><span class="sxs-lookup"><span data-stu-id="f8f7d-114">Type</span></span>|<span data-ttu-id="f8f7d-115">Runtime</span><span class="sxs-lookup"><span data-stu-id="f8f7d-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f8f7d-116">API interessate</span><span class="sxs-lookup"><span data-stu-id="f8f7d-116">Affected APIs</span></span>

-<xref:System.Web.HttpRequest.ContentEncoding?displayProperty=nameWithType></li></ul>|
