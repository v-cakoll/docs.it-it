---
title: Cenni preliminari sul modello di factory
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b5dc81c4-7554-44b9-b513-769bd61e2e7b
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 114b952f3b84122b2e61b1fa0d36d221449a3af6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="factory-model-overview"></a><span data-ttu-id="9c01e-102">Cenni preliminari sul modello di factory</span><span class="sxs-lookup"><span data-stu-id="9c01e-102">Factory Model Overview</span></span>
<span data-ttu-id="9c01e-103">In ADO.NET 2.0 sono state introdotte nuove classi di base nello spazio dei nomi <xref:System.Data.Common>.</span><span class="sxs-lookup"><span data-stu-id="9c01e-103">ADO.NET 2.0 introduced new base classes in the <xref:System.Data.Common> namespace.</span></span> <span data-ttu-id="9c01e-104">Le classi di base sono astratte, ovvero non è possibile creare un'istanza di tali classi in modo diretto.</span><span class="sxs-lookup"><span data-stu-id="9c01e-104">The base classes are abstract, which means that they can't be directly instantiated.</span></span> <span data-ttu-id="9c01e-105">Includono <xref:System.Data.Common.DbConnection>, <xref:System.Data.Common.DbCommand>e <xref:System.Data.Common.DbDataAdapter> e sono condivise tra i provider di dati .NET Framework, ad esempio <xref:System.Data.SqlClient> e <xref:System.Data.OleDb>.</span><span class="sxs-lookup"><span data-stu-id="9c01e-105">They include <xref:System.Data.Common.DbConnection>, <xref:System.Data.Common.DbCommand>, and <xref:System.Data.Common.DbDataAdapter> and are shared by the .NET Framework data providers, such as <xref:System.Data.SqlClient> and <xref:System.Data.OleDb>.</span></span> <span data-ttu-id="9c01e-106">L'aggiunta di classi di base consente di aggiungere più facilmente funzionalità ai provider di dati .NET Framework senza dover creare nuove interfacce.</span><span class="sxs-lookup"><span data-stu-id="9c01e-106">The addition of base classes simplifies adding functionality to the .NET Framework data providers without having to create new interfaces.</span></span>  
  
 <span data-ttu-id="9c01e-107">In ADO.NET 2.0 sono state inoltre introdotte classi di base astratte che consentono agli sviluppatori di scrivere codice per l'accesso ai dati generico e non dipendente da un provider di dati specifico.</span><span class="sxs-lookup"><span data-stu-id="9c01e-107">ADO.NET 2.0 also introduced abstract base classes, which enable a developer to write generic data access code that does not depend on a specific data provider.</span></span>  
  
## <a name="the-factory-design-pattern"></a><span data-ttu-id="9c01e-108">Modello di progettazione a livello di factory</span><span class="sxs-lookup"><span data-stu-id="9c01e-108">The Factory Design Pattern</span></span>  
 <span data-ttu-id="9c01e-109">Il modello di programmazione per la scrittura di codice indipendente dal provider è basato sul modello di progettazione a livello di factory, che usa una singola API per accedere ai database di più provider.</span><span class="sxs-lookup"><span data-stu-id="9c01e-109">The programming model for writing provider-independent code is based on the use of the "factory" design pattern, which uses a single API to access databases across multiple providers.</span></span> <span data-ttu-id="9c01e-110">Il nome di questo modello è appropriato in quanto richiede l'uso di un oggetto specializzato soltanto per creare altri oggetti, non molto diversamente da una fabbrica reale.</span><span class="sxs-lookup"><span data-stu-id="9c01e-110">This pattern is aptly named, as it calls for the use of a specialized object solely to create other objects, much like a real-world factory.</span></span> <span data-ttu-id="9c01e-111">Per una descrizione più dettagliata del modello di progettazione di factory, vedere "[la scrittura di codice di accesso ai dati generico in ASP.NET 2.0 e ADO.NET 2.0](http://go.microsoft.com/fwlink/?LinkId=55915)" e "Generico di codifica con di ADO.NET 2.0 Base le classi factory e" [http:// MSDN.microsoft.com/library/default.asp?url=/library/dnvs05/html/vsgenerics.asp](http://msdn.microsoft.com/library/default.asp?url=/library/dnvs05/html/vsgenerics.asp) su MSDN.</span><span class="sxs-lookup"><span data-stu-id="9c01e-111">For a more detailed description of the factory design pattern, see "[Writing Generic Data Access Code in ASP.NET 2.0 and ADO.NET 2.0](http://go.microsoft.com/fwlink/?LinkId=55915)" and "Generic Coding with the ADO.NET 2.0 Base Classes and Factories" [http://msdn.microsoft.com/library/default.asp?url=/library/dnvs05/html/vsgenerics.asp](http://msdn.microsoft.com/library/default.asp?url=/library/dnvs05/html/vsgenerics.asp) on MSDN.</span></span>  
  
 <span data-ttu-id="9c01e-112">A partire da ADO.NET 2.0 la classe <xref:System.Data.Common.DbProviderFactories> fornisce metodi `static` (o `Shared` in Visual Basic) per la creazione di un'istanza di <xref:System.Data.Common.DbProviderFactory>.</span><span class="sxs-lookup"><span data-stu-id="9c01e-112">Starting with ADO.NET 2.0, the <xref:System.Data.Common.DbProviderFactories> class provides `static` (or `Shared` in Visual Basic) methods for creating a <xref:System.Data.Common.DbProviderFactory> instance.</span></span> <span data-ttu-id="9c01e-113">L'istanza restituisce quindi un oggetto fortemente tipizzato corretto basato sulle informazioni fornite dal provider e dalla stringa di connessione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="9c01e-113">The instance then returns a correct strongly typed object based on provider information and the connection string supplied at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c01e-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9c01e-114">See Also</span></span>  
 [<span data-ttu-id="9c01e-115">Recupero di una classe DbProviderFactory</span><span class="sxs-lookup"><span data-stu-id="9c01e-115">Obtaining a DbProviderFactory</span></span>](../../../../docs/framework/data/adonet/obtaining-a-dbproviderfactory.md)  
 [<span data-ttu-id="9c01e-116">DbConnection, DbCommand e DbException</span><span class="sxs-lookup"><span data-stu-id="9c01e-116">DbConnection, DbCommand and DbException</span></span>](../../../../docs/framework/data/adonet/dbconnection-dbcommand-and-dbexception.md)  
 [<span data-ttu-id="9c01e-117">Modifica di dati con un oggetto DbDataAdapter</span><span class="sxs-lookup"><span data-stu-id="9c01e-117">Modifying Data with a DbDataAdapter</span></span>](../../../../docs/framework/data/adonet/modifying-data-with-a-dbdataadapter.md)  
 [<span data-ttu-id="9c01e-118">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="9c01e-118">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
