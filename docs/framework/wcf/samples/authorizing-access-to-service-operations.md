---
title: Autorizzazione dell'accesso alle operazioni del servizio
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, authorizing access sample
- Authorizing Access To Service Operations Sample [Windows Communication Foundation]
- authorization, Windows Communication Foundation sample
ms.assetid: ddcfdaa5-8b2e-4e13-bd85-887209dc6328
ms.openlocfilehash: 3097c86f50a75dec8a649ca4e1edd2511a046ca8
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84585532"
---
# <a name="authorizing-access-to-service-operations"></a><span data-ttu-id="96e7c-102">Autorizzazione dell'accesso alle operazioni del servizio</span><span class="sxs-lookup"><span data-stu-id="96e7c-102">Authorizing Access to Service Operations</span></span>
<span data-ttu-id="96e7c-103">In questo esempio viene illustrato come utilizzare [\<serviceAuthorization>](../../configure-apps/file-schema/wcf/serviceauthorization-element.md) per consentire l'utilizzo dell' <xref:System.Security.Permissions.PrincipalPermissionAttribute> attributo per autorizzare l'accesso alle operazioni del servizio.</span><span class="sxs-lookup"><span data-stu-id="96e7c-103">This sample demonstrates how to use the [\<serviceAuthorization>](../../configure-apps/file-schema/wcf/serviceauthorization-element.md) to enable use of the <xref:System.Security.Permissions.PrincipalPermissionAttribute> attribute to authorize access to service operations.</span></span> <span data-ttu-id="96e7c-104">Questo esempio è basato sull'esempio [Introduzione](getting-started-sample.md) .</span><span class="sxs-lookup"><span data-stu-id="96e7c-104">This sample is based on the [Getting Started](getting-started-sample.md) sample.</span></span> <span data-ttu-id="96e7c-105">Il servizio e il client sono configurati utilizzando [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="96e7c-105">The service and client are configured using the [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md).</span></span> <span data-ttu-id="96e7c-106">L' `mode` attributo di [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) è stato impostato su `Message` e `clientCredentialType` è stato impostato su `Windows` .</span><span class="sxs-lookup"><span data-stu-id="96e7c-106">The `mode` attribute of the [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) has been set to `Message` and `clientCredentialType` has been set to `Windows`.</span></span> <span data-ttu-id="96e7c-107"><xref:System.Security.Permissions.PrincipalPermissionAttribute> viene applicato a ogni metodo del servizio e usato per limitare l'accesso alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="96e7c-107">The <xref:System.Security.Permissions.PrincipalPermissionAttribute> is applied to each service method and used to restrict access to each operation.</span></span> <span data-ttu-id="96e7c-108">Il chiamante deve essere un amministratore Windows per accedere a tutte le operazioni.</span><span class="sxs-lookup"><span data-stu-id="96e7c-108">The caller must be a Windows administrator to access each operation.</span></span>  
  
 <span data-ttu-id="96e7c-109">In questo esempio, il client è un'applicazione console (.exe) e il servizio è ospitato da Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="96e7c-109">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="96e7c-110">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="96e7c-110">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="96e7c-111">Il file di configurazione del servizio usa [\<serviceAuthorization>](../../configure-apps/file-schema/wcf/serviceauthorization-element.md) per impostare l' `principalPermissionMode` attributo:</span><span class="sxs-lookup"><span data-stu-id="96e7c-111">The service configuration file uses the [\<serviceAuthorization>](../../configure-apps/file-schema/wcf/serviceauthorization-element.md) to set the `principalPermissionMode` attribute:</span></span>  
  
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
  
 <span data-ttu-id="96e7c-112">L'impostazione della `principalPermissionMode` su `UseWindowsGroups` abilita l'uso di <xref:System.Security.Permissions.PrincipalPermissionAttribute> basato sui nomi dei gruppi di Windows.</span><span class="sxs-lookup"><span data-stu-id="96e7c-112">Setting the `principalPermissionMode` to `UseWindowsGroups` enables the use of <xref:System.Security.Permissions.PrincipalPermissionAttribute> based on Windows group names.</span></span>  
  
 <span data-ttu-id="96e7c-113"><xref:System.Security.Permissions.PrincipalPermissionAttribute> viene applicato a ogni operazione per richiedere che il chiamante appartenga al gruppo Administrators di Windows, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="96e7c-113">The <xref:System.Security.Permissions.PrincipalPermissionAttribute> is applied to each operation to require the caller to be part of the Windows administrators group, as shown in the following sample code.</span></span>  
  
```csharp
[PrincipalPermission(SecurityAction.Demand,
                             Role = "Builtin\\Administrators")]  
public double Add(double n1, double n2)  
{  
    double result = n1 + n2;  
    return result;  
}  
```  
  
 <span data-ttu-id="96e7c-114">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="96e7c-114">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="96e7c-115">Il client comunica correttamente con ogni operazione se viene eseguito con un account che appartiene al gruppo Administrators. In caso contrario, l'accesso viene negato.</span><span class="sxs-lookup"><span data-stu-id="96e7c-115">The client successfully communicates with each operation if it is running under an account that is part of the Administrators group; otherwise, access is denied.</span></span> <span data-ttu-id="96e7c-116">Per sperimentare un errore di autorizzazione, eseguire il client con un account che non appartiene al gruppo Administrators.</span><span class="sxs-lookup"><span data-stu-id="96e7c-116">To experiment with authorization failure, run the client under an account that is not part of the Administrators group.</span></span> <span data-ttu-id="96e7c-117">Premere INVIO nella finestra della console per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="96e7c-117">Press ENTER in the console window to shut down the client.</span></span>  
  
 <span data-ttu-id="96e7c-118">Un servizio può ricevere una notifica di errori di autorizzazione implementando un <xref:System.ServiceModel.Dispatcher.IErrorHandler>.</span><span class="sxs-lookup"><span data-stu-id="96e7c-118">A service can be notified of authorization failures by implementing an <xref:System.ServiceModel.Dispatcher.IErrorHandler>.</span></span> <span data-ttu-id="96e7c-119">Per informazioni sull'implementazione di, vedere [estensione del controllo sulla gestione degli errori e creazione di report](extending-control-over-error-handling-and-reporting.md) `IErrorHandler` .</span><span class="sxs-lookup"><span data-stu-id="96e7c-119">See [Extending Control Over Error Handling and Reporting](extending-control-over-error-handling-and-reporting.md) for information about implementing `IErrorHandler`.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="96e7c-120">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="96e7c-120">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="96e7c-121">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="96e7c-121">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="96e7c-122">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="96e7c-122">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="96e7c-123">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="96e7c-123">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
