---
title: Scrittura di un provider di dati Entity Framework
ms.date: 03/30/2017
ms.assetid: 092e88c4-a301-453a-b5c3-5740c6575a9f
ms.openlocfilehash: 578de94aa191d7302b762f1cdc87d4a6810037e3
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32762634"
---
# <a name="writing-an-entity-framework-data-provider"></a><span data-ttu-id="fb05d-102">Scrittura di un provider di dati Entity Framework</span><span class="sxs-lookup"><span data-stu-id="fb05d-102">Writing an Entity Framework Data Provider</span></span>
<span data-ttu-id="fb05d-103">In questa sezione viene descritto come scrivere un [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] provider per supportare un'origine dati diverso da SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fb05d-103">This section discusses how to write an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] provider to support a data source other than SQL Server.</span></span> <span data-ttu-id="fb05d-104">Il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] include un provider che supporta SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fb05d-104">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] includes a provider that supports SQL Server.</span></span>  
  
## <a name="introducing-the-entity-framework-provider-model"></a><span data-ttu-id="fb05d-105">Introduzione al modello di provider Entity Framework</span><span class="sxs-lookup"><span data-stu-id="fb05d-105">Introducing the Entity Framework Provider Model</span></span>  
 <span data-ttu-id="fb05d-106">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] è indipendente dal database ed è possibile scrivere un provider usando il modello di provider ADO.NET per connettersi a un set di origini dati differente.</span><span class="sxs-lookup"><span data-stu-id="fb05d-106">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] is database independent, and you can write a provider by using the ADO.NET Provider Model to connect to a diverse set of data sources.</span></span>  
  
 <span data-ttu-id="fb05d-107">Il provider di dati Entity Framework, compilato usando il modello di provider di dati ADO.NET, consente di eseguire le funzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fb05d-107">The Entity Framework data provider (built using the ADO.NET Data Provider model) performs the following functions:</span></span>  
  
-   <span data-ttu-id="fb05d-108">Mapping dei tipi primitivi EDM (Entity Data Model) ai tipi di provider.</span><span class="sxs-lookup"><span data-stu-id="fb05d-108">Maps Entity Data Model (EDM) primitive types to provider types.</span></span>  
  
-   <span data-ttu-id="fb05d-109">Esposizione delle funzioni specifiche del provider.</span><span class="sxs-lookup"><span data-stu-id="fb05d-109">Exposes provider-specific functions.</span></span>  
  
-   <span data-ttu-id="fb05d-110">Generazione di comandi specifici del provider per un determinato DbQueryCommandTree per supportare le query [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb05d-110">Generates provider-specific commands for a given DbQueryCommandTree to support [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] queries.</span></span>  
  
-   <span data-ttu-id="fb05d-111">Generazione di comandi di aggiornamento specifici del provider per un determinato DbModificationCommandTree per supportare gli aggiornamenti mediante [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb05d-111">Generates provider-specific update commands for a given DbModificationCommandTree to support updates through the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span>  
  
-   <span data-ttu-id="fb05d-112">Esposizione di file di mapping per la definizione dello schema di archiviazione per supportare la generazione di un modello basato su un database.</span><span class="sxs-lookup"><span data-stu-id="fb05d-112">Exposes mapping files for the store schema definition, to support generation of a model based on a database.</span></span>  
  
-   <span data-ttu-id="fb05d-113">Esposizione di metadati, ad esempio tabelle e visualizzazioni, mediante un modello concettuale.</span><span class="sxs-lookup"><span data-stu-id="fb05d-113">Exposes metadata (tables and views, for example) via a conceptual model.</span></span>  
  
 <span data-ttu-id="fb05d-114">![b42a7a5c&#45;0ac0&#45;4911&#45;86be&#45;0460a78760ba](../../../../../docs/framework/data/adonet/ef/media/b42a7a5c-0ac0-4911-86be-0460a78760ba.gif "b42a7a5c-0ac0-4911-86be-0460a78760ba")</span><span class="sxs-lookup"><span data-stu-id="fb05d-114">![b42a7a5c&#45;0ac0&#45;4911&#45;86be&#45;0460a78760ba](../../../../../docs/framework/data/adonet/ef/media/b42a7a5c-0ac0-4911-86be-0460a78760ba.gif "b42a7a5c-0ac0-4911-86be-0460a78760ba")</span></span>  
  
## <a name="sample"></a><span data-ttu-id="fb05d-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="fb05d-115">Sample</span></span>  
 <span data-ttu-id="fb05d-116">Vedere la [Provider di esempio Entity Framework](http://go.microsoft.com/fwlink/?LinkId=180616) per un esempio di un [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] provider che supporta un'origine dati diverso da SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fb05d-116">See the [Entity Framework Sample Provider](http://go.microsoft.com/fwlink/?LinkId=180616) for a sample of an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] provider that supports a data source other than SQL Server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fb05d-117">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="fb05d-117">In This Section</span></span>  
 [<span data-ttu-id="fb05d-118">Generazione SQL</span><span class="sxs-lookup"><span data-stu-id="fb05d-118">SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/sql-generation.md)  
  
 [<span data-ttu-id="fb05d-119">Generazione di comandi SQL di modifica</span><span class="sxs-lookup"><span data-stu-id="fb05d-119">Modification SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/modification-sql-generation.md)  
  
 [<span data-ttu-id="fb05d-120">Specifica del manifesto del provider</span><span class="sxs-lookup"><span data-stu-id="fb05d-120">Provider Manifest Specification</span></span>](../../../../../docs/framework/data/adonet/ef/provider-manifest-specification.md)  
  
## <a name="see-also"></a><span data-ttu-id="fb05d-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fb05d-121">See Also</span></span>  
 [<span data-ttu-id="fb05d-122">Uso di provider di dati</span><span class="sxs-lookup"><span data-stu-id="fb05d-122">Working with Data Providers</span></span>](../../../../../docs/framework/data/adonet/ef/working-with-data-providers.md)
