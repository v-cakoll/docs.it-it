---
title: Scenari di sicurezza comuni
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: security [WCF], scenarios
ms.assetid: 201923b5-5162-4a8a-8d4c-e7bd242748d5
caps.latest.revision: "18"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 9428c5d7c8c6cf0f571b05a8b9c33b96d073d7a5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="common-security-scenarios"></a>Scenari di sicurezza comuni
Negli argomenti di questa sezione vengono illustrate alcune possibili configurazioni di sicurezza del client e del servizio. Le configurazioni dipendono da alcuni fattori. Variano, ad esempio, a seconda che un servizio o un client sia su una Intranet, o a seconda che la protezione sia fornita da Windows o da un trasporto, ad esempio HTTPS.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Servizio e il Client non protetta di Internet](../../../../docs/framework/wcf/feature-details/internet-unsecured-client-and-service.md)  
 Esempio di un client e di un servizio pubblico non protetti.  
  
 [Servizio intranet Client e non protetti](../../../../docs/framework/wcf/feature-details/intranet-unsecured-client-and-service.md)  
 Un servizio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] di base sviluppato per fornire informazioni su una rete privata protetta a un'applicazione [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 [Sicurezza del trasporto con l'autenticazione di base](../../../../docs/framework/wcf/feature-details/transport-security-with-basic-authentication.md)  
 L'applicazione consente ai client di accedere utilizzando l'autenticazione personalizzata.  
  
 [Sicurezza del trasporto con l'autenticazione di Windows](../../../../docs/framework/wcf/feature-details/transport-security-with-windows-authentication.md)  
 Vengono illustrati un client e un servizio protetti dalla protezione di Windows.  
  
 [Sicurezza del trasporto con un Client anonimo](../../../../docs/framework/wcf/feature-details/transport-security-with-an-anonymous-client.md)  
 In questo scenario viene utilizzata la protezione del trasporto, ad esempio HTTPS, per garantire riservatezza e integrità.  
  
 [Sicurezza del trasporto con l'autenticazione del certificato](../../../../docs/framework/wcf/feature-details/transport-security-with-certificate-authentication.md)  
 Vengono illustrati un client e un servizio protetti da un certificato.  
  
 [Sicurezza dei messaggi con un Client anonimo](../../../../docs/framework/wcf/feature-details/message-security-with-an-anonymous-client.md)  
 Vengono illustrati un client e un servizio protetti dalla protezione dei messaggi di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 [Sicurezza dei messaggi con un Client di nome utente](../../../../docs/framework/wcf/feature-details/message-security-with-a-user-name-client.md)  
 Il client è un'applicazione Windows Forms che consente ai client di accedere utilizzando un nome utente e una password del dominio.  
  
 [Sicurezza dei messaggi con un Client dei certificati](../../../../docs/framework/wcf/feature-details/message-security-with-a-certificate-client.md)  
 I server hanno i certificati e ogni client ne ha uno. Un contesto di sicurezza viene stabilito tramite la negoziazione Transport Layer Security (TLS).  
  
 [Sicurezza dei messaggi con un Client Windows](../../../../docs/framework/wcf/feature-details/message-security-with-a-windows-client.md)  
 Variazione del client del certificato. I server hanno i certificati e ogni client ne ha uno. Un contesto di sicurezza viene stabilito tramite la negoziazione TLS.  
  
 [Sicurezza dei messaggi con un Client di Windows senza negoziazione delle credenziali](../../../../docs/framework/wcf/feature-details/message-security-with-a-windows-client-without-credential-negotiation.md)  
 Vengono illustrati un client e un servizio protetti da un dominio Kerberos.  
  
 [Sicurezza dei messaggi con certificati reciproci](../../../../docs/framework/wcf/feature-details/message-security-with-mutual-certificates.md)  
 I server hanno i certificati e ogni client ne ha uno. Il certificato server viene distribuito con l'applicazione ed è disponibile fuori banda.  
  
 [Sicurezza dei messaggi con i token emessi](../../../../docs/framework/wcf/feature-details/message-security-with-issued-tokens.md)  
 Protezione federata che consente di stabilire una relazione di trust tra domini indipendenti.  
  
 [Sottosistema attendibile](../../../../docs/framework/wcf/feature-details/trusted-subsystem.md)  
 Un client accede a uno o più servizi Web distribuiti in una rete. I servizi Web accedono a risorse aggiuntive, ad esempio database o altri servizi Web, che devono essere protette.  
  
## <a name="reference"></a>Riferimento  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Autorizzazione](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
 [Cenni preliminari sulla sicurezza](../../../../docs/framework/wcf/feature-details/security-overview.md)  
  
 [Sicurezza](../../../../docs/framework/wcf/feature-details/security.md)  
  
 [Associazioni e protezione](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
  
 [Protezione di servizi e client](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
  
 [Autenticazione](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
 [Autorizzazione](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
 [Federazione e token emessi](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
  
 [Il controllo](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)  
  
## <a name="see-also"></a>Vedere anche  
 [Guida alla protezione e le procedure consigliate](../../../../docs/framework/wcf/feature-details/security-guidance-and-best-practices.md)  
 [Modello di sicurezza per Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
