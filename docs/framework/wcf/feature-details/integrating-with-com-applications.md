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
ms.openlocfilehash: dc3bbe0ee72ca5583b1e52a61c914ad866a22a05
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596810"
---
# <a name="integrating-with-com-applications"></a>Integrazione con applicazioni COM
I servizi Windows Communication Foundation (WCF) possono essere integrati direttamente nel codice esistente usando il moniker del servizio WCF. Il moniker servizio può essere usato da un'ampia gamma di ambienti di sviluppo basati su COM, ad esempio Office VBA, Visual Basic 6.0 o Visual C++ 6.0.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Panoramica dell'integrazione con applicazioni COM](integrating-with-com-applications-overview.md)  
 Fornisce una panoramica delle parti principali del processo di integrazione.  
  
 [Procedura: registrare e configurare un moniker servizio](how-to-register-and-configure-a-service-moniker.md)  
 Per utilizzare il moniker del servizio WCF all'interno di un'applicazione COM, registrare i tipi con attributi necessari con COM e configurare l'applicazione COM e il moniker con la configurazione dell'associazione necessaria.  
  
 [Procedura: usare il moniker servizio di Windows Communication Foundation senza registrazione](use-the-wcf-service-moniker-without-registration.md)  
 Illustra come ottenere la definizione del contratto in forma di documento WSDL (Web Services Definition Language) o da un endpoint WS-MetadataExchange.  
  
 [Procedura: usare un moniker di servizio con i contratti WSDL](how-to-use-a-service-moniker-with-wsdl-contracts.md)  
 Viene descritto come chiamare un esempio WCF utilizzando un moniker WSDL WCF.  
  
 [Procedura: usare un moniker di servizio con i contratti per lo scambio di metadati](how-to-use-a-service-moniker-with-metadata-exchange-contracts.md)  
 Viene descritto come chiamare un esempio WCF utilizzando un moniker WCF che specifica un endpoint MEX.  
  
 [Procedura: specificare credenziali di sicurezza del canale](how-to-specify-channel-security-credentials.md)  
 Il moniker del servizio WCF supporta l' `IChannelCredentials` interfaccia che consente un intervallo di metodi alternativi per specificare le credenziali del canale.  
  
## <a name="reference"></a>Informazioni di riferimento  
 <xref:System.ServiceModel>  
  
## <a name="see-also"></a>Vedere anche

- [Integrazione con applicazioni COM+](integrating-with-com-plus-applications.md)
