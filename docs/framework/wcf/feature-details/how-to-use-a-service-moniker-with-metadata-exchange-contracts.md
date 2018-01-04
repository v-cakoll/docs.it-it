---
title: 'Procedura: usare un moniker di servizio con i contratti per lo scambio di metadati'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c41a07e5-cb9d-45d6-9ea4-34511e227faf
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7d2b5b6d4a671a3eb281f49dd60fd3c00ee76f8a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-a-service-moniker-with-metadata-exchange-contracts"></a>Procedura: usare un moniker di servizio con i contratti per lo scambio di metadati
Dopo aver sviluppato alcuni nuovi servizi [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], è possibile scegliere di chiamare questi servizi da uno script o da un'applicazione Visual Basic 6.0. Uno metodo per ottenere questo risultato consiste nel generare un assembly client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], registrare l'assembly con COM, installare l'assembly nella cache di assembly globale e quindi fare riferimento ai tipi COM dal codice Visual Basic. Quando si distribuisce l'applicazione, è necessario distribuire anche l'assembly client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. L'utente dovrà quindi registrare l'assembly client WCF con COM e posizionarlo nella cache di assembly globale. L'interoperabilità COM [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] consente anche di eseguire le stesse chiamate al servizio senza basarsi su un assembly client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Il moniker [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] consente di chiamare qualsiasi servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] da qualsiasi linguaggio compatibile con COM (Visual Basic, VBScript, Visual Basic, Applications Edition (VBA) e così via) specificando un URI dell'endpoint Mex (metadata exchange) che il moniker del servizio usa per estrarre informazioni sui tipi per il servizio. In questo argomento viene illustrato come chiamare l'esempio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] della Guida introduttiva usando un moniker [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] che specifica un endpoint Mex.  
  
> [!NOTE]
>  Non viene mai creata un'istanza dei tipi definiti dall'assembly client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] e l'assembly viene usato solo per i metadati.  
  
### <a name="using-the-service-moniker-with-a-mex-address"></a>Utilizzo del moniker del servizio con un indirizzo Mex  
  
1.  Creare l'esempio della Guida introduttiva e usare Internet Explorer per passare all'URL (http://localhost/ServiceModelSamples/Service.svc) per verificare che il servizio sia in funzione.  
  
2.  Creare uno script di Visual Basic o un'applicazione Visual Basic che contiene il codice seguente:  
  
    ```  
    monString = "service:mexaddress=http://localhost/ServiceModelSamples/Service.svc/MEX"  
    monString = monString + ", address=http://localhost/ServiceModelSamples/Service.svc"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
    Set calc = GetObject(monString)  
    MsgBox calc.Add(3, 4)  
    ```  
  
3.  Eseguire l'applicazione o lo script Visual Basic.  
  
    > [!NOTE]
    >  Il servizio che si sta chiamando deve esporre un endpoint Mex affinché il moniker sia in grado di leggere i metadati dal servizio. Per ulteriori informazioni, vedere [procedura: pubblicare metadati per un servizio utilizzando un File di configurazione](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).  
  
    > [!NOTE]
    >  Se il formato del moniker non è valido o se il servizio non è disponibile, la chiamata a `GetObject` restituirà un errore di sintassi non valida.  Se si riceve questo errore, verificare che il moniker che si sta usando sia valido e che il servizio sia disponibile.  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: Usare il moniker servizio di Windows Communication Foundation senza registrazione](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)  
 [Procedura: usare un moniker servizio con contratti WSDL](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)
