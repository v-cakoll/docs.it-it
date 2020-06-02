---
title: Creazione di un oggetto DataTable
description: Informazioni su come creare una DataTable in ADO.NET, che rappresenta una tabella di dati relazionali in memoria, da usare in modo indipendente o da altri oggetti .NET Framework.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: eecf9d78-60e3-4fdc-8de0-e56c13a89414
ms.openlocfilehash: 335137eeef02e590539c6d83e46cb39901a1e03f
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286921"
---
# <a name="creating-a-datatable"></a><span data-ttu-id="40099-103">Creazione di un oggetto DataTable</span><span class="sxs-lookup"><span data-stu-id="40099-103">Creating a DataTable</span></span>
<span data-ttu-id="40099-104">È possibile creare una <xref:System.Data.DataTable>, che rappresenta una tabella di dati relazionali in memoria, e usarla in modo indipendente oppure usarla tramite altri oggetti di .NET Framework, in genere come membro di un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="40099-104">A <xref:System.Data.DataTable>, which represents one table of in-memory relational data, can be created and used independently, or can be used by other .NET Framework objects, most commonly as a member of a <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="40099-105">È possibile creare un oggetto **DataTable** usando il costruttore **DataTable** appropriato.</span><span class="sxs-lookup"><span data-stu-id="40099-105">You can create a **DataTable** object by using the appropriate **DataTable** constructor.</span></span> <span data-ttu-id="40099-106">È possibile aggiungerlo al **set di dati** usando il metodo **Add** per aggiungerlo alla raccolta **Tables** dell'oggetto **DataTable** .</span><span class="sxs-lookup"><span data-stu-id="40099-106">You can add it to the **DataSet** by using the **Add** method to add it to the **DataTable** object's **Tables** collection.</span></span>  
  
 <span data-ttu-id="40099-107">È anche possibile creare oggetti **DataTable** all'interno di un **set di dati** usando i metodi **Fill** o **FillSchema** dell'oggetto **DataAdapter** oppure da un XML Schema predefinito o dedotto usando i metodi **ReadXml**, **ReadXmlSchema**o **InferXmlSchema** del **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="40099-107">You can also create **DataTable** objects within a **DataSet** by using the **Fill** or **FillSchema** methods of the **DataAdapter** object, or from a predefined or inferred XML schema using the **ReadXml**, **ReadXmlSchema**, or **InferXmlSchema** methods of the **DataSet**.</span></span> <span data-ttu-id="40099-108">Si noti che dopo aver aggiunto un **DataTable** come membro della raccolta **Tables** di un **set di dati**, non è possibile aggiungerlo alla raccolta di tabelle di qualsiasi altro **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="40099-108">Note that after you have added a **DataTable** as a member of the **Tables** collection of one **DataSet**, you cannot add it to the collection of tables of any other **DataSet**.</span></span>  
  
 <span data-ttu-id="40099-109">Quando si crea una **DataTable**per la prima volta, non è presente uno schema, ovvero una struttura.</span><span class="sxs-lookup"><span data-stu-id="40099-109">When you first create a **DataTable**, it does not have a schema (that is, a structure).</span></span> <span data-ttu-id="40099-110">Per definire lo schema della tabella, è necessario creare e aggiungere <xref:System.Data.DataColumn> oggetti alla raccolta **Columns** della tabella.</span><span class="sxs-lookup"><span data-stu-id="40099-110">To define the schema of the table, you must create and add <xref:System.Data.DataColumn> objects to the **Columns** collection of the table.</span></span> <span data-ttu-id="40099-111">È inoltre possibile definire una colonna chiave primaria per la tabella e creare e aggiungere oggetti **Constraint** alla raccolta **Constraints** della tabella.</span><span class="sxs-lookup"><span data-stu-id="40099-111">You can also define a primary key column for the table, and create and add **Constraint** objects to the **Constraints** collection of the table.</span></span> <span data-ttu-id="40099-112">Dopo aver definito lo schema per una **DataTable**, è possibile aggiungere righe di dati alla tabella aggiungendo oggetti **DataRow** alla raccolta **Rows** della tabella.</span><span class="sxs-lookup"><span data-stu-id="40099-112">After you have defined the schema for a **DataTable**, you can add rows of data to the table by adding **DataRow** objects to the **Rows** collection of the table.</span></span>  
  
 <span data-ttu-id="40099-113">Non è necessario fornire un valore per la <xref:System.Data.DataTable.TableName%2A> proprietà quando si crea un **oggetto DataTable**; è possibile specificare la proprietà in un altro momento oppure lasciarlo vuoto.</span><span class="sxs-lookup"><span data-stu-id="40099-113">You are not required to supply a value for the <xref:System.Data.DataTable.TableName%2A> property when you create a **DataTable**; you can specify the property at another time, or you can leave it empty.</span></span> <span data-ttu-id="40099-114">Tuttavia, quando si aggiunge una tabella senza un valore **TableName** a un **set di dati**, alla tabella verrà assegnato il nome predefinito incrementale Table*N*, che inizia con "Table" per Table0.</span><span class="sxs-lookup"><span data-stu-id="40099-114">However, when you add a table without a **TableName** value to a **DataSet**, the table will be given an incremental default name of Table*N*, starting with "Table" for Table0.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="40099-115">Si consiglia di evitare la convenzione di denominazione "Table*N*" quando si fornisce un valore **TableName** , perché il nome fornito potrebbe entrare in conflitto con un nome di tabella predefinito esistente nel **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="40099-115">We recommend that you avoid the "Table*N*" naming convention when you supply a **TableName** value, because the name you supply may conflict with an existing default table name in the **DataSet**.</span></span> <span data-ttu-id="40099-116">Se il nome fornito è già presente, viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="40099-116">If the supplied name already exists, an exception is thrown.</span></span>  
  
 <span data-ttu-id="40099-117">Nell'esempio seguente viene creata un'istanza di un oggetto **DataTable** a cui viene assegnato il nome "Customers".</span><span class="sxs-lookup"><span data-stu-id="40099-117">The following example creates an instance of a **DataTable** object and assigns it the name "Customers."</span></span>  
  
