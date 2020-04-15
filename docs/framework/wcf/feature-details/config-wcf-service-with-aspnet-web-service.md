---
title: 'Procedura: configurare un servizio WCF che interagisca con client di servizi Web ASP.NET'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 48e1cd90-de80-4d6c-846e-631878955762
ms.openlocfilehash: 22713aba4f86fe493ba3d16ef09c2a71b6d55fe0
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389789"
---
# <a name="how-to-configure-wcf-service-to-interoperate-with-aspnet-web-service-clients"></a>Procedura: configurare un servizio WCF che interagisca con client di servizi Web ASP.NET

Per configurare un endpoint del servizio Windows Communication Foundation (WCF) per <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> l'interoperabilità con i client del servizio Web ASP.NET, usare il tipo come tipo di associazione per l'endpoint del servizio.  
  
 È possibile, se lo si desidera, attivare nell'associazione il supporto per HTTPS e l'autenticazione del client a livello di trasporto. ASP.NET client del servizio Web non supportano <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType> la codifica dei messaggi MTOM, pertanto la proprietà deve essere lasciata come valore predefinito, ovvero <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType>. I client di servizi Web ASP.NET non supportano WS-Security, pertanto <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> deve essere impostato su <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>.  
  
 Per rendere disponibili i metadati per un servizio WCF per ASP.NET strumenti di generazione di proxy del servizio Web, ovvero strumento del linguaggio di descrizione dei [servizi Web (Wsdl.exe),](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7h3ystb6(v%3dvs.100))strumento di [individuazione dei servizi Web (Disco.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cy2a3ybs(v=vs.100))e aggiunta di **riferimenti Web** in Visual Studio, è necessario esporre un endpoint dei metadati HTTP/GET.  
  
## <a name="add-an-endpoint-in-code"></a>Aggiungere un endpoint nel codiceAdd an endpoint in code  
  
1. Creare una nuova istanza <xref:System.ServiceModel.BasicHttpBinding>.  
  
2. Attivare facoltativamente la protezione del trasporto per questa associazione dell'endpoint del servizio impostando la modalità di sicurezza per l'associazione su <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>. Per informazioni dettagliate, vedere [Sicurezza del trasporto](../../../../docs/framework/wcf/feature-details/transport-security.md).  
  
3. Aggiungere un nuovo endpoint applicazione all'host del servizio utilizzando l'istanza di associazione appena creata. Per informazioni dettagliate su come aggiungere un endpoint del servizio nel codice, vedere [procedura: creare un endpoint del servizio nel codice](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md).  
  
4. Attivare un endpoint dei metadati HTTP/GET per il servizio. Per informazioni dettagliate, vedere [Procedura: pubblicare metadati per un servizio tramite codice](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md).  
  
## <a name="add-an-endpoint-in-a-configuration-file"></a>Aggiungere un endpoint in un file di configurazioneAdd an endpoint in a configuration file  
  
1. Creare una nuova configurazione dell'associazione <xref:System.ServiceModel.BasicHttpBinding>. Per informazioni dettagliate, vedere [procedura: specificare un'associazione](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)al servizio nella configurazione .  
  
2. Attivare facoltativamente la protezione del trasporto per questa configurazione dell'associazione dell'endpoint del servizio impostando la modalità di sicurezza per l'associazione su <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>. Per informazioni dettagliate, vedere [Sicurezza del trasporto](../../../../docs/framework/wcf/feature-details/transport-security.md).  
  
3. Configurare un nuovo endpoint applicazione per il servizio utilizzando la configurazione dell'associazione appena creata. Per informazioni dettagliate su come aggiungere un endpoint del servizio in un file di configurazione, vedere [procedura: creare un endpoint del servizio nella configurazione](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md).  
  
4. Attivare un endpoint dei metadati HTTP/GET per il servizio. Per informazioni dettagliate, vedere [Procedura: pubblicare metadati per un servizio utilizzando un file di configurazione](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).  
  
## <a name="example"></a>Esempio  
 Il codice di esempio seguente viene illustrato come aggiungere un endpoint WCF compatibile con ASP.NET client del servizio Web nel codice e in alternativa nei file di configurazione.  
  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)]
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)]
 [!code-xml[C_HowTo-WCFServiceAndASMXClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]
  
## <a name="see-also"></a>Vedere anche

- [Procedura: creare un endpoint del servizio nel codice](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)
- [Procedura: pubblicare metadati per un servizio usando codice](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)
- [Procedura: Specificare un'associazione al servizio nella configurazione](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)
- [Procedura: creare un endpoint di servizio nella configurazione](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)
- [Procedura: pubblicare metadati per un servizio usando un file di configurazione](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [Sicurezza dei trasporti](../../../../docs/framework/wcf/feature-details/transport-security.md)
- [Uso di metadati](../../../../docs/framework/wcf/feature-details/using-metadata.md)
