---
ms.openlocfilehash: cf1a8169351e29c18d85303fb32d4394877448f4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804272"
---
### <a name="log-file-name-created-by-the-objectcontextcreatedatabase-method-has-changed-to-match-sql-server-specifications"></a><span data-ttu-id="06cd7-101">Il nome del file di log creato dal metodo ObjectContext.CreateDatabase è stato modificato in base alle specifiche di SQL Server</span><span class="sxs-lookup"><span data-stu-id="06cd7-101">Log file name created by the ObjectContext.CreateDatabase method has changed to match SQL Server specifications</span></span>

|   |   |
|---|---|
|<span data-ttu-id="06cd7-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="06cd7-102">Details</span></span>|<span data-ttu-id="06cd7-103">Quando il metodo <xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=name> viene chiamato direttamente oppure tramite Code First con il provider SqlClient e un valore AttachDBFilename nella stringa di connessione, viene creato un file di log denominato nomefile_log.ldf invece di nomefile.ldf (dove nomefile è il nome del file specificato dal valore AttachDBFilename).</span><span class="sxs-lookup"><span data-stu-id="06cd7-103">When the <xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=name> method is called either directly or by using Code First with the SqlClient provider and an AttachDBFilename value in the connection string, it creates a log file named filename_log.ldf instead of filename.ldf (where filename is the name of the file specified by the AttachDBFilename value).</span></span> <span data-ttu-id="06cd7-104">Questa modifica migliora il debug fornendo un file di log il cui nome si basa sulle specifiche di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="06cd7-104">This change improves debugging by providing a log file named according to SQL Server specifications.</span></span>|
|<span data-ttu-id="06cd7-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="06cd7-105">Suggestion</span></span>|<span data-ttu-id="06cd7-106">Se il nome del file di log è importante per un'app, l'app deve essere aggiornata in modo da prevedere il formato nomefile_log.ldf standard.</span><span class="sxs-lookup"><span data-stu-id="06cd7-106">If the log file name is important for an app, the app should be updated to expect the standard _log.ldf file name format.</span></span>|
|<span data-ttu-id="06cd7-107">Ambito</span><span class="sxs-lookup"><span data-stu-id="06cd7-107">Scope</span></span>|<span data-ttu-id="06cd7-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="06cd7-108">Edge</span></span>|
|<span data-ttu-id="06cd7-109">Versione</span><span class="sxs-lookup"><span data-stu-id="06cd7-109">Version</span></span>|<span data-ttu-id="06cd7-110">4.5</span><span class="sxs-lookup"><span data-stu-id="06cd7-110">4.5</span></span>|
|<span data-ttu-id="06cd7-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="06cd7-111">Type</span></span>|<span data-ttu-id="06cd7-112">Runtime</span><span class="sxs-lookup"><span data-stu-id="06cd7-112">Runtime</span></span>|
|<span data-ttu-id="06cd7-113">API interessate</span><span class="sxs-lookup"><span data-stu-id="06cd7-113">Affected APIs</span></span>|<ul><li><xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=nameWithType></li></ul>|
