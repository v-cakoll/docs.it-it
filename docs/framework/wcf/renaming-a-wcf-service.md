---
title: Ridenominazione di un servizio WCF
ms.date: 03/30/2017
ms.assetid: 14235a65-b1c5-409d-b6cc-a979acd54bbd
ms.openlocfilehash: a215523b92757e3bde1dae2e50de22169020e870
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61955142"
---
# <a name="renaming-a-wcf-service"></a>Ridenominazione di un servizio WCF
In questo argomento viene descritto come ridenominare un servizio Windows Communication Foundation (WCF).  
  
## <a name="renaming-a-wcf-service"></a>Ridenominazione di un servizio WCF  
 Eseguire la procedura seguente per rinominare un servizio in un modello di Windows Communication Foundation (WCF)  
  
- Modificare il nome della classe che implementa il servizio.  
  
- Nel file di configurazione del servizio, impostare il nome del servizio sul nuovo nome scelto, come indicato nell'esempio seguente. A seconda del modello di hosting utilizzato, il file di configurazione può essere app.config oppure web.config.  
  
```xml  
<system.servicemodel>  
   <services>  
      <service name="WcfService.NewName">  
      </service>  
   </services>  
</system.servicemodel>  
```  
  
- Se il servizio è WebHosted, utilizza un file *.svc. Aprire questo file e modificare il nome del servizio, come indicato nell'esempio seguente. Questo passaggio non è necessario per le applicazioni indipendenti, in quanto questo tipo di applicazione non prevede alcun file con estensione svc.  
  
```  
<%@ ServiceHost Service="WcfService.NewName">  
```  
  
## <a name="renaming-a-wcf-service-contract"></a>Ridenominazione del contratto di un servizio WCF  
  
- Per ridenominare il contratto di servizio, attenersi ai passaggi seguenti:  
  
- Modificare il nome del contratto di servizio.  
  
- Nel file di configurazione del servizio, impostare il nome del contratto di servizio sul nuovo nome scelto, come indicato nell'esempio seguente. A seconda del modello di hosting utilizzato, il file di configurazione può essere app.config oppure web.config.  
  
```xml  
<system.servicemodel>  
   <services>  
      <service>  
         <endpoint contract="WcfService.NewContractName" />  
      </service>  
   </services>  
</system.servicemodel>  
```
