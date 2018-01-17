---
title: Esecuzione side-by-side in-process
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- in-process side-by-side execution
- side-by-side execution, in-process
ms.assetid: 18019342-a810-4986-8ec2-b933a17c2267
caps.latest.revision: "25"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 023a8db1e34498c4c2cbe741225d218280c04e41
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="in-process-side-by-side-execution"></a><span data-ttu-id="1743f-102">Esecuzione side-by-side in-process</span><span class="sxs-lookup"><span data-stu-id="1743f-102">In-Process Side-by-Side Execution</span></span>
<span data-ttu-id="1743f-103">A partire da [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], è possibile usare l'hosting side-by-side in-process per eseguire più versioni di Common Language Runtime (CLR) in un unico processo.</span><span class="sxs-lookup"><span data-stu-id="1743f-103">Starting with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], you can use in-process side-by-side hosting to run multiple versions of the common language runtime (CLR) in a single process.</span></span> <span data-ttu-id="1743f-104">Per impostazione predefinita, i componenti COM gestiti vengono eseguiti con la versione di .NET Framework con cui sono stati compilati, indipendentemente dalla versione di .NET Framework che viene caricata per il processo.</span><span class="sxs-lookup"><span data-stu-id="1743f-104">By default, managed COM components run with the .NET Framework version they were built with, regardless of the .NET Framework version that is loaded for the process.</span></span>  
  
## <a name="background"></a><span data-ttu-id="1743f-105">Sfondo</span><span class="sxs-lookup"><span data-stu-id="1743f-105">Background</span></span>  
 <span data-ttu-id="1743f-106">.NET Framework ha sempre offerto l'hosting side-by-side per applicazioni di codice gestito, ma prima di [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], tale funzionalità non era disponibile per i componenti COM gestiti.</span><span class="sxs-lookup"><span data-stu-id="1743f-106">The .NET Framework has always provided side-by-side hosting for managed code applications, but before the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], it did not provide that functionality for managed COM components.</span></span> <span data-ttu-id="1743f-107">In passato, i componenti COM gestiti che venivano caricati in un processo venivano eseguiti con la versione di runtime già caricata o con l'ultima versione di .NET Framework installata.</span><span class="sxs-lookup"><span data-stu-id="1743f-107">In the past, managed COM components that were loaded into a process ran either with the version of the runtime that was already loaded or with the latest installed version of the .NET Framework.</span></span> <span data-ttu-id="1743f-108">Se tale versione non era compatibile con il componente COM, l'esecuzione di quest'ultimo aveva esito negativo.</span><span class="sxs-lookup"><span data-stu-id="1743f-108">If this version was not compatible with the COM component, the component would fail.</span></span>  
  
 <span data-ttu-id="1743f-109">[!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] offre un nuovo approccio all'hosting side-by-side che assicura quanto segue:</span><span class="sxs-lookup"><span data-stu-id="1743f-109">The [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] provides a new approach to side-by-side hosting that ensures the following:</span></span>  
  
-   <span data-ttu-id="1743f-110">L'installazione di una nuova versione di .NET Framework non ha alcun effetto sulle applicazioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="1743f-110">Installing a new version of the .NET Framework has no effect on existing applications.</span></span>  
  
-   <span data-ttu-id="1743f-111">Le applicazioni vengono eseguite con la versione di .NET Framework con cui sono state compilate.</span><span class="sxs-lookup"><span data-stu-id="1743f-111">Applications run against the version of the .NET Framework that they were built with.</span></span> <span data-ttu-id="1743f-112">Non usano la nuova versione di .NET Framework a meno che non venga espressamente data istruzione in tal senso.</span><span class="sxs-lookup"><span data-stu-id="1743f-112">They do not use the new version of the .NET Framework unless expressly directed to do so.</span></span> <span data-ttu-id="1743f-113">Tuttavia, per le applicazioni è più facile passare all'uso di una nuova versione di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1743f-113">However, it is easier for applications to transition to using a new version of the .NET Framework.</span></span>  
  
## <a name="effects-on-users-and-developers"></a><span data-ttu-id="1743f-114">Effetti su utenti e sviluppatori</span><span class="sxs-lookup"><span data-stu-id="1743f-114">Effects on Users and Developers</span></span>  
  
