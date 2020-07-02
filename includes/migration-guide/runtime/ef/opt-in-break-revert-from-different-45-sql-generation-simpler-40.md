---
ms.openlocfilehash: 22b5abbe769733e8d5ca3e78dd9e6e13b2363737
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620311"
---
### <a name="opt-in-break-to-revert-from-different-45-sql-generation-to-simpler-40-sql-generation"></a><span data-ttu-id="5cd84-101">Interruzione del consenso esplicito per tornare alla generazione di codice SQL più semplice della versione 4.0 dalla versione 4.5</span><span class="sxs-lookup"><span data-stu-id="5cd84-101">Opt-in break to revert from different 4.5 SQL generation to simpler 4.0 SQL generation</span></span>

#### <a name="details"></a><span data-ttu-id="5cd84-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="5cd84-102">Details</span></span>

<span data-ttu-id="5cd84-103">Le query che producono istruzioni JSON e contengono una chiamata a un'operazione di limitazione senza prima usare OrderBy producono ora codice SQL più semplice.</span><span class="sxs-lookup"><span data-stu-id="5cd84-103">Queries that produce JOIN statements and contain a call to a limiting operation without first using OrderBy now produce simpler SQL.</span></span> <span data-ttu-id="5cd84-104">Dopo l'aggiornamento a .NET Framework 4.5, queste query producevano codice SQL più complesso rispetto alle versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="5cd84-104">After upgrading to .NET Framework 4.5, these queries produced more complicated SQL than previous versions.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="5cd84-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="5cd84-105">Suggestion</span></span>

<span data-ttu-id="5cd84-106">Questa funzionalità è disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="5cd84-106">This feature is disabled by default.</span></span> <span data-ttu-id="5cd84-107">Se Entity Framework genera istruzioni JOIN aggiuntive che causano una riduzione del livello delle prestazioni, è possibile abilitare questa funzionalità aggiungendo la voce seguente alla sezione <code>&lt;appSettings&gt;</code> del file di configurazione dell'applicazione (app.config):</span><span class="sxs-lookup"><span data-stu-id="5cd84-107">If Entity Framework generates extra JOIN statements that cause performance degradation, you can enable this feature by adding the following entry to the <code>&lt;appSettings&gt;</code> section of the application configuration (app.config) file:</span></span><pre><code class="lang-xml">&lt;add key=&quot;EntityFramework_SimplifyLimitOperations&quot; value=&quot;true&quot; /&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="5cd84-108">Nome</span><span class="sxs-lookup"><span data-stu-id="5cd84-108">Name</span></span>    | <span data-ttu-id="5cd84-109">Valore</span><span class="sxs-lookup"><span data-stu-id="5cd84-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="5cd84-110">Scope</span><span class="sxs-lookup"><span data-stu-id="5cd84-110">Scope</span></span>   |<span data-ttu-id="5cd84-111">Modalità trasparente</span><span class="sxs-lookup"><span data-stu-id="5cd84-111">Transparent</span></span>|
|<span data-ttu-id="5cd84-112">Version</span><span class="sxs-lookup"><span data-stu-id="5cd84-112">Version</span></span>|<span data-ttu-id="5cd84-113">4.5.2</span><span class="sxs-lookup"><span data-stu-id="5cd84-113">4.5.2</span></span>|
|<span data-ttu-id="5cd84-114">Type</span><span class="sxs-lookup"><span data-stu-id="5cd84-114">Type</span></span>|<span data-ttu-id="5cd84-115">Runtime</span><span class="sxs-lookup"><span data-stu-id="5cd84-115">Runtime</span></span>|
