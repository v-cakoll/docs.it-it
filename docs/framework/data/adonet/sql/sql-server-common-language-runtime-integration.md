---
title: Integrazione di Common Language Runtime di SQL Server
ms.date: 03/30/2017
ms.assetid: c7a324c4-160d-44c2-b593-641af06eca61
ms.openlocfilehash: 12ae15d72644e314aa694f8d169bc8f45fa284a2
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452344"
---
# <a name="sql-server-common-language-runtime-integration"></a><span data-ttu-id="b8b44-102">Integrazione di Common Language Runtime di SQL Server</span><span class="sxs-lookup"><span data-stu-id="b8b44-102">SQL Server Common Language Runtime Integration</span></span>
<span data-ttu-id="b8b44-103">In SQL Server 2005 è stata introdotta l'integrazione del componente CLR di .NET Framework per Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="b8b44-103">SQL Server 2005 introduced the integration of the common language runtime (CLR) component of the .NET Framework for Microsoft Windows.</span></span> <span data-ttu-id="b8b44-104">Questo significa che è possibile scrivere stored procedure, trigger, tipi definiti dall'utente, funzioni definite dall'utente, aggregati definiti dall'utente e funzioni con valori di tabella di flusso usando qualsiasi linguaggio di .NET Framework, inclusi Microsoft Visual Basic .NET e Microsoft Visual C#.</span><span class="sxs-lookup"><span data-stu-id="b8b44-104">This means that you can write stored procedures, triggers, user-defined types, user-defined functions, user-defined aggregates, and streaming table-valued functions, using any .NET Framework language, including Microsoft Visual Basic .NET and Microsoft Visual C#.</span></span> <span data-ttu-id="b8b44-105">Lo spazio dei nomi <xref:Microsoft.SqlServer.Server> contiene un set di nuove API (Application Programming Interface) che consente l'interazione del codice gestito con l'ambiente Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b8b44-105">The <xref:Microsoft.SqlServer.Server> namespace contains a set of new application programming interfaces (APIs) so that managed code can interact with the Microsoft SQL Server environment.</span></span>  
  
 <span data-ttu-id="b8b44-106">Questa sezione descrive le funzionalità e i comportamenti specifici dell'integrazione CLR di SQL Server, nonché le estensioni specifiche in-process di SQL Server per ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="b8b44-106">This section describes features and behaviors that are specific to SQL Server common language runtime (CLR) integration and the SQL Server in-process specific extensions to ADO.NET.</span></span>  
  
 <span data-ttu-id="b8b44-107">In questa sezione vengono fornite solo le informazioni di base per iniziare a programmare con l'integrazione CLR di SQL Server. Tali informazioni non sono da considerarsi esaustive.</span><span class="sxs-lookup"><span data-stu-id="b8b44-107">This section is meant to provide only enough information to get started programming with SQL Server CLR integration, and is not meant to be comprehensive.</span></span> <span data-ttu-id="b8b44-108">Per informazioni più dettagliate, vedere la versione della documentazione online di SQL Server corrispondente alla versione di SQL Server in uso.</span><span class="sxs-lookup"><span data-stu-id="b8b44-108">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="b8b44-109">**Documentazione di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="b8b44-109">**SQL Server documentation**</span></span>  
  
