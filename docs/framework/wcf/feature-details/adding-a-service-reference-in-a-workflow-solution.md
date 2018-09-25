---
title: Aggiunta di un riferimento al servizio in una soluzione del flusso di lavoro
ms.date: 03/30/2017
ms.assetid: 83574cf3-9803-49bc-837f-432936dc9c76
ms.openlocfilehash: 9dcbf779d948f6d295c2a23f5a09efc5ac989cdd
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47082864"
---
# <a name="adding-a-service-reference-in-a-workflow-solution"></a>Aggiunta di un riferimento al servizio in una soluzione del flusso di lavoro

L'aggiunta di un riferimento al servizio in un'applicazione flusso di lavoro è leggermente differente da quella in un'applicazione WCF normale. Quando si seleziona **Add > riferimento al servizio** e specificare l'URL del servizio, i metadati vengono scaricati e vengono generate attività personalizzate che consentono di richiamare il servizio WCF o è stato aggiunto un riferimento al servizio di flusso di lavoro WCF. Dopo avere aggiunto un riferimento al servizio, ricompilare la soluzione per compilare le attività generate che verranno visualizzate nella casella degli strumenti di Progettazione flussi di lavoro. Notare tuttavia che l'operazione viene eseguita solo se si aggiunge un riferimento al servizio all'interno di una soluzione del flusso di lavoro. Nel cast web seguente viene illustrato come aggiungere un riferimento al servizio in altri tipi di progetti: [chiama un servizio WCF da un flusso di lavoro in un progetto Web](https://go.microsoft.com/fwlink/?LinkId=207725).

L'aggiunta di due o più riferimenti ai servizi contenenti lo stesso nome di operazione causa un problema. Le attività generate chiameranno solo la prima operazione del servizio. Per ovviare a questo problema rinominare le operazioni del servizio in modo da renderle diverse o modificano il nome di configurazione dell'endpoint all'interno di ogni attività generata.

## <a name="see-also"></a>Vedere anche

- [Servizi flusso di lavoro](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [Procedura: Creare un servizio flusso di lavoro che chiama un altro servizio flusso di lavoro](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-that-calls-another-workflow-service.md)
- [Chiama un servizio WCF da un flusso di lavoro in un progetto Web](https://go.microsoft.com/fwlink/?LinkId=207725)
