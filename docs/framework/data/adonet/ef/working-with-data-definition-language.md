---
title: Utilizzo di Data Definition Language
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ec50083d-44f4-4093-9b23-5eacd601f96e
ms.openlocfilehash: c6b3151a95f949100e10e630da848e34ebbf1187
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="working-with-data-definition-language"></a><span data-ttu-id="bded2-102">Utilizzo di Data Definition Language</span><span class="sxs-lookup"><span data-stu-id="bded2-102">Working with Data Definition Language</span></span>
<span data-ttu-id="bded2-103">A partire dal [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] versione 4, il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] supporta il linguaggio di definizione dei dati (DDL).</span><span class="sxs-lookup"><span data-stu-id="bded2-103">Starting with the [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] version 4, the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] supports data definition language (DDL).</span></span> <span data-ttu-id="bded2-104">Ciò consente di creare o eliminare un'istanza di database in base alla stringa di connessione e ai metadati del modello di archiviazione (SSDL).</span><span class="sxs-lookup"><span data-stu-id="bded2-104">This allows you to create or delete a database instance based on the connection string and the metadata of the storage (SSDL) model.</span></span>  
  
 <span data-ttu-id="bded2-105">Di seguito sono indicati i metodi di <xref:System.Data.Objects.ObjectContext> che usano la stringa di connessione e il contenuto SSDL per portare a termine le operazioni seguenti: creare o eliminare il database, verificare l'esistenza del database e visualizzare lo script DDL generato.</span><span class="sxs-lookup"><span data-stu-id="bded2-105">The following methods on the <xref:System.Data.Objects.ObjectContext> use the connection string and the SSDL content to accomplish the following: create or delete the database, check whether the database exists, and view the generated DDL script:</span></span>  
  
-   <xref:System.Data.Objects.ObjectContext.CreateDatabase%2A>  
  
-   <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A>  
  
-   <xref:System.Data.Objects.ObjectContext.DatabaseExists%2A>  
  
-   <xref:System.Data.Objects.ObjectContext.CreateDatabaseScript%2A>  
  
> [!NOTE]
>  <span data-ttu-id="bded2-106">Per l'esecuzione dei comandi DDL si presuppone che si disponga di autorizzazioni sufficienti.</span><span class="sxs-lookup"><span data-stu-id="bded2-106">Executing the DDL commands assumes sufficient permissions.</span></span>  
  
 <span data-ttu-id="bded2-107">I metodi elencati precedentemente delegano la maggior parte del lavoro al provider di dati ADO.NET sottostante.</span><span class="sxs-lookup"><span data-stu-id="bded2-107">The methods previously listed delegate most of the work to the underlying ADO.NET data provider.</span></span> <span data-ttu-id="bded2-108">È responsabilità del provider assicurarsi che la convenzione di denominazione usata per generare oggetti di database sia coerente con le convenzioni usate per l'esecuzione di query e aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="bded2-108">It is the provider’s responsibility to ensure that the naming convention used to generate database objects is consistent with conventions used for querying and updates.</span></span>  
  
 <span data-ttu-id="bded2-109">Nell'esempio seguente viene mostrato come generare il database in base al modello esistente.</span><span class="sxs-lookup"><span data-stu-id="bded2-109">The following example shows you how to generate the database based on the existing model.</span></span> <span data-ttu-id="bded2-110">Viene inoltre aggiunto un nuovo oggetto entità al contesto dell'oggetto che viene quindi salvato nel database.</span><span class="sxs-lookup"><span data-stu-id="bded2-110">It also adds a new entity object to the object context and then saves it to the database.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="bded2-111">Procedure</span><span class="sxs-lookup"><span data-stu-id="bded2-111">Procedures</span></span>  
  
#### <a name="to-define-a-database-based-on-the-existing-model"></a><span data-ttu-id="bded2-112">Per definire un database in base al modello esistente</span><span class="sxs-lookup"><span data-stu-id="bded2-112">To define a database based on the existing model</span></span>  
  
1.  <span data-ttu-id="bded2-113">Creare un'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="bded2-113">Create a console application.</span></span>  
  
2.  <span data-ttu-id="bded2-114">Aggiungere un modello esistente all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bded2-114">Add an existing model to your application.</span></span>  
  
    1.  <span data-ttu-id="bded2-115">Aggiungere un modello vuoto denominato `SchoolModel`.</span><span class="sxs-lookup"><span data-stu-id="bded2-115">Add an empty model named `SchoolModel`.</span></span> <span data-ttu-id="bded2-116">Per creare un modello vuoto, vedere il [procedura: creare un nuovo File di edmx](http://msdn.microsoft.com/library/beb8189e-e51c-4051-839c-9902c224abf2) argomento.</span><span class="sxs-lookup"><span data-stu-id="bded2-116">To create an empty model, see the [How to: Create a New .edmx File](http://msdn.microsoft.com/library/beb8189e-e51c-4051-839c-9902c224abf2) topic.</span></span>  
  
     <span data-ttu-id="bded2-117">Il file SchoolModel.edmx verrà aggiunto al progetto.</span><span class="sxs-lookup"><span data-stu-id="bded2-117">The SchoolModel.edmx file is added to your project.</span></span>  
  
    1.  <span data-ttu-id="bded2-118">Copiare lo spazio di archiviazione, concettuale e il contenuto per il modello School dal mapping di [modello School](http://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac) argomento.</span><span class="sxs-lookup"><span data-stu-id="bded2-118">Copy the conceptual, storage, and mapping content for the School model from the [School Model](http://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac) topic.</span></span>  
  
    2.  <span data-ttu-id="bded2-119">Aprire il file SchoolModel.edmx e incollare il contenuto all'interno dei tag `edmx:Runtime`.</span><span class="sxs-lookup"><span data-stu-id="bded2-119">Open the SchoolModel.edmx file and paste the content within the `edmx:Runtime` tags.</span></span>  
  
3.  <span data-ttu-id="bded2-120">Aggiungere il codice seguente alla funzione principale.</span><span class="sxs-lookup"><span data-stu-id="bded2-120">Add the following code to your main function.</span></span> <span data-ttu-id="bded2-121">Il codice inizializza la stringa di connessione nel server database, visualizza lo script DDL, crea il database, aggiunge una nuova entità al contesto e salva le modifiche nel database.</span><span class="sxs-lookup"><span data-stu-id="bded2-121">The code initializes the connection string to your database server, views the DDL script, creates the database, adds a new entity to the context, and saves the changes to the database.</span></span>  
  
     [!code-csharp[DP ObjectServices Concepts#DDL](../../../../../samples/snippets/csharp/VS_Snippets_Data/DP ObjectServices Concepts/CS/Source.cs#ddl)]
     [!code-vb[DP ObjectServices Concepts#DDL](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP ObjectServices Concepts/VB/Source.vb#ddl)]
