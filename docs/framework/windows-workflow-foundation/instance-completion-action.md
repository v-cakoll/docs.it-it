---
title: Instance Completion Action
ms.date: 03/30/2017
ms.assetid: 90cc99d2-9fef-42fd-bcbf-a56917993721
ms.openlocfilehash: 646015fbcdb7c734ae8584c7ca3979d64b81339f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791118"
---
# <a name="instance-completion-action"></a><span data-ttu-id="7f842-102">Instance Completion Action</span><span class="sxs-lookup"><span data-stu-id="7f842-102">Instance Completion Action</span></span>
<span data-ttu-id="7f842-103">Il **Instance Completion Action** proprietà la Store di istanza del flusso di lavoro SQL consente di specificare se i dati e i metadati delle istanze del flusso di lavoro vengono eliminati dal database di persistenza dopo il completamento delle istanze.</span><span class="sxs-lookup"><span data-stu-id="7f842-103">The **Instance Completion Action** property of the SQL Workflow Instance Store lets you specify whether the data and metadata of workflow instances is deleted from the persistence database after the instances are completed.</span></span> <span data-ttu-id="7f842-104">I valori consentiti per questa proprietà sono **DeleteAll** e **DeleteNothing**.</span><span class="sxs-lookup"><span data-stu-id="7f842-104">The allowed values for this property are **DeleteAll** and **DeleteNothing**.</span></span> <span data-ttu-id="7f842-105">Nell'elenco seguente vengono descritte queste opzioni:</span><span class="sxs-lookup"><span data-stu-id="7f842-105">The following list describes these options:</span></span>  
  
- <span data-ttu-id="7f842-106">**DeleteAll (impostazione predefinita).**</span><span class="sxs-lookup"><span data-stu-id="7f842-106">**DeleteAll (default).**</span></span> <span data-ttu-id="7f842-107">Se il valore della proprietà viene impostato su DeleteAll, i dati e i metadati delle istanze del flusso di lavoro vengono eliminati dal database di persistenza dopo il completamento delle istanze.</span><span class="sxs-lookup"><span data-stu-id="7f842-107">If the value of the property is set to DeleteAll, the data and metadata of workflow instances is deleted from the persistence database after the instances are completed.</span></span>  
  
- <span data-ttu-id="7f842-108">**DeleteNothing.**</span><span class="sxs-lookup"><span data-stu-id="7f842-108">**DeleteNothing.**</span></span> <span data-ttu-id="7f842-109">Se il valore della proprietà viene impostato su DeleteNothing, i dati e i metadati delle istanze del flusso di lavoro vengono mantenuti nel database di persistenza anche dopo il completamento delle istanze.</span><span class="sxs-lookup"><span data-stu-id="7f842-109">If the value of the property is set to DeleteNothing, the data and metadata of workflow instances is kept in the persistence database even after the instances are completed.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="7f842-110">Il mantenimento delle informazioni sullo stato delle istanze dopo il relativo completamento comporta l'aumento delle dimensioni del database di persistenza.</span><span class="sxs-lookup"><span data-stu-id="7f842-110">Keeping instance state information after the instances are completed causes the persistence database to grow in size.</span></span> <span data-ttu-id="7f842-111">Se le dimensioni del database aumentano, le operazioni del database eseguite dal sottosistema di persistenza richiedono più tempo, pertanto è necessario eliminare periodicamente le informazioni sullo stato delle istanze dal database di persistenza affinché i servizi vengano eseguiti in base alle proprie esigenze di prestazione.</span><span class="sxs-lookup"><span data-stu-id="7f842-111">As the size of the database grows the database operations that the persistence subsystem performs take longer, so you need to purge the instance state information from the persistence database periodically to have services perform at the level that satisfy your performance needs.</span></span>
