---
title: Aggiunta di un riferimento al servizio in una soluzione del flusso di lavoro
ms.date: 03/30/2017
ms.assetid: 83574cf3-9803-49bc-837f-432936dc9c76
ms.openlocfilehash: 577026249e00b528cf5c6e7ccd9527e02cb22a28
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597670"
---
# <a name="add-a-service-reference-in-a-workflow-solution"></a>Aggiungere un riferimento al servizio in una soluzione del flusso di lavoro

L'aggiunta di un riferimento al servizio in un'applicazione flusso di lavoro è leggermente differente da quella in un'applicazione WCF normale. Quando si seleziona **Aggiungi**  >  **riferimento al servizio** e si specifica l'URL del servizio, i metadati vengono scaricati e vengono generate attività personalizzate che consentono di chiamare il servizio WCF o il servizio del flusso di lavoro WCF. Dopo avere aggiunto un riferimento al servizio, ricompilare la soluzione per compilare le attività generate che verranno visualizzate nella casella degli strumenti di Progettazione flussi di lavoro. Questa operazione funzionerà solo se si aggiunge un riferimento al servizio all'interno di una soluzione del flusso di lavoro. Nel cast Web seguente viene illustrato come aggiungere un riferimento al servizio in altri tipi di progetti: [chiamata di un servizio WCF da un flusso di lavoro in un progetto Web](https://docs.microsoft.com/archive/blogs/endpoint/how-to-consume-a-wcf-service-from-a-wf4-workflow).

L'aggiunta di due o più riferimenti ai servizi contenenti lo stesso nome di operazione causa un problema. Le attività generate chiameranno solo la prima operazione del servizio. Per risolvere questo problema, rinominare le operazioni del servizio in modo che siano diverse oppure modificare il nome della configurazione dell'endpoint all'interno di ogni attività generata.

## <a name="see-also"></a>Vedere anche

- [Servizi flusso di lavoro](workflow-services.md)
- [Chiamata di un servizio WCF da un flusso di lavoro in un progetto Web](https://docs.microsoft.com/archive/blogs/endpoint/how-to-consume-a-wcf-service-from-a-wf4-workflow)
