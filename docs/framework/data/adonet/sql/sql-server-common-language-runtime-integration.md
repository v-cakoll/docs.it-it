---
title: Integrazione di Common Language Runtime di SQL Server
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c7a324c4-160d-44c2-b593-641af06eca61
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: de415a6282b1d27d803d448bd3225355c08e011b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="sql-server-common-language-runtime-integration"></a><span data-ttu-id="f8449-102">Integrazione di Common Language Runtime di SQL Server</span><span class="sxs-lookup"><span data-stu-id="f8449-102">SQL Server Common Language Runtime Integration</span></span>
<span data-ttu-id="f8449-103">In SQL Server 2005 è stata introdotta l'integrazione del componente CLR di .NET Framework per Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="f8449-103">SQL Server 2005 introduced the integration of the common language runtime (CLR) component of the .NET Framework for Microsoft Windows.</span></span> <span data-ttu-id="f8449-104">Questo significa che è possibile scrivere stored procedure, trigger, tipi definiti dall'utente, funzioni definite dall'utente, aggregati definiti dall'utente e funzioni con valori di tabella di flusso usando qualsiasi linguaggio di .NET Framework, inclusi Microsoft Visual Basic .NET e Microsoft Visual C#.</span><span class="sxs-lookup"><span data-stu-id="f8449-104">This means that you can write stored procedures, triggers, user-defined types, user-defined functions, user-defined aggregates, and streaming table-valued functions, using any .NET Framework language, including Microsoft Visual Basic .NET and Microsoft Visual C#.</span></span> <span data-ttu-id="f8449-105">Lo spazio dei nomi <xref:Microsoft.SqlServer.Server> contiene un set di nuove API (Application Programming Interface) che consente l'interazione del codice gestito con l'ambiente Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f8449-105">The <xref:Microsoft.SqlServer.Server> namespace contains a set of new application programming interfaces (APIs) so that managed code can interact with the Microsoft SQL Server environment.</span></span>  
  
 <span data-ttu-id="f8449-106">Questa sezione descrive le funzionalità e i comportamenti specifici dell'integrazione CLR di SQL Server, nonché le estensioni specifiche in-process di SQL Server per ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="f8449-106">This section describes features and behaviors that are specific to SQL Server common language runtime (CLR) integration and the SQL Server in-process specific extensions to ADO.NET.</span></span>  
  
 <span data-ttu-id="f8449-107">In questa sezione vengono fornite solo le informazioni di base per iniziare a programmare con l'integrazione CLR di SQL Server. Tali informazioni non sono da considerarsi esaustive.</span><span class="sxs-lookup"><span data-stu-id="f8449-107">This section is meant to provide only enough information to get started programming with SQL Server CLR integration, and is not meant to be comprehensive.</span></span> <span data-ttu-id="f8449-108">Per informazioni più dettagliate, vedere la versione della documentazione online di SQL Server corrispondente alla versione di SQL Server in uso.</span><span class="sxs-lookup"><span data-stu-id="f8449-108">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="f8449-109">**Documentazione online di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="f8449-109">**SQL Server Books Online**</span></span>  
  
