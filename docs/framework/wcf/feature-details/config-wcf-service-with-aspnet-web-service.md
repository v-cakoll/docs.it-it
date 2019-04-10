---
title: 'Procedura: Configurare un servizio WCF per interagire con client di servizi Web ASP.NET'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 48e1cd90-de80-4d6c-846e-631878955762
ms.openlocfilehash: 84762d8917609b84a049ea665b575acfa6e5fecf
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59325189"
---
# <a name="how-to-configure-wcf-service-to-interoperate-with-aspnet-web-service-clients"></a>Procedura: Configurare un servizio WCF per interagire con client di servizi Web ASP.NET
Per configurare un endpoint del servizio Windows Communication Foundation (WCF) per essere interoperabile con [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] client del servizio Web, usare il <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> tipo come tipo di associazione per l'endpoint di servizio.  
  
 È possibile, se lo si desidera, attivare nell'associazione il supporto per HTTPS e l'autenticazione del client a livello di trasporto. [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] I client del servizio Web non supportano codifica MTOM, pertanto <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType> proprietà deve essere lasciata come relativo valore predefinito, ovvero <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType>. I client di servizi Web ASP.NET non supportano WS-Security, pertanto <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> deve essere impostato su <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>.  
  
 Per rendere disponibili per i metadati per un servizio WCF [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] strumenti di generazione proxy del servizio Web (vale a dire [Web Services Description Language Tool (Wsdl.exe)](https://go.microsoft.com/fwlink/?LinkId=73833), [strumento di individuazione Servizi Web (Disco.exe)](https://go.microsoft.com/fwlink/?LinkId=73834)e la funzionalità Aggiungi riferimento Web in Visual Studio), è consigliabile esporre un endpoint di metadati HTTP/GET.  
  
### <a name="to-add-a-wcf-endpoint-that-is-compatible-with-aspnet-web-service-clients-in-code"></a>Per aggiungere un endpoint WCF compatibile con client di servizi Web ASP.NET nel codice  
  
1. Creare una nuova istanza <xref:System.ServiceModel.BasicHttpBinding>.  
  
2. Attivare facoltativamente la protezione del trasporto per questa associazione dell'endpoint del servizio impostando la modalità di sicurezza per l'associazione su <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>. Per informazioni dettagliate, vedi [la sicurezza del trasporto](../../../../docs/framework/wcf/feature-details/transport-security.md).  
  
3. Aggiungere un nuovo endpoint applicazione all'host del servizio utilizzando l'istanza di associazione appena creata. Per informazioni dettagliate su come aggiungere un endpoint del servizio nel codice, vedere il [come: Creare un Endpoint del servizio nel codice](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md).  
  
4. Attivare un endpoint dei metadati HTTP/GET per il servizio. Per informazioni dettagliate vedere [come: Pubblicare i metadati per un servizio utilizzando codice](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md).  
  
### <a name="to-add-a-wcf-endpoint-that-is-compatible-with-aspnet-web-service-clients-in-a-configuration-file"></a>Per aggiungere un endpoint WCF compatibile con client di servizi Web ASP.NET in un file di configurazione  
  
1. Creare una nuova configurazione dell'associazione <xref:System.ServiceModel.BasicHttpBinding>. Per informazioni dettagliate, vedere il [come: Specificare un'associazione al servizio nella configurazione](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).  
  
2. Attivare facoltativamente la protezione del trasporto per questa configurazione dell'associazione dell'endpoint del servizio impostando la modalità di sicurezza per l'associazione su <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>. Per informazioni dettagliate, vedere [la sicurezza del trasporto](../../../../docs/framework/wcf/feature-details/transport-security.md).  
  
3. Configurare un nuovo endpoint applicazione per il servizio utilizzando la configurazione dell'associazione appena creata. Per informazioni dettagliate su come aggiungere un endpoint del servizio in un file di configurazione, vedere il [come: Creare un Endpoint del servizio nella configurazione](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md).  
  
4. Attivare un endpoint dei metadati HTTP/GET per il servizio. Per informazioni dettagliate, vedere il [come: Pubblicare i metadati per un servizio utilizzando un File di configurazione](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).  
  
## <a name="example"></a>Esempio  
 Esempio di codice seguente viene illustrato come aggiungere un endpoint WCF compatibile con [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] nel codice client del servizio Web e in alternativa nei file di configurazione.  
  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)] 
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)] 
 [!code-xml[C_HowTo-WCFServiceAndASMXClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]     
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Creare un endpoint del servizio nel codice](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)
- [Procedura: Pubblicare metadati per un servizio usando codice](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)
- [Procedura: Specificare un'associazione al servizio nella configurazione](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)
- [Procedura: Creare un endpoint di servizio nella configurazione](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)
- [Procedura: Pubblicare metadati per un servizio usando un file di configurazione](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [Protezione del trasporto](../../../../docs/framework/wcf/feature-details/transport-security.md)
- [Uso di metadati](../../../../docs/framework/wcf/feature-details/using-metadata.md)
