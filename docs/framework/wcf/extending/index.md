---
title: Estensione di WCF
ms.date: 03/30/2017
helpviewer_keywords:
- WCF, extensibility
- extensibility [WCF]
- Windows Communication Foundation, extensibility
ms.assetid: c145e2f6-f402-41f5-8b5a-eee03978737b
ms.openlocfilehash: 4990f14178551d9dccaca0f2899d8dbc4416cdc4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="extending-wcf"></a>Estensione di WCF
Windows Communication Foundation (WCF) consente di modificare ed estendere i componenti di runtime per controllare in modo accurato ed estendere le applicazioni basate su servizi. Negli argomenti di questa sezione viene esaminata in modo approfondito l'architettura di estendibilità. Per ulteriori informazioni sulla programmazione di base, vedere [programmazione WCF di base](../../../../docs/framework/wcf/basic-wcf-programming.md).  
  
## <a name="in-this-section"></a>In questa sezione  
 [Estensione di ServiceHost e del livello del modello di servizi](../../../../docs/framework/wcf/extending/extending-servicehost-and-the-service-model-layer.md)  
 Il livello del modello di servizi è responsabile del pull dei messaggi in arrivo dai canali sottostanti, della loro conversione in chiamate al metodo nel codice dell'applicazione e della restituzione dei risultati al chiamante.  Le estensioni del modello di servizi modificano o implementano il comportamento e le funzionalità dell'esecuzione o della comunicazione relativamente a funzionalità del dispatcher, comportamenti personalizzati, intercettazione di messaggi e parametri e altre funzionalità di estendibilità.  
  
 [Estensione delle associazioni](../../../../docs/framework/wcf/extending/extending-bindings.md)  
 Le associazioni sono oggetti che descrivono i dettagli di comunicazione necessari per connettersi a un endpoint. Le estensioni di associazione o le associazioni personalizzate implementano le funzionalità personalizzate di comunicazione necessarie per supportare le funzionalità dell'applicazione.  
  
 [Estensione del livello del canale](../../../../docs/framework/wcf/extending/extending-the-channel-layer.md)  
 Il livello del canale è posto sotto il livello del modello di servizio ed è responsabile dello scambio dei messaggi tra client e servizi. Le estensioni del canale possono implementare nuove funzionalità del protocollo, ad esempio la protezione. Possono inoltre implementare funzionalità di trasporto, ad esempio, implementando un nuovo trasporto di rete per il trasporto di messaggi SOAP.  
  
 [Estensione della sicurezza](../../../../docs/framework/wcf/extending/extending-security.md)  
 La protezione in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] è costituita dalla protezione del trasferimento (integrità, riservatezza e autenticazione), dal controllo dell'accesso (autorizzazione) e dal controllo. Le classi disponibili nello spazio dei nomi `IdentityModel` vengono usate da [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] per il controllo dell'accesso. Se si comprendono tutti gli aspetti dell'architettura di sicurezza è possibile creare tipi di attestazione personalizzati per adattare sistemi di controllo dell'accesso personalizzati.  
  
 [Estensione del sistema di metadati](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md)  
 Il sistema dei metadati di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] è un gruppo di classi e interfacce che rappresentano i metadati necessari per implementare applicazioni basate sul servizio. Modificare o estendere le classi o implementare e configurare le interfacce per esportare e importare metadati personalizzati quali estensioni WSDL (Web Services Description Language) o asserzioni di WS-PolicyAttachments personalizzate.  
  
 [Estensione di codificatori e serializzatori](../../../../docs/framework/wcf/extending/extending-encoders-and-serializers.md)  
 I codificatori e i serializzatori convertono i dati da uno modulo a un altro. Negli argomenti di questa sezione viene illustrato come estendere le classi fornite per soddisfare requisiti speciali.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Selectors>  
  
 <xref:System.IdentityModel.Tokens>  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Programmazione WCF di base](../../../../docs/framework/wcf/basic-wcf-programming.md)  
  
 [Dettagli delle funzionalità di WCF](../../../../docs/framework/wcf/feature-details/index.md)  
  
 [Linee guida e procedure consigliate](../../../../docs/framework/wcf/guidelines-and-best-practices.md)
