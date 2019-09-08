---
title: Estensione di WCF
ms.date: 03/30/2017
helpviewer_keywords:
- WCF, extensibility
- extensibility [WCF]
- Windows Communication Foundation, extensibility
ms.assetid: c145e2f6-f402-41f5-8b5a-eee03978737b
ms.openlocfilehash: 037182a3cb105f544e15a05f955c142ba57f62f3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795533"
---
# <a name="extending-wcf"></a>Estensione di WCF
Windows Communication Foundation (WCF) consente di modificare ed estendere i componenti di runtime per controllare e estendere con precisione le applicazioni basate su servizi. Negli argomenti di questa sezione viene esaminata in modo approfondito l'architettura di estendibilità. Per ulteriori informazioni sulla programmazione di base, vedere [programmazione WCF di base](../basic-wcf-programming.md).  
  
## <a name="in-this-section"></a>In questa sezione  
 [Estensione di ServiceHost e del livello del modello di servizi](extending-servicehost-and-the-service-model-layer.md)  
 Il livello del modello di servizi è responsabile del pull dei messaggi in arrivo dai canali sottostanti, della loro conversione in chiamate al metodo nel codice dell'applicazione e della restituzione dei risultati al chiamante.  Le estensioni del modello di servizi modificano o implementano il comportamento e le funzioni dell'esecuzione o della comunicazione relativamente a funzionalità del dispatcher, comportamenti personalizzati, intercettazione di messaggi e parametri e altre funzionalità di estendibilità.  
  
 [Estensione delle associazioni](extending-bindings.md)  
 Le associazioni sono oggetti che descrivono i dettagli di comunicazione necessari per connettersi a un endpoint. Le estensioni di associazione o le associazioni personalizzate implementano le funzionalità personalizzate di comunicazione necessarie per supportare le funzionalità dell'applicazione.  
  
 [Estensione del livello del canale](extending-the-channel-layer.md)  
 Il livello del canale è posto sotto il livello del modello di servizio ed è responsabile dello scambio dei messaggi tra client e servizi. Le estensioni del canale possono implementare nuove funzionalità del protocollo, ad esempio la protezione. Possono inoltre implementare funzionalità di trasporto, ad esempio, implementando un nuovo trasporto di rete per il trasporto di messaggi SOAP.  
  
 [Estensione della sicurezza](extending-security.md)  
 La sicurezza in WCF è costituita dalla sicurezza del trasferimento (integrità, riservatezza e autenticazione), dal controllo di accesso (autorizzazione) e dal controllo. Le classi disponibili nello `IdentityModel` spazio dei nomi vengono utilizzate da WCF per il controllo di accesso. Se si comprendono tutti gli aspetti dell'architettura di sicurezza è possibile creare tipi di attestazione personalizzati per adattare sistemi di controllo dell'accesso personalizzati.  
  
 [Estensione del sistema di metadati](extending-the-metadata-system.md)  
 Il sistema di metadati WCF è un gruppo di classi e interfacce che rappresentano i metadati necessari per implementare applicazioni basate su servizi. Modificare o estendere le classi o implementare e configurare le interfacce per esportare e importare metadati personalizzati quali estensioni WSDL (Web Services Description Language) o asserzioni di WS-PolicyAttachments personalizzate.  
  
 [Estensione di codificatori e serializzatori](extending-encoders-and-serializers.md)  
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
 [Programmazione WCF di base](../basic-wcf-programming.md)  
  
 [Dettagli delle funzionalità di WCF](../feature-details/index.md)  
  
 [Linee guida e procedure consigliate](../guidelines-and-best-practices.md)
