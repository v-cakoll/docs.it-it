---
title: Federazione e attendibilità
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- federation [WCF], and trust
ms.assetid: 4bdec4f2-f8a2-4512-bdcf-14ef54b5877a
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8ccd395f96f3e7af0ce7afe9938c0295d5778914
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2018
---
# <a name="federation-and-trust"></a>Federazione e attendibilità
In questo argomento vengono analizzati i vari aspetti relativi ad applicazioni federate, limiti e configurazione dell'attendibilità e utilizzo di token emessi in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].  
  
## <a name="services-security-token-services-and-trust"></a>Servizi, servizi token di sicurezza e attendibilità  
 I servizi che espongono endpoint federati in genere prevedono che i client siano autenticati utilizzando un token fornito da un emittente specifico. È importante che il servizio sia configurato con le credenziali corrette per l'emittente. In caso contrario, non sarà in grado di verificare le firme sui token emessi e il client non sarà in grado di comunicare con il servizio. Per ulteriori informazioni sulla configurazione delle credenziali dell'autorità di certificazione nel servizio, vedere [procedura: configurare le credenziali in un servizio federativo](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).  
  
 In modo analogo, quando si utilizzano chiavi simmetriche, queste vengono crittografate per il servizio di destinazione, è pertanto necessario configurare il servizio token di sicurezza con le credenziali corrette per il servizio di destinazione. In caso contrario, non sarà in grado di crittografare la chiave per il servizio di destinazione e il client non sarà in grado di comunicare con il servizio.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] i servizi utilizzano il valore della <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.MaxClockSkew%2A> proprietà nel [SecurityBindingElement](../../../../docs/framework/wcf/diagnostics/wmi/securitybindingelement.md) la possibilità di orologio sfasamento di orario tra il client e il servizio. Nella federazione, l'impostazione `MaxClockSkew` si applica agli sfasamenti dei segnali di clock tra client e servizio token di sicurezza da cui il client ha ottenuto il token emesso. I servizi token di sicurezza, pertanto, non hanno necessità di concedere lo sfasamento dei segnali di clock durante l'impostazione dei periodi di attività e di scadenza dei token emessi.  
  
> [!NOTE]
>  L'importanza dello sfasamento dei segnali di clock aumenta con l'abbreviarsi della durata del token emesso. Nella maggior parte dei casi, lo sfasamento dei segnali di clock non è un problema significativo se la durata del token è di 30 minuti o superiore. Gli scenari con durate più brevi o in cui è importante conoscere il periodo di validità esatto del token, devono essere progettati in modo da prendere in considerazione lo sfasamento dei segnali di clock.  
  
## <a name="federated-endpoints-and-time-outs"></a>Endpoint e timeout federati  
 Quando un client comunica con un endpoint federato, deve innanzitutto acquisire un token appropriato da un servizio token di sicurezza. Se il servizio token di sicurezza espone un endpoint federato, il client deve innanzitutto ottenere un token dall'emittente per quell'endpoint. Ogni acquisizione di token richiede tempo e questo tempo è soggetto al timeout complessivo per l'invio del messaggio effettivo all'endpoint finale.  
  
 Il timeout, ad esempio, nel canale lato client è impostato su 30 secondi. È necessario chiamare due emittenti del token per recuperare i token prima di inviare il messaggio all'endpoint finale e ognuno di essi richiede 15 secondi di tempo per emettere un token. In questo caso il tentativo non riuscirà e verrà generata un'eccezione <xref:System.TimeoutException>. È pertanto necessario impostare il valore <xref:System.ServiceModel.IContextChannel.OperationTimeout%2A> nel canale client su un valore sufficientemente grande da includere il tempo richiesto per recuperare tutti i token emessi. Nel caso in cui non sia specificato un valore per la proprietà <xref:System.ServiceModel.IContextChannel.OperationTimeout%2A>, la proprietà <xref:System.ServiceModel.Channels.Binding.OpenTimeout%2A> o <xref:System.ServiceModel.Channels.Binding.SendTimeout%2A> (o entrambe) devono essere impostate su un valore sufficientemente grande da includere il tempo richiesto per recuperare tutti i token emessi.  
  
## <a name="token-lifetime-and-renewal"></a>Durata e rinnovo dei token   
 I client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] non controllano il token emesso durante l'esecuzione di una richiesta iniziale a un servizio.  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] invece considera attendibile il servizio token di sicurezza per l'emissione di un token con periodi di validità e di scadenza appropriati. Se il token viene memorizzato nella cache dal client e riutilizzato, la sua durata viene controllata in base a richieste successive e il client lo rinnova automaticamente, se necessario. Per ulteriori informazioni sulla memorizzazione nella cache token, vedere [procedura: creare un Client federato](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md).  
  
 La specifica di durate brevi, nell'ordine di 30 secondi o meno per token emessi o token del contesto di sicurezza, può comportare la generazione di timeout della negoziazione o di altre eccezioni da parte dei client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] al momento di richiedere token emessi o di negoziare o rinnovare token del contesto di sicurezza.  
  
## <a name="issued-tokens-and-inclusionmode"></a>Token emessi e InclusionMode  
 L'impostazione della proprietà <xref:System.ServiceModel.Security.Tokens.SecurityTokenParameters.InclusionMode%2A> della classe <xref:System.ServiceModel.Security.Tokens.SecurityTokenParameters> consente di controllare se un token emesso viene serializzato in un messaggio inviato da un client a un endpoint federato. Questa proprietà può essere impostata su uno dei valori dell'enumerazione <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode> ma non è di nessuna utilità nella maggior parte degli scenari federati. I valori `SecurityTokenInclusionMode.Never` e `SecurityTokenInclusionMode.AlwaysToInitiator` fanno in modo che il client invii un riferimento al token emesso dal servizio token di sicurezza al componente. A meno che il relying party non sia in possesso di una copia del token emesso, l'autenticazione non riuscirà poiché il riferimento al token non è risolvibile. In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] `SecurityTokenInclusionMode.Once` viene considerato equivalente a `SecurityTokenInclusionMode.AlwaysToRecipient`.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>  
 [Procedura: Creare un client federato](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [Procedura: Configurare le credenziali in un servizio federativo](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)  
 [Procedura: Creare una classe WSFederationHttpBinding](../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
