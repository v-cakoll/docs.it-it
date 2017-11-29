---
title: 'Procedura: distribuire un''applicazione di integrazione COM+'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2e5a0510-db3c-4988-a09c-696285836650
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7d6d9103c2d36de81392858fedc249be9f7ae94f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-deploy-a-com-integration-application"></a>Procedura: distribuire un'applicazione di integrazione COM+
Dopo aver scritto un'applicazione di integrazione COM+, è possibile distribuirla ad altri computer. In questo argomento viene illustrato come trasferire un'applicazione di integrazione COM+ da un computer a un altro.  
  
### <a name="moving-a-com-hosted-integration-app"></a>Trasferimento di un'applicazione di integrazione COM+ ospitata  
  
1.  Assicurarsi che [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sia installato su entrambi i computer.  
  
2.  Esportare l'applicazione dal computer A.  
  
3.  Importare l'applicazione nel computer B.  
  
4.  Impostare la directory principale dell'applicazione. Per convenzione, è %PROGRAMFILES%/ComPlus Applications/{AppGUID}.  
  
5.  Copiare i file Application.config e Application.manifest dalla directory principale dell'applicazione del computer A nella directory principale dell'applicazione del computer B.  
  
6.  Modificare gli indirizzi endpoint del servizio nel file Application.config nel computer B per identificare il computer appropriato. Cambiare, ad esempio, http://machineA/MyService in http://machineB/MyService.  
  
### <a name="moving-a-web-hosted-integration-application"></a>Trasferimento di un'applicazione di integrazione ospitata da Web  
  
1.  Assicurarsi che [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sia installato su entrambi i computer.  
  
2.  Esportare l'applicazione dal computer A.  
  
3.  Importare l'applicazione nel computer B.  
  
4.  Creare una radice virtuale di IIS nel computer B.  
  
5.  Copiare il file con estensione svc (componentName.svc) e il file Web.config dalla radice virtuale nel computer A nella radice virtuale appena creata nel computer B.  
  
## <a name="see-also"></a>Vedere anche  
 [L'integrazione con panoramica delle applicazioni COM+](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications-overview.md)  
 [Procedura: configurare le impostazioni di servizio COM+](../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)  
 [Procedura: utilizzare lo strumento di configurazione del modello di servizio COM+](../../../../docs/framework/wcf/feature-details/how-to-use-the-com-service-model-configuration-tool.md)
