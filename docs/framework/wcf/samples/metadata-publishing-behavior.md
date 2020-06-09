---
title: Comportamento di pubblicazione dei metadati
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, metadata publishing sample
- Metadata Publishing Behaviors Sample [Windows Communication Foundation]
ms.assetid: 78c13633-d026-4814-910e-1c801cffdac7
ms.openlocfilehash: 60a5884bb8d1189ab758260bf765c321392e1bfe
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84584363"
---
# <a name="metadata-publishing-behavior"></a>Comportamento di pubblicazione dei metadati
L'esempio Comportamento di pubblicazione dei metadati illustra come controllare le caratteristiche di pubblicazione dei metadati di un servizio. Per impedire la divulgazione accidentale di metadati del servizio potenzialmente sensibili, la configurazione predefinita per i servizi di Windows Communication Foundation (WCF) Disabilita la pubblicazione dei metadati. Questo comportamento è protetto per impostazione predefinita, ma significa inoltre che non è possibile usare uno strumento di importazione di metadati (ad esempio Svcutil.exe) per generare il codice client necessario per chiamare il servizio, a meno che il comportamento del servizio di pubblicazione dei metadati non venga abilitato in modo esplicito in fase di configurazione.  
  
> [!IMPORTANT]
> Per maggior chiarezza, questo esempio illustra come creare un endpoint non protetto per la configurazione di metadati. Tali endpoint sono potenzialmente disponibili per utenti anonimi non autenticati e bisogna fare attenzione prima di distribuirli per garantire che la pubblicazione dei metadati di un servizio sia appropriata. Per un esempio di protezione di un endpoint di metadati, vedere l'esempio di [endpoint personalizzato di metadati protetti](custom-secure-metadata-endpoint.md) .  
  
 L'esempio è basato sulla [Introduzione](getting-started-sample.md), che implementa il `ICalculator` contratto di servizio. In questo esempio, il client è un'applicazione console (.exe) e il servizio è ospitato da Internet Information Services (IIS).  
  
> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
 Affinché un servizio esponga metadati, la classe <xref:System.ServiceModel.Description.ServiceMetadataBehavior> deve essere configurata nel servizio. Quando questo comportamento è presente, è possibile pubblicare metadati configurando un endpoint per esporre il contratto <xref:System.ServiceModel.Description.IMetadataExchange> come un'implementazione di un protocollo WS-MetadataExchange (MEX). Per convenienza, a questo contratto è stato dato il nome di configurazione abbreviato seguente: "IMetadataExchange." In questo esempio viene utilizzata l'associazione `mexHttpBinding`, ovvero un'utile associazione standard equivalente all'associazione `wsHttpBinding` con la modalità di sicurezza impostata su `None`. Nell'endpoint viene usato un indirizzo relativo di "mex", che quando viene risolto in base all'indirizzo di base dei servizi restituisce un indirizzo endpoint di `http://localhost/servicemodelsamples/service.svc/mex` . Di seguito viene illustrata la configurazione del comportamento:  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <!-- The serviceMetadata behavior publishes metadata through   
           the IMetadataExchange contract. When this behavior is   
           present, you can expose this contract through an endpoint   
           as shown below. Setting httpGetEnabled to true publishes   
           the service's WSDL at the <baseaddress>?wsdl, for example,  
           http://localhost/servicemodelsamples/service.svc?wsdl -->  
      <serviceMetadata httpGetEnabled="True"/>  
      <serviceDebug includeExceptionDetailInFaults="False" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 Di seguito viene illustrato l'endpoint MEX.  
  
```xml  
<!-- the MEX endpoint is exposed at   
     http://localhost/servicemodelsamples/service.svc/mex   
     To expose the IMetadataExchange contract, you   
     must enable the serviceMetadata behavior as demonstrated                           
     previously. -->  
<endpoint address="mex"  
          binding="mexHttpBinding"  
          contract="IMetadataExchange" />  
```  
  
 Questo esempio imposta la proprietà <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> su `true`, che espone anche i metadati del servizio utilizzando HTTP GET. Per abilitare un endpoint di metadati HTTP GET, il servizio deve avere un indirizzo di base HTTP. La stringa di query `?wsdl` viene utilizzata sull'indirizzo di base del servizio per accedere ai metadati. Ad esempio, per visualizzare il WSDL per il servizio in una Web browser si utilizzerà l'indirizzo `http://localhost/servicemodelsamples/service.svc?wsdl` . In alternativa, è possibile utilizzare questo comportamento per esporre metadati su HTTP impostando <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> su `true`. Ciò richiede un indirizzo di base HTTP.  
  
 Per accedere all'endpoint MEX del servizio, usare lo [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
 `svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /out:generatedClient.cs`  
  
 Ciò genera un client basato sui metadati del servizio.  
  
 Per accedere ai metadati del servizio tramite HTTP GET, puntare il browser a `http://localhost/servicemodelsamples/service.svc?wsdl` .  
  
 Se si rimuove questo comportamento e si tenta di aprire il servizio si otterrà un'eccezione. Questo errore si verifica perché senza il comportamento, l'endpoint configurato con il contratto `IMetadataExchange` non viene implementato.  
  
 Se si imposta `HttpGetEnabled` su `false`, si vede la pagina della Guida di CalculatorService invece dei metadati del servizio.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).  
  
3. Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Metadata`  
