---
ms.openlocfilehash: 135d59de135c8416d384b221379f912c8a9172ad
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621971"
---
### <a name="aspnet-incorrect-multipart-handling-may-result-in-lost-form-data"></a><span data-ttu-id="1706d-101">La gestione multipart di ASP.NET non corretta può comportare la perdita di dati del modulo.</span><span class="sxs-lookup"><span data-stu-id="1706d-101">ASP.NET Incorrect multipart handling may result in lost form data.</span></span>

#### <a name="details"></a><span data-ttu-id="1706d-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="1706d-102">Details</span></span>

<span data-ttu-id="1706d-103">Nelle applicazioni destinate a .NET Framework 4.7.2 e versioni precedenti, ASP.NET potrebbe analizzare erroneamente i valori limite multipart, causando la mancata disponibilità dei dati del modulo durante l'esecuzione della richiesta.</span><span class="sxs-lookup"><span data-stu-id="1706d-103">In applications that target .NET Framework 4.7.2 and earlier versions, ASP.Net might incorrectly parse multipart boundary values, resulting in form data being unavailable during request execution.</span></span> <span data-ttu-id="1706d-104">Le applicazioni destinate a .NET Framework 4.8 o versioni successive analizzano i dati multipart correttamente. I dati del modulo sono quindi disponibili durante l'esecuzione della richiesta.</span><span class="sxs-lookup"><span data-stu-id="1706d-104">Applications that target .NET Framework 4.8 or later versions correctly parse multipart data, so form values are available during request execution.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="1706d-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="1706d-105">Suggestion</span></span>

<span data-ttu-id="1706d-106">Nelle applicazioni in esecuzione in .NET Framework a partire dalla versione 4.8 e destinate a .NET Framework 4.8 o versioni successive che usano l'elemento <code>targetFrameworkVersion</code>, il comportamento predefinito cambia al fine di eliminare i delimitatori.</span><span class="sxs-lookup"><span data-stu-id="1706d-106">Starting with applications running on .NET Framework 4.8, when targeting .NET Framework 4.8 or later by using the <code>targetFrameworkVersion</code> element, the default behavior changes to strip delimiters.</span></span> <span data-ttu-id="1706d-107">Se si usano versioni del framework precedenti o non si usa <code>targetFrameworkVersion</code>, è possibile che vengano restituiti dei delimitatori finali per alcuni valori.Questo comportamento può anche essere controllato esplicitamente con un elemento <code>appSetting</code>:</span><span class="sxs-lookup"><span data-stu-id="1706d-107">When targeting previous framework versions or not using <code>targetFrameworkVersion</code>, trailing delimiters for some values are still returned.This behavior can also be explicitly controlled with an <code>appSetting</code>:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;aspnet:UseLegacyMultiValueHeaderHandling&quot;  value=&quot;true&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="1706d-108">Nome</span><span class="sxs-lookup"><span data-stu-id="1706d-108">Name</span></span>    | <span data-ttu-id="1706d-109">Valore</span><span class="sxs-lookup"><span data-stu-id="1706d-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="1706d-110">Scope</span><span class="sxs-lookup"><span data-stu-id="1706d-110">Scope</span></span>   |<span data-ttu-id="1706d-111">Sconosciuto</span><span class="sxs-lookup"><span data-stu-id="1706d-111">Unknown</span></span>|
|<span data-ttu-id="1706d-112">Version</span><span class="sxs-lookup"><span data-stu-id="1706d-112">Version</span></span>|<span data-ttu-id="1706d-113">4.8</span><span class="sxs-lookup"><span data-stu-id="1706d-113">4.8</span></span>|
|<span data-ttu-id="1706d-114">Type</span><span class="sxs-lookup"><span data-stu-id="1706d-114">Type</span></span>|<span data-ttu-id="1706d-115">Runtime</span><span class="sxs-lookup"><span data-stu-id="1706d-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="1706d-116">API interessate</span><span class="sxs-lookup"><span data-stu-id="1706d-116">Affected APIs</span></span>

-<xref:System.Web.HttpRequest.Form?displayProperty=nameWithType></li><li><xref:System.Web.HttpRequest.Files?displayProperty=nameWithType></li><li><xref:System.Web.HttpRequest.ContentEncoding?displayProperty=nameWithType></li></ul>|
