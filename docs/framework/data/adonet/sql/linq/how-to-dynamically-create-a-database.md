---
title: 'Procedura: Creare un database in modo dinamico'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fb7f23c4-4572-4c38-9898-a287807d070c
ms.openlocfilehash: ab5e2867ce85fcc82e1114696c129aae878bbee6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61877266"
---
# <a name="how-to-dynamically-create-a-database"></a><span data-ttu-id="6a86e-102">Procedura: Creare un database in modo dinamico</span><span class="sxs-lookup"><span data-stu-id="6a86e-102">How to: Dynamically Create a Database</span></span>
<span data-ttu-id="6a86e-103">In LINQ to SQL viene eseguito il mapping di un modello a oggetti a un database relazionale.</span><span class="sxs-lookup"><span data-stu-id="6a86e-103">In LINQ to SQL, an object model is mapped to a relational database.</span></span> <span data-ttu-id="6a86e-104">Per descrivere la struttura del database relazionale è possibile eseguire il mapping basato sull'attributo o usare un file di mapping esterno.</span><span class="sxs-lookup"><span data-stu-id="6a86e-104">Mapping is enabled by using attribute-based mapping or an external mapping file to describe the structure of the relational database.</span></span> <span data-ttu-id="6a86e-105">Entrambi gli scenari dispongono di informazioni sul database relazionale sufficienti per creare una nuova istanza del database mediante il metodo <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6a86e-105">In both scenarios, there is enough information about the relational database that you can create a new instance of the database using the <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="6a86e-106">Il metodo <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> crea una replica del database includendo solo le informazioni codificate nel modello a oggetti.</span><span class="sxs-lookup"><span data-stu-id="6a86e-106">The <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> method creates a replica of the database only to the extent of the information encoded in the object model.</span></span> <span data-ttu-id="6a86e-107">I file e gli attributi di mapping del modello a oggetti potrebbero non codificare tutte le informazioni sulla struttura di un database esistente.</span><span class="sxs-lookup"><span data-stu-id="6a86e-107">Mapping files and attributes from your object model might not encode everything about the structure of an existing database.</span></span> <span data-ttu-id="6a86e-108">Le informazioni sul mapping non rappresentano il contenuto di funzioni definite dall'utente, stored procedure, trigger o vincoli CHECK.</span><span class="sxs-lookup"><span data-stu-id="6a86e-108">Mapping information does not represent the contents of user-defined functions, stored procedures, triggers, or check constraints.</span></span> <span data-ttu-id="6a86e-109">Questo comportamento è sufficiente per vari tipi di database.</span><span class="sxs-lookup"><span data-stu-id="6a86e-109">This behavior is sufficient for a variety of databases.</span></span>  
  
 <span data-ttu-id="6a86e-110">È possibile usare il metodo <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> in un numero illimitato di scenari, specialmente se è nota la disponibilità di un provider di dati come Microsoft SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="6a86e-110">You can use the <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> method in any number of scenarios, especially if a known data provider like Microsoft SQL Server 2008 is available.</span></span> <span data-ttu-id="6a86e-111">Gli scenari tipici includono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="6a86e-111">Typical scenarios include the following:</span></span>  
  
-   <span data-ttu-id="6a86e-112">Si compila un'applicazione che viene installata automaticamente in un sistema del cliente.</span><span class="sxs-lookup"><span data-stu-id="6a86e-112">You are building an application that automatically installs itself on a customer system.</span></span>  
  
-   <span data-ttu-id="6a86e-113">Si compila un'applicazione client che richiede un database locale per salvare il proprio stato offline.</span><span class="sxs-lookup"><span data-stu-id="6a86e-113">You are building a client application that needs a local database to save its offline state.</span></span>  
  
 <span data-ttu-id="6a86e-114">È inoltre possibile usare il metodo <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> con SQL Server mediante un file con estensione mdf o con un nome di catalogo, a seconda della stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="6a86e-114">You can also use the <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> method with SQL Server by using an .mdf file or a catalog name, depending on your connection string.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="6a86e-115">usa la stringa di connessione per definire il database da creare e il server su cui dovrà essere creato il database.</span><span class="sxs-lookup"><span data-stu-id="6a86e-115">uses the connection string to define the database to be created and on which server the database is to be created.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6a86e-116">Se possibile, usare la sicurezza integrata di Windows per connettersi al database in modo che non vengano richieste le password nella stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="6a86e-116">Whenever possible, use Windows Integrated Security to connect to the database so that passwords are not required in the connection string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6a86e-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="6a86e-117">Example</span></span>  
 <span data-ttu-id="6a86e-118">Nel codice seguente viene fornito un esempio della creazione di un nuovo database denominato MyDVDs.mdf.</span><span class="sxs-lookup"><span data-stu-id="6a86e-118">The following code provides an example of how to create a new database named MyDVDs.mdf.</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#5)]
 [!code-vb[DLinqSubmittingChanges#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="6a86e-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="6a86e-119">Example</span></span>  
 <span data-ttu-id="6a86e-120">È possibile usare il modello a oggetti per creare un database eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6a86e-120">You can use the object model to create a database by doing the following:</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#6)]
 [!code-vb[DLinqSubmittingChanges#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="6a86e-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="6a86e-121">Example</span></span>  
 <span data-ttu-id="6a86e-122">Quando si compila un'applicazione che viene installata automaticamente in un sistema del cliente, verificare se il database già esiste e rilasciarlo prima di crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="6a86e-122">When building an application that automatically installs itself on a  customer system, see if the database already exists and drop it before creating a new one.</span></span> <span data-ttu-id="6a86e-123">La classe <xref:System.Data.Linq.DataContext> fornisce i metodi <xref:System.Data.Linq.DataContext.DatabaseExists%2A> e <xref:System.Data.Linq.DataContext.DeleteDatabase%2A> per semplificare tale processo.</span><span class="sxs-lookup"><span data-stu-id="6a86e-123">The <xref:System.Data.Linq.DataContext> class provides the <xref:System.Data.Linq.DataContext.DatabaseExists%2A> and <xref:System.Data.Linq.DataContext.DeleteDatabase%2A> methods to help you with this process.</span></span>  
  
 <span data-ttu-id="6a86e-124">Nell'esempio seguente viene illustrato un modo in cui è possibile usare questi metodi per implementare tale approccio:</span><span class="sxs-lookup"><span data-stu-id="6a86e-124">The following example shows one way these methods can be used to implement this approach:</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#7)]
 [!code-vb[DLinqSubmittingChanges#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="6a86e-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a86e-125">See also</span></span>

- [<span data-ttu-id="6a86e-126">Mapping basato su attributi</span><span class="sxs-lookup"><span data-stu-id="6a86e-126">Attribute-Based Mapping</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)
- <span data-ttu-id="6a86e-127">[External Mapping](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md) (Mapping esterno)</span><span class="sxs-lookup"><span data-stu-id="6a86e-127">[External Mapping](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md)</span></span>
- [<span data-ttu-id="6a86e-128">Mapping del tipo SQL-CLR</span><span class="sxs-lookup"><span data-stu-id="6a86e-128">SQL-CLR Type Mapping</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)
- [<span data-ttu-id="6a86e-129">Informazioni di base</span><span class="sxs-lookup"><span data-stu-id="6a86e-129">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
- [<span data-ttu-id="6a86e-130">Creazione e invio di modifiche dei dati</span><span class="sxs-lookup"><span data-stu-id="6a86e-130">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
