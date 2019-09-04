---
title: 'Procedura: Definire i file di modello e di mapping come risorse incorporate'
ms.date: 03/30/2017
ms.assetid: 20dfae4d-e95a-4264-9540-f5ad23b462d3
ms.openlocfilehash: c88e0c09742d76c7508d7d782eabbe46035d3501
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251441"
---
# <a name="how-to-make-model-and-mapping-files-embedded-resources"></a><span data-ttu-id="418d3-102">Procedura: Definire i file di modello e di mapping come risorse incorporate</span><span class="sxs-lookup"><span data-stu-id="418d3-102">How to: Make Model and Mapping Files Embedded Resources</span></span>
<span data-ttu-id="418d3-103">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] Consente di distribuire i file di modello e di mapping come risorse incorporate di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="418d3-103">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] enables you to deploy model and mapping files as embedded resources of an application.</span></span> <span data-ttu-id="418d3-104">L'assembly con i file di mapping e di modello incorporati deve essere caricato nello stesso dominio applicazione della connessione dell'entità.</span><span class="sxs-lookup"><span data-stu-id="418d3-104">The assembly with the embedded model and mapping files must be loaded in the same application domain as the entity connection.</span></span> <span data-ttu-id="418d3-105">Per altre informazioni, vedere [Connection Strings](connection-strings.md) (Stringhe di connessione).</span><span class="sxs-lookup"><span data-stu-id="418d3-105">For more information, see [Connection Strings](connection-strings.md).</span></span> <span data-ttu-id="418d3-106">Per impostazione predefinita, gli strumenti di Entity Data Model incorporano i file di modello e di mapping.</span><span class="sxs-lookup"><span data-stu-id="418d3-106">By default, the Entity Data Model tools embed the model and mapping files.</span></span> <span data-ttu-id="418d3-107">Quando si definiscono manualmente i file di modello e di mapping, utilizzare questa procedura per assicurarsi che i file vengano distribuiti come risorse incorporate insieme all'applicazione [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="418d3-107">When you manually define the model and mapping files, use this procedure to ensure that the files are deployed as embedded resources together with an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="418d3-108">Per gestire le risorse incorporate, è necessario ripetere la procedura ogni volta che si modificano i file di modello e di mapping.</span><span class="sxs-lookup"><span data-stu-id="418d3-108">To maintain embedded resources, you must repeat this procedure whenever the model and mapping files are modified.</span></span>  
  
### <a name="to-embed-model-and-mapping-files"></a><span data-ttu-id="418d3-109">Per incorporare i file di modello e di mapping</span><span class="sxs-lookup"><span data-stu-id="418d3-109">To embed model and mapping files</span></span>  
  
1. <span data-ttu-id="418d3-110">In **Esplora soluzioni**selezionare il file concettuale (con estensione CSDL).</span><span class="sxs-lookup"><span data-stu-id="418d3-110">In **Solution Explorer**, select the conceptual (.csdl) file.</span></span>  
  
2. <span data-ttu-id="418d3-111">Nel riquadro **Proprietà** impostare azione di **compilazione** su **risorsa incorporata**.</span><span class="sxs-lookup"><span data-stu-id="418d3-111">In the **Properties** pane, set **Build Action** to **Embedded Resource**.</span></span>  
  
3. <span data-ttu-id="418d3-112">Ripetere i passaggi 1 e 2 per il file di archiviazione (.ssdl) e il file di mapping (.msl).</span><span class="sxs-lookup"><span data-stu-id="418d3-112">Repeat steps 1 and 2 for the storage (.ssdl) file and the mapping (.msl) file.</span></span>  
  
4. <span data-ttu-id="418d3-113">In **Esplora soluzioni**fare doppio clic sul file app. config e quindi modificare il `Metadata` parametro nell' `connectionString` attributo in base a uno dei formati seguenti:</span><span class="sxs-lookup"><span data-stu-id="418d3-113">In **Solution Explorer**, double-click the App.config file and then modify the `Metadata` parameter in the `connectionString` attribute based on one of the following formats:</span></span>  
  
    - <span data-ttu-id="418d3-114">`Metadata=` `res://<assemblyFullName>/<resourceName>;`</span><span class="sxs-lookup"><span data-stu-id="418d3-114">`Metadata=` `res://<assemblyFullName>/<resourceName>;`</span></span>  
  
    - <span data-ttu-id="418d3-115">`Metadata=` `res://*/<resourceName>;`</span><span class="sxs-lookup"><span data-stu-id="418d3-115">`Metadata=` `res://*/<resourceName>;`</span></span>  
  
    - `Metadata=res://*;`  
  
     <span data-ttu-id="418d3-116">Per altre informazioni, vedere [Connection Strings](connection-strings.md) (Stringhe di connessione).</span><span class="sxs-lookup"><span data-stu-id="418d3-116">For more information, see [Connection Strings](connection-strings.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="418d3-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="418d3-117">Example</span></span>  
 <span data-ttu-id="418d3-118">La stringa di connessione seguente fa riferimento ai file di modello e di mapping incorporati per il [modello Sales di AdventureWorks](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span><span class="sxs-lookup"><span data-stu-id="418d3-118">The following connection string references embedded model and mapping files for the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span></span> <span data-ttu-id="418d3-119">Questa stringa di connessione è archiviata nel file App.config del progetto.</span><span class="sxs-lookup"><span data-stu-id="418d3-119">This connection string is stored in the project's App.config file.</span></span>  

## <a name="see-also"></a><span data-ttu-id="418d3-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="418d3-120">See also</span></span>

- [<span data-ttu-id="418d3-121">Modellazione e mapping</span><span class="sxs-lookup"><span data-stu-id="418d3-121">Modeling and Mapping</span></span>](modeling-and-mapping.md)
- [<span data-ttu-id="418d3-122">Procedura: Definire la stringa di connessione</span><span class="sxs-lookup"><span data-stu-id="418d3-122">How to: Define the Connection String</span></span>](how-to-define-the-connection-string.md)
- [<span data-ttu-id="418d3-123">Procedura: Compilare una stringa di connessione EntityConnection</span><span class="sxs-lookup"><span data-stu-id="418d3-123">How to: Build an EntityConnection Connection String</span></span>](how-to-build-an-entityconnection-connection-string.md)
- <span data-ttu-id="418d3-124">[Strumenti Entity Data Model ADO.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="418d3-124">[ADO.NET Entity Data Model Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
