---
ms.openlocfilehash: e5d81d791e1a2f1a2dbdafc787dec1227423883d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67803179"
---
### <a name="opt-in-break-to-revert-from-different-45-sql-generation-to-simpler-40-sql-generation"></a><span data-ttu-id="b129b-101">Interruzione del consenso esplicito per tornare alla generazione di codice SQL più semplice della versione 4.0 dalla versione 4.5</span><span class="sxs-lookup"><span data-stu-id="b129b-101">Opt-in break to revert from different 4.5 SQL generation to simpler 4.0 SQL generation</span></span>

|   |   |
|---|---|
|<span data-ttu-id="b129b-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="b129b-102">Details</span></span>|<span data-ttu-id="b129b-103">Le query che producono istruzioni JSON e contengono una chiamata a un'operazione di limitazione senza prima usare OrderBy producono ora codice SQL più semplice.</span><span class="sxs-lookup"><span data-stu-id="b129b-103">Queries that produce JOIN statements and contain a call to a limiting operation without first using OrderBy now produce simpler SQL.</span></span> <span data-ttu-id="b129b-104">Dopo l'aggiornamento a .NET Framework 4.5, queste query producevano codice SQL più complesso rispetto alle versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="b129b-104">After upgrading to .NET Framework 4.5, these queries produced more complicated SQL than previous versions.</span></span>|
|<span data-ttu-id="b129b-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="b129b-105">Suggestion</span></span>|<span data-ttu-id="b129b-106">Questa funzionalità è disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b129b-106">This feature is disabled by default.</span></span> <span data-ttu-id="b129b-107">Se Entity Framework genera istruzioni JOIN aggiuntive che causano una riduzione del livello delle prestazioni, è possibile abilitare questa funzionalità aggiungendo la voce seguente alla sezione <code>&lt;appSettings&gt;</code> del file di configurazione dell'applicazione (app.config):</span><span class="sxs-lookup"><span data-stu-id="b129b-107">If Entity Framework generates extra JOIN statements that cause performance degradation, you can enable this feature by adding the following entry to the <code>&lt;appSettings&gt;</code> section of the application configuration (app.config) file:</span></span><pre><code class="lang-xml">&lt;add key=&quot;EntityFramework_SimplifyLimitOperations&quot; value=&quot;true&quot; /&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="b129b-108">Scope</span><span class="sxs-lookup"><span data-stu-id="b129b-108">Scope</span></span>|<span data-ttu-id="b129b-109">Trasparente</span><span class="sxs-lookup"><span data-stu-id="b129b-109">Transparent</span></span>|
|<span data-ttu-id="b129b-110">Versione</span><span class="sxs-lookup"><span data-stu-id="b129b-110">Version</span></span>|<span data-ttu-id="b129b-111">4.5.2</span><span class="sxs-lookup"><span data-stu-id="b129b-111">4.5.2</span></span>|
|<span data-ttu-id="b129b-112">Type</span><span class="sxs-lookup"><span data-stu-id="b129b-112">Type</span></span>|<span data-ttu-id="b129b-113">Runtime</span><span class="sxs-lookup"><span data-stu-id="b129b-113">Runtime</span></span>|
