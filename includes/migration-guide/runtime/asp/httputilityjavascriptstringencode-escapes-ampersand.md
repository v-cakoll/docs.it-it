---
ms.openlocfilehash: d587e542a72d584502ac3ac892619cc38b88ef77
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620143"
---
### <a name="httputilityjavascriptstringencode-escapes-ampersand"></a><span data-ttu-id="ea4ef-101">HttpUtility.JavaScriptStringEncode esegue l'escape del carattere e commerciale</span><span class="sxs-lookup"><span data-stu-id="ea4ef-101">HttpUtility.JavaScriptStringEncode escapes ampersand</span></span>

#### <a name="details"></a><span data-ttu-id="ea4ef-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="ea4ef-102">Details</span></span>

<span data-ttu-id="ea4ef-103">A partire da .NET Framework 4.5, <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=fullName> esegue l'escape del carattere e commerciale (&amp;).</span><span class="sxs-lookup"><span data-stu-id="ea4ef-103">Starting with the .NET Framework 4.5, <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=fullName> escapes the ampersand (&amp;) character.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ea4ef-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="ea4ef-104">Suggestion</span></span>

<span data-ttu-id="ea4ef-105">Se l'app dipende dal comportamento precedente di questo metodo, è possibile aggiungere un'impostazione aspnet:JavaScriptDoNotEncodeAmpersand all'[elemento appSettings di ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/hh975440(v=vs.120)) nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="ea4ef-105">If your app depends on the previous behavior of this method, you can add an aspnet:JavaScriptDoNotEncodeAmpersand setting to the [ASP.NET appSettings element](https://docs.microsoft.com/previous-versions/aspnet/hh975440(v=vs.120)) in your configuration file.</span></span>

| <span data-ttu-id="ea4ef-106">Nome</span><span class="sxs-lookup"><span data-stu-id="ea4ef-106">Name</span></span>    | <span data-ttu-id="ea4ef-107">Valore</span><span class="sxs-lookup"><span data-stu-id="ea4ef-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ea4ef-108">Scope</span><span class="sxs-lookup"><span data-stu-id="ea4ef-108">Scope</span></span>   |<span data-ttu-id="ea4ef-109">Minorenne</span><span class="sxs-lookup"><span data-stu-id="ea4ef-109">Minor</span></span>|
|<span data-ttu-id="ea4ef-110">Version</span><span class="sxs-lookup"><span data-stu-id="ea4ef-110">Version</span></span>|<span data-ttu-id="ea4ef-111">4.5</span><span class="sxs-lookup"><span data-stu-id="ea4ef-111">4.5</span></span>|
|<span data-ttu-id="ea4ef-112">Type</span><span class="sxs-lookup"><span data-stu-id="ea4ef-112">Type</span></span>|<span data-ttu-id="ea4ef-113">Runtime</span><span class="sxs-lookup"><span data-stu-id="ea4ef-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ea4ef-114">API interessate</span><span class="sxs-lookup"><span data-stu-id="ea4ef-114">Affected APIs</span></span>

-<xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=nameWithType></li><li><xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)?displayProperty=nameWithType></li></ul>|
