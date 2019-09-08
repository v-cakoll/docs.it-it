---
title: Creazione e invio di modifiche dei dati
ms.date: 03/30/2017
ms.assetid: d68c2dc3-99b3-49ab-b547-2ca5b386429a
ms.openlocfilehash: 18468c9a2018a28e85d87155d98b0853854013fd
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792959"
---
# <a name="making-and-submitting-data-changes"></a><span data-ttu-id="b46a7-102">Creazione e invio di modifiche dei dati</span><span class="sxs-lookup"><span data-stu-id="b46a7-102">Making and Submitting Data Changes</span></span>

<span data-ttu-id="b46a7-103">Negli argomenti in questa sezione viene descritto come effettuare e trasmettere modifiche al database e come gestire i conflitti di concorrenza ottimistica.</span><span class="sxs-lookup"><span data-stu-id="b46a7-103">The topics in this section describe how to make and transmit changes to the database and how to handle optimistic concurrency conflicts.</span></span>

> [!NOTE]
> <span data-ttu-id="b46a7-104">È possibile eseguire l'override dei metodi predefiniti [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] per le operazioni di database `Insert`, `Update`e `Delete`.</span><span class="sxs-lookup"><span data-stu-id="b46a7-104">You can override [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default methods for `Insert`, `Update`, and `Delete` database operations.</span></span> <span data-ttu-id="b46a7-105">Per ulteriori informazioni, vedere [personalizzazione di operazioni di inserimento, aggiornamento ed eliminazione](customizing-insert-update-and-delete-operations.md).</span><span class="sxs-lookup"><span data-stu-id="b46a7-105">For more information, see [Customizing Insert, Update, and Delete Operations](customizing-insert-update-and-delete-operations.md).</span></span>
>
> <span data-ttu-id="b46a7-106">Gli sviluppatori che utilizzano Visual Studio possono utilizzare il Object Relational Designer per sviluppare stored procedure allo stesso scopo.</span><span class="sxs-lookup"><span data-stu-id="b46a7-106">Developers using Visual Studio can use the Object Relational Designer to develop stored procedures for the same purpose.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="b46a7-107">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="b46a7-107">In This Section</span></span>

<span data-ttu-id="b46a7-108">[Procedura: Inserire righe nel database](how-to-insert-rows-into-the-database.md) </span><span class="sxs-lookup"><span data-stu-id="b46a7-108">[How to: Insert Rows Into the Database](how-to-insert-rows-into-the-database.md) </span></span>\
<span data-ttu-id="b46a7-109">Viene descritto come inserire righe nel database mediante l'aggiunta di oggetti al modello a oggetti.</span><span class="sxs-lookup"><span data-stu-id="b46a7-109">Describes how to insert rows in the database by adding objects to the object model.</span></span>

<span data-ttu-id="b46a7-110">[Procedura: Aggiornare righe nel database](how-to-update-rows-in-the-database.md) </span><span class="sxs-lookup"><span data-stu-id="b46a7-110">[How to: Update Rows in the Database](how-to-update-rows-in-the-database.md) </span></span>\
<span data-ttu-id="b46a7-111">Viene descritto come aggiornare righe nel database mediante l'aggiornamento di oggetti nel modello a oggetti.</span><span class="sxs-lookup"><span data-stu-id="b46a7-111">Describes how to update rows in the database by updating objects in the object model.</span></span>

<span data-ttu-id="b46a7-112">[Procedura: Eliminare righe dal database](how-to-delete-rows-from-the-database.md) </span><span class="sxs-lookup"><span data-stu-id="b46a7-112">[How to: Delete Rows From the Database](how-to-delete-rows-from-the-database.md) </span></span>\
<span data-ttu-id="b46a7-113">Viene descritto come eliminare righe nel database mediante l'eliminazione di oggetti nel modello a oggetti.</span><span class="sxs-lookup"><span data-stu-id="b46a7-113">Describes how to delete rows in the database by deleting objects in the object model.</span></span>

<span data-ttu-id="b46a7-114">[Procedura: Inviare le modifiche al database](how-to-submit-changes-to-the-database.md) </span><span class="sxs-lookup"><span data-stu-id="b46a7-114">[How to: Submit Changes to the Database](how-to-submit-changes-to-the-database.md) </span></span>\
<span data-ttu-id="b46a7-115">Viene descritto come inviare modifiche del modello a oggetti al database.</span><span class="sxs-lookup"><span data-stu-id="b46a7-115">Describes how to send object-model changes to the database.</span></span>

<span data-ttu-id="b46a7-116">[Procedura: Invii di dati tra parentesi quadre tramite transazioni](how-to-bracket-data-submissions-by-using-transactions.md) </span><span class="sxs-lookup"><span data-stu-id="b46a7-116">[How to: Bracket Data Submissions by Using Transactions](how-to-bracket-data-submissions-by-using-transactions.md) </span></span>\
<span data-ttu-id="b46a7-117">Viene descritto come includere operazioni in una transazione.</span><span class="sxs-lookup"><span data-stu-id="b46a7-117">Describes how to include operations in a transaction.</span></span>

<span data-ttu-id="b46a7-118">[Procedura: Creazione dinamica di un database](how-to-dynamically-create-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="b46a7-118">[How to: Dynamically Create a Database](how-to-dynamically-create-a-database.md) </span></span>\
<span data-ttu-id="b46a7-119">Viene descritto come generare dinamicamente database e scenari tipici per questo approccio.</span><span class="sxs-lookup"><span data-stu-id="b46a7-119">Describes how to generate databases dynamically, and typical scenarios for this approach.</span></span>

<span data-ttu-id="b46a7-120">[Procedura: Gestione dei conflitti di modifica](how-to-manage-change-conflicts.md) </span><span class="sxs-lookup"><span data-stu-id="b46a7-120">[How to: Manage Change Conflicts](how-to-manage-change-conflicts.md) </span></span>\
<span data-ttu-id="b46a7-121">Vengono descritte le tecniche per risolvere i problemi di concorrenza ottimistica.</span><span class="sxs-lookup"><span data-stu-id="b46a7-121">Describes techniques for addressing optimistic concurrency issues.</span></span>
