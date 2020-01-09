---
title: SRMP
ms.date: 03/30/2017
ms.assetid: cf37078c-dcb4-45e0-acaf-2f196521b226
ms.openlocfilehash: 1e0290a4df688d39f84086dc4c1b41712f81076a
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345151"
---
# <a name="srmp"></a>SRMP
In questo esempio viene illustrato come eseguire comunicazioni transazionali in coda usando Accodamento messaggi (MSMQ) su HTTP.  
  
 Nella comunicazione in coda, il client comunica al servizio usando una coda. Più precisamente, il client invia messaggi a una coda. Il servizio riceve messaggi dalla coda. Di conseguenza, per comunicare mediante una coda il servizio e il client non devono essere in esecuzione contemporaneamente.  
  
 MSMQ consente di usare HTTP (e HTTPS) per inviare messaggi a una coda. In questo esempio viene illustrato l'utilizzo della comunicazione in coda Windows Communication Foundation (WCF) e come inviare messaggi tramite HTTP. MSMQ usa un protocollo chiamato SRMP, protocollo basato su SOAP per la comunicazione su HTTP.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
4. Prima di eseguire l'esempio in **Installazione componenti di Windows**, verificare che MSMQ sia installato con supporto http. L'installazione del supporto HTTP installa automaticamente Internet Information Services (IIS) e aggiunge il supporto dei protocolli per MSMQ in IIS.  
  
5. Per essere sicuri che venga usato HTTP per la comunicazione, è possibile abilitare MSMQ per l'esecuzione in modalità di protezione avanzata. In questo modo si garantisce che i messaggi inviati alla coda sul computer ospitato usando un trasporto diverso da HTTP non arrivino a destinazione.  
  
6. Dopo aver selezionato MSMQ per l'esecuzione in modalità di protezione avanzata, è necessario riavviare il computer in Windows Server 2003.  
  
7. Eseguire il servizio.  
  
8. Eseguire il client. Assicurarsi di modificare l'indirizzo endpoint in modo che punti al nome del computer o all'indirizzo IP, anziché a localhost. Il client invia un messaggio e viene chiuso.  
  
## <a name="requirements"></a>Requisiti di  
 Per eseguire questo esempio è necessario che, oltre a MSMQ, IIS sia installato sul computer del servizio e su quello del client,  
  
## <a name="demonstrates"></a>Dimostrazione  
 Nell'esempio viene illustrato l'invio di messaggi accodati WCF tramite MSMQ su HTTP. Questa procedura viene anche chiamata messaggistica SRMP. Quando viene inviato un messaggio in coda, MSMQ sul computer mittente trasferisce i messaggi al gestore code di destinazione usando il trasporto TCP o HTTP. Se sceglie SRMP, l'utente sceglie HTTP come tipo di trasporto per il trasferimento della coda. Il protocollo SRMP protetto consente l'uso di HTTPS.  
  
## <a name="example"></a>Esempio  
 L'esempio di codice si basa sull'esempio transazionale. L'invio di un messaggio alla coda e la ricezione di un messaggio dalla coda mediante SRMP sono uguali all'invio e alla ricezione di messaggi mediante un protocollo nativo.  
  
 La configurazione per il client viene modificata per indicare la scelta del protocollo di trasferimento dalla coda. Il protocollo di trasferimento dalla coda può essere nativo, SRMP o SrmpSecure. Per impostazione predefinita, il protocollo di trasferimento è nativo. Nella configurazione di questo esempio il client e il servizio specificano di usare SRMP.  
  
 L'uso del protocollo SRMP presenta alcuni limiti relativi alla sicurezza del trasporto. La sicurezza del trasporto MSMQ predefinita richiede Active Directory che richiede a sua volta che il gestore delle code mittente e il gestore delle code di destinazione risiedano nello stesso dominio Windows. Questo non è possibile quando si inviano messaggi mediante HTTP. Per questa ragione, la sicurezza del trasporto predefinita non funziona. Se si desidera che il trasporto sia protetto, è necessario impostare la sicurezza del trasporto su Certificato. È possibile inoltre usare la sicurezza dei messaggi per proteggere il messaggio. In questo esempio, il trasporto e la sicurezza dei messaggi sono disattivati per illustrare la messaggistica SRMP.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  
  <system.serviceModel>  
  
    <client>  
      <!-- Define NetMsmqEndpoint -->  
      <endpoint name="OrderProcessorEndpoint"  
           address=  
          "net.msmq://localhost/private/ServiceModelSamplesSrmp"   
           bindingConfiguration="srmpBinding"   
           binding="netMsmqBinding"   
           contract="IOrderProcessor" />  
    </client>  
    <bindings>  
      <netMsmqBinding>  
        <binding name="srmpBinding"  
                 queueTransferProtocol="Srmp">  
          <security mode="None" />  
        </binding>  
      </netMsmqBinding>  
    </bindings>  
  </system.serviceModel>  
  
</configuration>  
```  
  
 L'esecuzione dell'esempio produce l'output seguente.  
  
```console  
Processing Purchase Order: 556b70be-31ee-4a3b-8df4-ed5e538015a4   
Customer: somecustomer.com   
OrderDetails   
    Order LineItem: 54 of Blue Widget @unit price: $29.99   
    Order LineItem: 890 of Red Widget @unit price: $45.89   
    Total cost of this order: $42461.56   
    Order status: Pending  
```  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\SRMP`  