1.  [<span data-ttu-id="f8449-110">Concetti della programmazione di integrazione Common Language Runtime (CLR)</span><span class="sxs-lookup"><span data-stu-id="f8449-110">Common Language Runtime (CLR) Integration Programming Concepts</span></span>](http://go.microsoft.com/fwlink/?LinkId=115240)  
  
## <a name="in-this-section"></a><span data-ttu-id="f8449-111">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="f8449-111">In This Section</span></span>  
 [<span data-ttu-id="f8449-112">Introduzione all'integrazione CLR in SQL Server</span><span class="sxs-lookup"><span data-stu-id="f8449-112">Introduction to SQL Server CLR Integration</span></span>](../../../../../docs/framework/data/adonet/sql/introduction-to-sql-server-clr-integration.md)  
 <span data-ttu-id="f8449-113">Viene fornita un'introduzione all'integrazione CLR di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f8449-113">Provides an introduction to SQL Server CLR integration.</span></span> <span data-ttu-id="f8449-114">Vengono forniti collegamenti ad argomenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="f8449-114">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="f8449-115">Funzioni definite dall'utente CLR</span><span class="sxs-lookup"><span data-stu-id="f8449-115">CLR User-Defined Functions</span></span>](../../../../../docs/framework/data/adonet/sql/clr-user-defined-functions.md)  
 <span data-ttu-id="f8449-116">Viene descritto come implementare e usare i diversi tipi di funzioni CLR, ovvero le funzioni con valori di tabella, le funzioni scalari e le funzioni di aggregazione definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="f8449-116">Describes how to implement and use the various types of CLR functions: table-valued, scalar, and user-defined aggregate functions.</span></span>  
  
 [<span data-ttu-id="f8449-117">Tipi definiti dall'utente CLR</span><span class="sxs-lookup"><span data-stu-id="f8449-117">CLR User-Defined Types</span></span>](../../../../../docs/framework/data/adonet/sql/clr-user-defined-types.md)  
 <span data-ttu-id="f8449-118">Viene descritto come implementare e usare i tipi CLR definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="f8449-118">Describes how to implement and use CLR user-defined types.</span></span> <span data-ttu-id="f8449-119">Vengono forniti collegamenti ad argomenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="f8449-119">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="f8449-120">Stored procedure CLR</span><span class="sxs-lookup"><span data-stu-id="f8449-120">CLR Stored Procedures</span></span>](../../../../../docs/framework/data/adonet/sql/clr-stored-procedures.md)  
 <span data-ttu-id="f8449-121">Viene descritto come implementare e usare le stored procedure CLR.</span><span class="sxs-lookup"><span data-stu-id="f8449-121">Describes how to implement and use CLR stored procedures.</span></span> <span data-ttu-id="f8449-122">Vengono forniti collegamenti ad argomenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="f8449-122">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="f8449-123">Trigger CLR</span><span class="sxs-lookup"><span data-stu-id="f8449-123">CLR Triggers</span></span>](../../../../../docs/framework/data/adonet/sql/clr-triggers.md)  
 <span data-ttu-id="f8449-124">Viene descritto come implementare e usare i trigger CLR.</span><span class="sxs-lookup"><span data-stu-id="f8449-124">Describes how to implement and use CLR triggers.</span></span> <span data-ttu-id="f8449-125">Vengono forniti collegamenti ad argomenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="f8449-125">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="f8449-126">Connessione di contesto</span><span class="sxs-lookup"><span data-stu-id="f8449-126">The Context Connection</span></span>](../../../../../docs/framework/data/adonet/sql/the-context-connection.md)  
 <span data-ttu-id="f8449-127">Viene descritta la connessione di contesto.</span><span class="sxs-lookup"><span data-stu-id="f8449-127">Describes the context connection.</span></span>  
  
 [<span data-ttu-id="f8449-128">Comportamento specifico in-process SQL Server di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f8449-128">SQL Server In-Process-Specific Behavior of ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-in-process-specific-behavior-of-adonet.md)  
 <span data-ttu-id="f8449-129">Vengono descritte le estensioni specifiche in-process di SQL Server per ADO.NET e la connessione di contesto.</span><span class="sxs-lookup"><span data-stu-id="f8449-129">Describes the SQL Server in-process specific extensions to ADO.NET, and the context connection.</span></span> <span data-ttu-id="f8449-130">Vengono forniti collegamenti ad argomenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="f8449-130">Provides links to additional topics.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8449-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8449-131">See Also</span></span>  
 [<span data-ttu-id="f8449-132">SQL Server e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f8449-132">SQL Server and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/index.md)  
 [<span data-ttu-id="f8449-133">Creazione di oggetti di SQL Server 2005 nel codice gestito</span><span class="sxs-lookup"><span data-stu-id="f8449-133">Creating SQL Server 2005 Objects In Managed Code</span></span>](http://msdn.microsoft.com/en-us/5358a825-e19b-49aa-8214-674ce5fed1da)  
 [<span data-ttu-id="f8449-134">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="f8449-134">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
