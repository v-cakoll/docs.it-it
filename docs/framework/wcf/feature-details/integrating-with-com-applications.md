---
title: Integrazione con applicazioni COM
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Communication Foundation, COM integration
- COM [WCF], Windows Communication Foundation integration
- WCF, reusing code
- Windows Communication Foundation, reusing code
- COM [WCF]
- WCF, COM integration
ms.assetid: c98bda3e-6779-419e-8e6d-9aa94053026d
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 130a7cda170721f34a5b44f3361bd591d6375267
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="integrating-with-com-applications"></a>Integrazione con applicazioni COM
I servizi [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] possono essere integrati direttamente nel codice esistente usando il moniker servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Il moniker servizio può essere usato da un'ampia gamma di ambienti di sviluppo basati su COM, ad esempio Office VBA, Visual Basic 6.0 o Visual C++ 6.0.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Panoramica dell'integrazione con applicazioni COM](../../../../docs/framework/wcf/feature-details/integrating-with-com-applications-overview.md)  
 Fornisce una panoramica delle parti principali del processo di integrazione.  
  
 [Procedura: Registrare e configurare un moniker servizio](../../../../docs/framework/wcf/feature-details/how-to-register-and-configure-a-service-moniker.md)  
 Per usare il moniker servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] all'interno di un'applicazione COM, registrare i tipi con attributi necessari con COM e configurare l'applicazione COM e il moniker con la configurazione dell'associazione necessaria.  
  
 [Procedura: Usare il moniker servizio di Windows Communication Foundation senza registrazione](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)  
 Illustra come ottenere la definizione del contratto in forma di documento WSDL (Web Services Definition Language) o da un endpoint WS-MetadataExchange.  
  
 [Procedura: usare un moniker servizio con contratti WSDL](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)  
 Descrive come chiamare un esempio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usando un moniker WSDL [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 [Procedura: Usare un moniker servizio con contratti per lo scambio di metadati](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-metadata-exchange-contracts.md)  
 Descrive come chiamare un esempio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usando un moniker [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] che specifica un endpoint MEX.  
  
 [Procedura: Specificare credenziali di sicurezza del canale](../../../../docs/framework/wcf/feature-details/how-to-specify-channel-security-credentials.md)  
 Il moniker servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] supporta l'interfaccia `IChannelCredentials` che consente un intervallo di metodi alternativi per la specifica di credenziali del canale.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.ServiceModel>  
  
## <a name="see-also"></a>Vedere anche  
 [Integrazione con applicazioni COM+](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
