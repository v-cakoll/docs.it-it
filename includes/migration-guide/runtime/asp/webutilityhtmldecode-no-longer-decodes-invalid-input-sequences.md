---
ms.openlocfilehash: 0b7d6d9543035ab0a8fdda675ae71572ace12a1f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620164"
---
### <a name="webutilityhtmldecode-no-longer-decodes-invalid-input-sequences"></a><span data-ttu-id="27f55-101">WebUtility.HtmlDecode non decodifica più sequenze di input non valide</span><span class="sxs-lookup"><span data-stu-id="27f55-101">WebUtility.HtmlDecode no longer decodes invalid input sequences</span></span>

#### <a name="details"></a><span data-ttu-id="27f55-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="27f55-102">Details</span></span>

<span data-ttu-id="27f55-103">Per impostazione predefinita, i metodi di decodifica non decodificano più una sequenza di input non valido in una stringa UTF-16 non valida.</span><span class="sxs-lookup"><span data-stu-id="27f55-103">By default, decoding methods no longer decode an invalid input sequence into an invalid UTF-16 string.</span></span> <span data-ttu-id="27f55-104">Al contrario, viene restituito l'input originale.</span><span class="sxs-lookup"><span data-stu-id="27f55-104">Instead, they return the original input.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="27f55-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="27f55-105">Suggestion</span></span>

<span data-ttu-id="27f55-106">La modifica dell'output del decodificatore è importante solo se si archiviano dati binari anziché dati UTF-16 nelle stringhe.</span><span class="sxs-lookup"><span data-stu-id="27f55-106">The change in decoder output should matter only if you store binary data instead of UTF-16 data in strings.</span></span> <span data-ttu-id="27f55-107">Per controllare questo comportamento in modo esplicito, impostare l'attributo <code>aspnet:AllowRelaxedUnicodeDecoding</code> dell'elemento [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/index.md) su <code>true</code> per abilitare il comportamento legacy o su <code>false</code> per abilitare il comportamento corrente.</span><span class="sxs-lookup"><span data-stu-id="27f55-107">To explicitly control this behavior, set the <code>aspnet:AllowRelaxedUnicodeDecoding</code> attribute of the [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/index.md) element to <code>true</code> to enable legacy behavior or to <code>false</code> to enable the current behavior.</span></span>

| <span data-ttu-id="27f55-108">Nome</span><span class="sxs-lookup"><span data-stu-id="27f55-108">Name</span></span>    | <span data-ttu-id="27f55-109">Valore</span><span class="sxs-lookup"><span data-stu-id="27f55-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="27f55-110">Scope</span><span class="sxs-lookup"><span data-stu-id="27f55-110">Scope</span></span>   |<span data-ttu-id="27f55-111">Minorenne</span><span class="sxs-lookup"><span data-stu-id="27f55-111">Minor</span></span>|
|<span data-ttu-id="27f55-112">Version</span><span class="sxs-lookup"><span data-stu-id="27f55-112">Version</span></span>|<span data-ttu-id="27f55-113">4.5</span><span class="sxs-lookup"><span data-stu-id="27f55-113">4.5</span></span>|
|<span data-ttu-id="27f55-114">Type</span><span class="sxs-lookup"><span data-stu-id="27f55-114">Type</span></span>|<span data-ttu-id="27f55-115">Runtime</span><span class="sxs-lookup"><span data-stu-id="27f55-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="27f55-116">API interessate</span><span class="sxs-lookup"><span data-stu-id="27f55-116">Affected APIs</span></span>

-<xref:System.Net.WebUtility.HtmlDecode(System.String)?displayProperty=nameWithType></li><li><xref:System.Net.WebUtility.HtmlDecode(System.String,System.IO.TextWriter)?displayProperty=nameWithType></li><li><xref:System.Net.WebUtility.UrlDecode(System.String)?displayProperty=nameWithType></li></ul>|
