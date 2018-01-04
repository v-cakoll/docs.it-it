---
title: Instance Encoding Option
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 89e4b029-4f68-438c-8117-9b21fe094ef4
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a7664eecb68ff9aec0f5e3e31aa08058700f0e92
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="instance-encoding-option"></a><span data-ttu-id="4f1b5-102">Instance Encoding Option</span><span class="sxs-lookup"><span data-stu-id="4f1b5-102">Instance Encoding Option</span></span>
<span data-ttu-id="4f1b5-103">Il **Instance Encoding Option** proprietà dell'archivio di istanze del flusso di lavoro SQL consente di specificare se il provider di persistenza SQL deve comprimere le informazioni sullo stato di istanza del flusso di lavoro usando l'algoritmo GZip prima di salvare il informazioni nel database di persistenza.</span><span class="sxs-lookup"><span data-stu-id="4f1b5-103">The **Instance Encoding Option** property of the SQL Workflow Instance Store lets you specify whether the SQL persistence provider should compress the workflow instance state information using the GZip algorithm before saving the information into the persistence database.</span></span> <span data-ttu-id="4f1b5-104">I valori consentiti per questa proprietà sono GZip e None.</span><span class="sxs-lookup"><span data-stu-id="4f1b5-104">The allowed values for this property are: GZip and None.</span></span> <span data-ttu-id="4f1b5-105">Il valore predefinito è None.</span><span class="sxs-lookup"><span data-stu-id="4f1b5-105">The default value is None.</span></span> <span data-ttu-id="4f1b5-106">Nell'elenco seguente vengono descritte queste opzioni.</span><span class="sxs-lookup"><span data-stu-id="4f1b5-106">The following list describes these options.</span></span>  
  
1.  <span data-ttu-id="4f1b5-107">**GZip**.</span><span class="sxs-lookup"><span data-stu-id="4f1b5-107">**GZip**.</span></span> <span data-ttu-id="4f1b5-108">Il provider di persistenza codifica le informazioni sullo stato usando l'algoritmo GZip prima di rendere persistenti le informazioni sullo stato nel database di persistenza.</span><span class="sxs-lookup"><span data-stu-id="4f1b5-108">The persistence provider encodes the state information using the GZip algorithm before persisting the state information in the persistence database.</span></span>  
  
2.  <span data-ttu-id="4f1b5-109">**Nessuna**.</span><span class="sxs-lookup"><span data-stu-id="4f1b5-109">**None**.</span></span> <span data-ttu-id="4f1b5-110">Il provider di persistenza non codifica le informazioni sullo stato prima di salvare le informazioni nel database di persistenza.</span><span class="sxs-lookup"><span data-stu-id="4f1b5-110">The persistence provider does not encode the state information before saving the information into the persistence database.</span></span>  
  
 <span data-ttu-id="4f1b5-111">La codifica delle informazioni sullo stato dell'istanza del flusso di lavoro tramite l'algoritmo GZip riduce il consumo di memoria nel database SQL e anche l'uso della rete se il database si trova in un computer della rete diverso dal computer in cui è in esecuzione l'host del servizio del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="4f1b5-111">Encoding workflow instance state information using the GZip reduces memory consumption in the SQL database and also reduces network consumption if the database resides on a different computer on the network from the computer on which the workflow service host is running.</span></span> <span data-ttu-id="4f1b5-112">Una Guida generale consiste nell'impostare il **Instance Encoding Option** proprietà **Nessuno** se lo stato dell'istanza del flusso di lavoro è piccolo.</span><span class="sxs-lookup"><span data-stu-id="4f1b5-112">A general guidance is to set the **Instance Encoding Option** property to **None** if the workflow instance state is small.</span></span>
