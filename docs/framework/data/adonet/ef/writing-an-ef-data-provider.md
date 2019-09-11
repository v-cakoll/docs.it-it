---
title: Scrittura di un provider di dati Entity Framework
ms.date: 03/30/2017
ms.assetid: 092e88c4-a301-453a-b5c3-5740c6575a9f
ms.openlocfilehash: 29aa8cb1c6b31d9ada6b01860d76bcf03d37416c
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854156"
---
# <a name="writing-an-entity-framework-data-provider"></a><span data-ttu-id="c4489-102">Scrittura di un provider di dati Entity Framework</span><span class="sxs-lookup"><span data-stu-id="c4489-102">Writing an Entity Framework Data Provider</span></span>
<span data-ttu-id="c4489-103">In questa sezione viene illustrato come scrivere un provider Entity Framework per supportare un'origine dati diversa da SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c4489-103">This section discusses how to write an Entity Framework provider to support a data source other than SQL Server.</span></span> <span data-ttu-id="c4489-104">Il Entity Framework include un provider che supporta SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c4489-104">The Entity Framework includes a provider that supports SQL Server.</span></span>  
  
## <a name="introducing-the-entity-framework-provider-model"></a><span data-ttu-id="c4489-105">Introduzione al modello di provider Entity Framework</span><span class="sxs-lookup"><span data-stu-id="c4489-105">Introducing the Entity Framework Provider Model</span></span>  
 <span data-ttu-id="c4489-106">Il Entity Framework è indipendente dal database ed è possibile scrivere un provider utilizzando il modello di provider ADO.NET per connettersi a un set diversificato di origini dati.</span><span class="sxs-lookup"><span data-stu-id="c4489-106">The Entity Framework is database independent, and you can write a provider by using the ADO.NET Provider Model to connect to a diverse set of data sources.</span></span>  
  
 <span data-ttu-id="c4489-107">Il provider di dati Entity Framework, compilato usando il modello di provider di dati ADO.NET, consente di eseguire le funzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c4489-107">The Entity Framework data provider (built using the ADO.NET Data Provider model) performs the following functions:</span></span>  
  
- <span data-ttu-id="c4489-108">Mapping dei tipi primitivi EDM (Entity Data Model) ai tipi di provider.</span><span class="sxs-lookup"><span data-stu-id="c4489-108">Maps Entity Data Model (EDM) primitive types to provider types.</span></span>  
  
- <span data-ttu-id="c4489-109">Esposizione delle funzioni specifiche del provider.</span><span class="sxs-lookup"><span data-stu-id="c4489-109">Exposes provider-specific functions.</span></span>  
  
- <span data-ttu-id="c4489-110">Genera comandi specifici del provider per un determinato DbQueryCommandTree per supportare le query Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="c4489-110">Generates provider-specific commands for a given DbQueryCommandTree to support Entity Framework queries.</span></span>  
  
- <span data-ttu-id="c4489-111">Genera comandi di aggiornamento specifici del provider per un determinato DbModificationCommandTree per supportare gli aggiornamenti tramite il Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="c4489-111">Generates provider-specific update commands for a given DbModificationCommandTree to support updates through the Entity Framework.</span></span>  
  
- <span data-ttu-id="c4489-112">Esposizione di file di mapping per la definizione dello schema di archiviazione per supportare la generazione di un modello basato su un database.</span><span class="sxs-lookup"><span data-stu-id="c4489-112">Exposes mapping files for the store schema definition, to support generation of a model based on a database.</span></span>  
  
- <span data-ttu-id="c4489-113">Esposizione di metadati, ad esempio tabelle e visualizzazioni, mediante un modello concettuale.</span><span class="sxs-lookup"><span data-stu-id="c4489-113">Exposes metadata (tables and views, for example) via a conceptual model.</span></span>  
  
 <span data-ttu-id="c4489-114">![b42a7a5c&#45;0ac0&#45;4911&#45;86be&#45;0460a78760ba](./media/b42a7a5c-0ac0-4911-86be-0460a78760ba.gif "b42a7a5c-0ac0-4911-86be-0460a78760ba")</span><span class="sxs-lookup"><span data-stu-id="c4489-114">![b42a7a5c&#45;0ac0&#45;4911&#45;86be&#45;0460a78760ba](./media/b42a7a5c-0ac0-4911-86be-0460a78760ba.gif "b42a7a5c-0ac0-4911-86be-0460a78760ba")</span></span>  
  
## <a name="sample"></a><span data-ttu-id="c4489-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="c4489-115">Sample</span></span>  
 <span data-ttu-id="c4489-116">Vedere il [provider di esempio Entity Framework](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) per un esempio di un provider Entity Framework che supporta un'origine dati diversa da SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c4489-116">See the [Entity Framework Sample Provider](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) for a sample of an Entity Framework provider that supports a data source other than SQL Server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c4489-117">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="c4489-117">In This Section</span></span>  
 [<span data-ttu-id="c4489-118">Generazione SQL</span><span class="sxs-lookup"><span data-stu-id="c4489-118">SQL Generation</span></span>](sql-generation.md)  
  
 [<span data-ttu-id="c4489-119">Generazione di comandi SQL di modifica</span><span class="sxs-lookup"><span data-stu-id="c4489-119">Modification SQL Generation</span></span>](modification-sql-generation.md)  
  
 [<span data-ttu-id="c4489-120">Specifica del manifesto del provider</span><span class="sxs-lookup"><span data-stu-id="c4489-120">Provider Manifest Specification</span></span>](provider-manifest-specification.md)  
  
## <a name="see-also"></a><span data-ttu-id="c4489-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c4489-121">See also</span></span>

- [<span data-ttu-id="c4489-122">Uso di provider di dati</span><span class="sxs-lookup"><span data-stu-id="c4489-122">Working with Data Providers</span></span>](working-with-data-providers.md)
