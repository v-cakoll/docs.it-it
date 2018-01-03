---
title: Tipi definiti dall'utente CLR
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9f70e0b0-3a0d-4eb1-b914-07a5d0c167c2
caps.latest.revision: "6"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 7b083dd7284789b1d0271bc688c08bbae591e160
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="clr-user-defined-types"></a><span data-ttu-id="76f16-102">Tipi definiti dall'utente CLR</span><span class="sxs-lookup"><span data-stu-id="76f16-102">CLR User-Defined Types</span></span>
<span data-ttu-id="76f16-103">In Microsoft SQL Server viene fornito il supporto per i tipi definiti dall'utente implementati con CLR (Common Language Runtime) Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="76f16-103">Microsoft SQL Server provides support for user-defined types (UDTs) implemented with the Microsoft .NET Framework common language runtime (CLR).</span></span> <span data-ttu-id="76f16-104">Il CLR è integrato in SQL Server e consente di estendere il sistema di tipi del database.</span><span class="sxs-lookup"><span data-stu-id="76f16-104">The CLR is integrated into SQL Server, and this mechanism enables you to extend the type system of the database.</span></span> <span data-ttu-id="76f16-105">Gli UDT forniscono l'estensibilità utenti nel sistema di tipi di dati di SQL Server e la capacità di definire tipi strutturati complessi.</span><span class="sxs-lookup"><span data-stu-id="76f16-105">UDTs provide user extensibility of the SQL Server data type system, and also the ability to define complex structured types.</span></span>  
  
 <span data-ttu-id="76f16-106">Gli UDT possono fornire due vantaggi chiave dal punto di vista dell'architettura delle applicazioni:</span><span class="sxs-lookup"><span data-stu-id="76f16-106">UDTs can provide two key benefits from an application architecture perspective:</span></span>  
  
-   <span data-ttu-id="76f16-107">Incapsulamento sicuro (nel client e nel server) tra lo stato interno e i comportamenti esterni.</span><span class="sxs-lookup"><span data-stu-id="76f16-107">Strong encapsulation (both in the client and the server) between the internal state and the external behaviors.</span></span>  
  
-   <span data-ttu-id="76f16-108">Integrazione perfetta con altre funzionalità relative al server.</span><span class="sxs-lookup"><span data-stu-id="76f16-108">Deep integration with other related server features.</span></span> <span data-ttu-id="76f16-109">Una volta definito, l'UDT può essere usato in tutti i contesti in cui si può usare un tipo del sistema in SQL Server, incluse definizioni di colonna, e come variabili, parametri, risultati di funzioni, cursori, trigger e replica.</span><span class="sxs-lookup"><span data-stu-id="76f16-109">Once you define your own UDT, you can use it in all contexts where you can use a system type in SQL Server, including column definitions, and as variables, parameters, function results, cursors, triggers, and replication.</span></span>  
  
 <span data-ttu-id="76f16-110">Per informazioni più dettagliate, vedere la versione della documentazione online di SQL Server corrispondente alla versione di SQL Server in uso.</span><span class="sxs-lookup"><span data-stu-id="76f16-110">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="76f16-111">**Documentazione online di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="76f16-111">**SQL Server Books Online**</span></span>  
  
1.  [<span data-ttu-id="76f16-112">Tipi definiti dall'utente CLR</span><span class="sxs-lookup"><span data-stu-id="76f16-112">CLR User-Defined Types</span></span>](http://go.microsoft.com/fwlink/?LinkId=98366)  
  
## <a name="see-also"></a><span data-ttu-id="76f16-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="76f16-113">See Also</span></span>  
 [<span data-ttu-id="76f16-114">Creazione di oggetti di SQL Server 2005 nel codice gestito</span><span class="sxs-lookup"><span data-stu-id="76f16-114">Creating SQL Server 2005 Objects In Managed Code</span></span>](http://msdn.microsoft.com/en-us/5358a825-e19b-49aa-8214-674ce5fed1da)  
 [<span data-ttu-id="76f16-115">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="76f16-115">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
