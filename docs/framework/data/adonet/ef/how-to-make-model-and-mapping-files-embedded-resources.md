---
title: 'Procedura: definire file di modello e di mapping come risorse incorporate'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 20dfae4d-e95a-4264-9540-f5ad23b462d3
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 98fb3ada369279a34ed08110644aabcbbe72a501
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-make-model-and-mapping-files-embedded-resources"></a><span data-ttu-id="6277a-102">Procedura: definire file di modello e di mapping come risorse incorporate</span><span class="sxs-lookup"><span data-stu-id="6277a-102">How to: Make Model and Mapping Files Embedded Resources</span></span>
<span data-ttu-id="6277a-103">Il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] consente di distribuire i file di modello e mapping come risorse incorporate di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6277a-103">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] enables you to deploy model and mapping files as embedded resources of an application.</span></span> <span data-ttu-id="6277a-104">L'assembly con i file di mapping e di modello incorporati deve essere caricato nello stesso dominio applicazione della connessione dell'entità.</span><span class="sxs-lookup"><span data-stu-id="6277a-104">The assembly with the embedded model and mapping files must be loaded in the same application domain as the entity connection.</span></span> <span data-ttu-id="6277a-105">Per ulteriori informazioni, vedere [le stringhe di connessione](../../../../../docs/framework/data/adonet/ef/connection-strings.md).</span><span class="sxs-lookup"><span data-stu-id="6277a-105">For more information, see [Connection Strings](../../../../../docs/framework/data/adonet/ef/connection-strings.md).</span></span> <span data-ttu-id="6277a-106">Gli strumenti [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] incorporano i file di modello e di mapping per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6277a-106">By default, the [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] tools embed the model and mapping files.</span></span> <span data-ttu-id="6277a-107">Quando si definiscono manualmente i file di modello e di mapping, utilizzare questa procedura per assicurarsi che i file vengano distribuiti come risorse incorporate insieme all'applicazione [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6277a-107">When you manually define the model and mapping files, use this procedure to ensure that the files are deployed as embedded resources together with an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6277a-108">Per gestire le risorse incorporate, è necessario ripetere la procedura ogni volta che si modificano i file di modello e di mapping.</span><span class="sxs-lookup"><span data-stu-id="6277a-108">To maintain embedded resources, you must repeat this procedure whenever the model and mapping files are modified.</span></span>  
  
### <a name="to-embed-model-and-mapping-files"></a><span data-ttu-id="6277a-109">Per incorporare i file di modello e di mapping</span><span class="sxs-lookup"><span data-stu-id="6277a-109">To embed model and mapping files</span></span>  
  
1.  <span data-ttu-id="6277a-110">In **Esplora**, selezionare il file concettuale (CSDL).</span><span class="sxs-lookup"><span data-stu-id="6277a-110">In **Solution Explorer**, select the conceptual (.csdl) file.</span></span>  
  
2.  <span data-ttu-id="6277a-111">Nel **proprietà** riquadro, impostare **azione di compilazione** a **risorsa incorporata**.</span><span class="sxs-lookup"><span data-stu-id="6277a-111">In the **Properties** pane, set **Build Action** to **Embedded Resource**.</span></span>  
  
3.  <span data-ttu-id="6277a-112">Ripetere i passaggi 1 e 2 per il file di archiviazione (.ssdl) e il file di mapping (.msl).</span><span class="sxs-lookup"><span data-stu-id="6277a-112">Repeat steps 1 and 2 for the storage (.ssdl) file and the mapping (.msl) file.</span></span>  
  
4.  <span data-ttu-id="6277a-113">In **Esplora**, doppio clic sul file app. config e quindi modificare il `Metadata` parametro il `connectionString` attributo basato su uno dei formati seguenti:</span><span class="sxs-lookup"><span data-stu-id="6277a-113">In **Solution Explorer**, double-click the App.config file and then modify the `Metadata` parameter in the `connectionString` attribute based on one of the following formats:</span></span>  
  
    -   <span data-ttu-id="6277a-114">`Metadata=` `res://<assemblyFullName>/<resourceName>;`</span><span class="sxs-lookup"><span data-stu-id="6277a-114">`Metadata=` `res://<assemblyFullName>/<resourceName>;`</span></span>  
  
    -   <span data-ttu-id="6277a-115">`Metadata=` `res://*/<resourceName>;`</span><span class="sxs-lookup"><span data-stu-id="6277a-115">`Metadata=` `res://*/<resourceName>;`</span></span>  
  
    -   `Metadata=res://*;`  
  
     <span data-ttu-id="6277a-116">Per ulteriori informazioni, vedere [le stringhe di connessione](../../../../../docs/framework/data/adonet/ef/connection-strings.md).</span><span class="sxs-lookup"><span data-stu-id="6277a-116">For more information, see [Connection Strings](../../../../../docs/framework/data/adonet/ef/connection-strings.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6277a-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="6277a-117">Example</span></span>  
 <span data-ttu-id="6277a-118">Stringa di connessione seguente fa riferimento a modello incorporato e i file di mapping per il [modello Sales di AdventureWorks](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832).</span><span class="sxs-lookup"><span data-stu-id="6277a-118">The following connection string references embedded model and mapping files for the [AdventureWorks Sales Model](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832).</span></span> <span data-ttu-id="6277a-119">Questa stringa di connessione è archiviata nel file App.config del progetto.</span><span class="sxs-lookup"><span data-stu-id="6277a-119">This connection string is stored in the project's App.config file.</span></span>  
  
  
  
## <a name="see-also"></a><span data-ttu-id="6277a-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6277a-120">See Also</span></span>  
 [<span data-ttu-id="6277a-121">Modellazione e Mapping</span><span class="sxs-lookup"><span data-stu-id="6277a-121">Modeling and Mapping</span></span>](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)  
 [<span data-ttu-id="6277a-122">Procedura: definire la stringa di connessione</span><span class="sxs-lookup"><span data-stu-id="6277a-122">How to: Define the Connection String</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-define-the-connection-string.md)  
 [<span data-ttu-id="6277a-123">Procedura: compilare una stringa di connessione EntityConnection</span><span class="sxs-lookup"><span data-stu-id="6277a-123">How to: Build an EntityConnection Connection String</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)  
 [<span data-ttu-id="6277a-124">Strumenti di ADO.NET Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="6277a-124">ADO.NET Entity Data Model  Tools</span></span>](http://msdn.microsoft.com/en-us/91076853-0881-421b-837a-f582f36be527)
