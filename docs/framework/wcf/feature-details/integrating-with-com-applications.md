---
title: Integrazione con applicazioni COM
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, COM integration
- COM [WCF], Windows Communication Foundation integration
- WCF, reusing code
- Windows Communication Foundation, reusing code
- COM [WCF]
- WCF, COM integration
ms.assetid: c98bda3e-6779-419e-8e6d-9aa94053026d
ms.openlocfilehash: 51626da6e97e346f43cfe606a5164024580a2ac7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59155324"
---
# <a name="integrating-with-com-applications"></a>Integrazione con applicazioni COM
Servizi Windows Communication Foundation (WCF) possono essere integrati direttamente nel codice esistente usando il moniker del servizio WCF. Il moniker servizio può essere usato da un'ampia gamma di ambienti di sviluppo basati su COM, ad esempio Office VBA, Visual Basic 6.0 o Visual C++ 6.0.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Panoramica sull'integrazione con applicazioni COM](../../../../docs/framework/wcf/feature-details/integrating-with-com-applications-overview.md)  
 Fornisce una panoramica delle parti principali del processo di integrazione.  
  
 [Procedura: Registrare e configurare un moniker del servizio](../../../../docs/framework/wcf/feature-details/how-to-register-and-configure-a-service-moniker.md)  
 Per usare il moniker del servizio WCF all'interno di un'applicazione COM, registrare i tipi con attributi necessari con COM e configurare l'applicazione COM e il moniker con la configurazione dell'associazione necessaria.  
  
 [Procedura: Usare il moniker del servizio di Windows Communication Foundation senza registrazione](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)  
 Illustra come ottenere la definizione del contratto in forma di documento WSDL (Web Services Definition Language) o da un endpoint WS-MetadataExchange.  
  
 [Procedura: Usare un moniker del servizio con i contratti WSDL](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)  
 Viene descritto come chiamare un esempio WCF usando un moniker WSDL WCF.  
  
 [Procedura: Usare un moniker del servizio con i contratti di scambio di metadati](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-metadata-exchange-contracts.md)  
 Viene descritto come chiamare un esempio WCF usando un moniker WCF che specifica un endpoint Mex.  
  
 [Procedura: Specificare credenziali di sicurezza del canale](../../../../docs/framework/wcf/feature-details/how-to-specify-channel-security-credentials.md)  
 Il moniker del servizio WCF supporta i `IChannelCredentials` interfaccia che consente un intervallo di metodi alternativi per specificare le credenziali del canale.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.ServiceModel>  
  
## <a name="see-also"></a>Vedere anche

- [Integrazione con applicazioni COM+](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
