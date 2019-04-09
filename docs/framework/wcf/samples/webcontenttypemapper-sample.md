---
title: Esempio di WebContentTypeMapper
ms.date: 03/30/2017
ms.assetid: a4fe59e7-44d8-43c6-a1f8-40c45223adca
ms.openlocfilehash: 7858b07c3da8684326b931b54f825c87a6e35717
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59131508"
---
# <a name="webcontenttypemapper-sample"></a>Esempio di WebContentTypeMapper
In questo esempio viene illustrato come eseguire il mapping di nuovi tipi di contenuto a formati del corpo del messaggio di Windows Communication Foundation (WCF).  
  
 Il <xref:System.ServiceModel.Description.WebHttpEndpoint> elemento inserisce il codificatore di messaggi Web, che consente a WCF ricevere i messaggi binari non elaborati sullo stesso endpoint, XML o JSON. Il codificatore determina il formato del corpo del messaggio analizzando il tipo di contenuto HTTP della richiesta. In questo esempio viene presentata la classe <xref:System.ServiceModel.Channels.WebContentTypeMapper>, che consente all'utente di controllare il mapping tra il tipo di contenuto e il formato del corpo.  
  
 WCF fornisce un set di mapping predefiniti per i tipi di contenuto. Ad esempio, `application/json` esegue il mapping a JSON e `text/xml` esegue il mapping a XML. Qualsiasi tipo di contenuto per cui non viene eseguito il mapping a JSON o a XML, viene associato al formato binario non elaborato.  
  
 In alcuni scenari (ad esempio, API di tipo push), lo sviluppatore del servizio non controlla il tipo di contenuto restituito dal client. Ad esempio, i client potrebbero restituire JSON come `text/javascript` anziché `application/json`. In questo caso, lo sviluppatore del servizio deve fornire un tipo che deriva da <xref:System.ServiceModel.Channels.WebContentTypeMapper> per gestire correttamente il tipo di contenuto specificato, come illustrato nell'esempio di codice seguente.  
  
```  
public class JsonContentTypeMapper : WebContentTypeMapper  
{  
    public override WebContentFormat  
               GetMessageFormatForContentType(string contentType)  
    {  
        if (contentType == "text/javascript")  
        {  
            return WebContentFormat.Json;  
        }  
        else  
        {  
            return WebContentFormat.Default;  
        }  
    }  
}  
```  
  
 È necessario che il tipo esegua l'override del metodo <xref:System.ServiceModel.Channels.WebContentTypeMapper.GetMessageFormatForContentType%28System.String%29>. Il metodo deve valutare l'argomento `contentType` e restituire uno dei seguenti valori: <xref:System.ServiceModel.Channels.WebContentFormat.Json>, <xref:System.ServiceModel.Channels.WebContentFormat.Xml>, <xref:System.ServiceModel.Channels.WebContentFormat.Raw>, or <xref:System.ServiceModel.Channels.WebContentFormat.Default>. La restituzione di <xref:System.ServiceModel.Channels.WebContentFormat.Default> rinvia ai mapping del codificatore di messaggi Web predefiniti. Nell'esempio di codice precedente il tipo di contenuto `text/javascript` viene associato a JSON e tutti gli altri mapping rimangono immutati.  
  
 Per utilizzare la classe `JsonContentTypeMapper`, modificare il file Web.config nel modo seguente:  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>  
    <webHttpEndpoint>  
      <standardEndpoint name="" contentTypeMapper="Microsoft.Samples.WebContentTypeMapper.JsonContentTypeMapper, JsonContentTypeMapper, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
    </webHttpEndpoint>  
  </standardEndpoints>  
</system.serviceModel>  
```  
  
 Per verificare il requisito per l'utilizzo di JsonContentTypeMapper, rimuovere l'attributo contentTypeMapper dal file di configurazione illustrato in precedenza. Si verifica un errore durante il caricamento della pagina client quando si tenta di utilizzare  `text/javascript` per inviare contenuto JSON.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1.  Assicurarsi di avere eseguito il [monouso procedura di installazione per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Compilare la soluzione Webcontenttypemappersample come descritto in [Building Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Passare a `http://localhost/ServiceModelSamples/JCTMClientPage.htm` (non aprire Jctmclientpage nel browser dalla directory del progetto).  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Ajax\WebContentTypeMapper`  
