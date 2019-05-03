---
title: Associazioni di Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], bindings
- Windows Communication Foundation [WCF], bindings
- bindings [WCF]
ms.assetid: 83639133-89f7-43f0-b4ef-8d9e57c08d25
ms.openlocfilehash: e69cd500c50e9d76824d0e438a1af86f3a722c52
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61857688"
---
# <a name="windows-communication-foundation-bindings"></a>Associazioni di Windows Communication Foundation
Windows Communication Foundation (WCF) separa il modo in cui il software per un'applicazione viene scritto dal modo in cui comunica con altro software. Le associazioni vengono utilizzate per specificare i dettagli sul trasporto, la codifica e il protocollo necessari per consentire la comunicazione tra client e servizi. WCF utilizza le associazioni per generare la rappresentazione della rete sottostante dell'endpoint, pertanto la maggior parte dei dettagli dell'associazione devono essere concordata dalle parti che stanno comunicando. Il modo più semplice per conseguire questo risultato consiste nel fare in modo che i client di un servizio utilizzino la stessa associazione utilizzata dall'endpoint del servizio. Per altre informazioni su come eseguire questa operazione, vedere [utilizzando le associazioni per configurare servizi e client](~/docs/framework/wcf/using-bindings-to-configure-services-and-clients.md).  
  
 Un'associazione è costituita da una raccolta di elementi di associazione. Ogni elemento descrive alcuni aspetti relativi alla modalità di comunicazione tra l'endpoint e i client. Un'associazione deve includere almeno un elemento di associazione di trasporto, almeno un elemento di associazione di codifica del messaggio (che può essere fornito per impostazione predefinita dall'elemento di associazione di trasporto) e un numero qualsiasi di altri elementi di associazione del protocollo. Il processo che genera una fase di esecuzione da questa descrizione consente a ogni elemento di associazione di fornire codice alla fase di esecuzione.  
  
 WCF fornisce associazioni che contengono selezioni comuni di elementi di associazione. Questi possono essere utilizzati con le rispettive impostazioni predefinite oppure è possibile modificare i valori predefiniti in base ai requisiti dell'utente. Le associazioni fornite dal sistema presentano proprietà che consentono il controllo diretto degli elementi di associazione e delle relative impostazioni. È inoltre possibile utilizzare facilmente e side-by-side più versioni di un'associazione, assegnando a ogni versione dell'associazione un nome diverso. Per informazioni dettagliate, vedere [associazioni Configuring System-Provided](../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md).  
  
 Se risulta necessario una raccolta di elementi di associazione non disponibili tra queste associazioni fornite dal sistema, è possibile creare un'associazione personalizzata costituita dalla raccolta di elementi di associazione necessari. Le associazioni personalizzate sono di facile creazione e non richiedono una nuova classe ma non forniscono proprietà per il controllo degli elementi di associazione o delle relative impostazioni. È possibile accedere agli elementi di associazione e modificarne le impostazioni tramite la raccolta che li contiene. Per informazioni dettagliate, vedere [associazioni personalizzate](../../../../docs/framework/wcf/extending/custom-bindings.md).  
  
## <a name="in-this-section"></a>In questa sezione  
 [Configurazione di associazioni fornite dal sistema](../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 Viene descritto come utilizzare e modificare i binding forniti da WCF per supportare scenari comuni.  
  
 [Uso di associazioni per configurare servizi e client](../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 Viene descritto come definire associazioni Windows Communication Foundation (WCF) per servizi e client in modo imperativo nel codice e in modo dichiarativo utilizzando la configurazione.  
  
 [Associazioni personalizzate](../../../../docs/framework/wcf/extending/custom-bindings.md)  
 Viene descritto l'elemento <xref:System.ServiceModel.Channels.CustomBinding> e la circostanza in cui è utilizzato.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.ServiceModel.Channels.Binding>  
  
 <xref:System.ServiceModel.Channels.BindingElement>  
  
 <xref:System.ServiceModel.Channels.CustomBinding>  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Estensione delle associazioni](../../../../docs/framework/wcf/extending/extending-bindings.md)
