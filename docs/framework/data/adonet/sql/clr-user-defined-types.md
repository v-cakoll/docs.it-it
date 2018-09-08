---
title: Tipi definiti dall'utente CLR
ms.date: 03/30/2017
ms.assetid: 9f70e0b0-3a0d-4eb1-b914-07a5d0c167c2
ms.openlocfilehash: 4ea415a348375c52e42ddf26ea09a74e7de5e355
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44075488"
---
# <a name="clr-user-defined-types"></a><span data-ttu-id="f34cd-102">Tipi definiti dall'utente CLR</span><span class="sxs-lookup"><span data-stu-id="f34cd-102">CLR User-Defined Types</span></span>
<span data-ttu-id="f34cd-103">In Microsoft SQL Server viene fornito il supporto per i tipi definiti dall'utente implementati con CLR (Common Language Runtime) Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f34cd-103">Microsoft SQL Server provides support for user-defined types (UDTs) implemented with the Microsoft .NET Framework common language runtime (CLR).</span></span> <span data-ttu-id="f34cd-104">Il CLR è integrato in SQL Server e consente di estendere il sistema di tipi del database.</span><span class="sxs-lookup"><span data-stu-id="f34cd-104">The CLR is integrated into SQL Server, and this mechanism enables you to extend the type system of the database.</span></span> <span data-ttu-id="f34cd-105">Gli UDT forniscono l'estensibilità utenti nel sistema di tipi di dati di SQL Server e la capacità di definire tipi strutturati complessi.</span><span class="sxs-lookup"><span data-stu-id="f34cd-105">UDTs provide user extensibility of the SQL Server data type system, and also the ability to define complex structured types.</span></span>  
  
 <span data-ttu-id="f34cd-106">Gli UDT possono fornire due vantaggi chiave dal punto di vista dell'architettura delle applicazioni:</span><span class="sxs-lookup"><span data-stu-id="f34cd-106">UDTs can provide two key benefits from an application architecture perspective:</span></span>  
  
-   <span data-ttu-id="f34cd-107">Incapsulamento sicuro (nel client e nel server) tra lo stato interno e i comportamenti esterni.</span><span class="sxs-lookup"><span data-stu-id="f34cd-107">Strong encapsulation (both in the client and the server) between the internal state and the external behaviors.</span></span>  
  
-   <span data-ttu-id="f34cd-108">Integrazione perfetta con altre funzionalità relative al server.</span><span class="sxs-lookup"><span data-stu-id="f34cd-108">Deep integration with other related server features.</span></span> <span data-ttu-id="f34cd-109">Una volta definito, l'UDT può essere usato in tutti i contesti in cui si può usare un tipo del sistema in SQL Server, incluse definizioni di colonna, e come variabili, parametri, risultati di funzioni, cursori, trigger e replica.</span><span class="sxs-lookup"><span data-stu-id="f34cd-109">Once you define your own UDT, you can use it in all contexts where you can use a system type in SQL Server, including column definitions, and as variables, parameters, function results, cursors, triggers, and replication.</span></span>  
  
 <span data-ttu-id="f34cd-110">Per informazioni più dettagliate, vedere la [documentazione di SQL Server](/sql) per la versione di SQL Server in uso.</span><span class="sxs-lookup"><span data-stu-id="f34cd-110">For more detailed information, see the [SQL Server documentation](/sql) for the version of SQL Server you're using.</span></span>
  
 <span data-ttu-id="f34cd-111">**Documentazione di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="f34cd-111">**SQL Server documentation**</span></span>
  
1. [<span data-ttu-id="f34cd-112">Tipi definiti dall'utente CLR</span><span class="sxs-lookup"><span data-stu-id="f34cd-112">CLR User-Defined Types</span></span>](/sql/relational-databases/clr-integration-database-objects-user-defined-types/clr-user-defined-types)  
  
## <a name="see-also"></a><span data-ttu-id="f34cd-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f34cd-113">See also</span></span>  

[<span data-ttu-id="f34cd-114">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f34cd-114">ADO.NET Overview</span></span>](../ado-net-overview.md)  