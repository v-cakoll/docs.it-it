---
ms.openlocfilehash: c6c897c13c84ce4b2be21da18e5702365518f286
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620324"
---
### <a name="ef-no-longer-throws-for-queryviews-with-specific-characteristics"></a><span data-ttu-id="67f16-101">Entity Framework non genera più eccezioni per QueryView con caratteristiche specifiche</span><span class="sxs-lookup"><span data-stu-id="67f16-101">EF no longer throws for QueryViews with specific characteristics</span></span>

#### <a name="details"></a><span data-ttu-id="67f16-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="67f16-102">Details</span></span>

<span data-ttu-id="67f16-103">Entity Framework non genera più un'eccezione <xref:System.StackOverflowException?displayProperty=fullName> quando un'app esegue una query che coinvolge un elemento QueryView con una proprietà di navigazione 0..1 che tenta di includere le entità correlate nella query.</span><span class="sxs-lookup"><span data-stu-id="67f16-103">Entity Framework no longer throws a <xref:System.StackOverflowException?displayProperty=fullName> exception when an app executes a query that involves a QueryView with a 0..1 navigation property that attempts to include the related entities as part of the query.</span></span> <span data-ttu-id="67f16-104">Ad esempio, chiamando <code>.Include(e =&gt; e.RelatedNavProp)</code>.</span><span class="sxs-lookup"><span data-stu-id="67f16-104">For example, by calling <code>.Include(e =&gt; e.RelatedNavProp)</code>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="67f16-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="67f16-105">Suggestion</span></span>

<span data-ttu-id="67f16-106">Questa modifica riguarda solo il codice che usa elementi QueryView con relazioni 1-0..1 in caso di esecuzione di query che chiamano .Include.</span><span class="sxs-lookup"><span data-stu-id="67f16-106">This change only affects code that uses QueryViews with 1-0..1 relationships when running queries that call .Include.</span></span> <span data-ttu-id="67f16-107">Migliora l'affidabilità e dovrebbe essere trasparente a quasi tutte le app.</span><span class="sxs-lookup"><span data-stu-id="67f16-107">It improves reliability and should be transparent to almost all apps.</span></span> <span data-ttu-id="67f16-108">Se tuttavia questa modifica causa un comportamento imprevisto, è possibile disabilitarla aggiungendo la voce seguente alla sezione <code>&lt;appSettings&gt;</code> del file di configurazione dell'app:</span><span class="sxs-lookup"><span data-stu-id="67f16-108">However, if it causes unexpected behavior, you can disable it by adding the following entry to the <code>&lt;appSettings&gt;</code> section of the app's configuration file:</span></span><pre><code class="lang-xml">&lt;add key=&quot;EntityFramework_SimplifyUserSpecifiedViews&quot; value=&quot;false&quot; /&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="67f16-109">Nome</span><span class="sxs-lookup"><span data-stu-id="67f16-109">Name</span></span>    | <span data-ttu-id="67f16-110">Valore</span><span class="sxs-lookup"><span data-stu-id="67f16-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="67f16-111">Scope</span><span class="sxs-lookup"><span data-stu-id="67f16-111">Scope</span></span>   |<span data-ttu-id="67f16-112">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="67f16-112">Edge</span></span>|
|<span data-ttu-id="67f16-113">Version</span><span class="sxs-lookup"><span data-stu-id="67f16-113">Version</span></span>|<span data-ttu-id="67f16-114">4.5.2</span><span class="sxs-lookup"><span data-stu-id="67f16-114">4.5.2</span></span>|
|<span data-ttu-id="67f16-115">Type</span><span class="sxs-lookup"><span data-stu-id="67f16-115">Type</span></span>|<span data-ttu-id="67f16-116">Runtime</span><span class="sxs-lookup"><span data-stu-id="67f16-116">Runtime</span></span>|
