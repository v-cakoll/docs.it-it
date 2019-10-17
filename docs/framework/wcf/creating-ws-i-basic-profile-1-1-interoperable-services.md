---
title: Creazione di servizi interoperativi WS-I Basic Profile 1.1
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- configuration [WCF], interoperable services
ms.assetid: 91b70a21-8f5c-4679-808c-2ed5fa6b2013
ms.openlocfilehash: eb1cd12c45a276d5c3cb14f89205fff618121abc
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320136"
---
# <a name="creating-ws-i-basic-profile-11-interoperable-services"></a>Creazione di servizi interoperativi WS-I Basic Profile 1.1
Per configurare un endpoint del servizio WCF per l'interoperabilità con i client del servizio Web ASP.NET:  
  
- Utilizzare il tipo <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> come tipo di associazione per l'endpoint del servizio.  
  
- Non utilizzare funzioni di callback e di contratto di sessioni né comportamenti della transazione nell'endpoint del servizio.  
  
 È possibile, se lo si desidera, attivare nell'associazione il supporto per HTTPS e l'autenticazione del client a livello di trasporto.  
  
 Le funzionalità seguenti della classe <xref:System.ServiceModel.BasicHttpBinding> richiedono altre funzionalità oltre a WS-I Basic Profile 1.1:  
  
- Codifica del messaggio MTOM (Message Transmission Optimization Mechanism, meccanismo di ottimizzazione della trasmissione dei messaggi) controllata dalla proprietà <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType>. Lasciare l'impostazione predefinita di questa proprietà, ovvero <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType> per non utilizzare MTOM.  
  
- La sicurezza dei messaggi controllata dal valore di <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> fornisce supporto WS-Security conforme a WS-I Basic Security Profile 1.0. Lasciare l'impostazione predefinita di questa proprietà, ovvero <xref:System.ServiceModel.SecurityMode.Transport?displayProperty=nameWithType> per non utilizzare WS-Security.  
  
 Per rendere disponibili i metadati per un servizio WCF a ASP.NET, utilizzare gli strumenti di generazione client del servizio Web: [Web Services Description Language strumento (WSDL. exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7h3ystb6%28v=vs.100%29), [strumento di individuazione servizi Web (disco. exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cy2a3ybs%28v=vs.100%29)e la funzionalità `Add Web Reference` in Visual Studio. è necessario abilitare la pubblicazione dei metadati. Per ulteriori informazioni, vedere [pubblicazione di endpoint dei metadati](publishing-metadata-endpoints.md).  
  
## <a name="example"></a>Esempio  
  
### <a name="description"></a>Descrizione  
 Nell'esempio di codice seguente viene illustrato come aggiungere un endpoint WCF compatibile con i client del servizio Web ASP.NET nel codice e, in alternativa, in un file di configurazione.  
  
### <a name="code"></a>Codice  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)]
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)]  
 [!code-xml[C_HowTo-WCFServiceAndASMXClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]  
  
## <a name="see-also"></a>Vedere anche

- [Interoperabilità con servizi Web ASP.NET](./feature-details/interop-with-aspnet-web-services.md)
