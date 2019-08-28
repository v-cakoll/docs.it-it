---
title: Opzioni di hosting di flussi di lavoro
ms.date: 03/30/2017
ms.assetid: 37bcd668-9c5c-4e7c-81da-a1f1b3a16514
ms.openlocfilehash: 4eaed147f312f3963aa1ca1d4f5dbe010c4189ad
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "70037829"
---
# <a name="workflow-hosting-options"></a>Opzioni di hosting di flussi di lavoro
La maggior parte degli esempi di Windows Workflow Foundation (WF) utilizzano i flussi di lavoro ospitati in un'applicazione console, ma questo non è uno scenario realistico per i flussi di lavoro reali. I flussi di lavoro nelle applicazioni aziendali effettive saranno ospitati in processi permanenti, ovvero un servizio Windows creato dallo sviluppatore o un'applicazione server come IIS 7,0 o AppFabric. Di seguito sono riportate le differenze tra questi approcci.

## <a name="hosting-workflows-in-iis-with-windows-appfabric"></a>Hosting di flussi di lavoro in IIS con Windows AppFabric

IIS con AppFabric è l'host preferito per i flussi di lavoro. L'applicazione host per i flussi di lavoro che usano AppFabric è Windows Activation Service che rimuove la dipendenza di HTTP su IIS indipendente.

## <a name="hosting-workflows-in-iis-alone"></a>Hosting di flussi di lavoro in IIS indipendente

L'utilizzo di IIS 7,0 da solo non è consigliato, in quanto sono disponibili strumenti di gestione e monitoraggio con AppFabric che facilitano la manutenzione delle applicazioni in esecuzione. I flussi di lavoro devono essere ospitati solo in IIS 7,0 solo se si verificano problemi di infrastruttura con il passaggio a AppFabric.

> [!WARNING]
> IIS 7,0 ricicla periodicamente i pool di applicazioni per vari motivi. Quando un pool di applicazioni viene riciclato, IIS smette di accettare i messaggi del pool precedente e crea un'istanza di un nuovo pool di applicazioni per accettare le nuove richieste. Se un flusso di lavoro continua a funzionare dopo l'invio di una risposta, IIS 7,0 non sarà in grado di riconoscere il lavoro svolto e potrebbe riciclare il pool di applicazioni host. In tal caso, il flusso di lavoro verrà interrotto e i servizi di rilevamento registreranno un messaggio [1004-WorkflowInstanceAborted](1004-workflowinstanceaborted.md) con un campo motivo vuoto.
>
> Se si usa la persistenza, l'host deve esplicitamente riavviare le istanze arrestate dall'ultimo punto di persistenza.
>
> Se si usa AppFabric, il servizio di gestione del flusso di lavoro eventualmente riprenderà il flusso di lavoro dall'ultimo il punto di persistenza riuscito se si usa la persistenza. Se la persistenza non viene usata e il flusso di lavoro esegue operazioni all'esterno di un modello di risposta-richiesta, i dati verranno persi quando il flusso di lavoro viene interrotto.

## <a name="hosting-a-workflow-in-a-custom-windows-service"></a>Hosting di un flusso di lavoro in un servizio Windows personalizzato

La creazione di un servizio personalizzato di flusso di lavoro per ospitare il flusso di lavoro richiede allo sviluppatore di duplicare molte funzionalità fornite in modo predefinito da AppFabric, ma consente maggiore flessibilità con le funzionalità personalizzate. Da tenere in considerazione solo se AppFabric dimostra di non essere un'opzione.
