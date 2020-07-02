---
ms.openlocfilehash: 768a948849064cedb38110f5ed271717442325c0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620314"
---
### <a name="log-file-name-created-by-the-objectcontextcreatedatabase-method-has-changed-to-match-sql-server-specifications"></a><span data-ttu-id="5300c-101">Il nome del file di log creato dal metodo ObjectContext.CreateDatabase è stato modificato in base alle specifiche di SQL Server</span><span class="sxs-lookup"><span data-stu-id="5300c-101">Log file name created by the ObjectContext.CreateDatabase method has changed to match SQL Server specifications</span></span>

#### <a name="details"></a><span data-ttu-id="5300c-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="5300c-102">Details</span></span>

<span data-ttu-id="5300c-103">Quando il metodo <xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=fullName> viene chiamato direttamente oppure tramite Code First con il provider SqlClient e un valore AttachDBFilename nella stringa di connessione, viene creato un file di log denominato nomefile_log.ldf invece di nomefile.ldf (dove nomefile è il nome del file specificato dal valore AttachDBFilename).</span><span class="sxs-lookup"><span data-stu-id="5300c-103">When the <xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=fullName> method is called either directly or by using Code First with the SqlClient provider and an AttachDBFilename value in the connection string, it creates a log file named filename_log.ldf instead of filename.ldf (where filename is the name of the file specified by the AttachDBFilename value).</span></span> <span data-ttu-id="5300c-104">Questa modifica migliora il debug fornendo un file di log il cui nome si basa sulle specifiche di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5300c-104">This change improves debugging by providing a log file named according to SQL Server specifications.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="5300c-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="5300c-105">Suggestion</span></span>

<span data-ttu-id="5300c-106">Se il nome del file di log è importante per un'app, l'app deve essere aggiornata in modo da prevedere il formato nomefile_log.ldf standard.</span><span class="sxs-lookup"><span data-stu-id="5300c-106">If the log file name is important for an app, the app should be updated to expect the standard _log.ldf file name format.</span></span>

| <span data-ttu-id="5300c-107">Nome</span><span class="sxs-lookup"><span data-stu-id="5300c-107">Name</span></span>    | <span data-ttu-id="5300c-108">Valore</span><span class="sxs-lookup"><span data-stu-id="5300c-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="5300c-109">Scope</span><span class="sxs-lookup"><span data-stu-id="5300c-109">Scope</span></span>   |<span data-ttu-id="5300c-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="5300c-110">Edge</span></span>|
|<span data-ttu-id="5300c-111">Version</span><span class="sxs-lookup"><span data-stu-id="5300c-111">Version</span></span>|<span data-ttu-id="5300c-112">4.5</span><span class="sxs-lookup"><span data-stu-id="5300c-112">4.5</span></span>|
|<span data-ttu-id="5300c-113">Type</span><span class="sxs-lookup"><span data-stu-id="5300c-113">Type</span></span>|<span data-ttu-id="5300c-114">Runtime</span><span class="sxs-lookup"><span data-stu-id="5300c-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="5300c-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="5300c-115">Affected APIs</span></span>

-<xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=nameWithType></li></ul>|
