---
ms.openlocfilehash: 6f5c1ecead4e2f74e621354058aab70bfa1cccb6
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620224"
---
### <a name="eventlistener-truncates-strings-with-embedded-nulls"></a><span data-ttu-id="21a1e-101">EventListener tronca le stringhe con valori Null incorporati</span><span class="sxs-lookup"><span data-stu-id="21a1e-101">EventListener truncates strings with embedded nulls</span></span>

#### <a name="details"></a><span data-ttu-id="21a1e-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="21a1e-102">Details</span></span>

<span data-ttu-id="21a1e-103"><xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> tronca le stringhe con valori null incorporati.</span><span class="sxs-lookup"><span data-stu-id="21a1e-103"><xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> truncates strings with embedded nulls.</span></span> <span data-ttu-id="21a1e-104">I caratteri null non sono supportati dalla classe <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="21a1e-104">Null characters are not supported by the <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> class.</span></span> <span data-ttu-id="21a1e-105">La modifica influisce solo sulle app che usano <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> per leggere i dati <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> in-process e che usano i caratteri null come delimitatori.</span><span class="sxs-lookup"><span data-stu-id="21a1e-105">The change only affects apps that use <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> to read <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> data in process and that use null characters as delimiters.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="21a1e-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="21a1e-106">Suggestion</span></span>

<span data-ttu-id="21a1e-107">I dati <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> devono essere aggiornati, se possibile, in modo da non usare caratteri Null incorporati.</span><span class="sxs-lookup"><span data-stu-id="21a1e-107"><xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> data should be updated, if possible, to not use embedded null characters.</span></span>

| <span data-ttu-id="21a1e-108">Nome</span><span class="sxs-lookup"><span data-stu-id="21a1e-108">Name</span></span>    | <span data-ttu-id="21a1e-109">Valore</span><span class="sxs-lookup"><span data-stu-id="21a1e-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="21a1e-110">Scope</span><span class="sxs-lookup"><span data-stu-id="21a1e-110">Scope</span></span>   |<span data-ttu-id="21a1e-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="21a1e-111">Edge</span></span>|
|<span data-ttu-id="21a1e-112">Version</span><span class="sxs-lookup"><span data-stu-id="21a1e-112">Version</span></span>|<span data-ttu-id="21a1e-113">4.5.1</span><span class="sxs-lookup"><span data-stu-id="21a1e-113">4.5.1</span></span>|
|<span data-ttu-id="21a1e-114">Type</span><span class="sxs-lookup"><span data-stu-id="21a1e-114">Type</span></span>|<span data-ttu-id="21a1e-115">Runtime</span><span class="sxs-lookup"><span data-stu-id="21a1e-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="21a1e-116">API interessate</span><span class="sxs-lookup"><span data-stu-id="21a1e-116">Affected APIs</span></span>

-<xref:System.Diagnostics.Tracing.EventListener.%23ctor></li><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords,System.Collections.Generic.IDictionary{System.String,System.String})?displayProperty=nameWithType></li></ul>|
