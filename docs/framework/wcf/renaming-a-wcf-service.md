---
title: Ridenominazione di un servizio WCF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14235a65-b1c5-409d-b6cc-a979acd54bbd
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f2ab3d780f85131fc7adf24c5f420bd5fe643d9e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="renaming-a-wcf-service"></a>Ridenominazione di un servizio WCF
In questo argomento viene illustrato come ridenominare un servizio [!INCLUDE[indigo1](../../../includes/indigo1-md.md)].  
  
## <a name="renaming-a-wcf-service"></a>Ridenominazione di un servizio WCF  
 Per ridenominare un servizio di un modello di [!INCLUDE[indigo1](../../../includes/indigo1-md.md)], eseguire i passaggi seguenti.  
  
-   Modificare il nome della classe che implementa il servizio.  
  
-   Nel file di configurazione del servizio, impostare il nome del servizio sul nuovo nome scelto, come indicato nell'esempio seguente. A seconda del modello di hosting utilizzato, il file di configurazione può essere app.config oppure web.config.  
  
```xml  
<system.servicemodel>  
   <services>  
      <service name="WcfService.NewName">  
      </service>  
   </services>  
</system.servicemodel>  
```  
  
-   Se il servizio è WebHosted, utilizza un file *.svc. Aprire questo file e modificare il nome del servizio, come indicato nell'esempio seguente. Questo passaggio non è necessario per le applicazioni indipendenti, in quanto questo tipo di applicazione non prevede alcun file con estensione svc.  
  
```  
<%@ ServiceHost Service="WcfService.NewName">  
```  
  
## <a name="renaming-a-wcf-service-contract"></a>Ridenominazione del contratto di un servizio WCF  
  
-   Per ridenominare il contratto di servizio, attenersi ai passaggi seguenti:  
  
-   Modificare il nome del contratto di servizio.  
  
-   Nel file di configurazione del servizio, impostare il nome del contratto di servizio sul nuovo nome scelto, come indicato nell'esempio seguente. A seconda del modello di hosting utilizzato, il file di configurazione può essere app.config oppure web.config.  
  
```xml  
<system.servicemodel>  
   <services>  
      <service>  
         <endpoint contract="WcfService.NewContractName" />  
      </service>  
   </services>  
</system.servicemodel>  
```
