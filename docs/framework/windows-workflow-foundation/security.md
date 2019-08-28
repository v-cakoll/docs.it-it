---
title: Security
ms.date: 03/30/2017
ms.assetid: 737ec121-bfc5-4b75-a504-2d53c2c8af39
ms.openlocfilehash: f47b75fa1fd345869f560326861ebc31e6b5e1a9
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "70045318"
---
# <a name="security"></a>Security
Nell'archivio di istanze del flusso di lavoro SQL vengono usati i seguenti ruoli di sicurezza del database, per un accesso protetto alle informazioni sullo stato dell'istanza nel database di persistenza.  
  
- **System.Activities.DurableInstancing.InstanceStoreUsers**. Questo ruolo dispone di autorizzazioni di accesso in lettura e scrittura a visualizzazioni pubbliche e diritti di esecuzione di stored procedure coinvolte in operazioni di creazione, caricamento e salvataggio di istanze.  
  
- **System.Activities.DurableInstancing.InstanceStoreObservers**. Questo ruolo dispone di accesso in sola lettura alle visualizzazioni pubbliche.  
  
- **System.Activities.DurableInstancing.WorkflowActivationUsers**. Questo ruolo dispone di diritti di esecuzione per stored procedure incluse nel processo di attivazione delle istanze. Per ulteriori informazioni sull'attivazione dell'istanza, vedere [attivazione dell'istanza](instance-activation.md). L'account utente con cui viene eseguito un host generico, ad esempio il servizio di gestione del flusso di lavoro delle funzionalità di hosting di Windows Server AppFabric, deve essere aggiunto a questo ruolo del database.  
  
 Per altre informazioni sulla sicurezza per gli archivi di persistenza con Windows Server AppFabric, vedere [configurazione della sicurezza per gli archivi di persistenza in App Fabric](https://go.microsoft.com/fwlink/?LinkId=201208)  
  
> [!CAUTION]
> Un client con accesso ai dati dell'istanza nell'archivio di istanze dispone dell'accesso a tutte le altre istanze nello stesso archivio di istanze. L'archivio di istanze non supporta la specifica delle autorizzazioni della sicurezza a livello di istanza. È necessario creare archivi di istanze separati e mappare gruppi/utenti diversi per disporre dell'accesso ai diversi archivi.
