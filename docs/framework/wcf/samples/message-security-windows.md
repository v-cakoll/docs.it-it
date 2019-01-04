---
title: Sicurezza dei messaggi di Windows
ms.date: 03/30/2017
helpviewer_keywords:
- WS Security
ms.assetid: d2221d1c-c9cb-48d1-b044-a3b4445c7f05
ms.openlocfilehash: e5bb27980f38237f69f77721578f30df3830ade2
ms.sourcegitcommit: 3b9b7ae6771712337d40374d2fef6b25b0d53df6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/04/2019
ms.locfileid: "54029645"
---
# <a name="message-security-windows"></a><span data-ttu-id="296b6-102">Sicurezza dei messaggi di Windows</span><span class="sxs-lookup"><span data-stu-id="296b6-102">Message Security Windows</span></span>
<span data-ttu-id="296b6-103">In questo esempio viene illustrato come configurare un'associazione <xref:System.ServiceModel.WSHttpBinding> per usare la sicurezza a livello di messaggio con autenticazione Windows.</span><span class="sxs-lookup"><span data-stu-id="296b6-103">This sample demonstrates how to configure a <xref:System.ServiceModel.WSHttpBinding> binding to use message-level security with Windows authentication.</span></span> <span data-ttu-id="296b6-104">In questo esempio si basa sul [introduttiva](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="296b6-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span> <span data-ttu-id="296b6-105">In questo esempio, il servizio è ospitato da Internet Information Services (IIS) e il client è un'applicazione console (.exe).</span><span class="sxs-lookup"><span data-stu-id="296b6-105">In this sample, the service is hosted in Internet Information Services (IIS) and the client is a console application (.exe).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="296b6-106">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="296b6-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="296b6-107">La sicurezza predefinita per il [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) sicurezza dei messaggi utilizzando l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="296b6-107">The default security for the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) is message security using Windows authentication.</span></span> <span data-ttu-id="296b6-108">Impostare in modo esplicito i file di configurazione in questo esempio il `mode` attributo del [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) a `Message` e la `clientCredentialType` dell'attributo `Windows`.</span><span class="sxs-lookup"><span data-stu-id="296b6-108">The configuration files in this sample explicitly set the `mode` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) to `Message` and the `clientCredentialType` attribute to `Windows`.</span></span> <span data-ttu-id="296b6-109">Questi valori sono i valori predefiniti per questa associazione, ma sono stati configurati in modo esplicito, come illustrato nell'esempio di configurazione seguente per descriverne l'uso.</span><span class="sxs-lookup"><span data-stu-id="296b6-109">These values are the default values for this binding, but they have been explicitly configured, as shown in the following sample configuration to demonstrate their use.</span></span>  
  
```xml  
<bindings>  
    <wsHttpBinding>  
        <binding>  
            <security mode="Message">  
                <message clientCredentialType="Windows"/>  
            </security>  
        </binding>  
    </wsHttpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="296b6-110">La configurazione dell'endpoint client è costituita da un indirizzo assoluto per l'endpoint del servizio, l'associazione e il contratto.</span><span class="sxs-lookup"><span data-stu-id="296b6-110">The client endpoint configuration consists of an absolute address for the service endpoint, the binding, and the contract.</span></span> <span data-ttu-id="296b6-111">L'associazione client viene configurata con la `securityMode` e la `authenticationMode` appropriate.</span><span class="sxs-lookup"><span data-stu-id="296b6-111">The client binding is configured with the appropriate `securityMode` and `authenticationMode`.</span></span>  
  
```xml  
<system.serviceModel>  
  <client>  
    <endpoint address=  
            "http://localhost/servicemodelsamples/service.svc"   
            binding="wsHttpBinding"   
            bindingConfiguration="Binding1"   
            contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  </client>  
  
  <bindings>  
    <wsHttpBinding>  
      <!-- The default security for the WSHttpBinding is -->  
      <!-- Message security using Windows authentication. -->  
      <!-- This configuration explicitly defines the security mode -->  
      <!-- as Message and the clientCredentialType as Windows -->  
      <!-- for demonstration purposes. -->  
      <binding name="Binding1">  
        <security mode="Message">  
          <message clientCredentialType="Windows"/>  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="296b6-112">Il codice sorgente del servizio è stato modificato per illustrare come <xref:System.ServiceModel.OperationContext.ServiceSecurityContext%2A> può essere usato per accedere all'identità del chiamante.</span><span class="sxs-lookup"><span data-stu-id="296b6-112">The service source code has been modified to demonstrate how the <xref:System.ServiceModel.OperationContext.ServiceSecurityContext%2A> can be used to access the identity of the caller.</span></span>  

```csharp
public string GetCallerIdentity()  
{  
    // The Windows identity of the caller can be accessed on the ServiceSecurityContext.WindowsIdentity.  
    return OperationContext.Current.ServiceSecurityContext.WindowsIdentity.Name;  
}  
```

 <span data-ttu-id="296b6-113">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="296b6-113">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="296b6-114">Il primo metodo chiamato, `GetCallerIdentity`, restituisce il nome dell'identità del chiamante al client.</span><span class="sxs-lookup"><span data-stu-id="296b6-114">The first method called - `GetCallerIdentity` - returns the name of the caller identity back to the client.</span></span> <span data-ttu-id="296b6-115">Premere INVIO nella finestra della console per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="296b6-115">Press ENTER in the console window to shut down the client.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="296b6-116">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="296b6-116">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="296b6-117">Assicurarsi di avere eseguito il [monouso procedura di installazione per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="296b6-117">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="296b6-118">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="296b6-118">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="296b6-119">Per eseguire l'esempio in una configurazione singola o tra computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="296b6-119">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="296b6-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="296b6-120">See Also</span></span>
