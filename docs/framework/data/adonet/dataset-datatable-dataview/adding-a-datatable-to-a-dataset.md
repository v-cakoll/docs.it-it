---
title: Aggiunta di un oggetto DataTable a un dataset
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 556d29a3-8fc9-4e38-b3ee-c188f7e7b155
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: c5846f93cfa75d7f0e760a24ee65fa838abc1eb8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="adding-a-datatable-to-a-dataset"></a><span data-ttu-id="fac90-102">Aggiunta di un oggetto DataTable a un dataset</span><span class="sxs-lookup"><span data-stu-id="fac90-102">Adding a DataTable to a DataSet</span></span>
<span data-ttu-id="fac90-103">ADO.NET consente di creare oggetti <xref:System.Data.DataTable> e di aggiungerli a un tipo <xref:System.Data.DataSet> esistente.</span><span class="sxs-lookup"><span data-stu-id="fac90-103">ADO.NET enables you to create <xref:System.Data.DataTable> objects and add them to an existing <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="fac90-104">È possibile impostare le informazioni relative ai vincoli per un tipo <xref:System.Data.DataTable> usando le proprietà <xref:System.Data.DataTable.PrimaryKey%2A> e <xref:System.Data.DataColumn.Unique%2A>.</span><span class="sxs-lookup"><span data-stu-id="fac90-104">You can set constraint information for a <xref:System.Data.DataTable> by using the <xref:System.Data.DataTable.PrimaryKey%2A> and <xref:System.Data.DataColumn.Unique%2A> properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fac90-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="fac90-105">Example</span></span>  
 <span data-ttu-id="fac90-106">L'esempio seguente consente di creare un tipo <xref:System.Data.DataSet>, aggiungere un nuovo oggetto <xref:System.Data.DataTable> al <xref:System.Data.DataSet> e aggiungere tre oggetti <xref:System.Data.DataColumn> alla tabella.</span><span class="sxs-lookup"><span data-stu-id="fac90-106">The following example constructs a <xref:System.Data.DataSet>, adds a new <xref:System.Data.DataTable> object to the <xref:System.Data.DataSet>, and then adds three <xref:System.Data.DataColumn> objects to the table.</span></span> <span data-ttu-id="fac90-107">Il codice consente infine di impostare una colonna come colonna di chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="fac90-107">Finally, the code sets one column as the primary key column.</span></span>  
  
 [!code-csharp[DataWorks Data.DataTableAdd#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableAdd/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableAdd#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableAdd/VB/source.vb#1)]  
  
## <a name="case-sensitivity"></a><span data-ttu-id="fac90-108">Distinzione fra maiuscole e minuscole</span><span class="sxs-lookup"><span data-stu-id="fac90-108">Case Sensitivity</span></span>  
 <span data-ttu-id="fac90-109">In un tipo <xref:System.Data.DataSet> sono consentite due o più tabelle o relazioni con lo stesso nome ma con diversa combinazione di maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="fac90-109">Two or more tables or relations with the same name, but different casing, can exist in a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="fac90-110">In questi casi, i riferimenti basati sui nomi a tabelle e relazioni prevedono la distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="fac90-110">In such cases, references by name to tables and relations are case sensitive.</span></span> <span data-ttu-id="fac90-111">Ad esempio, se il <xref:System.Data.DataSet> **dataSet** contiene tabelle **Table1** e **table1**, si fa riferimento a **Table1** con nome **Table1 "]**, e **table1** come **Table1"]**.</span><span class="sxs-lookup"><span data-stu-id="fac90-111">For example, if the <xref:System.Data.DataSet> **dataSet** contains tables **Table1** and **table1**, you would reference **Table1** by name as **dataSet.Tables["Table1"]**, and **table1** as **dataSet.Tables["table1"]**.</span></span> <span data-ttu-id="fac90-112">Il tentativo di fare riferimento a una delle tabelle come **Table1 "]** verrà generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="fac90-112">Attempting to reference either of the tables as **dataSet.Tables["TABLE1"]** would generate an exception.</span></span>  
  
 <span data-ttu-id="fac90-113">La distinzione tra maiuscole e minuscole non è rilevante se è presente solo una tabella o relazione con un determinato nome.</span><span class="sxs-lookup"><span data-stu-id="fac90-113">The case-sensitivity behavior does not apply if only one table or relation has a particular name.</span></span> <span data-ttu-id="fac90-114">Ad esempio, se il <xref:System.Data.DataSet> solo **Table1**, è possibile farvi riferimento tramite **Table1 "]**.</span><span class="sxs-lookup"><span data-stu-id="fac90-114">For example, if the <xref:System.Data.DataSet> has only **Table1**, you can reference it using **dataSet.Tables["TABLE1"]**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fac90-115">La proprietà <xref:System.Data.DataSet.CaseSensitive%2A> del tipo <xref:System.Data.DataSet> non influisce su tale comportamento.</span><span class="sxs-lookup"><span data-stu-id="fac90-115">The <xref:System.Data.DataSet.CaseSensitive%2A> property of the <xref:System.Data.DataSet> does not affect this behavior.</span></span> <span data-ttu-id="fac90-116">La proprietà <xref:System.Data.DataSet.CaseSensitive%2A> viene infatti applicata ai dati del tipo <xref:System.Data.DataSet> e influisce sull'ordinamento, la ricerca, l'applicazione di filtri, di vincoli e così via.</span><span class="sxs-lookup"><span data-stu-id="fac90-116">The <xref:System.Data.DataSet.CaseSensitive%2A> property applies to the data in the <xref:System.Data.DataSet> and affects sorting, searching, filtering, enforcing constraints, and so on.</span></span>  
  
## <a name="namespace-support"></a><span data-ttu-id="fac90-117">Supporto dello spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="fac90-117">Namespace Support</span></span>  
 <span data-ttu-id="fac90-118">Nelle versioni ADO.NET precedenti alla 2.0 due tabelle non potevano avere lo stesso nome, anche se si trovavano in spazi dei nomi diversi.</span><span class="sxs-lookup"><span data-stu-id="fac90-118">In versions of ADO.NET earlier than 2.0, two tables could not have the same name, even if they were in different namespaces.</span></span> <span data-ttu-id="fac90-119">In ADO.NET 2.0 questa limitazione è stata eliminata.</span><span class="sxs-lookup"><span data-stu-id="fac90-119">This limitation was removed in ADO.NET 2.0.</span></span> <span data-ttu-id="fac90-120">Un tipo <xref:System.Data.DataSet> può contenere due tabelle con lo stesso valore per la proprietà <xref:System.Data.DataTable.TableName%2A> ma con valori diversi per la proprietà <xref:System.Data.DataTable.Namespace%2A>.</span><span class="sxs-lookup"><span data-stu-id="fac90-120">A <xref:System.Data.DataSet> can contain two tables that have the same <xref:System.Data.DataTable.TableName%2A> property value but different <xref:System.Data.DataTable.Namespace%2A> property values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fac90-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fac90-121">See Also</span></span>  
 [<span data-ttu-id="fac90-122">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="fac90-122">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="fac90-123">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="fac90-123">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
