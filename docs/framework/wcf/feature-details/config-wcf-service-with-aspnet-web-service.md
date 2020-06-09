---
title: 'Procedura: configurare un servizio WCF che interagisca con client di servizi Web ASP.NET'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 48e1cd90-de80-4d6c-846e-631878955762
ms.openlocfilehash: 52f7857a2dc7108eb308fde942bf153d85d8e8ed
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84593607"
---
# <a name="how-to-configure-wcf-service-to-interoperate-with-aspnet-web-service-clients"></a>Procedura: configurare un servizio WCF che interagisca con client di servizi Web ASP.NET

Per configurare un endpoint del servizio Windows Communication Foundation (WCF) per l'interoperabilità con i client del servizio Web ASP.NET, usare il <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> tipo come tipo di binding per l'endpoint del servizio.  
  
 È possibile, se lo si desidera, attivare nell'associazione il supporto per HTTPS e l'autenticazione del client a livello di trasporto. I client del servizio Web ASP.NET non supportano la codifica dei messaggi MTOM, quindi la <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType> proprietà deve essere lasciata come valore predefinito, ovvero <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType> . I client del servizio Web ASP.NET non supportano WS-Security, quindi <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> è necessario impostare su <xref:System.ServiceModel.BasicHttpSecurityMode.Transport> .  
  
 Per rendere disponibili i metadati per un servizio WCF agli strumenti di generazione del proxy del servizio Web ASP.NET (ovvero [Web Services Description Language strumento (WSDL. exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7h3ystb6(v%3dvs.100)), [strumento di individuazione servizi Web (disco. exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cy2a3ybs(v=vs.100))e la funzionalità **Aggiungi riferimento Web** in Visual Studio), è necessario esporre un endpoint dei metadati HTTP/Get.  
  
## <a name="add-an-endpoint-in-code"></a>Aggiungere un endpoint nel codice  
  
1. Creare una nuova istanza <xref:System.ServiceModel.BasicHttpBinding>.  
  
2. Attivare facoltativamente la protezione del trasporto per questa associazione dell'endpoint del servizio impostando la modalità di sicurezza per l'associazione su <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>. Per informazioni dettagliate, vedere [sicurezza del trasporto](transport-security.md).  
  
3. Aggiungere un nuovo endpoint applicazione all'host del servizio utilizzando l'istanza di associazione appena creata. Per informazioni dettagliate su come aggiungere un endpoint di servizio nel codice, vedere [procedura: creare un endpoint di servizio nel codice](how-to-create-a-service-endpoint-in-code.md).  
  
4. Attivare un endpoint dei metadati HTTP/GET per il servizio. Per informazioni dettagliate [, vedere Procedura: pubblicare metadati per un servizio usando il codice](how-to-publish-metadata-for-a-service-using-code.md).  
  
## <a name="add-an-endpoint-in-a-configuration-file"></a>Aggiungere un endpoint in un file di configurazione  
  
1. Creare una nuova configurazione dell'associazione <xref:System.ServiceModel.BasicHttpBinding>. Per informazioni dettagliate, vedere [procedura: specificare un'associazione al servizio nella configurazione](../how-to-specify-a-service-binding-in-configuration.md).  
  
2. Attivare facoltativamente la protezione del trasporto per questa configurazione dell'associazione dell'endpoint del servizio impostando la modalità di sicurezza per l'associazione su <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>. Per informazioni dettagliate, vedere [sicurezza del trasporto](transport-security.md).  
  
3. Configurare un nuovo endpoint applicazione per il servizio utilizzando la configurazione dell'associazione appena creata. Per informazioni dettagliate su come aggiungere un endpoint di servizio in un file di configurazione, vedere [procedura: creare un endpoint del servizio nella configurazione](how-to-create-a-service-endpoint-in-configuration.md).  
  
4. Attivare un endpoint dei metadati HTTP/GET per il servizio. Per informazioni dettagliate [, vedere Procedura: pubblicare metadati per un servizio usando un file di configurazione](how-to-publish-metadata-for-a-service-using-a-configuration-file.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene illustrato come aggiungere un endpoint WCF compatibile con i client del servizio Web ASP.NET nel codice e, in alternativa, nei file di configurazione.  
  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)]
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)]
 [!code-xml[C_HowTo-WCFServiceAndASMXClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]
  
## <a name="see-also"></a>Vedere anche

- [Procedura: creare un endpoint del servizio nel codice](how-to-create-a-service-endpoint-in-code.md)
- [Procedura: pubblicare metadati per un servizio usando codice](how-to-publish-metadata-for-a-service-using-code.md)
- [Procedura: Specificare un'associazione al servizio nella configurazione](../how-to-specify-a-service-binding-in-configuration.md)
- [Procedura: creare un endpoint di servizio nella configurazione](how-to-create-a-service-endpoint-in-configuration.md)
- [Procedura: pubblicare metadati per un servizio usando un file di configurazione](how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [Sicurezza del trasporto](transport-security.md)
- [Uso di metadati](using-metadata.md)
