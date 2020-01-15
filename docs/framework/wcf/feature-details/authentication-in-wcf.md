---
title: Autenticazione in WCF
ms.date: 03/30/2017
helpviewer_keywords:
- authentication [WCF]
- security [WCF], authentication
ms.assetid: 9254d873-843d-4c6e-bea4-8184ac3e44f4
ms.openlocfilehash: abe7aff025207ad8bdf8657daba3584e6a1b2e7f
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964701"
---
# <a name="authentication-in-wcf"></a>Autenticazione in WCF
Negli argomenti seguenti vengono illustrati diversi meccanismi di Windows Communication Foundation (WCF) che forniscono l'autenticazione, ad esempio autenticazione di Windows, certificati X. 509 e nome utente e password.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Procedura: Usare provider di appartenenza ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)  
 Le funzionalità ASP.NET comprendono un provider di appartenenze e ruoli, un database in cui archiviare coppie di nome utente e password per l'autenticazione e ruoli utente per l'autorizzazione. In questo argomento viene illustrato il modo in cui i servizi WCF possono utilizzare lo stesso database per autenticare e autorizzare gli utenti.  
  
 [Procedura: Usare un validator di nome utente e password personalizzato](../../../../docs/framework/wcf/feature-details/how-to-use-a-custom-user-name-and-password-validator.md)  
 Viene dimostrato come integrare un validator di nome utente e password personalizzato  
  
 [Identità del servizio e autenticazione](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 Come ulteriore sicurezza, un client può autenticare il servizio specificando l' *identità* prevista del servizio. Se l'identità prevista e l'identità restituita dal servizio non corrispondono, si verifica l'errore di autenticazione.  
  
 [Negoziazione di sicurezza e timeout](../../../../docs/framework/wcf/feature-details/security-negotiation-and-timeouts.md)  
 Viene descritto l'utilizzo della proprietà <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> nella classe <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>.  
  
 [Debug degli errori di autenticazione di Windows](../../../../docs/framework/wcf/feature-details/debugging-windows-authentication-errors.md)  
 Vengono analizzati problemi comuni riscontrabili durante l'autenticazione di Windows.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Scenari di sicurezza comuni](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica della sicurezza](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [Modello di sicurezza per Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))
