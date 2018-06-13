---
title: Sicurezza
ms.date: 03/30/2017
ms.assetid: 737ec121-bfc5-4b75-a504-2d53c2c8af39
ms.openlocfilehash: b8fd870bcd14b8a80861914448f75fafe6af2863
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33518017"
---
# <a name="security"></a>Sicurezza
Nell'archivio di istanze del flusso di lavoro SQL vengono usati i seguenti ruoli di sicurezza del database, per un accesso protetto alle informazioni sullo stato dell'istanza nel database di persistenza.  
  
-   **Instancestoreusers**. Questo ruolo dispone di autorizzazioni di accesso in lettura e scrittura a visualizzazioni pubbliche e diritti di esecuzione di stored procedure coinvolte in operazioni di creazione, caricamento e salvataggio di istanze.  
  
-   **System.Activities.DurableInstancing.InstanceStoreObservers**. Questo ruolo dispone di accesso in sola lettura alle visualizzazioni pubbliche.  
  
-   **System.Activities.DurableInstancing.WorkflowActivationUsers**. Questo ruolo dispone di diritti di esecuzione per stored procedure incluse nel processo di attivazione delle istanze. Per ulteriori informazioni sull'attivazione di istanze, vedere [attivazione di istanze](../../../docs/framework/windows-workflow-foundation/instance-activation.md). L'account utente con il quale viene eseguito un host generico (ad esempio il Servizio di gestione flussi di lavoro di [!INCLUDE[dublin](../../../includes/dublin-md.md)]) deve essere aggiunto a questo ruolo del database.  
  
 Per ulteriori informazioni sulla sicurezza per gli archivi di persistenza con Windows Server AppFabric, vedere [configurazione della sicurezza per gli archivi di persistenza in AppFabric](http://go.microsoft.com/fwlink/?LinkId=201208)  
  
> [!CAUTION]
>  Un client con accesso ai dati dell'istanza nell'archivio di istanze dispone dell'accesso a tutte le altre istanze nello stesso archivio di istanze. L'archivio di istanze non supporta la specifica delle autorizzazioni della sicurezza a livello di istanza. È necessario creare archivi di istanze separati e mappare gruppi/utenti diversi per disporre dell'accesso ai diversi archivi.
