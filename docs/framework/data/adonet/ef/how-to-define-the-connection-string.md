---
title: 'Procedura: definire una stringa di connessione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6027335d-4e26-420d-9151-6523289b1989
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: e42fba03b50c0ffd765bbe25ef60b3317ed1b307
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-define-the-connection-string"></a><span data-ttu-id="e0489-102">Procedura: definire una stringa di connessione</span><span class="sxs-lookup"><span data-stu-id="e0489-102">How to: Define the Connection String</span></span>
<span data-ttu-id="e0489-103">In questo argomento viene illustrato come definire la stringa di connessione usata per la connessione a un modello concettuale.</span><span class="sxs-lookup"><span data-stu-id="e0489-103">This topic shows how to define the connection string that is used when connecting to a conceptual model.</span></span> <span data-ttu-id="e0489-104">Questo argomento è basato sul [Sales di AdventureWorks](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) modello concettuale.</span><span class="sxs-lookup"><span data-stu-id="e0489-104">This topic is based on the [AdventureWorks Sales](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) conceptual model.</span></span> <span data-ttu-id="e0489-105">Il modello Sales di AdventureWorks viene usato in tutti gli argomenti correlati ad attività inclusi nella documentazione di [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e0489-105">The AdventureWorks Sales Model is used throughout the task-related topics in the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] documentation.</span></span> <span data-ttu-id="e0489-106">Questo argomento si presuppone che sia già stato configurato il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] e definito il modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="e0489-106">This topic assumes that you have already configured the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] and defined the AdventureWorks Sales Model.</span></span> <span data-ttu-id="e0489-107">Per ulteriori informazioni, vedere [procedura: definire manualmente i file di modello e Mapping](http://msdn.microsoft.com/en-us/d4fd6864-f2a1-48f0-aa32-1e318775a99a).</span><span class="sxs-lookup"><span data-stu-id="e0489-107">For more information, see [How to: Manually Define the Model and Mapping Files](http://msdn.microsoft.com/en-us/d4fd6864-f2a1-48f0-aa32-1e318775a99a).</span></span> <span data-ttu-id="e0489-108">Le procedure descritte in questo argomento sono incluse anche in [procedura: configurare manualmente un progetto Entity Framework](http://msdn.microsoft.com/en-us/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e).</span><span class="sxs-lookup"><span data-stu-id="e0489-108">The procedures in this topic are also included in [How to: Manually Configure an Entity Framework Project](http://msdn.microsoft.com/en-us/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e0489-109">Se si usa la Procedura guidata [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] in un progetto [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)], viene automaticamente generato un file con estensione edmx e il progetto viene configurato per l'uso di [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e0489-109">If you use the [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] Wizard in a [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] project, it automatically generates an .edmx file and configures the project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="e0489-110">Per ulteriori informazioni, vedere [procedura: utilizzare la procedura guidata Entity Data Model](http://msdn.microsoft.com/en-us/dadb058a-c5d9-4c5c-8b01-28044112231d)</span><span class="sxs-lookup"><span data-stu-id="e0489-110">For more information, see [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/en-us/dadb058a-c5d9-4c5c-8b01-28044112231d)</span></span>  
  
### <a name="to-define-the-entity-framework-connection-string"></a><span data-ttu-id="e0489-111">Per definire la stringa di connessione Entity Framework</span><span class="sxs-lookup"><span data-stu-id="e0489-111">To define the Entity Framework connection string</span></span>  
  
-   <span data-ttu-id="e0489-112">Aprire il file di configurazione dell'applicazione (app.config) del progetto e aggiungere la stringa di connessione seguente.</span><span class="sxs-lookup"><span data-stu-id="e0489-112">Open the project's application configuration file (app.config) and add the following connection string:</span></span>  
  
  
  
     <span data-ttu-id="e0489-113">Se il progetto non dispone di un file di configurazione dell'applicazione, è possibile aggiungerne una selezionando **Aggiungi nuovo elemento** dal **progetto** dal menu selezionando il **generale** categoria selezione **File di configurazione applicazione**e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="e0489-113">If your project does not have an application configuration file, you can add one by selecting **Add New Item** from the **Project** menu, selecting the **General** category, selecting **Application Configuration File**, and then clicking **Add**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0489-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0489-114">See Also</span></span>  
 [<span data-ttu-id="e0489-115">Guida rapida</span><span class="sxs-lookup"><span data-stu-id="e0489-115">Quickstart</span></span>](http://msdn.microsoft.com/en-us/0bc534be-789f-4819-b9f6-76e51d961675)  
 [<span data-ttu-id="e0489-116">Procedura: creare un nuovo File con estensione edmx</span><span class="sxs-lookup"><span data-stu-id="e0489-116">How to: Create a New .edmx File</span></span>](http://msdn.microsoft.com/en-us/beb8189e-e51c-4051-839c-9902c224abf2)  
 [<span data-ttu-id="e0489-117">Strumenti di ADO.NET Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="e0489-117">ADO.NET Entity Data Model  Tools</span></span>](http://msdn.microsoft.com/en-us/91076853-0881-421b-837a-f582f36be527)
