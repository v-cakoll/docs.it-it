---
ms.openlocfilehash: 08a9292c5a41e7b9b7c1bcc18ec96460de19863f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621184"
---
### <a name="support-special-relative-uri-notation-when-unicode-is-present"></a><span data-ttu-id="965ed-101">Supporto della notazione URI relativa speciale quando è presente Unicode</span><span class="sxs-lookup"><span data-stu-id="965ed-101">Support special relative URI notation when Unicode is present</span></span>

#### <a name="details"></a><span data-ttu-id="965ed-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="965ed-102">Details</span></span>

<span data-ttu-id="965ed-103"><xref:System.Uri>non genererà più un oggetto <xref:System.NullReferenceException> quando viene chiamato <xref:System.Uri.TryCreate%2A> su determinati URI relativi che contengono Unicode.</span><span class="sxs-lookup"><span data-stu-id="965ed-103"><xref:System.Uri> will no longer throw a <xref:System.NullReferenceException> when calling <xref:System.Uri.TryCreate%2A> on certain relative URIs containing Unicode.</span></span> <span data-ttu-id="965ed-104">La riproduzione più semplice di <xref:System.NullReferenceException> è riportata di seguito, con due istruzioni equivalenti:</span><span class="sxs-lookup"><span data-stu-id="965ed-104">The simplest reproduction of the <xref:System.NullReferenceException> is below, with the two statements being equivalent:</span></span><pre><code class="lang-csharp">bool success = Uri.TryCreate(&quot;http:%C3%A8&quot;, UriKind.RelativeOrAbsolute, out Uri href);&#13;&#10;bool success = Uri.TryCreate(&quot;http:&#232;&quot;, UriKind.RelativeOrAbsolute, out Uri href);&#13;&#10;</code></pre><span data-ttu-id="965ed-105">Per riprodurre <xref:System.NullReferenceException>, gli elementi seguenti devono essere true:</span><span class="sxs-lookup"><span data-stu-id="965ed-105">To reproduce the <xref:System.NullReferenceException>, the following items must be true:</span></span><ul><li><span data-ttu-id="965ed-106">L'URI deve essere specificato come relativo, anteponendo 'http:' non seguito da '//'.</span><span class="sxs-lookup"><span data-stu-id="965ed-106">The URI must be specified as relative by prepending it with ‘http:’ and not following it with ‘//’.</span></span></li><li><span data-ttu-id="965ed-107">L'URI deve contenere Unicode codificato in percentuale o simboli non riservati.</span><span class="sxs-lookup"><span data-stu-id="965ed-107">The URI must contain percent-encoded Unicode or unreserved symbols.</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="965ed-108">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="965ed-108">Suggestion</span></span>

<span data-ttu-id="965ed-109">Gli utenti che si basano su questo comportamento per impedire l'uso di URI relativi devono invece specificare <xref:System.UriKind.Absolute?displayProperty=nameWithType> al momento della creazione di un URI.</span><span class="sxs-lookup"><span data-stu-id="965ed-109">Users depending on this behavior to disallow relative URIs should instead specify <xref:System.UriKind.Absolute?displayProperty=nameWithType> when creating a URI.</span></span>

| <span data-ttu-id="965ed-110">Nome</span><span class="sxs-lookup"><span data-stu-id="965ed-110">Name</span></span>    | <span data-ttu-id="965ed-111">Valore</span><span class="sxs-lookup"><span data-stu-id="965ed-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="965ed-112">Scope</span><span class="sxs-lookup"><span data-stu-id="965ed-112">Scope</span></span>   |<span data-ttu-id="965ed-113">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="965ed-113">Edge</span></span>|
|<span data-ttu-id="965ed-114">Version</span><span class="sxs-lookup"><span data-stu-id="965ed-114">Version</span></span>|<span data-ttu-id="965ed-115">4.7.2</span><span class="sxs-lookup"><span data-stu-id="965ed-115">4.7.2</span></span>|
|<span data-ttu-id="965ed-116">Type</span><span class="sxs-lookup"><span data-stu-id="965ed-116">Type</span></span>|<span data-ttu-id="965ed-117">Runtime</span><span class="sxs-lookup"><span data-stu-id="965ed-117">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="965ed-118">API interessate</span><span class="sxs-lookup"><span data-stu-id="965ed-118">Affected APIs</span></span>

-<xref:System.Uri.TryCreate(System.Uri,System.Uri,System.Uri@)?displayProperty=nameWithType></li><li><xref:System.Uri.TryCreate(System.String,System.UriKind,System.Uri@)?displayProperty=nameWithType></li><li><xref:System.Uri.TryCreate(System.Uri,System.String,System.Uri@)?displayProperty=nameWithType></li></ul>|
