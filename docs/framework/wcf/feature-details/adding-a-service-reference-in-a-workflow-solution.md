---
title: Aggiunta di un riferimento al servizio in una soluzione del flusso di lavoro
ms.date: 03/30/2017
ms.assetid: 83574cf3-9803-49bc-837f-432936dc9c76
ms.openlocfilehash: 7197ae991207efd60ea398794c7c23f427f6b0cc
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964221"
---
# <a name="adding-a-service-reference-in-a-workflow-solution"></a>Aggiunta di un riferimento al servizio in una soluzione del flusso di lavoro

L'aggiunta di un riferimento al servizio in un'applicazione flusso di lavoro è leggermente differente da quella in un'applicazione WCF normale. Quando si seleziona **aggiungi > riferimento al servizio** e si specifica l'URL del servizio, i metadati vengono scaricati e vengono generate attività personalizzate che consentono di chiamare il servizio WCF o il servizio del flusso di lavoro WCF a cui è stato aggiunto un riferimento. Dopo avere aggiunto un riferimento al servizio, ricompilare la soluzione per compilare le attività generate che verranno visualizzate nella casella degli strumenti di Progettazione flussi di lavoro. Notare tuttavia che l'operazione viene eseguita solo se si aggiunge un riferimento al servizio all'interno di una soluzione del flusso di lavoro. Nel cast Web seguente viene illustrato come aggiungere un riferimento al servizio in altri tipi di progetti: [chiamata di un servizio WCF da un flusso di lavoro in un progetto Web](https://docs.microsoft.com/archive/blogs/endpoint/how-to-consume-a-wcf-service-from-a-wf4-workflow).

L'aggiunta di due o più riferimenti ai servizi contenenti lo stesso nome di operazione causa un problema. Le attività generate chiameranno solo la prima operazione del servizio. Per ovviare a questo problema rinominare le operazioni del servizio in modo da renderle diverse o modificano il nome di configurazione dell'endpoint all'interno di ogni attività generata.

## <a name="see-also"></a>Vedere anche

- [Servizi flusso di lavoro](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [Chiamata di un servizio WCF da un flusso di lavoro in un progetto Web](https://docs.microsoft.com/archive/blogs/endpoint/how-to-consume-a-wcf-service-from-a-wf4-workflow)