```vb  
Dim workTable as DataTable = New DataTable("Customers")  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
```  
  
 <span data-ttu-id="40099-118">Nell'esempio seguente viene creata un'istanza di un **oggetto DataTable** aggiungendola alla raccolta **Tables** di un **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="40099-118">The following example creates an instance of a **DataTable** by adding it to the **Tables** collection of a **DataSet**.</span></span>  
  
```vb  
Dim customers As DataSet = New DataSet  
Dim customersTable As DataTable = _  
   customers.Tables.Add("CustomersTable")  
```  
  
```csharp  
DataSet customers = new DataSet();  
DataTable customersTable = customers.Tables.Add("CustomersTable");  
```  
  
## <a name="see-also"></a><span data-ttu-id="40099-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="40099-119">See also</span></span>

- <xref:System.Data.DataTable>
- <xref:System.Data.DataTableCollection>
- [<span data-ttu-id="40099-120">DataTable</span><span class="sxs-lookup"><span data-stu-id="40099-120">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="40099-121">Popolamento di un set di dati da un oggetto DataAdapter</span><span class="sxs-lookup"><span data-stu-id="40099-121">Populating a DataSet from a DataAdapter</span></span>](../populating-a-dataset-from-a-dataadapter.md)
- [<span data-ttu-id="40099-122">Caricamento di un dataset da XML</span><span class="sxs-lookup"><span data-stu-id="40099-122">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="40099-123">Caricamento delle informazioni dello schema di dataset da XML</span><span class="sxs-lookup"><span data-stu-id="40099-123">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="40099-124">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="40099-124">ADO.NET Overview</span></span>](../ado-net-overview.md)
