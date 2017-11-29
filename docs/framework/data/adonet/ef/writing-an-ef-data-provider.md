---
title: Scrittura di un provider di dati Entity Framework
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 092e88c4-a301-453a-b5c3-5740c6575a9f
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 6cbb6d4c11c06c1771cb32021c6c148564a6034a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="writing-an-entity-framework-data-provider"></a><span data-ttu-id="2a05f-102">Scrittura di un provider di dati Entity Framework</span><span class="sxs-lookup"><span data-stu-id="2a05f-102">Writing an Entity Framework Data Provider</span></span>
<span data-ttu-id="2a05f-103">In questa sezione viene descritto come scrivere un provider [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] per supportare un'origine dati diversa da [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2a05f-103">This section discusses how to write an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] provider to support a data source other than [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="2a05f-104">In [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] è incluso un provider che supporta [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2a05f-104">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] includes a provider that supports [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="introducing-the-entity-framework-provider-model"></a><span data-ttu-id="2a05f-105">Introduzione al modello di provider Entity Framework</span><span class="sxs-lookup"><span data-stu-id="2a05f-105">Introducing the Entity Framework Provider Model</span></span>  
 <span data-ttu-id="2a05f-106">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] è indipendente dal database ed è possibile scrivere un provider usando il modello di provider ADO.NET per connettersi a un set di origini dati differente.</span><span class="sxs-lookup"><span data-stu-id="2a05f-106">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] is database independent, and you can write a provider by using the ADO.NET Provider Model to connect to a diverse set of data sources.</span></span>  
  
 <span data-ttu-id="2a05f-107">Il provider di dati Entity Framework, compilato usando il modello di provider di dati ADO.NET, consente di eseguire le funzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a05f-107">The Entity Framework data provider (built using the ADO.NET Data Provider model) performs the following functions:</span></span>  
  
-   <span data-ttu-id="2a05f-108">Mapping dei tipi primitivi EDM (Entity Data Model) ai tipi di provider.</span><span class="sxs-lookup"><span data-stu-id="2a05f-108">Maps Entity Data Model (EDM) primitive types to provider types.</span></span>  
  
-   <span data-ttu-id="2a05f-109">Esposizione delle funzioni specifiche del provider.</span><span class="sxs-lookup"><span data-stu-id="2a05f-109">Exposes provider-specific functions.</span></span>  
  
-   <span data-ttu-id="2a05f-110">Generazione di comandi specifici del provider per un determinato DbQueryCommandTree per supportare le query [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2a05f-110">Generates provider-specific commands for a given DbQueryCommandTree to support [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] queries.</span></span>  
  
-   <span data-ttu-id="2a05f-111">Generazione di comandi di aggiornamento specifici del provider per un determinato DbModificationCommandTree per supportare gli aggiornamenti mediante [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2a05f-111">Generates provider-specific update commands for a given DbModificationCommandTree to support updates through the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span>  
  
-   <span data-ttu-id="2a05f-112">Esposizione di file di mapping per la definizione dello schema di archiviazione per supportare la generazione di un modello basato su un database.</span><span class="sxs-lookup"><span data-stu-id="2a05f-112">Exposes mapping files for the store schema definition, to support generation of a model based on a database.</span></span>  
  
-   <span data-ttu-id="2a05f-113">Esposizione di metadati, ad esempio tabelle e visualizzazioni, mediante un modello concettuale.</span><span class="sxs-lookup"><span data-stu-id="2a05f-113">Exposes metadata (tables and views, for example) via a conceptual model.</span></span>  
  
 <span data-ttu-id="2a05f-114">![b42a7a5c &#45;0ac0 &#45;4911; &#45; 86be &#45; 0460a78760ba](../../../../../docs/framework/data/adonet/ef/media/b42a7a5c-0ac0-4911-86be-0460a78760ba.gif "b42a7a5c-0ac0-4911-86be-0460a78760ba")</span><span class="sxs-lookup"><span data-stu-id="2a05f-114">![b42a7a5c&#45;0ac0&#45;4911&#45;86be&#45;0460a78760ba](../../../../../docs/framework/data/adonet/ef/media/b42a7a5c-0ac0-4911-86be-0460a78760ba.gif "b42a7a5c-0ac0-4911-86be-0460a78760ba")</span></span>  
  
## <a name="sample"></a><span data-ttu-id="2a05f-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="2a05f-115">Sample</span></span>  
 <span data-ttu-id="2a05f-116">Vedere il [Provider di esempio Entity Framework](http://go.microsoft.com/fwlink/?LinkId=180616) per un esempio di un [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] provider che supporta un'origine dati diversa da [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2a05f-116">See the [Entity Framework Sample Provider](http://go.microsoft.com/fwlink/?LinkId=180616) for a sample of an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] provider that supports a data source other than [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2a05f-117">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="2a05f-117">In This Section</span></span>  
 [<span data-ttu-id="2a05f-118">Generazione SQL</span><span class="sxs-lookup"><span data-stu-id="2a05f-118">SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/sql-generation.md)  
  
 [<span data-ttu-id="2a05f-119">Generazione SQL di modifica</span><span class="sxs-lookup"><span data-stu-id="2a05f-119">Modification SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/modification-sql-generation.md)  
  
 [<span data-ttu-id="2a05f-120">Specifica del manifesto del provider</span><span class="sxs-lookup"><span data-stu-id="2a05f-120">Provider Manifest Specification</span></span>](../../../../../docs/framework/data/adonet/ef/provider-manifest-specification.md)  
  
## <a name="see-also"></a><span data-ttu-id="2a05f-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a05f-121">See Also</span></span>  
 [<span data-ttu-id="2a05f-122">Utilizzo di provider di dati</span><span class="sxs-lookup"><span data-stu-id="2a05f-122">Working with Data Providers</span></span>](../../../../../docs/framework/data/adonet/ef/working-with-data-providers.md)
