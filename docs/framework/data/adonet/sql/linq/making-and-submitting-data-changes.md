---
title: Creazione e invio di modifiche dei dati
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d68c2dc3-99b3-49ab-b547-2ca5b386429a
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: cb52916e8e0948725a2eeb15cf78410077c7dca1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="making-and-submitting-data-changes"></a><span data-ttu-id="0599f-102">Creazione e invio di modifiche dei dati</span><span class="sxs-lookup"><span data-stu-id="0599f-102">Making and Submitting Data Changes</span></span>
<span data-ttu-id="0599f-103">Negli argomenti in questa sezione viene descritto come effettuare e trasmettere modifiche al database e come gestire i conflitti di concorrenza ottimistica.</span><span class="sxs-lookup"><span data-stu-id="0599f-103">The topics in this section describe how to make and transmit changes to the database and how to handle optimistic concurrency conflicts.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0599f-104">È possibile eseguire l'override dei metodi predefiniti [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] per le operazioni di database `Insert`, `Update`e `Delete`.</span><span class="sxs-lookup"><span data-stu-id="0599f-104">You can override [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default methods for `Insert`, `Update`, and `Delete` database operations.</span></span> <span data-ttu-id="0599f-105">Per ulteriori informazioni, vedere [personalizzazione di operazioni di inserimento, aggiornamento ed eliminare](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span><span class="sxs-lookup"><span data-stu-id="0599f-105">For more information, see [Customizing Insert, Update, and Delete Operations](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span></span>  
>   
>  <span data-ttu-id="0599f-106">Gli sviluppatori che usano [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] possono adoperare [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] per sviluppare stored procedure allo stesso scopo.</span><span class="sxs-lookup"><span data-stu-id="0599f-106">Developers using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to develop stored procedures for the same purpose.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0599f-107">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="0599f-107">In This Section</span></span>  
 [<span data-ttu-id="0599f-108">Procedura: inserire righe nel Database</span><span class="sxs-lookup"><span data-stu-id="0599f-108">How to: Insert Rows Into the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-insert-rows-into-the-database.md)  
 <span data-ttu-id="0599f-109">Viene descritto come inserire righe nel database mediante l'aggiunta di oggetti al modello a oggetti.</span><span class="sxs-lookup"><span data-stu-id="0599f-109">Describes how to insert rows in the database by adding objects to the object model.</span></span>  
  
 [<span data-ttu-id="0599f-110">Procedura: aggiornare righe nel Database</span><span class="sxs-lookup"><span data-stu-id="0599f-110">How to: Update Rows in the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-update-rows-in-the-database.md)  
 <span data-ttu-id="0599f-111">Viene descritto come aggiornare righe nel database mediante l'aggiornamento di oggetti nel modello a oggetti.</span><span class="sxs-lookup"><span data-stu-id="0599f-111">Describes how to update rows in the database by updating objects in the object model.</span></span>  
  
 [<span data-ttu-id="0599f-112">Procedura: eliminare righe dal Database</span><span class="sxs-lookup"><span data-stu-id="0599f-112">How to: Delete Rows From the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md)  
 <span data-ttu-id="0599f-113">Viene descritto come eliminare righe nel database mediante l'eliminazione di oggetti nel modello a oggetti.</span><span class="sxs-lookup"><span data-stu-id="0599f-113">Describes how to delete rows in the database by deleting objects in the object model.</span></span>  
  
 [<span data-ttu-id="0599f-114">Procedura: inviare modifiche al Database</span><span class="sxs-lookup"><span data-stu-id="0599f-114">How to: Submit Changes to the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-submit-changes-to-the-database.md)  
 <span data-ttu-id="0599f-115">Viene descritto come inviare modifiche del modello a oggetti al database.</span><span class="sxs-lookup"><span data-stu-id="0599f-115">Describes how to send object-model changes to the database.</span></span>  
  
 [<span data-ttu-id="0599f-116">Procedura: racchiudere tra parentesi quadre gli invii di dati tramite transazioni</span><span class="sxs-lookup"><span data-stu-id="0599f-116">How to: Bracket Data Submissions by Using Transactions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-bracket-data-submissions-by-using-transactions.md)  
 <span data-ttu-id="0599f-117">Viene descritto come includere operazioni in una transazione.</span><span class="sxs-lookup"><span data-stu-id="0599f-117">Describes how to include operations in a transaction.</span></span>  
  
 [<span data-ttu-id="0599f-118">Procedura: creare in modo dinamico un Database</span><span class="sxs-lookup"><span data-stu-id="0599f-118">How to: Dynamically Create a Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-dynamically-create-a-database.md)  
 <span data-ttu-id="0599f-119">Viene descritto come generare dinamicamente database e scenari tipici per questo approccio.</span><span class="sxs-lookup"><span data-stu-id="0599f-119">Describes how to generate databases dynamically, and typical scenarios for this approach.</span></span>  
  
 [<span data-ttu-id="0599f-120">Procedura: gestire i conflitti di modifiche</span><span class="sxs-lookup"><span data-stu-id="0599f-120">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)  
 <span data-ttu-id="0599f-121">Vengono descritte le tecniche per risolvere i problemi di concorrenza ottimistica.</span><span class="sxs-lookup"><span data-stu-id="0599f-121">Describes techniques for addressing optimistic concurrency issues.</span></span>
