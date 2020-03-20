---
title: Autorizzazione dell'accesso alle operazioni del servizio
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, authorizing access sample
- Authorizing Access To Service Operations Sample [Windows Communication Foundation]
- authorization, Windows Communication Foundation sample
ms.assetid: ddcfdaa5-8b2e-4e13-bd85-887209dc6328
ms.openlocfilehash: c2ad6977674666ef65df1ea4cfe58cfd4bff8b69
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183919"
---
# <a name="authorizing-access-to-service-operations"></a><span data-ttu-id="ef5d1-102">Autorizzazione dell'accesso alle operazioni del servizio</span><span class="sxs-lookup"><span data-stu-id="ef5d1-102">Authorizing Access to Service Operations</span></span>
<span data-ttu-id="ef5d1-103">In questo esempio viene illustrato come utilizzare il <xref:System.Security.Permissions.PrincipalPermissionAttribute> [ \<>serviceAuthorization](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) per consentire l'utilizzo dell'attributo per autorizzare l'accesso alle operazioni del servizio.</span><span class="sxs-lookup"><span data-stu-id="ef5d1-103">This sample demonstrates how to use the [\<serviceAuthorization>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) to enable use of the <xref:System.Security.Permissions.PrincipalPermissionAttribute> attribute to authorize access to service operations.</span></span> <span data-ttu-id="ef5d1-104">Questo esempio è basato sull'esempio [introduttivo.](../../../../docs/framework/wcf/samples/getting-started-sample.md)</span><span class="sxs-lookup"><span data-stu-id="ef5d1-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) sample.</span></span> <span data-ttu-id="ef5d1-105">Il servizio e il client vengono configurati utilizzando il [ \<>wsHttpBinding ](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="ef5d1-105">The service and client are configured using the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span> <span data-ttu-id="ef5d1-106">`mode` L'attributo [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) del>di `Message` sicurezza è stato impostato su ed `clientCredentialType` è stato impostato su `Windows`.</span><span class="sxs-lookup"><span data-stu-id="ef5d1-106">The `mode` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) has been set to `Message` and `clientCredentialType` has been set to `Windows`.</span></span> <span data-ttu-id="ef5d1-107"><xref:System.Security.Permissions.PrincipalPermissionAttribute> viene applicato a ogni metodo del servizio e usato per limitare l'accesso alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="ef5d1-107">The <xref:System.Security.Permissions.PrincipalPermissionAttribute> is applied to each service method and used to restrict access to each operation.</span></span> <span data-ttu-id="ef5d1-108">Il chiamante deve essere un amministratore Windows per accedere a tutte le operazioni.</span><span class="sxs-lookup"><span data-stu-id="ef5d1-108">The caller must be a Windows administrator to access each operation.</span></span>  
  
 <span data-ttu-id="ef5d1-109">In questo esempio, il client è un'applicazione console (.exe) e il servizio è ospitato da Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="ef5d1-109">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ef5d1-110">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="ef5d1-110">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="ef5d1-111">Il file di configurazione del servizio `principalPermissionMode` utilizza il [ \<>serviceAuthorization](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) per impostare l'attributo:The service configuration file uses the serviceAuthorization>to set the attribute:</span><span class="sxs-lookup"><span data-stu-id="ef5d1-111">The service configuration file uses the [\<serviceAuthorization>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) to set the `principalPermissionMode` attribute:</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior>
      <!-- The serviceAuthorization behavior sets the  
           principalPermissionMode to UseWindowsGroups.  
           This puts a WindowsPrincipal on the current thread when a   
           service is invoked. -->  
      <serviceAuthorization principalPermissionMode="UseWindowsGroups" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="ef5d1-112">L'impostazione della `principalPermissionMode` su `UseWindowsGroups` abilita l'uso di <xref:System.Security.Permissions.PrincipalPermissionAttribute> basato sui nomi dei gruppi di Windows.</span><span class="sxs-lookup"><span data-stu-id="ef5d1-112">Setting the `principalPermissionMode` to `UseWindowsGroups` enables the use of <xref:System.Security.Permissions.PrincipalPermissionAttribute> based on Windows group names.</span></span>  
  
 <span data-ttu-id="ef5d1-113"><xref:System.Security.Permissions.PrincipalPermissionAttribute> viene applicato a ogni operazione per richiedere che il chiamante appartenga al gruppo Administrators di Windows, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="ef5d1-113">The <xref:System.Security.Permissions.PrincipalPermissionAttribute> is applied to each operation to require the caller to be part of the Windows administrators group, as shown in the following sample code.</span></span>  
  
```csharp
[PrincipalPermission(SecurityAction.Demand,
                             Role = "Builtin\\Administrators")]  
public double Add(double n1, double n2)  
{  
    double result = n1 + n2;  
    return result;  
}  
```  
  
 <span data-ttu-id="ef5d1-114">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="ef5d1-114">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="ef5d1-115">Il client comunica correttamente con ogni operazione se viene eseguito con un account che appartiene al gruppo Administrators. In caso contrario, l'accesso viene negato.</span><span class="sxs-lookup"><span data-stu-id="ef5d1-115">The client successfully communicates with each operation if it is running under an account that is part of the Administrators group; otherwise, access is denied.</span></span> <span data-ttu-id="ef5d1-116">Per sperimentare un errore di autorizzazione, eseguire il client con un account che non appartiene al gruppo Administrators.</span><span class="sxs-lookup"><span data-stu-id="ef5d1-116">To experiment with authorization failure, run the client under an account that is not part of the Administrators group.</span></span> <span data-ttu-id="ef5d1-117">Premere INVIO nella finestra della console per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="ef5d1-117">Press ENTER in the console window to shut down the client.</span></span>  
  
 <span data-ttu-id="ef5d1-118">Un servizio può ricevere una notifica di errori di autorizzazione implementando un <xref:System.ServiceModel.Dispatcher.IErrorHandler>.</span><span class="sxs-lookup"><span data-stu-id="ef5d1-118">A service can be notified of authorization failures by implementing an <xref:System.ServiceModel.Dispatcher.IErrorHandler>.</span></span> <span data-ttu-id="ef5d1-119">Per [Extending Control Over Error Handling and Reporting](../../../../docs/framework/wcf/samples/extending-control-over-error-handling-and-reporting.md) informazioni sull'implementazione `IErrorHandler`di .</span><span class="sxs-lookup"><span data-stu-id="ef5d1-119">See [Extending Control Over Error Handling and Reporting](../../../../docs/framework/wcf/samples/extending-control-over-error-handling-and-reporting.md) for information about implementing `IErrorHandler`.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ef5d1-120">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="ef5d1-120">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="ef5d1-121">Assicurarsi di aver eseguito la procedura di [installazione una tantera per Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ef5d1-121">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="ef5d1-122">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ef5d1-122">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="ef5d1-123">Per eseguire l'esempio in una configurazione a singolo o tra computer, seguire le istruzioni in Esecuzione di [Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ef5d1-123">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
