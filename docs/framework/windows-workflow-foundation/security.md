---
title: Sicurezza
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 737ec121-bfc5-4b75-a504-2d53c2c8af39
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 461bc36fd85a158e67c29c3f4ad001997218c824
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="security"></a>Sicurezza
Nell'archivio di istanze del flusso di lavoro SQL vengono usati i seguenti ruoli di sicurezza del database, per un accesso protetto alle informazioni sullo stato dell'istanza nel database di persistenza.  
  
-   **System.Activities.DurableInstancing.InstanceStoreUsers**. Questo ruolo dispone di autorizzazioni di accesso in lettura e scrittura a visualizzazioni pubbliche e diritti di esecuzione di stored procedure coinvolte in operazioni di creazione, caricamento e salvataggio di istanze.  
  
-   **System.Activities.DurableInstancing.InstanceStoreObservers**. Questo ruolo dispone di accesso in sola lettura alle visualizzazioni pubbliche.  
  
-   **System.Activities.DurableInstancing.WorkflowActivationUsers**. Questo ruolo dispone di diritti di esecuzione per stored procedure incluse nel processo di attivazione delle istanze. Per ulteriori informazioni sull'attivazione di istanze, vedere [attivazione di istanze](../../../docs/framework/windows-workflow-foundation/instance-activation.md). L'account utente con il quale viene eseguito un host generico (ad esempio il Servizio di gestione flussi di lavoro di [!INCLUDE[dublin](../../../includes/dublin-md.md)]) deve essere aggiunto a questo ruolo del database.  
  
 [!INCLUDE[crabout](../../../includes/crabout-md.md)]sicurezza per gli archivi di persistenza con Windows Server AppFabric, vedere [configurazione della sicurezza per gli archivi di persistenza in AppFabric](http://go.microsoft.com/fwlink/?LinkId=201208)  
  
> [!CAUTION]
>  Un client con accesso ai dati dell'istanza nell'archivio di istanze dispone dell'accesso a tutte le altre istanze nello stesso archivio di istanze. L'archivio di istanze non supporta la specifica delle autorizzazioni della sicurezza a livello di istanza. È necessario creare archivi di istanze separati e mappare gruppi/utenti diversi per disporre dell'accesso ai diversi archivi.
