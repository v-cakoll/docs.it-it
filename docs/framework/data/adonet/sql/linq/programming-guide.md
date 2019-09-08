---
title: Guida per programmatori
ms.date: 03/30/2017
ms.assetid: ed1012d4-3ff2-4877-af27-93125c4180ea
ms.openlocfilehash: c33c7749599de0450a9f969e5802485d154a61e1
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781249"
---
# <a name="programming-guide"></a><span data-ttu-id="5cdaf-102">Guida per programmatori</span><span class="sxs-lookup"><span data-stu-id="5cdaf-102">Programming Guide</span></span>
<span data-ttu-id="5cdaf-103">Questa sezione fornisce informazioni sulla creazione e sull'uso del modello a oggetti di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5cdaf-103">This section contains information about how to create and use your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span> <span data-ttu-id="5cdaf-104">Se si usa Visual Studio, è anche possibile usare la Object Relational Designer per eseguire molte di queste stesse attività.</span><span class="sxs-lookup"><span data-stu-id="5cdaf-104">If you are using Visual Studio, you can also use the Object Relational Designer to perform many of these same tasks.</span></span>  
  
 <span data-ttu-id="5cdaf-105">È anche possibile cercare Microsoft Docs per problemi specifici ed è possibile partecipare al forum su [LINQ](https://go.microsoft.com/fwlink/?LinkId=76488), in cui è possibile discutere in dettaglio argomenti più complessi con gli esperti.</span><span class="sxs-lookup"><span data-stu-id="5cdaf-105">You can also search Microsoft Docs for specific issues, and you can participate in the [LINQ Forum](https://go.microsoft.com/fwlink/?LinkId=76488), where you can discuss more complex topics in detail with experts.</span></span> <span data-ttu-id="5cdaf-106">Infine, la [LINQ to SQL: query integrata nel linguaggio .NET per i dati relazionali](https://go.microsoft.com/fwlink/?LinkId=93205) white paper [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] la tecnologia di dettagli, complete C# di Visual Basic ed esempi di codice.</span><span class="sxs-lookup"><span data-stu-id="5cdaf-106">Finally, the [LINQ to SQL: .NET Language-Integrated Query for Relational Data](https://go.microsoft.com/fwlink/?LinkId=93205) white paper details [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology, complete with Visual Basic and C# code examples.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5cdaf-107">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="5cdaf-107">In This Section</span></span>  
 [<span data-ttu-id="5cdaf-108">Creazione del modello a oggetti</span><span class="sxs-lookup"><span data-stu-id="5cdaf-108">Creating the Object Model</span></span>](creating-the-object-model.md)  
 <span data-ttu-id="5cdaf-109">Viene descritto come generare un modello a oggetti.</span><span class="sxs-lookup"><span data-stu-id="5cdaf-109">Describes how to generate an object model.</span></span>  
  
 [<span data-ttu-id="5cdaf-110">Comunicazione con il database</span><span class="sxs-lookup"><span data-stu-id="5cdaf-110">Communicating with the Database</span></span>](communicating-with-the-database.md)  
 <span data-ttu-id="5cdaf-111">Viene descritto come usare un oggetto <xref:System.Data.Linq.DataContext> come canale di accesso al database.</span><span class="sxs-lookup"><span data-stu-id="5cdaf-111">Describes how to use a <xref:System.Data.Linq.DataContext> object as a conduit to the database.</span></span>  
  
 [<span data-ttu-id="5cdaf-112">Esecuzione di query sul database</span><span class="sxs-lookup"><span data-stu-id="5cdaf-112">Querying the Database</span></span>](querying-the-database.md)  
 <span data-ttu-id="5cdaf-113">Viene descritto come eseguire query in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] e vengono forniti molti esempi.</span><span class="sxs-lookup"><span data-stu-id="5cdaf-113">Describes how to execute queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], and provides many examples.</span></span>  
  
 [<span data-ttu-id="5cdaf-114">Creazione e invio di modifiche dei dati</span><span class="sxs-lookup"><span data-stu-id="5cdaf-114">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)  
 <span data-ttu-id="5cdaf-115">Viene descritto come modificare i dati nel database.</span><span class="sxs-lookup"><span data-stu-id="5cdaf-115">Describes how change data in the database.</span></span>  
  
 [<span data-ttu-id="5cdaf-116">Supporto per il debug</span><span class="sxs-lookup"><span data-stu-id="5cdaf-116">Debugging Support</span></span>](debugging-support.md)  
 <span data-ttu-id="5cdaf-117">Viene descritto il supporto disponibile per il debug di progetti [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5cdaf-117">Describes the support available for debugging [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] projects.</span></span>  
  
 [<span data-ttu-id="5cdaf-118">Informazioni di base</span><span class="sxs-lookup"><span data-stu-id="5cdaf-118">Background Information</span></span>](background-information.md)  
 <span data-ttu-id="5cdaf-119">Sono inclusi elementi aggiuntivi, ad esempio per la risoluzione dei conflitti di concorrenza, la creazione di nuovi database e altro, per gli utenti più avanzati.</span><span class="sxs-lookup"><span data-stu-id="5cdaf-119">Includes additional items, such as concurrency conflict resolution, creating new databases, and more, for more advanced users.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5cdaf-120">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="5cdaf-120">Related Sections</span></span>  
 [<span data-ttu-id="5cdaf-121">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="5cdaf-121">LINQ to SQL</span></span>](index.md)  
 <span data-ttu-id="5cdaf-122">Vengono forniti collegamenti ad argomenti che illustrano la tecnologia [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] e ne vengono descritte le funzionalità.</span><span class="sxs-lookup"><span data-stu-id="5cdaf-122">Provides links to topics that explain the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology and demonstrate features.</span></span>  
  
 [<span data-ttu-id="5cdaf-123">stored procedure</span><span class="sxs-lookup"><span data-stu-id="5cdaf-123">Stored Procedures</span></span>](stored-procedures.md)  
 <span data-ttu-id="5cdaf-124">Sono inclusi collegamenti ad argomenti che illustrano come usare stored procedure.</span><span class="sxs-lookup"><span data-stu-id="5cdaf-124">Includes links to topics that illustrate how to use stored procedures.</span></span>  
  
 [<span data-ttu-id="5cdaf-125">Introduzione a LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="5cdaf-125">Introduction to LINQ (C#)</span></span>](../../../../../csharp/programming-guide/concepts/linq/index.md)  
 <span data-ttu-id="5cdaf-126">Fornisce risorse che consentono di iniziare a conoscere LINQ to SQL usando C#.</span><span class="sxs-lookup"><span data-stu-id="5cdaf-126">Provides resources to help you begin to learn about LINQ to SQL using C#.</span></span>

 [<span data-ttu-id="5cdaf-127">Introduzione a LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5cdaf-127">Introduction to LINQ (Visual Basic)</span></span>](../../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md)  
 <span data-ttu-id="5cdaf-128">Sono disponibili risorse che consentono di iniziare a conoscere LINQ to SQL usando Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="5cdaf-128">Provides resources to help you begin to learn about LINQ to SQL using Visual Basic.</span></span>
