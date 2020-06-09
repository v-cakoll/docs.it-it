---
title: Serializzazione in Json con la programmazione a livello di messaggi
ms.date: 03/30/2017
ms.assetid: 5f940ba2-57ee-4c49-a779-957c5e7e71fa
ms.openlocfilehash: 854f03e94510b7f02bb1b7660f1e5108fd8faed8
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600400"
---
# <a name="serializing-in-json-with-message-level-programming"></a>Serializzazione in Json con la programmazione a livello di messaggi
WCF supporta la serializzazione dei dati in formato JSON. In questo argomento viene descritto come impostare WCF in modo da serializzare i tipi utilizzando <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.  
  
## <a name="typed-message-programming"></a>Programmazione di messaggi tipizzati  
 L'oggetto <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> viene utilizzato quando l'oggetto <xref:System.ServiceModel.Web.WebGetAttribute> o <xref:System.ServiceModel.Web.WebInvokeAttribute> viene applicato a un'operazione del servizio. Entrambi gli attributi consentono di specificare `RequestFormat` e `ResponseFormat`. Per usare JSON per le richieste e le risposte. impostare entrambe le impostazioni su `WebMessageFormat.Json` .  Per usare JSON, è necessario usare <xref:System.ServiceModel.WebHttpBinding> , che configura automaticamente <xref:System.ServiceModel.Description.WebHttpBehavior> . Per ulteriori informazioni sulla serializzazione WCF, vedere [serializzazione e deserializzazione](serialization-and-deserialization.md). Per altre informazioni su JSON e WCF, vedere [Service Station: Introduzione ai servizi RESTful con WCF](https://docs.microsoft.com/archive/msdn-magazine/2009/january/service-station-an-introduction-to-restful-services-with-wcf).  
  
> [!IMPORTANT]
> L'utilizzo di JSON richiede gli oggetti <xref:System.ServiceModel.WebHttpBinding> e <xref:System.ServiceModel.Description.WebHttpBehavior> che non supportano la comunicazione SOAP. I servizi che comunicano con il non <xref:System.ServiceModel.WebHttpBinding> supportano l'esposizione dei metadati del servizio, pertanto non sarà possibile utilizzare la funzionalità di Aggiungi riferimento al servizio di Visual Studio o lo strumento da riga di comando svcutil per generare un proxy sul lato client. Per ulteriori informazioni su come è possibile chiamare i servizi a livello di codice che utilizzano <xref:System.ServiceModel.WebHttpBinding> , vedere [come utilizzare i servizi REST con WCF](https://docs.microsoft.com/archive/blogs/pedram/how-to-consume-rest-services-with-wcf).  
  
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

- [Integrazione AJAX e supporto JSON](ajax-integration-and-json-support.md)
- [Serializzazione JSON autonoma](stand-alone-json-serialization.md)
- [Serializzazione JSON](../samples/json-serialization.md)
