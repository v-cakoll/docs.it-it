---
title: Serializzazione in Json con la programmazione a livello di messaggi
ms.date: 03/30/2017
ms.assetid: 5f940ba2-57ee-4c49-a779-957c5e7e71fa
ms.openlocfilehash: fc2777d71376cc482b715898fa81ddf618bd8284
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59186940"
---
# <a name="serializing-in-json-with-message-level-programming"></a>Serializzazione in Json con la programmazione a livello di messaggi
WCF supporta la serializzazione dei dati in formato JSON. In questo argomento viene descritto come impostare WCF in modo da serializzare i tipi utilizzando <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.  
  
## <a name="typed-message-programming"></a>Programmazione di messaggi tipizzati  
 L'oggetto <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> viene utilizzato quando l'oggetto <xref:System.ServiceModel.Web.WebGetAttribute> o <xref:System.ServiceModel.Web.WebInvokeAttribute> viene applicato a un'operazione del servizio. Entrambi gli attributi consentono di specificare `RequestFormat` e `ResponseFormat`. Per utilizzare JSON per le richieste e risposte. impostare entrambi i `WebMessageFormat.Json`.  Per utilizzare JSON, è necessario usare il <xref:System.ServiceModel.WebHttpBinding>, che configura automaticamente il <xref:System.ServiceModel.Description.WebHttpBehavior>. Per altre informazioni sulla serializzazione WCF, vedere [serializzazione e deserializzazione](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md). Per altre informazioni su JSON e WCF, vedere [stazione di servizio - un'introduzione a REST servizi con WCF](https://msdn.microsoft.com/magazine/dd315413.aspx).  
  
> [!IMPORTANT]
>  L'utilizzo di JSON richiede gli oggetti <xref:System.ServiceModel.WebHttpBinding> e <xref:System.ServiceModel.Description.WebHttpBehavior> che non supportano la comunicazione SOAP. Servizi che comunicano con il <xref:System.ServiceModel.WebHttpBinding> non supportano l'esposizione dei metadati del servizio in modo non sarà in grado di usare la funzionalità Aggiungi riferimento al servizio di Visual Studio o lo strumento da riga di comando svcutil per generare un proxy lato client. Per ulteriori informazioni su come è possibile chiamare a livello di programmazione di servizi che usano <xref:System.ServiceModel.WebHttpBinding>, vedere [come utilizzare i servizi REST con WCF](https://blogs.msdn.com/b/pedram/archive/2008/04/21/how-to-consume-rest-services-with-wcf.aspx).  
  
## <a name="untyped-message-programming"></a>Programmazione di messaggi non tipizzati  
 Quando si utilizzano direttamente oggetti Message non tipizzati, è necessario impostare in modo esplicito le proprietà nel messaggio non tipizzato per serializzarlo come JSON. Nel frammento di codice seguente viene illustrato come eseguire questa operazione.  
  
```  
 Message response = Message.CreateMessage(  
                  MessageVersion.None,    // No SOAP message version  
                             "*",                     // SOAP action, ignored since this is JSON  
                             "Response string: JSON format specified", // Message body  
                             new DataContractJsonSerializer(typeof(string))); // Specify DataContractJsonSerializer  
      response.Properties.Add( WebBodyFormatMessageProperty.Name,   
                    new WebBodyFormatMessageProperty(WebContentFormat.Json)); // Use JSON format  
```  
  
## <a name="see-also"></a>Vedere anche

- [Integrazione AJAX e supporto JSON](../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)
- [Serializzazione JSON autonoma](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md)
- [Serializzazione JSON](../../../../docs/framework/wcf/samples/json-serialization.md)
