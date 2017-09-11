---
title: LINQ to ADO.NET (pagina portale)
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 6bd269b4-3509-4688-b672-836008704182
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d768d5796e5eb7ff4fed071d906c672b83b42d2b
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="linq-to-adonet-portal-page"></a><span data-ttu-id="6b6ab-102">LINQ to ADO.NET (pagina portale)</span><span class="sxs-lookup"><span data-stu-id="6b6ab-102">LINQ to ADO.NET (Portal Page)</span></span>
[!INCLUDE[linq_adonet](~/includes/linq-adonet-md.md)]<span data-ttu-id="6b6ab-103"> consente di eseguire una query in qualsiasi oggetto enumerabile in [!INCLUDE[vstecado](~/includes/vstecado-md.md)] usando il modello di programmazione [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6b6ab-103"> enables you to query over any enumerable object in [!INCLUDE[vstecado](~/includes/vstecado-md.md)] by using the [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] programming model.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6b6ab-104">La documentazione di [!INCLUDE[linq_adonet](~/includes/linq-adonet-md.md)] si trova nella sezione ADO.NET di .NET Framework SDK: [LINQ e ADO.NET](http://msdn.microsoft.com/library/bf0c8f93-3ff7-49f3-8aed-f2b7ac938dec).</span><span class="sxs-lookup"><span data-stu-id="6b6ab-104">The [!INCLUDE[linq_adonet](~/includes/linq-adonet-md.md)] documentation is located in the ADO.NET section of the .NET Framework SDK: [LINQ and ADO.NET](http://msdn.microsoft.com/library/bf0c8f93-3ff7-49f3-8aed-f2b7ac938dec).</span></span>  
  
 <span data-ttu-id="6b6ab-105">Sono disponibili tre diverse tecnologie [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] ADO.NET: [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)], [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] e [!INCLUDE[linq_entities](~/includes/linq-entities-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6b6ab-105">There are three separate ADO.NET [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] technologies: [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)], [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], and [!INCLUDE[linq_entities](~/includes/linq-entities-md.md)].</span></span> [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)]<span data-ttu-id="6b6ab-106"> offre un supporto più completo e ottimizzato per l'esecuzione di query su <xref:System.Data.DataSet>, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] consente di eseguire query direttamente sugli schemi di database di [!INCLUDE[ssNoVersion](~/includes/ssnoversion-md.md)] e [!INCLUDE[linq_entities](~/includes/linq-entities-md.md)] consente di eseguire query su [!INCLUDE[adonet_edm](~/includes/adonet-edm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6b6ab-106"> provides richer, optimized querying over the <xref:System.Data.DataSet>, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] enables you to directly query [!INCLUDE[ssNoVersion](~/includes/ssnoversion-md.md)] database schemas, and [!INCLUDE[linq_entities](~/includes/linq-entities-md.md)] allows you to query an [!INCLUDE[adonet_edm](~/includes/adonet-edm-md.md)].</span></span>  
  
## <a name="linq-to-dataset"></a><span data-ttu-id="6b6ab-107">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="6b6ab-107">LINQ to DataSet</span></span>  
 <span data-ttu-id="6b6ab-108"><xref:System.Data.DataSet> è uno dei componenti maggiormente usati in [!INCLUDE[vstecado](~/includes/vstecado-md.md)] ed è un elemento chiave del modello di programmazione disconnesso su cui è basato [!INCLUDE[vstecado](~/includes/vstecado-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6b6ab-108">The <xref:System.Data.DataSet> is one of the most widely used components in [!INCLUDE[vstecado](~/includes/vstecado-md.md)], and is a key element of the disconnected programming model that [!INCLUDE[vstecado](~/includes/vstecado-md.md)] is built on.</span></span> <span data-ttu-id="6b6ab-109">Nonostante l'importanza che lo contraddistingue, tuttavia, <xref:System.Data.DataSet> ha solo funzionalità limitate di query.</span><span class="sxs-lookup"><span data-stu-id="6b6ab-109">Despite this prominence, however, the <xref:System.Data.DataSet> has limited query capabilities.</span></span>  
  
 [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)]<span data-ttu-id="6b6ab-110"> consente di compilare funzionalità di esecuzione di query più complesse nell'oggetto <xref:System.Data.DataSet> usando la stessa funzionalità di query disponibile per molte altre origini dati.</span><span class="sxs-lookup"><span data-stu-id="6b6ab-110"> enables you to build richer query capabilities into <xref:System.Data.DataSet> by using the same query functionality that is available for many other data sources.</span></span>  
  
 <span data-ttu-id="6b6ab-111">Per altre informazioni, vedere [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="6b6ab-111">For more information, see [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md).</span></span>  
  
## <a name="linq-to-sql"></a><span data-ttu-id="6b6ab-112">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="6b6ab-112">LINQ to SQL</span></span>  
 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]<span data-ttu-id="6b6ab-113"> fornisce un'infrastruttura di runtime per la gestione di dati relazionali come oggetti.</span><span class="sxs-lookup"><span data-stu-id="6b6ab-113"> provides a run-time infrastructure for managing relational data as objects.</span></span> <span data-ttu-id="6b6ab-114">In [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] viene eseguito il mapping del modello dati di un database relazionale a un modello a oggetti espresso nel linguaggio di programmazione dello sviluppatore.</span><span class="sxs-lookup"><span data-stu-id="6b6ab-114">In [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], the data model of a relational database is mapped to an object model expressed in the programming language of the developer.</span></span> <span data-ttu-id="6b6ab-115">Quando l'applicazione viene eseguita, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] converte in SQL le query LINQ (Language Integrated Query) nel modello a oggetti e le invia al database per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="6b6ab-115">When you execute the application, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] translates language-integrated queries in the object model into SQL and sends them to the database for execution.</span></span> <span data-ttu-id="6b6ab-116">Quando il database restituisce i risultati, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] li converte di nuovo in oggetti che è possibile modificare.</span><span class="sxs-lookup"><span data-stu-id="6b6ab-116">When the database returns the results, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] translates them back into objects that you can manipulate.</span></span>  
  
 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]<span data-ttu-id="6b6ab-117"> include il supporto di stored procedure e funzioni definite dall'utente nel database e dell'ereditarietà nel modello a oggetti.</span><span class="sxs-lookup"><span data-stu-id="6b6ab-117"> includes support for stored procedures and user-defined functions in the database, and for inheritance in the object model.</span></span>  
  
 <span data-ttu-id="6b6ab-118">Per altre informazioni, vedere [LINQ to SQL](https://msdn.microsoft.com/library/bb386976).</span><span class="sxs-lookup"><span data-stu-id="6b6ab-118">For more information, see [LINQ to SQL](https://msdn.microsoft.com/library/bb386976).</span></span>  
  
## <a name="linq-to-entities"></a><span data-ttu-id="6b6ab-119">LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="6b6ab-119">LINQ to Entities</span></span>  
 <span data-ttu-id="6b6ab-120">Tramite [!INCLUDE[adonet_edm](~/includes/adonet-edm-md.md)], i dati relazionali vengono esposti come oggetti nell'ambiente .NET.</span><span class="sxs-lookup"><span data-stu-id="6b6ab-120">Through the [!INCLUDE[adonet_edm](~/includes/adonet-edm-md.md)], relational data is exposed as objects in the .NET environment.</span></span> <span data-ttu-id="6b6ab-121">Ciò rende il livello di oggetto una destinazione ideale per il supporto di [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], consentendo agli sviluppatori di formulare query sul database a partire dal linguaggio usato per compilare la logica di business.</span><span class="sxs-lookup"><span data-stu-id="6b6ab-121">This makes the object layer an ideal target for [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] support, allowing developers to formulate queries against the database from the language used to build the business logic.</span></span> <span data-ttu-id="6b6ab-122">Questa funzionalità è nota come [!INCLUDE[linq_entities](~/includes/linq-entities-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6b6ab-122">This capability is known as [!INCLUDE[linq_entities](~/includes/linq-entities-md.md)].</span></span> <span data-ttu-id="6b6ab-123">Per altre informazioni, vedere [LINQ to Entities](../../../../framework/data/adonet/ef/language-reference/linq-to-entities.md).</span><span class="sxs-lookup"><span data-stu-id="6b6ab-123">See [LINQ to Entities](../../../../framework/data/adonet/ef/language-reference/linq-to-entities.md) for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b6ab-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6b6ab-124">See Also</span></span>  
 <span data-ttu-id="6b6ab-125">[LINQ e ADO.NET](http://msdn.microsoft.com/library/bf0c8f93-3ff7-49f3-8aed-f2b7ac938dec) </span><span class="sxs-lookup"><span data-stu-id="6b6ab-125">[LINQ and ADO.NET](http://msdn.microsoft.com/library/bf0c8f93-3ff7-49f3-8aed-f2b7ac938dec) </span></span>  
 [<span data-ttu-id="6b6ab-126">Language-Integrated Query (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="6b6ab-126">Language-Integrated Query (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/index.md)

