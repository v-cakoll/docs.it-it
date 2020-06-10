---
title: "Procedura: distribuire un'applicazione di integrazione COM+"
ms.date: 03/30/2017
ms.assetid: 2e5a0510-db3c-4988-a09c-696285836650
ms.openlocfilehash: b4ae7f730296d54debc1cf2971b61e5700503430
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595427"
---
# <a name="how-to-deploy-a-com-integration-application"></a>Procedura: distribuire un'applicazione di integrazione COM+
Dopo aver scritto un'applicazione di integrazione COM+, è possibile distribuirla ad altri computer. In questo argomento viene illustrato come trasferire un'applicazione di integrazione COM+ da un computer a un altro.  
  
### <a name="moving-a-com-hosted-integration-app"></a>Trasferimento di un'applicazione di integrazione COM+ ospitata  
  
1. Assicurarsi che WCF sia installato in entrambi i computer.  
  
2. Esportare l'applicazione dal computer A.  
  
3. Importare l'applicazione nel computer B.  
  
4. Impostare la directory principale dell'applicazione. Per convenzione, è %PROGRAMFILES%/ComPlus Applications/{AppGUID}.  
  
5. Copiare i file Application.config e Application.manifest dalla directory principale dell'applicazione del computer A nella directory principale dell'applicazione del computer B.  
  
6. Modificare gli indirizzi endpoint del servizio nel file Application.config nel computer B per identificare il computer appropriato. Ad esempio, sostituire `http://machineA/MyService` con `http://machineB/MyService`.  
  
### <a name="moving-a-web-hosted-integration-application"></a>Trasferimento di un'applicazione di integrazione ospitata da Web  
  
1. Assicurarsi che WCF sia installato in entrambi i computer.  
  
2. Esportare l'applicazione dal computer A.  
  
3. Importare l'applicazione nel computer B.  
  
4. Creare una radice virtuale di IIS nel computer B.  
  
5. Copiare il file con estensione svc (componentName.svc) e il file Web.config dalla radice virtuale nel computer A nella radice virtuale appena creata nel computer B.  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica sull'integrazione con applicazioni COM+](integrating-with-com-plus-applications-overview.md)
- [Procedura: configurare le impostazioni del servizio COM+](how-to-configure-com-service-settings.md)
- [Procedura: usare lo strumento di configurazione del modello di servizi di COM+](how-to-use-the-com-service-model-configuration-tool.md)
