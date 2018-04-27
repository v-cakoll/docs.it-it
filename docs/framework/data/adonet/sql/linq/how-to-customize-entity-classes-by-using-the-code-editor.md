---
title: "Procedura: personalizzare classi di entità mediante l'Editor del codice"
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec28332f-9f3c-4e0a-baca-60f9141a68c0
caps.latest.revision: 3
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 3e518a18787a7faa1d3e501d5941fae70daf8b9d
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-customize-entity-classes-by-using-the-code-editor"></a><span data-ttu-id="c8db5-102">Procedura: personalizzare classi di entità mediante l'Editor del codice</span><span class="sxs-lookup"><span data-stu-id="c8db5-102">How to: Customize Entity Classes by Using the Code Editor</span></span>
<span data-ttu-id="c8db5-103">Gli sviluppatori che usano Visual Studio è possono utilizzare il [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] per creare o personalizzare le classi di entità.</span><span class="sxs-lookup"><span data-stu-id="c8db5-103">Developers using Visual Studio can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to create or customize their entity classes.</span></span>  
  
 <span data-ttu-id="c8db5-104">È anche possibile usare l'editor di codice [!INCLUDE[vsprvs](../../../../../../includes/vsprvs-md.md)]per scrivere codice di mapping o per personalizzare codice già generato.</span><span class="sxs-lookup"><span data-stu-id="c8db5-104">You can also use the [!INCLUDE[vsprvs](../../../../../../includes/vsprvs-md.md)] code editor to write your own mapping code or to customize code that has already been generated.</span></span> <span data-ttu-id="c8db5-105">Per ulteriori informazioni, vedere [Mapping basato sugli attributi](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="c8db5-105">For more information, see [Attribute-Based Mapping](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).</span></span>  
  
 <span data-ttu-id="c8db5-106">Negli argomenti di questa sezione viene descritto come personalizzare il modello a oggetti.</span><span class="sxs-lookup"><span data-stu-id="c8db5-106">The topics in this section describe how to customize your object model.</span></span>  
  
 [<span data-ttu-id="c8db5-107">Procedura: specificare nomi di database</span><span class="sxs-lookup"><span data-stu-id="c8db5-107">How to: Specify Database Names</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-database-names.md)  
 <span data-ttu-id="c8db5-108">Viene descritto come usare <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.</span><span class="sxs-lookup"><span data-stu-id="c8db5-108">Describes how to use <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.</span></span>  
  
 [<span data-ttu-id="c8db5-109">Procedura: rappresentare tabelle come classi</span><span class="sxs-lookup"><span data-stu-id="c8db5-109">How to: Represent Tables as Classes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-tables-as-classes.md)  
 <span data-ttu-id="c8db5-110">Viene descritto come usare <xref:System.Data.Linq.Mapping.TableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="c8db5-110">Describes how to use <xref:System.Data.Linq.Mapping.TableAttribute>.</span></span>  
  
 [<span data-ttu-id="c8db5-111">Procedura: rappresentare colonne come membri di classi</span><span class="sxs-lookup"><span data-stu-id="c8db5-111">How to: Represent Columns as Class Members</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-columns-as-class-members.md)  
 <span data-ttu-id="c8db5-112">Viene descritto come usare <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="c8db5-112">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span></span>  
  
 [<span data-ttu-id="c8db5-113">Procedura: rappresentare le chiavi primarie</span><span class="sxs-lookup"><span data-stu-id="c8db5-113">How to: Represent Primary Keys</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-primary-keys.md)  
 <span data-ttu-id="c8db5-114">Viene descritto come usare <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="c8db5-114">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span></span>  
  
 [<span data-ttu-id="c8db5-115">Procedura: eseguire il mapping di relazioni tra database</span><span class="sxs-lookup"><span data-stu-id="c8db5-115">How to: Map Database Relationships</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-database-relationships.md)  
 <span data-ttu-id="c8db5-116">Vengono forniti esempi relativi all'utilizzo dell'attributo <xref:System.Data.Linq.Mapping.AssociationAttribute>.</span><span class="sxs-lookup"><span data-stu-id="c8db5-116">Provides examples of using the <xref:System.Data.Linq.Mapping.AssociationAttribute> attribute.</span></span>  
  
 [<span data-ttu-id="c8db5-117">Procedura: rappresentare colonne come generate dal database</span><span class="sxs-lookup"><span data-stu-id="c8db5-117">How to: Represent Columns as Database-Generated</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-columns-as-database-generated.md)  
 <span data-ttu-id="c8db5-118">Viene descritto come usare <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span><span class="sxs-lookup"><span data-stu-id="c8db5-118">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span></span>  
  
 [<span data-ttu-id="c8db5-119">Procedura: rappresentare colonne come timestamp o versioni</span><span class="sxs-lookup"><span data-stu-id="c8db5-119">How to: Represent Columns as Timestamp or Version Columns</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-columns-as-timestamp-or-version-columns.md)  
 <span data-ttu-id="c8db5-120">Viene descritto come usare <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span><span class="sxs-lookup"><span data-stu-id="c8db5-120">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span></span>  
  
 [<span data-ttu-id="c8db5-121">Procedura: specificare i tipi di dati del database</span><span class="sxs-lookup"><span data-stu-id="c8db5-121">How to: Specify Database Data Types</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-database-data-types.md)  
 <span data-ttu-id="c8db5-122">Viene descritto come usare <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.</span><span class="sxs-lookup"><span data-stu-id="c8db5-122">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.</span></span>  
  
 [<span data-ttu-id="c8db5-123">Procedura: rappresentare colonne calcolate</span><span class="sxs-lookup"><span data-stu-id="c8db5-123">How to: Represent Computed Columns</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-computed-columns.md)  
 <span data-ttu-id="c8db5-124">Viene descritto come usare <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span><span class="sxs-lookup"><span data-stu-id="c8db5-124">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span></span>  
  
 [<span data-ttu-id="c8db5-125">Procedura: specificare campi di archiviazione privati</span><span class="sxs-lookup"><span data-stu-id="c8db5-125">How to: Specify Private Storage Fields</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-private-storage-fields.md)  
 <span data-ttu-id="c8db5-126">Viene descritto come usare <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span><span class="sxs-lookup"><span data-stu-id="c8db5-126">Describes how to use <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span></span>  
  
 [<span data-ttu-id="c8db5-127">Procedura: rappresentare colonne per l'accettazione di valori Null</span><span class="sxs-lookup"><span data-stu-id="c8db5-127">How to: Represent Columns as Allowing Null Values</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-columns-as-allowing-null-values.md)  
 <span data-ttu-id="c8db5-128">Viene descritto come usare <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span><span class="sxs-lookup"><span data-stu-id="c8db5-128">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span></span>  
  
 [<span data-ttu-id="c8db5-129">Procedura: eseguire il mapping di gerarchie di ereditarietà</span><span class="sxs-lookup"><span data-stu-id="c8db5-129">How to: Map Inheritance Hierarchies</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-inheritance-hierarchies.md)  
 <span data-ttu-id="c8db5-130">Vengono descritti i mapping necessari per specificare una gerarchia di ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="c8db5-130">Describes the mappings required to specify an inheritance hierarchy.</span></span>  
  
 [<span data-ttu-id="c8db5-131">Procedura: specificare il controllo di conflitti di concorrenza</span><span class="sxs-lookup"><span data-stu-id="c8db5-131">How to: Specify Concurrency-Conflict Checking</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-concurrency-conflict-checking.md)  
 <span data-ttu-id="c8db5-132">Viene descritto come usare <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span><span class="sxs-lookup"><span data-stu-id="c8db5-132">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8db5-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8db5-133">See Also</span></span>  
 [<span data-ttu-id="c8db5-134">SqlMetal.exe (strumento per la generazione del codice)</span><span class="sxs-lookup"><span data-stu-id="c8db5-134">SqlMetal.exe (Code Generation Tool)</span></span>](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)
