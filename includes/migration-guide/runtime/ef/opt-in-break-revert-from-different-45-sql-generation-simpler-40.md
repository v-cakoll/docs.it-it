---
ms.openlocfilehash: 64d540278544e74c46d46b77c97bccd26d4116dd
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2019
ms.locfileid: "67803179"
---
### <a name="opt-in-break-to-revert-from-different-45-sql-generation-to-simpler-40-sql-generation"></a><span data-ttu-id="d230a-101">Interruzione del consenso esplicito per tornare alla generazione di codice SQL più semplice della versione 4.0 dalla versione 4.5</span><span class="sxs-lookup"><span data-stu-id="d230a-101">Opt-in break to revert from different 4.5 SQL generation to simpler 4.0 SQL generation</span></span>

|   |   |
|---|---|
|<span data-ttu-id="d230a-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="d230a-102">Details</span></span>|<span data-ttu-id="d230a-103">Le query che producono istruzioni JSON e contengono una chiamata a un'operazione di limitazione senza prima usare OrderBy producono ora codice SQL più semplice.</span><span class="sxs-lookup"><span data-stu-id="d230a-103">Queries that produce JOIN statements and contain a call to a limiting operation without first using OrderBy now produce simpler SQL.</span></span> <span data-ttu-id="d230a-104">Dopo l'aggiornamento a .NET Framework 4.5, queste query producevano codice SQL più complesso rispetto alle versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="d230a-104">After upgrading to .NET Framework 4.5, these queries produced more complicated SQL than previous versions.</span></span>|
|<span data-ttu-id="d230a-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="d230a-105">Suggestion</span></span>|<span data-ttu-id="d230a-106">Questa funzionalità è disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="d230a-106">This feature is disabled by default.</span></span> <span data-ttu-id="d230a-107">Se Entity Framework genera istruzioni JOIN aggiuntive che causano una riduzione del livello delle prestazioni, è possibile abilitare questa funzionalità aggiungendo la voce seguente alla sezione <code>&lt;appSettings&gt;</code> del file di configurazione dell'applicazione (app.config):</span><span class="sxs-lookup"><span data-stu-id="d230a-107">If Entity Framework generates extra JOIN statements that cause performance degradation, you can enable this feature by adding the following entry to the <code>&lt;appSettings&gt;</code> section of the application configuration (app.config) file:</span></span><pre><code class="lang-xml">&lt;add key=&quot;EntityFramework_SimplifyLimitOperations&quot; value=&quot;true&quot; /&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="d230a-108">Ambito</span><span class="sxs-lookup"><span data-stu-id="d230a-108">Scope</span></span>|<span data-ttu-id="d230a-109">Trasparente</span><span class="sxs-lookup"><span data-stu-id="d230a-109">Transparent</span></span>|
|<span data-ttu-id="d230a-110">Versione</span><span class="sxs-lookup"><span data-stu-id="d230a-110">Version</span></span>|<span data-ttu-id="d230a-111">4.5.2</span><span class="sxs-lookup"><span data-stu-id="d230a-111">4.5.2</span></span>|
|<span data-ttu-id="d230a-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="d230a-112">Type</span></span>|<span data-ttu-id="d230a-113">Runtime</span><span class="sxs-lookup"><span data-stu-id="d230a-113">Runtime</span></span>|

