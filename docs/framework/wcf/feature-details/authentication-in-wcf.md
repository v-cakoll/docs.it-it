---
title: Autenticazione in WCF
description: Informazioni sui diversi meccanismi in WCF che forniscono l'autenticazione, ad esempio l'autenticazione di Windows, i certificati X. 509 e il nome utente e la password.
ms.date: 03/30/2017
helpviewer_keywords:
- authentication [WCF]
- security [WCF], authentication
ms.assetid: 9254d873-843d-4c6e-bea4-8184ac3e44f4
ms.openlocfilehash: 4c3348cfb84b8571dc1f24b774ffcd691aaa5001
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247520"
---
# <a name="authentication-in-wcf"></a>Autenticazione in WCF
Negli argomenti seguenti vengono illustrati diversi meccanismi di Windows Communication Foundation (WCF) che forniscono l'autenticazione, ad esempio autenticazione di Windows, certificati X. 509 e nome utente e password.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Procedura: usare provider di appartenenza ASP.NET](how-to-use-the-aspnet-membership-provider.md)  
 Le funzionalità ASP.NET comprendono un provider di appartenenze e ruoli, un database in cui archiviare coppie di nome utente e password per l'autenticazione e ruoli utente per l'autorizzazione. In questo argomento viene illustrato il modo in cui i servizi WCF possono utilizzare lo stesso database per autenticare e autorizzare gli utenti.  
  
 [Procedura: usare un validator di nome utente e password personalizzato](how-to-use-a-custom-user-name-and-password-validator.md)  
 Viene dimostrato come integrare un validator di nome utente e password personalizzato  
  
 [Identità del servizio e autenticazione](service-identity-and-authentication.md)  
 Come ulteriore sicurezza, un client può autenticare il servizio specificando l' *identità* prevista del servizio. Se l'identità prevista e l'identità restituita dal servizio non corrispondono, si verifica l'errore di autenticazione.  
  
 [Negoziazione di sicurezza e timeout](security-negotiation-and-timeouts.md)  
 Viene descritto l'utilizzo della proprietà <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> nella classe <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>.  
  
 [Debug degli errori di autenticazione di Windows](debugging-windows-authentication-errors.md)  
 Vengono analizzati problemi comuni riscontrabili durante l'autenticazione di Windows.  
  
## <a name="reference"></a>Informazioni di riferimento  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Scenari di sicurezza comuni](common-security-scenarios.md)  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica della sicurezza](security-overview.md)
- [Sicurezza e protezione](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))
