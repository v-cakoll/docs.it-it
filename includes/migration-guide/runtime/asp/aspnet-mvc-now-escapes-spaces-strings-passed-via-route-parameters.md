---
ms.openlocfilehash: c53fe57f3278741a927a2f00b11af6e26dafce66
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620152"
---
### <a name="aspnet-mvc-now-escapes-spaces-in-strings-passed-in-via-route-parameters"></a><span data-ttu-id="47cc0-101">ASP.NET MVC usa ora caratteri di escape per gli spazi nelle stringhe passate tramite i parametri di una route</span><span class="sxs-lookup"><span data-stu-id="47cc0-101">ASP.NET MVC now escapes spaces in strings passed in via route parameters</span></span>

#### <a name="details"></a><span data-ttu-id="47cc0-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="47cc0-102">Details</span></span>

<span data-ttu-id="47cc0-103">Per conformità allo standard RFC 2396, vengono ora usati caratteri di escape per gli spazi nei percorsi di route durante il popolamento dei parametri di azione da una route.</span><span class="sxs-lookup"><span data-stu-id="47cc0-103">In order to conform to RFC 2396, spaces in route paths are now escaped when populating action parameters from a route.</span></span> <span data-ttu-id="47cc0-104">Pertanto, mentre <code>/controller/action/some data</code> in precedenza corrispondeva alla route <code>/controller/action/{data}</code> e forniva il parametro dati <code>some data</code>, ora fornisce invece <code>some%20data</code>.</span><span class="sxs-lookup"><span data-stu-id="47cc0-104">So, whereas  <code>/controller/action/some data</code> would previously match the route <code>/controller/action/{data}</code> and provide <code>some data</code> as the data parameter, it will now provide <code>some%20data</code> instead.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="47cc0-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="47cc0-105">Suggestion</span></span>

<span data-ttu-id="47cc0-106">È necessario aggiornare il codice per rimuovere i caratteri di escape dai parametri stringa da una route.</span><span class="sxs-lookup"><span data-stu-id="47cc0-106">Code should be updated to unescape string parameters from a route.</span></span> <span data-ttu-id="47cc0-107">Se è necessario l'URI originale, è possibile accedervi con l'API <xref:System.Net.HttpWebRequest.RequestUri>.OriginalString.</span><span class="sxs-lookup"><span data-stu-id="47cc0-107">If the original URI is needed, it can be accessed with the <xref:System.Net.HttpWebRequest.RequestUri>.OriginalString API.</span></span>

| <span data-ttu-id="47cc0-108">Nome</span><span class="sxs-lookup"><span data-stu-id="47cc0-108">Name</span></span>    | <span data-ttu-id="47cc0-109">Valore</span><span class="sxs-lookup"><span data-stu-id="47cc0-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="47cc0-110">Scope</span><span class="sxs-lookup"><span data-stu-id="47cc0-110">Scope</span></span>   |<span data-ttu-id="47cc0-111">Minorenne</span><span class="sxs-lookup"><span data-stu-id="47cc0-111">Minor</span></span>|
|<span data-ttu-id="47cc0-112">Version</span><span class="sxs-lookup"><span data-stu-id="47cc0-112">Version</span></span>|<span data-ttu-id="47cc0-113">4.5.2</span><span class="sxs-lookup"><span data-stu-id="47cc0-113">4.5.2</span></span>|
|<span data-ttu-id="47cc0-114">Type</span><span class="sxs-lookup"><span data-stu-id="47cc0-114">Type</span></span>|<span data-ttu-id="47cc0-115">Runtime</span><span class="sxs-lookup"><span data-stu-id="47cc0-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="47cc0-116">API interessate</span><span class="sxs-lookup"><span data-stu-id="47cc0-116">Affected APIs</span></span>

-<xref:System.Web.Mvc.RouteAttribute.%23ctor(System.String)></li></ul>|
