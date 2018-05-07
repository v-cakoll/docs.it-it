---
title: WSStreamedHttpBinding
ms.date: 03/30/2017
ms.assetid: 97ce4d3d-ca6f-45fa-b33b-2429bb84e65b
ms.openlocfilehash: f146e469a323dffa2cdb9b76b6956be97747b2de
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="wsstreamedhttpbinding"></a>WSStreamedHttpBinding
Nell'esempio viene illustrato come creare un'associazione progettata per supportare scenari basati sul flusso quando viene utilizzato il trasporto HTTP.  
  
> [!NOTE]
>  La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Binding\WSStreamedHttpBinding`  
  
 I passaggi per creare e configurare una nuova associazione standard sono i seguenti.  
  
1.  Creazione di una nuova associazione standard  
  
     Le associazioni standard in Windows Communication Foundation (WCF), ad esempio basicHttpBinding e netTcpBinding configurano i trasporti sottostanti e stack di canali per i requisiti specifici. In questo esempio, `WSStreamedHttpBinding` configura lo stack di canali per supportare il flusso. Per impostazione predefinita, WS-Security e la messaggistica affidabile non vengono aggiunti allo stack di canali perché entrambi le funzionalità non sono supportate dal flusso. La nuova associazione viene implementata nella classe `WSStreamedHttpBinding` che deriva da <xref:System.ServiceModel.Channels.Binding>. `WSStreamedHttpBinding` contiene i seguenti elementi di associazione: <xref:System.ServiceModel.Channels.HttpTransportBindingElement>, <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>, <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> e <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>. La classe fornisce un metodo `CreateBindingElements()` per configurare lo stack dell'associazione risultante, come illustrato nell'esempio di codice seguente.  
  
    ```  
    public override BindingElementCollection CreateBindingElements()  
    {  
         // return collection of BindingElements  
         BindingElementCollection bindingElements = new BindingElementCollection();  
  
        // the order of binding elements within the collection is important: layered channels are applied in the order included, followed by  
        // the message encoder, and finally the transport at the end  
        if (flowTransactions)  
        {  
            bindingElements.Add(transactionFlow);  
        }  
        bindingElements.Add(textEncoding);  
  
        // add transport (http or https)  
        bindingElements.Add(transport);  
        return bindingElements.Clone();  
    }  
    ```  
  
2.  Aggiunta del supporto di configurazione  
  
     Per esporre il trasporto tramite la configurazione l'esempio implementa altre due classi: `WSStreamedHttpBindingConfigurationElement` e `WSStreamedHttpBindingSection`. La classe `WSStreamedHttpBindingSection` è una classe  <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602> che espone `WSStreamedHttpBinding` al sistema di configurazione di  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. La maggior parte dell'implementazione viene delegata a `WSStreamedHttpBindingConfigurationElement` che deriva da <xref:System.ServiceModel.Configuration.StandardBindingElement>. La classe `WSStreamedHttpBindingConfigurationElement` è dotata delle proprietà che corrispondono alle proprietà di `WSStreamedHttpBinding` e funzioni che consentono di eseguire il mapping di ogni elemento di configurazione a un'associazione.  
  
     Registrare il gestore nel sistema di configurazione, aggiungendo la sezione seguente al file di configurazione del servizio.  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <extensions>  
          <bindingExtensions>  
            <add name="wsStreamedHttpBinding" type="Microsoft.ServiceModel.Samples.WSStreamedHttpBindingCollectionElement, WSStreamedHttpBinding, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null" />  
          </bindingExtensions>  
        </extensions>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
     È possibile fare riferimento al gestore dalla sezione di configurazione serviceModel.  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <client>  
          <endpoint  
                    address="https://localhost/servicemodelsamples/service.svc"  
                    bindingConfiguration="Binding"  
                    binding="wsStreamedHttpBinding"  
                    contract="Microsoft.ServiceModel.Samples.IStreamedEchoService"/>  
        </client>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1.  Installare [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 usando il comando seguente.  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2.  Assicurarsi di avere eseguito i passaggi elencati in [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
3.  Assicurarsi di avere eseguito la [istruzioni di installazione certificato Server Internet Information Services (IIS)](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).  
  
4.  Per compilare la soluzione, seguire le istruzioni in [compilazione degli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
5.  Per eseguire l'esempio in una configurazione con più computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
6.  Quando viene visualizzata la finestra client, digitare "Esempio.txt." Nella directory dovrebbe essere presente una "Copia di Esempio.txt".  
  
## <a name="the-wsstreamedhttpbinding-sample-service"></a>Esempio di servizio WSStreamedHttpBinding  
 L'esempio di servizio che utilizza `WSStreamedHttpBinding` si trova nella sottodirectory del servizio. L'implementazione di `OperationContract` utilizza un `MemoryStream` per recuperare tutti i dati dal flusso in ingresso prima di restituire `MemoryStream`. L'esempio di servizio è ospitato da Internet Information Services (IIS).  
  
```  
[ServiceContract]  
public interface IStreamedEchoService  
{  
    [OperationContract]  
    Stream Echo(Stream data);  
}  
  
public class StreamedEchoService : IStreamedEchoService  
{  
    public Stream Echo(Stream data)  
    {  
        MemoryStream dataStorage = new MemoryStream();  
        byte[] byteArray = new byte[8192];  
        int bytesRead = data.Read(byteArray, 0, 8192);  
        while (bytesRead > 0)  
        {  
            dataStorage.Write(byteArray, 0, bytesRead);  
            bytesRead = data.Read(byteArray, 0, 8192);  
        }  
        data.Close();  
        dataStorage.Seek(0, SeekOrigin.Begin);  
  
        return dataStorage;  
    }  
}  
```  
  
## <a name="the-wsstreamedhttpbinding-sample-client"></a>Esempio di Client WSStreamedHttpBinding  
 Il client utilizzato per interagire con il servizio utilizzando `WSStreamedHttpBinding` si trova nella sottodirectory client. Poiché il certificato usato in questo esempio è un certificato di prova creato con Makecert.exe, viene visualizzato un avviso di sicurezza quando si tenta di accedere a un indirizzo HTTPS nel browser, ad esempio https://localhost/servicemodelsamples/service.svc. Per consentire al client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] di lavorare con un certificato di prova, è stato aggiunto altro codice al client per sopprimere l'avviso di sicurezza. Il codice e la classe associata non sono richiesti quando si utilizzano i certificati di produzione.  
  
```  
// WARNING: This code is only required for test certificates such as those created by makecert. It is   
// not recommended for production code.  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```  
  
## <a name="see-also"></a>Vedere anche