-   <span data-ttu-id="1743f-115">**Utenti finali e amministratori di sistema**.</span><span class="sxs-lookup"><span data-stu-id="1743f-115">**End users and system administrators**.</span></span> <span data-ttu-id="1743f-116">Tali utenti possono ora avere maggiore certezza che quando installano una nuova versione del runtime, in modo indipendente o con un'applicazione, ciò non avrà alcun impatto sui computer.</span><span class="sxs-lookup"><span data-stu-id="1743f-116">These users can now have greater confidence that when they install a new version of the runtime, either independently or with an application, it will have no impact on their computers.</span></span> <span data-ttu-id="1743f-117">Le applicazioni esistenti continueranno a essere eseguite come in precedenza.</span><span class="sxs-lookup"><span data-stu-id="1743f-117">Existing applications will continue to run as they did before.</span></span>  
  
-   <span data-ttu-id="1743f-118">**Sviluppatori di applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="1743f-118">**Application developers**.</span></span> <span data-ttu-id="1743f-119">L'hosting side-by-side non ha praticamente alcun effetto che possa interessare gli sviluppatori di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="1743f-119">Side-by-side hosting has almost no effect on application developers.</span></span> <span data-ttu-id="1743f-120">Per impostazione predefinita, le applicazioni vengono sempre eseguite con la versione di .NET Framework con cui sono state compilate. Questo non è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="1743f-120">By default, applications always run against the version of the .NET Framework they were built on; this has not changed.</span></span> <span data-ttu-id="1743f-121">Tuttavia, gli sviluppatori possono eseguire l'override di questo comportamento e indirizzare l'applicazione per l'esecuzione in una versione più recente di .NET Framework. Vedere [Scenario 2](#scenarios).</span><span class="sxs-lookup"><span data-stu-id="1743f-121">However, developers can override this behavior and direct the application to run under a newer version of the .NET Framework (see [scenario 2](#scenarios)).</span></span>  
  
-   <span data-ttu-id="1743f-122">**Sviluppatori di librerie e consumer**.</span><span class="sxs-lookup"><span data-stu-id="1743f-122">**Library developers and consumers**.</span></span> <span data-ttu-id="1743f-123">L'hosting side-by-side non risolve i problemi di compatibilità che devono affrontare gli sviluppatori di librerie.</span><span class="sxs-lookup"><span data-stu-id="1743f-123">Side-by-side hosting does not solve the compatibility problems that library developers face.</span></span> <span data-ttu-id="1743f-124">Una libreria che viene caricata direttamente da un'applicazione, tramite un riferimento diretto o mediante una chiamata a <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>, continua a usare il runtime di <xref:System.AppDomain> in cui viene caricata.</span><span class="sxs-lookup"><span data-stu-id="1743f-124">A library that is directly loaded by an application -- either through a direct reference or through an <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> call -- continues to use the runtime of the <xref:System.AppDomain> it is loaded into.</span></span> <span data-ttu-id="1743f-125">È consigliabile testare le librerie con tutte le versioni di .NET Framework che si vuole supportare.</span><span class="sxs-lookup"><span data-stu-id="1743f-125">You should test your libraries against all versions of the .NET Framework that you want to support.</span></span> <span data-ttu-id="1743f-126">Se un'applicazione viene compilata usando il runtime di [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] ma include una libreria che è stata compilata usando un runtime precedente, tale libreria userà anche il runtime di [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1743f-126">If an application is compiled using the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] runtime but includes a library that was built using an earlier runtime, that library will use the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] runtime as well.</span></span> <span data-ttu-id="1743f-127">Tuttavia, se si ha un'applicazione compilata con un runtime precedente e una libreria compilata usando [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], è necessario forzare l'applicazione a usare anche [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]. Vedere [scenario 3](#scenarios).</span><span class="sxs-lookup"><span data-stu-id="1743f-127">However, if you have an application that was built using an earlier runtime and a library that was built using the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], you must force your application to also use the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] (see [scenario 3](#scenarios)).</span></span>  
  
-   <span data-ttu-id="1743f-128">**Sviluppatori di componenti COM gestiti**.</span><span class="sxs-lookup"><span data-stu-id="1743f-128">**Managed COM component developers**.</span></span> <span data-ttu-id="1743f-129">In passato, i componenti COM gestiti venivano eseguiti automaticamente usando la versione più recente del runtime installato nel computer.</span><span class="sxs-lookup"><span data-stu-id="1743f-129">In the past, managed COM components automatically ran using the latest version of the runtime installed on the computer.</span></span> <span data-ttu-id="1743f-130">È ora possibile eseguire i componenti COM con la versione del runtime con cui sono stati compilati.</span><span class="sxs-lookup"><span data-stu-id="1743f-130">You can now execute COM components against the version of the runtime they were built with.</span></span>  
  
     <span data-ttu-id="1743f-131">Come illustrato nella tabella seguente, i componenti compilati con .NET Framework versione 1.1 possono essere eseguiti side-by-side con i componenti della versione 4, ma non possono essere eseguiti con i componenti della versione 2.0, 3.0 o 3.5, perché l'hosting side-by-side non è disponibile per tali versioni.</span><span class="sxs-lookup"><span data-stu-id="1743f-131">As shown by the following table, components that were built with the .NET Framework version 1.1 can run side by side with version 4 components, but they cannot run with version 2.0, 3.0, or 3.5 components, because side-by-side hosting is not available for those versions.</span></span>  
  
    |<span data-ttu-id="1743f-132">Versione di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="1743f-132">.NET Framework version</span></span>|<span data-ttu-id="1743f-133">1.1</span><span class="sxs-lookup"><span data-stu-id="1743f-133">1.1</span></span>|<span data-ttu-id="1743f-134">2.0 - 3.5</span><span class="sxs-lookup"><span data-stu-id="1743f-134">2.0 - 3.5</span></span>|<span data-ttu-id="1743f-135">4</span><span class="sxs-lookup"><span data-stu-id="1743f-135">4</span></span>|  
    |----------------------------|---------|----------------|-------|  
    |<span data-ttu-id="1743f-136">1.1</span><span class="sxs-lookup"><span data-stu-id="1743f-136">1.1</span></span>|<span data-ttu-id="1743f-137">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="1743f-137">Not applicable</span></span>|<span data-ttu-id="1743f-138">No</span><span class="sxs-lookup"><span data-stu-id="1743f-138">No</span></span>|<span data-ttu-id="1743f-139">Yes</span><span class="sxs-lookup"><span data-stu-id="1743f-139">Yes</span></span>|  
    |<span data-ttu-id="1743f-140">2.0 - 3.5</span><span class="sxs-lookup"><span data-stu-id="1743f-140">2.0 - 3.5</span></span>|<span data-ttu-id="1743f-141">No</span><span class="sxs-lookup"><span data-stu-id="1743f-141">No</span></span>|<span data-ttu-id="1743f-142">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="1743f-142">Not applicable</span></span>|<span data-ttu-id="1743f-143">Yes</span><span class="sxs-lookup"><span data-stu-id="1743f-143">Yes</span></span>|  
    |<span data-ttu-id="1743f-144">4</span><span class="sxs-lookup"><span data-stu-id="1743f-144">4</span></span>|<span data-ttu-id="1743f-145">Yes</span><span class="sxs-lookup"><span data-stu-id="1743f-145">Yes</span></span>|<span data-ttu-id="1743f-146">Yes</span><span class="sxs-lookup"><span data-stu-id="1743f-146">Yes</span></span>|<span data-ttu-id="1743f-147">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="1743f-147">Not applicable</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="1743f-148">Le versioni di .NET framework 3.0 e 3.5 sono state compilate in modo incrementale dalla versione 2.0 e non necessitano dell'esecuzione side-by-side.</span><span class="sxs-lookup"><span data-stu-id="1743f-148">.NET Framework versions 3.0 and 3.5 are built incrementally on version 2.0, and do not need to run side by side.</span></span> <span data-ttu-id="1743f-149">Sono praticamente la stessa versione.</span><span class="sxs-lookup"><span data-stu-id="1743f-149">These are inherently the same version.</span></span>  
  
<a name="scenarios"></a>   
## <a name="common-side-by-side-hosting-scenarios"></a><span data-ttu-id="1743f-150">Scenari comuni di hosting side-by-side</span><span class="sxs-lookup"><span data-stu-id="1743f-150">Common Side-by-Side Hosting Scenarios</span></span>  
  
-   <span data-ttu-id="1743f-151">**Scenario 1:** applicazione nativa che usa i componenti COM compilati con versioni precedenti di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1743f-151">**Scenario 1:** Native application that uses COM components built with earlier versions of the .NET Framework.</span></span>  
  
     <span data-ttu-id="1743f-152">Versioni di .NET framework installate: [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] e tutte le altre versioni di .NET Framework usate dai componenti COM.</span><span class="sxs-lookup"><span data-stu-id="1743f-152">.NET Framework versions installed: The [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] and all other versions of the .NET Framework used by the COM components.</span></span>  
  
     <span data-ttu-id="1743f-153">Cosa fare: in questo scenario, non eseguire alcuna operazione.</span><span class="sxs-lookup"><span data-stu-id="1743f-153">What to do: In this scenario, do nothing.</span></span> <span data-ttu-id="1743f-154">I componenti COM verranno eseguiti con la versione di .NET Framework con la quale sono stati registrati.</span><span class="sxs-lookup"><span data-stu-id="1743f-154">The COM components will run with the version of the .NET Framework they were registered with.</span></span>  
  
-   <span data-ttu-id="1743f-155">**Scenario 2**: applicazione gestita compilata con [!INCLUDE[net_v20SP1_short](../../../includes/net-v20sp1-short-md.md)] che si vuole eseguire con [!INCLUDE[dnprdnext](../../../includes/dnprdnext-md.md)], ma che verrà eseguita in [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] se la versione 2.0 non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="1743f-155">**Scenario 2**: Managed application built with the [!INCLUDE[net_v20SP1_short](../../../includes/net-v20sp1-short-md.md)] that you would prefer to run with the [!INCLUDE[dnprdnext](../../../includes/dnprdnext-md.md)], but are willing to run on the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] if version 2.0 is not present.</span></span>  
  
     <span data-ttu-id="1743f-156">Versioni di .NET framework installate: una versione precedente di .NET Framework e [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1743f-156">.NET Framework versions installed: An earlier version of the .NET Framework and the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)].</span></span>  
  
     <span data-ttu-id="1743f-157">Cosa fare: nel [file di configurazione dell'applicazione](../../../docs/framework/configure-apps/index.md) contenuto nella directory dell'applicazione usare [l'elemento \<startup>](../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) e [l'elemento \<supportedRuntime>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) impostati nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="1743f-157">What to do: In the [application configuration file](../../../docs/framework/configure-apps/index.md) in the application directory, use the [\<startup> element](../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) and the [\<supportedRuntime> element](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) set as follows:</span></span>  
  
    ```xml  
    <configuration>  
      <startup >  
        <supportedRuntime version="v2.0.50727" />  
        <supportedRuntime version="v4.0" />  
      </startup>  
    </configuration>  
    ```  
  
-   <span data-ttu-id="1743f-158">**Scenario 3:** applicazione nativa che usa i componenti COM compilati con versioni precedenti di .NET Framework che si vuole eseguire con [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1743f-158">**Scenario 3:** Native application that uses COM components built with earlier versions of the .NET Framework that you want to run with the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)].</span></span>  
  
     <span data-ttu-id="1743f-159">Versioni di .NET framework installate: [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1743f-159">.NET Framework versions installed: The [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)].</span></span>  
  
     <span data-ttu-id="1743f-160">Cosa fare: nel file di configurazione dell'applicazione contenuto nella directory dell'applicazione usare l'elemento `<startup>` con l'attributo `useLegacyV2RuntimeActivationPolicy` impostato su `true` e l'elemento `<supportedRuntime>` impostato nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="1743f-160">What to do: In the application configuration file in the application directory, use the `<startup>` element with the `useLegacyV2RuntimeActivationPolicy` attribute set to `true` and the `<supportedRuntime>` element set as follows:</span></span>  
  
    ```xml  
    <configuration>  
      <startup useLegacyV2RuntimeActivationPolicy="true">  
        <supportedRuntime version="v4.0" />  
      </startup>  
    </configuration>  
    ```  
  
## <a name="example"></a><span data-ttu-id="1743f-161">Esempio</span><span class="sxs-lookup"><span data-stu-id="1743f-161">Example</span></span>  
 <span data-ttu-id="1743f-162">Nell'esempio seguente viene illustrato un host COM non gestito che esegue un componente COM gestito usando la versione di .NET Framework con cui è stato compilato il componente da usare.</span><span class="sxs-lookup"><span data-stu-id="1743f-162">The following example demonstrates an unmanaged COM host that is running a managed COM component by using the version of the .NET Framework that the component was compiled to use.</span></span>  
  
 <span data-ttu-id="1743f-163">Per eseguire l'esempio riportato di seguito, compilare e registrare il seguente componente COM gestito utilizzando [!INCLUDE[net_v35_long](../../../includes/net-v35-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1743f-163">To run the following example, compile and register the following managed COM component using the [!INCLUDE[net_v35_long](../../../includes/net-v35-long-md.md)].</span></span> <span data-ttu-id="1743f-164">Per registrare il componente, nel menu **Progetto** scegliere **Proprietà**, fare clic sulla scheda **Build**, quindi selezionare la casella di controllo **Registra per interoperabilità COM**.</span><span class="sxs-lookup"><span data-stu-id="1743f-164">To register the component, on the **Project** menu, click **Properties**, click the **Build** tab, and then select the **Register for COM interop** check box.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.Runtime.InteropServices;  
  
namespace BasicComObject  
{  
    [ComVisible(true), Guid("9C99C4B5-CA54-4c58-8988-49B6811BA53B")]  
    public class MyObject : SimpleObjectModel.IPrintInfo  
    {  
        public MyObject()  
        {  
        }  
        public void PrintInfo()  
        {  
            Console.WriteLine("MyObject was activated in {0} runtime in:\n\tAppDomain {1}:{2}", System.Runtime.InteropServices.RuntimeEnvironment.GetSystemVersion(), AppDomain.CurrentDomain.Id, AppDomain.CurrentDomain.FriendlyName);  
        }  
    }  
}  
```  
  
 <span data-ttu-id="1743f-165">Compilare la seguente applicazione C++ non gestita, che attiva l'oggetto COM che viene creato dall'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="1743f-165">Compile the following unmanaged C++ application, which activates the COM object that is created by the previous example.</span></span>  
  
```  
#include "stdafx.h"  
#include <string>  
#include <iostream>  
#include <objbase.h>  
#include <string.h>  
#include <process.h>  
  
using namespace std;  
  
int _tmain(int argc, _TCHAR* argv[])  
{  
    char input;  
    CoInitialize(NULL) ;  
    CLSID clsid;  
    HRESULT hr;  
    HRESULT clsidhr = CLSIDFromString(L"{9C99C4B5-CA54-4c58-8988-49B6811BA53B}",&clsid);  
    hr = -1;  
    if (FAILED(clsidhr))  
    {  
        printf("Failed to construct CLSID from String\n");  
    }  
    UUID id = __uuidof(IUnknown);  
    IUnknown * pUnk = NULL;  
    hr = ::CoCreateInstance(clsid,NULL,CLSCTX_INPROC_SERVER,id,(void **) &pUnk);  
    if (FAILED(hr))  
    {  
        printf("Failed CoCreateInstance\n");  
    }else  
    {  
        pUnk->AddRef();  
        printf("Succeeded\n");  
    }  
  
    DISPID dispid;  
    IDispatch* pPrintInfo;  
    pUnk->QueryInterface(IID_IDispatch, (void**)&pPrintInfo);  
    OLECHAR FAR* szMethod[1];  
    szMethod[0]=OLESTR("PrintInfo");   
    hr = pPrintInfo->GetIDsOfNames(IID_NULL,szMethod, 1, LOCALE_SYSTEM_DEFAULT, &dispid);  
    DISPPARAMS dispparams;  
    dispparams.cNamedArgs = 0;  
    dispparams.cArgs = 0;  
    VARIANTARG* pvarg = NULL;  
    EXCEPINFO * pexcepinfo = NULL;  
    WORD wFlags = DISPATCH_METHOD ;  
;  
    LPVARIANT pvRet = NULL;  
    UINT * pnArgErr = NULL;  
    hr = pPrintInfo->Invoke(dispid,IID_NULL, LOCALE_USER_DEFAULT, wFlags,  
        &dispparams, pvRet, pexcepinfo, pnArgErr);  
    printf("Press Enter to exit");  
    scanf_s("%c",&input);  
    CoUninitialize();  
    return 0;  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="1743f-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1743f-166">See Also</span></span>  
 [<span data-ttu-id="1743f-167">Elemento \<startup</span><span class="sxs-lookup"><span data-stu-id="1743f-167">\<startup> Element</span></span>](../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)  
 [<span data-ttu-id="1743f-168">Elemento \<supportedRuntime></span><span class="sxs-lookup"><span data-stu-id="1743f-168">\<supportedRuntime> Element</span></span>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)
