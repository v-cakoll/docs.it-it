---
title: Guida per programmatori
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ed1012d4-3ff2-4877-af27-93125c4180ea
caps.latest.revision: 3
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 703f10466755ddea5a0117a3413374613e178346
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="programming-guide"></a><span data-ttu-id="c001c-102">Guida per programmatori</span><span class="sxs-lookup"><span data-stu-id="c001c-102">Programming Guide</span></span>
<span data-ttu-id="c001c-103">Questa sezione fornisce informazioni sulla creazione e sull'uso del modello a oggetti di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c001c-103">This section contains information about how to create and use your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span> <span data-ttu-id="c001c-104">Se si utilizza Visual Studio, è inoltre possibile utilizzare il [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] per eseguire molte di queste stesse attività.</span><span class="sxs-lookup"><span data-stu-id="c001c-104">If you are using Visual Studio, you can also use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to perform many of these same tasks.</span></span>  
  
 <span data-ttu-id="c001c-105">È inoltre possibile cercare Microsoft Docs problemi specifici e, è possibile partecipare il [forum su LINQ](http://go.microsoft.com/fwlink/?LinkId=76488), in cui è possibile discutere in dettaglio argomenti più complessi con gli esperti.</span><span class="sxs-lookup"><span data-stu-id="c001c-105">You can also search Microsoft Docs for specific issues, and you can participate in the [LINQ Forum](http://go.microsoft.com/fwlink/?LinkId=76488), where you can discuss more complex topics in detail with experts.</span></span> <span data-ttu-id="c001c-106">Infine, il [LINQ to SQL: e alle Query per i dati relazionali](http://go.microsoft.com/fwlink/?LinkId=93205) white paper relativo alle dettagli [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] la tecnologia di esempi di codice Visual Basic e c#.</span><span class="sxs-lookup"><span data-stu-id="c001c-106">Finally, the [LINQ to SQL: .NET Language-Integrated Query for Relational Data](http://go.microsoft.com/fwlink/?LinkId=93205) white paper details [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology, complete with Visual Basic and C# code examples.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c001c-107">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="c001c-107">In This Section</span></span>  
 [<span data-ttu-id="c001c-108">Creazione del modello a oggetti</span><span class="sxs-lookup"><span data-stu-id="c001c-108">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)  
 <span data-ttu-id="c001c-109">Viene descritto come generare un modello a oggetti.</span><span class="sxs-lookup"><span data-stu-id="c001c-109">Describes how to generate an object model.</span></span>  
  
 [<span data-ttu-id="c001c-110">Comunicazione con il database</span><span class="sxs-lookup"><span data-stu-id="c001c-110">Communicating with the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)  
 <span data-ttu-id="c001c-111">Viene descritto come usare un oggetto <xref:System.Data.Linq.DataContext> come canale di accesso al database.</span><span class="sxs-lookup"><span data-stu-id="c001c-111">Describes how to use a <xref:System.Data.Linq.DataContext> object as a conduit to the database.</span></span>  
  
 [<span data-ttu-id="c001c-112">Esecuzione di query sul database</span><span class="sxs-lookup"><span data-stu-id="c001c-112">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)  
 <span data-ttu-id="c001c-113">Viene descritto come eseguire query in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] e vengono forniti molti esempi.</span><span class="sxs-lookup"><span data-stu-id="c001c-113">Describes how to execute queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], and provides many examples.</span></span>  
  
 [<span data-ttu-id="c001c-114">Creazione e invio di modifiche dei dati</span><span class="sxs-lookup"><span data-stu-id="c001c-114">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)  
 <span data-ttu-id="c001c-115">Viene descritto come modificare i dati nel database.</span><span class="sxs-lookup"><span data-stu-id="c001c-115">Describes how change data in the database.</span></span>  
  
 [<span data-ttu-id="c001c-116">Supporto per il debug</span><span class="sxs-lookup"><span data-stu-id="c001c-116">Debugging Support</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md)  
 <span data-ttu-id="c001c-117">Viene descritto il supporto disponibile per il debug di progetti [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c001c-117">Describes the support available for debugging [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] projects.</span></span>  
  
 [<span data-ttu-id="c001c-118">Informazioni di base</span><span class="sxs-lookup"><span data-stu-id="c001c-118">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 <span data-ttu-id="c001c-119">Sono inclusi elementi aggiuntivi, ad esempio per la risoluzione dei conflitti di concorrenza, la creazione di nuovi database e altro, per gli utenti più avanzati.</span><span class="sxs-lookup"><span data-stu-id="c001c-119">Includes additional items, such as concurrency conflict resolution, creating new databases, and more, for more advanced users.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c001c-120">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="c001c-120">Related Sections</span></span>  
 [<span data-ttu-id="c001c-121">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="c001c-121">LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/index.md)  
 <span data-ttu-id="c001c-122">Vengono forniti collegamenti ad argomenti che illustrano la tecnologia [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] e ne vengono descritte le funzionalità.</span><span class="sxs-lookup"><span data-stu-id="c001c-122">Provides links to topics that explain the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology and demonstrate features.</span></span>  
  
 [<span data-ttu-id="c001c-123">stored procedure</span><span class="sxs-lookup"><span data-stu-id="c001c-123">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)  
 <span data-ttu-id="c001c-124">Sono inclusi collegamenti ad argomenti che illustrano come usare stored procedure.</span><span class="sxs-lookup"><span data-stu-id="c001c-124">Includes links to topics that illustrate how to use stored procedures.</span></span>  
  
 [<span data-ttu-id="c001c-125">Introduzione a LINQ</span><span class="sxs-lookup"><span data-stu-id="c001c-125">Introduction to LINQ</span></span>](http://msdn.microsoft.com/library/24dddf19-12a0-4707-a4bc-eba4fa7f219e)  
 <span data-ttu-id="c001c-126">Vengono fornite risorse che facilitano l'apprendimento di informazioni su [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c001c-126">Provides resources to help you begin to learn about [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>
