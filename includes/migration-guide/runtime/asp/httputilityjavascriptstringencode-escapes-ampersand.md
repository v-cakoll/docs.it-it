---
ms.openlocfilehash: 0056baa1e5f0cdc5bfcf8b0e83c9490ec5722926
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235705"
---
### <a name="httputilityjavascriptstringencode-escapes-ampersand"></a><span data-ttu-id="afb3c-101">HttpUtility.JavaScriptStringEncode esegue l'escape del carattere e commerciale</span><span class="sxs-lookup"><span data-stu-id="afb3c-101">HttpUtility.JavaScriptStringEncode escapes ampersand</span></span>

|   |   |
|---|---|
|<span data-ttu-id="afb3c-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="afb3c-102">Details</span></span>|<span data-ttu-id="afb3c-103">A partire da .NET Framework 4.5, <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=name> esegue l'escape del carattere e commerciale (&amp;).</span><span class="sxs-lookup"><span data-stu-id="afb3c-103">Starting with the .NET Framework 4.5, <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=name> escapes the ampersand (&amp;) character.</span></span>|
|<span data-ttu-id="afb3c-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="afb3c-104">Suggestion</span></span>|<span data-ttu-id="afb3c-105">Se l'app dipende dal comportamento precedente di questo metodo, è possibile aggiungere un'impostazione aspnet:JavaScriptDoNotEncodeAmpersand all'[elemento appSettings di ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/hh975440(v=vs.120)) nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="afb3c-105">If your app depends on the previous behavior of this method, you can add an aspnet:JavaScriptDoNotEncodeAmpersand setting to the [ASP.NET appSettings element](https://docs.microsoft.com/previous-versions/aspnet/hh975440(v=vs.120)) in your configuration file.</span></span>|
|<span data-ttu-id="afb3c-106">Ambito</span><span class="sxs-lookup"><span data-stu-id="afb3c-106">Scope</span></span>|<span data-ttu-id="afb3c-107">Secondario</span><span class="sxs-lookup"><span data-stu-id="afb3c-107">Minor</span></span>|
|<span data-ttu-id="afb3c-108">Versione</span><span class="sxs-lookup"><span data-stu-id="afb3c-108">Version</span></span>|<span data-ttu-id="afb3c-109">4.5</span><span class="sxs-lookup"><span data-stu-id="afb3c-109">4.5</span></span>|
|<span data-ttu-id="afb3c-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="afb3c-110">Type</span></span>|<span data-ttu-id="afb3c-111">Runtime</span><span class="sxs-lookup"><span data-stu-id="afb3c-111">Runtime</span></span>|
|<span data-ttu-id="afb3c-112">API interessate</span><span class="sxs-lookup"><span data-stu-id="afb3c-112">Affected APIs</span></span>|<ul><li><xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=nameWithType></li><li><xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)?displayProperty=nameWithType></li></ul>|
