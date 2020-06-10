---
title: Scenari di sicurezza comuni
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF], scenarios
ms.assetid: 201923b5-5162-4a8a-8d4c-e7bd242748d5
ms.openlocfilehash: f36ebdb5ea248ec8134c688f89eb5d0be38dfe38
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84579736"
---
# <a name="common-security-scenarios"></a>Scenari di sicurezza comuni
Negli argomenti di questa sezione vengono illustrate alcune possibili configurazioni di sicurezza del client e del servizio. Le configurazioni dipendono da alcuni fattori. Variano, ad esempio, a seconda che un servizio o un client sia su una Intranet, o a seconda che la protezione sia fornita da Windows o da un trasporto, ad esempio HTTPS.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Client e servizio non protetti in Internet](internet-unsecured-client-and-service.md)  
 Esempio di un client e di un servizio pubblico non protetti.  
  
 [Client e servizio Intranet non protetti](intranet-unsecured-client-and-service.md)  
 Un servizio Basic Windows Communication Foundation (WCF) sviluppato per fornire informazioni su una rete privata protetta a un'applicazione WCF.  
  
 [Protezione del trasporto con l'autenticazione di base](transport-security-with-basic-authentication.md)  
 L'applicazione consente ai client di accedere utilizzando l'autenticazione personalizzata.  
  
 [Protezione del trasporto con l'autenticazione di Windows](transport-security-with-windows-authentication.md)  
 Vengono illustrati un client e un servizio protetti dalla protezione di Windows.  
  
 [Sicurezza del trasporto con un client anonimo](transport-security-with-an-anonymous-client.md)  
 In questo scenario viene utilizzata la protezione del trasporto, ad esempio HTTPS, per garantire riservatezza e integrità.  
  
 [Sicurezza del trasporto con autenticazione del certificato](transport-security-with-certificate-authentication.md)  
 Vengono illustrati un client e un servizio protetti da un certificato.  
  
 [Protezione dei messaggi con un client anonimo](message-security-with-an-anonymous-client.md)  
 Mostra un client e un servizio protetti dalla sicurezza dei messaggi WCF.  
  
 [Protezione dei messaggi tramite client con tipo di credenziale UserName](message-security-with-a-user-name-client.md)  
 Il client è un'applicazione Windows Form che consente ai client di accedere utilizzando un nome utente e una password del dominio.  
  
 [Protezione dei messaggi con un client di certificato](message-security-with-a-certificate-client.md)  
 I server hanno i certificati e ogni client ne ha uno. Un contesto di sicurezza viene stabilito tramite la negoziazione Transport Layer Security (TLS).  
  
 [Protezione dei messaggi con un client Windows](message-security-with-a-windows-client.md)  
 Variazione del client del certificato. I server hanno i certificati e ogni client ne ha uno. Un contesto di sicurezza viene stabilito tramite la negoziazione TLS.  
  
 [Sicurezza dei messaggi con un client Windows senza negoziazione delle credenziali](message-security-with-a-windows-client-without-credential-negotiation.md)  
 Vengono illustrati un client e un servizio protetti da un dominio Kerberos.  
  
 [Protezione dei messaggi con certificati reciproci](message-security-with-mutual-certificates.md)  
 I server hanno i certificati e ogni client ne ha uno. Il certificato server viene distribuito con l'applicazione ed è disponibile fuori banda.  
  
 [Protezione a livello di messaggio con il client token emessi](message-security-with-issued-tokens.md)  
 Protezione federata che consente di stabilire una relazione di trust tra domini indipendenti.  
  
 [Sottosistema attendibile](trusted-subsystem.md)  
 Un client accede a uno o più servizi Web distribuiti in una rete. I servizi Web accedono a risorse aggiuntive, ad esempio database o altri servizi Web, che devono essere protette.  
  
## <a name="reference"></a>Informazioni di riferimento  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Autorizzazione](authorization-in-wcf.md)  
  
 [Panoramica della sicurezza](security-overview.md)  
  
 [Sicurezza](security.md)  
  
 [Associazioni e protezione](bindings-and-security.md)  
  
 [Securing Services and Clients](securing-services-and-clients.md)  
  
 [autenticazione](authentication-in-wcf.md)  
  
 [Autorizzazione](authorization-in-wcf.md)  
  
 [Federazione e token emessi](federation-and-issued-tokens.md)  
  
 [Controllo](auditing-security-events.md)  
  
## <a name="see-also"></a>Vedere anche

- [Indicazioni di sicurezza e procedure consigliate](security-guidance-and-best-practices.md)
- [Sicurezza e protezione](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))
