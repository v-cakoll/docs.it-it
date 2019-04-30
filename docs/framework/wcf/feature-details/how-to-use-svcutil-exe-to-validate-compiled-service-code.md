---
title: 'Procedura: Usare Svcutil.exe per convalidare il codice del servizio compilato'
ms.date: 03/30/2017
ms.assetid: d0d820fb-41c2-45b8-8f22-0fa5aeebbbaa
ms.openlocfilehash: 599f5624b7eb0c32cbcc0a78e6c7f989ce470b58
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62038753"
---
# <a name="how-to-use-svcutilexe-to-validate-compiled-service-code"></a><span data-ttu-id="f30d7-102">Procedura: Usare Svcutil.exe per convalidare il codice del servizio compilato</span><span class="sxs-lookup"><span data-stu-id="f30d7-102">How to: Use Svcutil.exe to Validate Compiled Service Code</span></span>
<span data-ttu-id="f30d7-103">È possibile usare la [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) per rilevare errori in configurazioni e le implementazioni del servizio senza ospitare il servizio.</span><span class="sxs-lookup"><span data-stu-id="f30d7-103">You can use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to detect errors in service implementations and configurations without hosting the service.</span></span>  
  
### <a name="to-validate-a-service"></a><span data-ttu-id="f30d7-104">Per convalidare un servizio</span><span class="sxs-lookup"><span data-stu-id="f30d7-104">To validate a service</span></span>  
  
1. <span data-ttu-id="f30d7-105">Compilare il servizio in un file eseguibile e in uno o più assembly dipendenti.</span><span class="sxs-lookup"><span data-stu-id="f30d7-105">Compile your service into an executable file and one or more dependent assemblies.</span></span>  
  
2. <span data-ttu-id="f30d7-106">Aprire un prompt dei comandi SDK.</span><span class="sxs-lookup"><span data-stu-id="f30d7-106">Open an SDK command prompt</span></span>  
  
3. <span data-ttu-id="f30d7-107">Al prompt dei comandi, avviare lo strumento Svcutil.exe usando il formato seguente.</span><span class="sxs-lookup"><span data-stu-id="f30d7-107">At the command prompt, launch the Svcutil.exe tool using the following format.</span></span> <span data-ttu-id="f30d7-108">Per altre informazioni sui vari parametri, vedere la sezione convalida del servizio di [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) argomento.</span><span class="sxs-lookup"><span data-stu-id="f30d7-108">For more information on the various parameters, see the Service Validationsection of the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) topic.</span></span>  
  
    ```  
    svcutil.exe /validate /serviceName:<serviceConfigName>  <assemblyPath>*  
    ```  
  
     <span data-ttu-id="f30d7-109">È necessario usare l'opzione `/serviceName` per indicare il nome di configurazione del servizio che si desidera convalidare.</span><span class="sxs-lookup"><span data-stu-id="f30d7-109">You must use the `/serviceName` option to indicate the configuration name of the service you want to validate.</span></span>  
  
     <span data-ttu-id="f30d7-110">L'argomento `assemblyPath` specifica il percorso del file eseguibile per il servizio e uno o più assembly che contengono i tipi di servizio da convalidare.</span><span class="sxs-lookup"><span data-stu-id="f30d7-110">The `assemblyPath` argument specifies the path to the executable file for the service and one or more assemblies that contain the service types to be validated.</span></span> <span data-ttu-id="f30d7-111">L'assembly eseguibile deve avere un file di configurazione associato per fornire la configurazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="f30d7-111">The executable assembly must have an associated configuration file to provide the service configuration.</span></span> <span data-ttu-id="f30d7-112">È possibile usare caratteri jolly della riga di comando standard per fornire più assembly.</span><span class="sxs-lookup"><span data-stu-id="f30d7-112">You can use standard command-line wildcards to provide multiple assemblies.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f30d7-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="f30d7-113">Example</span></span>  
 <span data-ttu-id="f30d7-114">Il comando seguente implementa il servizio myServiceName nel file eseguibile myServiceHost.exe.</span><span class="sxs-lookup"><span data-stu-id="f30d7-114">The following command the service myServiceName implemented in the myServiceHost.exe executable file.</span></span>  <span data-ttu-id="f30d7-115">Il file di configurazione per il servizio (myServiceHost.exe.config) viene automaticamente caricato.</span><span class="sxs-lookup"><span data-stu-id="f30d7-115">The configuration file for the service (myServiceHost.exe.config) is automatically loaded.</span></span>  
  
```  
svcutil /validate /serviceName:myServiceName myServiceHost.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="f30d7-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f30d7-116">See also</span></span>

- [<span data-ttu-id="f30d7-117">Strumento ServiceModel Metadata Utility Tool (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="f30d7-117">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
