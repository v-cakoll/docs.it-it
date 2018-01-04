---
title: 'Procedura: configurare un servizio WCF che interagisca con client di servizi Web ASP.NET'
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
ms.assetid: 48e1cd90-de80-4d6c-846e-631878955762
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b4bd1dce4128e6f25294525f10226d98f732cd4e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-configure-wcf-service-to-interoperate-with-aspnet-web-service-clients"></a>Procedura: configurare un servizio WCF che interagisca con client di servizi Web ASP.NET
Per configurare un endpoint del servizio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] per l'interoperabilità con client di servizi Web [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], utilizzare il tipo <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> come tipo di associazione per l'endpoint del servizio.  
  
 È possibile, se lo si desidera, attivare nell'associazione il supporto per HTTPS e l'autenticazione del client a livello di trasporto. I client di servizi Web [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] non supportano la codifica messaggi MTOM, pertanto la proprietà <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType> deve essere lasciata con il suo valore predefinito <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType>. I client di servizi Web ASP.NET non supportano WS-Security, pertanto <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> deve essere impostato su <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>.  
  
 Per rendere i metadati un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] servizio disponibile per [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] strumenti di generazione del proxy del servizio Web (vale a dire [Web Services Description Language Tool (Wsdl.exe)](http://go.microsoft.com/fwlink/?LinkId=73833), [(strumento di individuazione Servizi Web Disco.exe)](http://go.microsoft.com/fwlink/?LinkId=73834)e la funzionalità Aggiungi riferimento Web in Visual Studio), è necessario esporre un endpoint dei metadati HTTP/GET.  
  
### <a name="to-add-a-wcf-endpoint-that-is-compatible-with-aspnet-web-service-clients-in-code"></a>Per aggiungere un endpoint WCF compatibile con client di servizi Web ASP.NET nel codice  
  
1.  Creare una nuova istanza <xref:System.ServiceModel.BasicHttpBinding>.  
  
2.  Attivare facoltativamente la protezione del trasporto per questa associazione dell'endpoint del servizio impostando la modalità di sicurezza per l'associazione su <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>. Per informazioni dettagliate, vedere [la sicurezza del trasporto](../../../../docs/framework/wcf/feature-details/transport-security.md).  
  
3.  Aggiungere un nuovo endpoint applicazione all'host del servizio utilizzando l'istanza di associazione appena creata. Per informazioni dettagliate su come aggiungere un endpoint del servizio nel codice, vedere il [procedura: creare un Endpoint del servizio nel codice](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md).  
  
4.  Attivare un endpoint dei metadati HTTP/GET per il servizio. Per informazioni dettagliate, vedere [procedura: pubblicare metadati per un codice del servizio utilizzando](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md).  
  
### <a name="to-add-a-wcf-endpoint-that-is-compatible-with-aspnet-web-service-clients-in-a-configuration-file"></a>Per aggiungere un endpoint WCF compatibile con client di servizi Web ASP.NET in un file di configurazione  
  
1.  Creare una nuova configurazione dell'associazione <xref:System.ServiceModel.BasicHttpBinding>. Per informazioni dettagliate, vedere il [procedura: specificare un'associazione al servizio nella configurazione](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).  
  
2.  Attivare facoltativamente la protezione del trasporto per questa configurazione dell'associazione dell'endpoint del servizio impostando la modalità di sicurezza per l'associazione su <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>. Per informazioni dettagliate, vedere [la sicurezza del trasporto](../../../../docs/framework/wcf/feature-details/transport-security.md).  
  
3.  Configurare un nuovo endpoint applicazione per il servizio utilizzando la configurazione dell'associazione appena creata. Per informazioni dettagliate su come aggiungere un endpoint del servizio in un file di configurazione, vedere il [procedura: creare un Endpoint del servizio nella configurazione](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md).  
  
4.  Attivare un endpoint dei metadati HTTP/GET per il servizio. Per informazioni dettagliate, vedere il [procedura: pubblicare metadati per un servizio utilizzando un File di configurazione](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene illustrato come aggiungere un endpoint [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] compatibile con i client di servizi Web [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] nel codice e, in alternativa, nei file di configurazione.  
  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)] 
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)] 
 [!code-xml[C_HowTo-WCFServiceAndASMXClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]     
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: Creare un endpoint di servizio nel codice](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)  
 [Procedura: Pubblicare metadati per un servizio usando il codice](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 [Procedura: Specificare un'associazione al servizio nella configurazione](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)  
 [Procedura: Creare un endpoint di servizio nella configurazione](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)  
 [Procedura: Pubblicare metadati per un servizio usando un file di configurazione](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [Sicurezza del trasporto](../../../../docs/framework/wcf/feature-details/transport-security.md)  
 [Uso di metadati](../../../../docs/framework/wcf/feature-details/using-metadata.md)
