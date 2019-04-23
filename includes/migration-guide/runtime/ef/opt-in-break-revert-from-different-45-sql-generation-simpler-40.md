---
ms.openlocfilehash: e5d81d791e1a2f1a2dbdafc787dec1227423883d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774260"
---
### <a name="opt-in-break-to-revert-from-different-45-sql-generation-to-simpler-40-sql-generation"></a><span data-ttu-id="21cc9-101">Interruzione del consenso esplicito per tornare alla generazione di codice SQL più semplice della versione 4.0 dalla versione 4.5</span><span class="sxs-lookup"><span data-stu-id="21cc9-101">Opt-in break to revert from different 4.5 SQL generation to simpler 4.0 SQL generation</span></span>

|   |   |
|---|---|
|<span data-ttu-id="21cc9-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="21cc9-102">Details</span></span>|<span data-ttu-id="21cc9-103">Le query che producono istruzioni JSON e contengono una chiamata a un'operazione di limitazione senza prima usare OrderBy producono ora codice SQL più semplice.</span><span class="sxs-lookup"><span data-stu-id="21cc9-103">Queries that produce JOIN statements and contain a call to a limiting operation without first using OrderBy now produce simpler SQL.</span></span> <span data-ttu-id="21cc9-104">Dopo l'aggiornamento a .NET Framework 4.5, queste query producevano codice SQL più complesso rispetto alle versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="21cc9-104">After upgrading to .NET Framework 4.5, these queries produced more complicated SQL than previous versions.</span></span>|
|<span data-ttu-id="21cc9-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="21cc9-105">Suggestion</span></span>|<span data-ttu-id="21cc9-106">Questa funzionalità è disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="21cc9-106">This feature is disabled by default.</span></span> <span data-ttu-id="21cc9-107">Se Entity Framework genera istruzioni JOIN aggiuntive che causano una riduzione del livello delle prestazioni, è possibile abilitare questa funzionalità aggiungendo la voce seguente alla sezione <code>&lt;appSettings&gt;</code> del file di configurazione dell'applicazione (app.config):</span><span class="sxs-lookup"><span data-stu-id="21cc9-107">If Entity Framework generates extra JOIN statements that cause performance degradation, you can enable this feature by adding the following entry to the <code>&lt;appSettings&gt;</code> section of the application configuration (app.config) file:</span></span><pre><code class="lang-xml">&lt;add key=&quot;EntityFramework_SimplifyLimitOperations&quot; value=&quot;true&quot; /&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="21cc9-108">Ambito</span><span class="sxs-lookup"><span data-stu-id="21cc9-108">Scope</span></span>|<span data-ttu-id="21cc9-109">Trasparente</span><span class="sxs-lookup"><span data-stu-id="21cc9-109">Transparent</span></span>|
|<span data-ttu-id="21cc9-110">Versione</span><span class="sxs-lookup"><span data-stu-id="21cc9-110">Version</span></span>|<span data-ttu-id="21cc9-111">4.5.2</span><span class="sxs-lookup"><span data-stu-id="21cc9-111">4.5.2</span></span>|
|<span data-ttu-id="21cc9-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="21cc9-112">Type</span></span>|<span data-ttu-id="21cc9-113">Runtime</span><span class="sxs-lookup"><span data-stu-id="21cc9-113">Runtime</span></span>|