1. [<span data-ttu-id="b8b44-110">Concetti relativi alla programmazione dell'integrazione con CLR (Common Language Runtime)</span><span class="sxs-lookup"><span data-stu-id="b8b44-110">Common Language Runtime (CLR) Integration Programming Concepts</span></span>](/sql/relational-databases/clr-integration/common-language-runtime-clr-integration-programming-concepts)  
  
## <a name="in-this-section"></a><span data-ttu-id="b8b44-111">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="b8b44-111">In This Section</span></span>  
 [<span data-ttu-id="b8b44-112">Introduzione all'integrazione CLR in SQL Server</span><span class="sxs-lookup"><span data-stu-id="b8b44-112">Introduction to SQL Server CLR Integration</span></span>](introduction-to-sql-server-clr-integration.md)  
 <span data-ttu-id="b8b44-113">Viene fornita un'introduzione all'integrazione CLR di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b8b44-113">Provides an introduction to SQL Server CLR integration.</span></span> <span data-ttu-id="b8b44-114">Vengono forniti collegamenti ad argomenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="b8b44-114">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="b8b44-115">Funzioni definite dall'utente CLR</span><span class="sxs-lookup"><span data-stu-id="b8b44-115">CLR User-Defined Functions</span></span>](clr-user-defined-functions.md)  
 <span data-ttu-id="b8b44-116">Viene descritto come implementare e usare i diversi tipi di funzioni CLR, ovvero le funzioni con valori di tabella, le funzioni scalari e le funzioni di aggregazione definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="b8b44-116">Describes how to implement and use the various types of CLR functions: table-valued, scalar, and user-defined aggregate functions.</span></span>  
  
 [<span data-ttu-id="b8b44-117">Tipi definiti dall'utente CLR</span><span class="sxs-lookup"><span data-stu-id="b8b44-117">CLR User-Defined Types</span></span>](clr-user-defined-types.md)  
 <span data-ttu-id="b8b44-118">Viene descritto come implementare e usare i tipi CLR definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="b8b44-118">Describes how to implement and use CLR user-defined types.</span></span> <span data-ttu-id="b8b44-119">Vengono forniti collegamenti ad argomenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="b8b44-119">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="b8b44-120">Stored procedure CLR</span><span class="sxs-lookup"><span data-stu-id="b8b44-120">CLR Stored Procedures</span></span>](clr-stored-procedures.md)  
 <span data-ttu-id="b8b44-121">Viene descritto come implementare e usare le stored procedure CLR.</span><span class="sxs-lookup"><span data-stu-id="b8b44-121">Describes how to implement and use CLR stored procedures.</span></span> <span data-ttu-id="b8b44-122">Vengono forniti collegamenti ad argomenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="b8b44-122">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="b8b44-123">Trigger CLR</span><span class="sxs-lookup"><span data-stu-id="b8b44-123">CLR Triggers</span></span>](clr-triggers.md)  
 <span data-ttu-id="b8b44-124">Viene descritto come implementare e usare i trigger CLR.</span><span class="sxs-lookup"><span data-stu-id="b8b44-124">Describes how to implement and use CLR triggers.</span></span> <span data-ttu-id="b8b44-125">Vengono forniti collegamenti ad argomenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="b8b44-125">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="b8b44-126">Connessione di contesto</span><span class="sxs-lookup"><span data-stu-id="b8b44-126">The Context Connection</span></span>](the-context-connection.md)  
 <span data-ttu-id="b8b44-127">Viene descritta la connessione di contesto.</span><span class="sxs-lookup"><span data-stu-id="b8b44-127">Describes the context connection.</span></span>  
  
 [<span data-ttu-id="b8b44-128">Comportamento specifico in-process SQL Server di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b8b44-128">SQL Server In-Process-Specific Behavior of ADO.NET</span></span>](sql-server-in-process-specific-behavior-of-adonet.md)  
 <span data-ttu-id="b8b44-129">Vengono descritte le estensioni specifiche in-process di SQL Server per ADO.NET e la connessione di contesto.</span><span class="sxs-lookup"><span data-stu-id="b8b44-129">Describes the SQL Server in-process specific extensions to ADO.NET, and the context connection.</span></span> <span data-ttu-id="b8b44-130">Vengono forniti collegamenti ad argomenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="b8b44-130">Provides links to additional topics.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8b44-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8b44-131">See also</span></span>

- [<span data-ttu-id="b8b44-132">SQL Server e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b8b44-132">SQL Server and ADO.NET</span></span>](index.md)
- [<span data-ttu-id="b8b44-133">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b8b44-133">ADO.NET Overview</span></span>](../ado-net-overview.md)
