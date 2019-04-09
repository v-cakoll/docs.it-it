---
title: 'Procedura: Definire i file di modello e di mapping come risorse incorporate'
ms.date: 03/30/2017
ms.assetid: 20dfae4d-e95a-4264-9540-f5ad23b462d3
ms.openlocfilehash: b00ccdd0a1fc1cb22cf7cc0d0a3177dcc0e8017f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59138593"
---
# <a name="how-to-make-model-and-mapping-files-embedded-resources"></a><span data-ttu-id="0920a-102">Procedura: Definire i file di modello e di mapping come risorse incorporate</span><span class="sxs-lookup"><span data-stu-id="0920a-102">How to: Make Model and Mapping Files Embedded Resources</span></span>
<span data-ttu-id="0920a-103">Il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] consente di distribuire file di modello e il mapping come risorse incorporate di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0920a-103">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] enables you to deploy model and mapping files as embedded resources of an application.</span></span> <span data-ttu-id="0920a-104">L'assembly con i file di mapping e di modello incorporati deve essere caricato nello stesso dominio applicazione della connessione dell'entità.</span><span class="sxs-lookup"><span data-stu-id="0920a-104">The assembly with the embedded model and mapping files must be loaded in the same application domain as the entity connection.</span></span> <span data-ttu-id="0920a-105">Per altre informazioni, vedere [Connection Strings](../../../../../docs/framework/data/adonet/ef/connection-strings.md) (Stringhe di connessione).</span><span class="sxs-lookup"><span data-stu-id="0920a-105">For more information, see [Connection Strings](../../../../../docs/framework/data/adonet/ef/connection-strings.md).</span></span> <span data-ttu-id="0920a-106">Gli strumenti [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] incorporano i file di modello e di mapping per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="0920a-106">By default, the [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] tools embed the model and mapping files.</span></span> <span data-ttu-id="0920a-107">Quando si definiscono manualmente i file di modello e di mapping, utilizzare questa procedura per assicurarsi che i file vengano distribuiti come risorse incorporate insieme all'applicazione [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0920a-107">When you manually define the model and mapping files, use this procedure to ensure that the files are deployed as embedded resources together with an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0920a-108">Per gestire le risorse incorporate, è necessario ripetere la procedura ogni volta che si modificano i file di modello e di mapping.</span><span class="sxs-lookup"><span data-stu-id="0920a-108">To maintain embedded resources, you must repeat this procedure whenever the model and mapping files are modified.</span></span>  
  
### <a name="to-embed-model-and-mapping-files"></a><span data-ttu-id="0920a-109">Per incorporare i file di modello e di mapping</span><span class="sxs-lookup"><span data-stu-id="0920a-109">To embed model and mapping files</span></span>  
  
1.  <span data-ttu-id="0920a-110">Nelle **Esplora soluzioni**, selezionare il file concettuale (CSDL).</span><span class="sxs-lookup"><span data-stu-id="0920a-110">In **Solution Explorer**, select the conceptual (.csdl) file.</span></span>  
  
2.  <span data-ttu-id="0920a-111">Nel **delle proprietà** riquadro, impostare **azione di compilazione** al **risorsa incorporata**.</span><span class="sxs-lookup"><span data-stu-id="0920a-111">In the **Properties** pane, set **Build Action** to **Embedded Resource**.</span></span>  
  
3.  <span data-ttu-id="0920a-112">Ripetere i passaggi 1 e 2 per il file di archiviazione (.ssdl) e il file di mapping (.msl).</span><span class="sxs-lookup"><span data-stu-id="0920a-112">Repeat steps 1 and 2 for the storage (.ssdl) file and the mapping (.msl) file.</span></span>  
  
4.  <span data-ttu-id="0920a-113">In **Esplora soluzioni**, fare doppio clic sul file app. config e quindi modificare il `Metadata` parametri nel `connectionString` attributo basato su uno dei formati seguenti:</span><span class="sxs-lookup"><span data-stu-id="0920a-113">In **Solution Explorer**, double-click the App.config file and then modify the `Metadata` parameter in the `connectionString` attribute based on one of the following formats:</span></span>  
  
    -   `Metadata=` `res://<assemblyFullName>/<resourceName>;`  
  
    -   `Metadata=` `res://*/<resourceName>;`  
  
    -   `Metadata=res://*;`  
  
     <span data-ttu-id="0920a-114">Per altre informazioni, vedere [Connection Strings](../../../../../docs/framework/data/adonet/ef/connection-strings.md) (Stringhe di connessione).</span><span class="sxs-lookup"><span data-stu-id="0920a-114">For more information, see [Connection Strings](../../../../../docs/framework/data/adonet/ef/connection-strings.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0920a-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="0920a-115">Example</span></span>  
 <span data-ttu-id="0920a-116">La stringa di connessione seguente fa riferimento a modello incorporato e file di mapping per il [modello Sales di AdventureWorks](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span><span class="sxs-lookup"><span data-stu-id="0920a-116">The following connection string references embedded model and mapping files for the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span></span> <span data-ttu-id="0920a-117">Questa stringa di connessione è archiviata nel file App.config del progetto.</span><span class="sxs-lookup"><span data-stu-id="0920a-117">This connection string is stored in the project's App.config file.</span></span>  

## <a name="see-also"></a><span data-ttu-id="0920a-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0920a-118">See also</span></span>

- [<span data-ttu-id="0920a-119">Modellazione e mapping</span><span class="sxs-lookup"><span data-stu-id="0920a-119">Modeling and Mapping</span></span>](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)
- [<span data-ttu-id="0920a-120">Procedura: Definire la stringa di connessione</span><span class="sxs-lookup"><span data-stu-id="0920a-120">How to: Define the Connection String</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-define-the-connection-string.md)
- [<span data-ttu-id="0920a-121">Procedura: Compilare una stringa di connessione EntityConnection</span><span class="sxs-lookup"><span data-stu-id="0920a-121">How to: Build an EntityConnection Connection String</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)
- [<span data-ttu-id="0920a-122">Strumenti di ADO.NET Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="0920a-122">ADO.NET Entity Data Model Tools</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
