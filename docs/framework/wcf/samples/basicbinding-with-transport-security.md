---
title: BasicBinding con sicurezza del trasporto
ms.date: 03/30/2017
ms.assetid: f49b1de6-0254-4362-8ef2-fccd8ff9688b
ms.openlocfilehash: bba185cdd9aa61975cbe4e93720f4b3377b475b3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59771010"
---
# <a name="basicbinding-with-transport-security"></a>BasicBinding con sicurezza del trasporto
Questo esempio dimostra l'uso della sicurezza del trasporto SSL con l'associazione di base. In questo esempio si basa sul [introduttiva](../../../../docs/framework/wcf/samples/getting-started-sample.md) che implementa un servizio di calcolatrice.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Basic\TransportSecurity`  
  
## <a name="sample-details"></a>Dettagli dell'esempio  
 Per impostazione predefinita, l'associazione di base supporta la comunicazione HTTP. L'esempio illustra come abilitare sicurezza del trasporto per l'associazione di base. Prima di eseguire l'esempio, è necessario creare un certificato e assegnarlo usando la Procedura guidata certificati server Web.  
  
> [!NOTE]
>  La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
 È identico a quello del codice del programma nell'esempio il [introduttiva](../../../../docs/framework/wcf/samples/getting-started-sample.md) servizio. Le definizioni dell'endpoint e dell'associazione nelle impostazioni del file di configurazione sono state modificate per consentire la comunicazione protetta, come illustrato nella configurazione di esempio seguente.  
  
```xml  
<system.serviceModel>  
  <services>  
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"  
             behaviorConfiguration="CalculatorServiceBehavior">  
      <endpoint address=""  
                binding="basicHttpBinding"  
                bindingConfiguration="Binding1"   
                contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </service>  
   </services>  
  <bindings>  
    <basicHttpBinding>  
      <!-- Configure basicHttpBinding with Transport security -->  
      <!-- mode and clientCredentialType set to None. -->  
      <binding name="Binding1">  
        <security mode="Transport">  
          <transport clientCredentialType="None"/>  
        </security>  
      </binding>  
    </basicHttpBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
 Poiché il certificato usato in questo esempio è un certificato di prova creato con Makecert.exe, viene visualizzato un avviso di sicurezza quando si tenta di accedere a HTTPS: indirizzo nel browser, ad esempio https://localhost/servicemodelsamples/service.svc. Per consentire al client di Windows Communication Foundation (WCF) lavorare con un certificato di test, viene aggiunto ulteriore codice per il client per sopprimere l'avviso di sicurezza. Il codice e la classe associata non sono necessari quando si usano certificati reali.  

```csharp
// This code is required only for test certificates such as those   
// created by Makecert.exe.  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```

 Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client. Premere INVIO nella finestra del client per arrestare il client.  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Installare [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 usando il comando seguente:  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. Assicurarsi di avere eseguito il [monouso procedura di installazione per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
3. Assicurarsi di avere eseguito il [istruzioni di installazione certificato Server Internet Information Services (IIS)](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).  
  
4. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
5. Per eseguire l'esempio in una configurazione singola o tra computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
