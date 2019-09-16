---
title: 'Procedura: Usare Svcutil.exe per convalidare il codice del servizio compilato'
ms.date: 03/30/2017
ms.assetid: d0d820fb-41c2-45b8-8f22-0fa5aeebbbaa
ms.openlocfilehash: be8755ab4281b40d23ea4c8674c8c4f33631e7b6
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991600"
---
# <a name="how-to-use-svcutilexe-to-validate-compiled-service-code"></a><span data-ttu-id="69f5d-102">Procedura: Usare Svcutil.exe per convalidare il codice del servizio compilato</span><span class="sxs-lookup"><span data-stu-id="69f5d-102">How to: Use Svcutil.exe to Validate Compiled Service Code</span></span>
<span data-ttu-id="69f5d-103">È possibile utilizzare lo [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) per rilevare gli errori nelle configurazioni e nelle implementazioni del servizio senza ospitare il servizio.</span><span class="sxs-lookup"><span data-stu-id="69f5d-103">You can use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to detect errors in service implementations and configurations without hosting the service.</span></span>  
  
### <a name="to-validate-a-service"></a><span data-ttu-id="69f5d-104">Per convalidare un servizio</span><span class="sxs-lookup"><span data-stu-id="69f5d-104">To validate a service</span></span>  
  
1. <span data-ttu-id="69f5d-105">Compilare il servizio in un file eseguibile e in uno o più assembly dipendenti.</span><span class="sxs-lookup"><span data-stu-id="69f5d-105">Compile your service into an executable file and one or more dependent assemblies.</span></span>  
  
2. <span data-ttu-id="69f5d-106">Aprire un prompt dei comandi SDK.</span><span class="sxs-lookup"><span data-stu-id="69f5d-106">Open an SDK command prompt</span></span>  
  
3. <span data-ttu-id="69f5d-107">Al prompt dei comandi, avviare lo strumento Svcutil.exe usando il formato seguente.</span><span class="sxs-lookup"><span data-stu-id="69f5d-107">At the command prompt, launch the Svcutil.exe tool using the following format.</span></span> <span data-ttu-id="69f5d-108">Per ulteriori informazioni sui vari parametri, vedere l'argomento Service Validationsection dell'argomento [ServiceModel Metadata Utility Tool (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) .</span><span class="sxs-lookup"><span data-stu-id="69f5d-108">For more information on the various parameters, see the Service Validationsection of the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) topic.</span></span>  
  
    ```console
    svcutil.exe /validate /serviceName:<serviceConfigName>  <assemblyPath>*  
    ```  
  
     <span data-ttu-id="69f5d-109">È necessario usare l'opzione `/serviceName` per indicare il nome di configurazione del servizio che si desidera convalidare.</span><span class="sxs-lookup"><span data-stu-id="69f5d-109">You must use the `/serviceName` option to indicate the configuration name of the service you want to validate.</span></span>  
  
     <span data-ttu-id="69f5d-110">L'argomento `assemblyPath` specifica il percorso del file eseguibile per il servizio e uno o più assembly che contengono i tipi di servizio da convalidare.</span><span class="sxs-lookup"><span data-stu-id="69f5d-110">The `assemblyPath` argument specifies the path to the executable file for the service and one or more assemblies that contain the service types to be validated.</span></span> <span data-ttu-id="69f5d-111">L'assembly eseguibile deve avere un file di configurazione associato per fornire la configurazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="69f5d-111">The executable assembly must have an associated configuration file to provide the service configuration.</span></span> <span data-ttu-id="69f5d-112">È possibile usare caratteri jolly della riga di comando standard per fornire più assembly.</span><span class="sxs-lookup"><span data-stu-id="69f5d-112">You can use standard command-line wildcards to provide multiple assemblies.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69f5d-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="69f5d-113">Example</span></span>  
 <span data-ttu-id="69f5d-114">Il comando seguente implementa il servizio myServiceName nel file eseguibile myServiceHost.exe.</span><span class="sxs-lookup"><span data-stu-id="69f5d-114">The following command the service myServiceName implemented in the myServiceHost.exe executable file.</span></span>  <span data-ttu-id="69f5d-115">Il file di configurazione per il servizio (myServiceHost.exe.config) viene automaticamente caricato.</span><span class="sxs-lookup"><span data-stu-id="69f5d-115">The configuration file for the service (myServiceHost.exe.config) is automatically loaded.</span></span>  
  
```console  
svcutil /validate /serviceName:myServiceName myServiceHost.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="69f5d-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="69f5d-116">See also</span></span>

- [<span data-ttu-id="69f5d-117">Strumento ServiceModel Metadata Utility Tool (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="69f5d-117">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
