---
title: Serializzazione in Json con la programmazione a livello di messaggi
ms.date: 03/30/2017
ms.assetid: 5f940ba2-57ee-4c49-a779-957c5e7e71fa
ms.openlocfilehash: 36459dbc0ddee883678a98a27f9abb74fde78e86
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184490"
---
# <a name="serializing-in-json-with-message-level-programming"></a>Serializzazione in Json con la programmazione a livello di messaggi
WCF supporta la serializzazione dei dati in formato JSON. In questo argomento viene descritto come impostare WCF in modo da serializzare i tipi utilizzando <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.  
  
## <a name="typed-message-programming"></a>Programmazione di messaggi tipizzati  
 L'oggetto <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> viene utilizzato quando l'oggetto <xref:System.ServiceModel.Web.WebGetAttribute> o <xref:System.ServiceModel.Web.WebInvokeAttribute> viene applicato a un'operazione del servizio. Entrambi gli attributi consentono di specificare `RequestFormat` e `ResponseFormat`. Per usare JSON per richieste e risposte. impostare entrambi `WebMessageFormat.Json`su .  Per utilizzare JSON, è necessario <xref:System.ServiceModel.WebHttpBinding>utilizzare l'opzione <xref:System.ServiceModel.Description.WebHttpBehavior>, che configura automaticamente il metodo . Per altre informazioni sulla serializzazione WCF, vedere [serializzazione e deserializzazione](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md). Per altre informazioni su JSON e WCF, vedere [Stazione di servizio - Introduzione ai servizi RESTful con WCF](https://docs.microsoft.com/archive/msdn-magazine/2009/january/service-station-an-introduction-to-restful-services-with-wcf).  
  
> [!IMPORTANT]
> L'utilizzo di JSON richiede gli oggetti <xref:System.ServiceModel.WebHttpBinding> e <xref:System.ServiceModel.Description.WebHttpBehavior> che non supportano la comunicazione SOAP. I servizi che <xref:System.ServiceModel.WebHttpBinding> comunicano con i servizi non supportano l'esposizione dei metadati del servizio, pertanto non sarà possibile utilizzare la funzionalità Aggiungi riferimento al servizio di Visual Studio o lo strumento da riga di comando svcutil per generare un proxy sul lato client. Per altre informazioni su come chiamare <xref:System.ServiceModel.WebHttpBinding>a livello di codice i servizi che [utilizzano](https://docs.microsoft.com/archive/blogs/pedram/how-to-consume-rest-services-with-wcf), vedere Come utilizzare i servizi REST con WCF .  
  
## <a name="untyped-message-programming"></a>Programmazione di messaggi non tipizzati  
 Quando si utilizzano direttamente oggetti Message non tipizzati, è necessario impostare in modo esplicito le proprietà nel messaggio non tipizzato per serializzarlo come JSON. Nel frammento di codice seguente viene illustrato come eseguire questa operazione.  
  
```csharp
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
