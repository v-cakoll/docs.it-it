---
title: Creazione di servizi interoperativi WS-I Basic Profile 1.1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: configuration [WCF], interoperable services
ms.assetid: 91b70a21-8f5c-4679-808c-2ed5fa6b2013
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 61c4f26c9880d8a7f6a8fb356bafcc0d312509dc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="creating-ws-i-basic-profile-11-interoperable-services"></a>Creazione di servizi interoperativi WS-I Basic Profile 1.1
Per configurare l'interoperabilità di un endpoint del servizio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] con client del servizio Web [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]:  
  
-   Utilizzare il tipo <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> come tipo di associazione per l'endpoint del servizio.  
  
-   Non utilizzare funzionalità di callback e di contratto di sessioni né comportamenti della transazione nell'endpoint del servizio.  
  
 È possibile, se lo si desidera, attivare nell'associazione il supporto per HTTPS e l'autenticazione del client a livello di trasporto.  
  
 Le funzionalità seguenti della classe <xref:System.ServiceModel.BasicHttpBinding> richiedono altre funzionalità oltre a WS-I Basic Profile 1.1:  
  
-   Codifica del messaggio MTOM (Message Transmission Optimization Mechanism, meccanismo di ottimizzazione della trasmissione dei messaggi) controllata dalla proprietà <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType>. Lasciare l'impostazione predefinita di questa proprietà, ovvero <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType> per non utilizzare MTOM.  
  
-   La sicurezza dei messaggi controllata dal valore di <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> fornisce supporto WS-Security conforme a WS-I Basic Security Profile 1.0. Lasciare l'impostazione predefinita di questa proprietà, ovvero <xref:System.ServiceModel.SecurityMode.Transport?displayProperty=nameWithType> per non utilizzare WS-Security.  
  
 Per rendere i metadati un [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] servizio disponibile per [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], utilizzare gli strumenti di generazione client del servizio Web: [Web Services Description Language Tool (Wsdl.exe)](http://msdn.microsoft.com/en-us/b9210348-8bc2-4367-8c91-d1a04b403e88), [(strumento di individuazione Servizi Web Disco.exe)](http://msdn.microsoft.com/en-us/acd88078-c581-42bc-94ca-6633e2851979)e `Add Web Reference` funzionalità [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]; è necessario abilitare la pubblicazione dei metadati. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Gli endpoint dei metadati di pubblicazione](../../../docs/framework/wcf/publishing-metadata-endpoints.md).  
  
## <a name="example"></a>Esempio  
  
### <a name="description"></a>Descrizione  
 Esempio di codice seguente viene illustrato come aggiungere un [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] endpoint compatibile con [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] client del servizio nel codice e, in alternativa, in un file di configurazione Web.  
  
### <a name="code"></a>Codice  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)]
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)]  
 [!code-xml[C_HowTo-WCFServiceAndASMXClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interoperabilità con servizi Web ASP.NET](../../../docs/framework/wcf/feature-details/interop-with-aspnet-web-services.md)
