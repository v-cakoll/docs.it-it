---
ms.openlocfilehash: 668d047d3247d64cb1400d4a9ea6887795fa0d44
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235426"
---
### <a name="httprequestcontentencoding-property-prohibits-utf7"></a><span data-ttu-id="9104e-101">La proprietà HttpRequest.ContentEncoding non consente UTF7</span><span class="sxs-lookup"><span data-stu-id="9104e-101">HttpRequest.ContentEncoding property prohibits UTF7</span></span>

|   |   |
|---|---|
|<span data-ttu-id="9104e-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="9104e-102">Details</span></span>|<span data-ttu-id="9104e-103">A partire da .NET Framework 4.5, la codifica UTF-7 non è consentita nel corpo di <xref:System.Web.HttpRequest?displayProperty=name>.</span><span class="sxs-lookup"><span data-stu-id="9104e-103">Beginning in .NET Framework 4.5, UTF-7 encoding is prohibited in <xref:System.Web.HttpRequest?displayProperty=name>s' bodies.</span></span> <span data-ttu-id="9104e-104">In alcuni casi i dati per le applicazioni che dipendono dai dati UTF-7 in ingresso non verranno decodificati correttamente.</span><span class="sxs-lookup"><span data-stu-id="9104e-104">Data for applications that depend on incoming UTF-7 data will not decode properly in some cases.</span></span>|
|<span data-ttu-id="9104e-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="9104e-105">Suggestion</span></span>|<span data-ttu-id="9104e-106">È consigliabile aggiornare le applicazioni in modo da non usare la codifica UTF-7 in <xref:System.Web.HttpRequest?displayProperty=name>.</span><span class="sxs-lookup"><span data-stu-id="9104e-106">Ideally, applications should be updated to not use UTF-7 encoding in <xref:System.Web.HttpRequest?displayProperty=name>s.</span></span> <span data-ttu-id="9104e-107">In alternativa, è possibile ripristinare il comportamento legacy usando l'attributo <code>aspnet:AllowUtf7RequestContentEncoding</code> dell'elemento [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="9104e-107">Alternatively, legacy behavior can be restored by using the <code>aspnet:AllowUtf7RequestContentEncoding</code> attribute of the [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) element.</span></span>|
|<span data-ttu-id="9104e-108">Ambito</span><span class="sxs-lookup"><span data-stu-id="9104e-108">Scope</span></span>|<span data-ttu-id="9104e-109">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="9104e-109">Edge</span></span>|
|<span data-ttu-id="9104e-110">Versione</span><span class="sxs-lookup"><span data-stu-id="9104e-110">Version</span></span>|<span data-ttu-id="9104e-111">4.5</span><span class="sxs-lookup"><span data-stu-id="9104e-111">4.5</span></span>|
|<span data-ttu-id="9104e-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="9104e-112">Type</span></span>|<span data-ttu-id="9104e-113">Runtime</span><span class="sxs-lookup"><span data-stu-id="9104e-113">Runtime</span></span>|
|<span data-ttu-id="9104e-114">API interessate</span><span class="sxs-lookup"><span data-stu-id="9104e-114">Affected APIs</span></span>|<ul><li><xref:System.Web.HttpRequest.ContentEncoding?displayProperty=nameWithType></li></ul>|
