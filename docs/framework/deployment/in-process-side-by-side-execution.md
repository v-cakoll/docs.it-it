---
title: Esecuzione side-by-side in-process
ms.date: 03/30/2017
helpviewer_keywords:
- in-process side-by-side execution
- side-by-side execution, in-process
ms.assetid: 18019342-a810-4986-8ec2-b933a17c2267
ms.openlocfilehash: 0c699f90143a87b7e7bee24c892efe2936a9399e
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716474"
---
# <a name="in-process-side-by-side-execution"></a><span data-ttu-id="f9c16-102">Esecuzione side-by-side in-process</span><span class="sxs-lookup"><span data-stu-id="f9c16-102">In-Process Side-by-Side Execution</span></span>
<span data-ttu-id="f9c16-103">A partire da .NET Framework 4, è possibile usare l'hosting side-by-side in-process per eseguire più versioni di Common Language Runtime (CLR) in un unico processo.</span><span class="sxs-lookup"><span data-stu-id="f9c16-103">Starting with the .NET Framework 4, you can use in-process side-by-side hosting to run multiple versions of the common language runtime (CLR) in a single process.</span></span> <span data-ttu-id="f9c16-104">Per impostazione predefinita, i componenti COM gestiti vengono eseguiti con la versione di .NET Framework con cui sono stati compilati, indipendentemente dalla versione di .NET Framework che viene caricata per il processo.</span><span class="sxs-lookup"><span data-stu-id="f9c16-104">By default, managed COM components run with the .NET Framework version they were built with, regardless of the .NET Framework version that is loaded for the process.</span></span>  
  
## <a name="background"></a><span data-ttu-id="f9c16-105">Informazioni di background sul</span><span class="sxs-lookup"><span data-stu-id="f9c16-105">Background</span></span>  
 <span data-ttu-id="f9c16-106">.NET Framework ha sempre offerto l'hosting side-by-side per applicazioni di codice gestito, ma prima di .NET Framework 4 tale funzionalità non era disponibile per i componenti COM gestiti.</span><span class="sxs-lookup"><span data-stu-id="f9c16-106">The .NET Framework has always provided side-by-side hosting for managed code applications, but before the .NET Framework 4, it did not provide that functionality for managed COM components.</span></span> <span data-ttu-id="f9c16-107">In passato, i componenti COM gestiti che venivano caricati in un processo venivano eseguiti con la versione di runtime già caricata o con l'ultima versione di .NET Framework installata.</span><span class="sxs-lookup"><span data-stu-id="f9c16-107">In the past, managed COM components that were loaded into a process ran either with the version of the runtime that was already loaded or with the latest installed version of the .NET Framework.</span></span> <span data-ttu-id="f9c16-108">Se tale versione non era compatibile con il componente COM, l'esecuzione di quest'ultimo aveva esito negativo.</span><span class="sxs-lookup"><span data-stu-id="f9c16-108">If this version was not compatible with the COM component, the component would fail.</span></span>  
  
 <span data-ttu-id="f9c16-109">.NET Framework 4 offre un nuovo approccio all'hosting side-by-side che assicura quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f9c16-109">The .NET Framework 4 provides a new approach to side-by-side hosting that ensures the following:</span></span>  
  
- <span data-ttu-id="f9c16-110">L'installazione di una nuova versione di .NET Framework non ha alcun effetto sulle applicazioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="f9c16-110">Installing a new version of the .NET Framework has no effect on existing applications.</span></span>  
  
- <span data-ttu-id="f9c16-111">Le applicazioni vengono eseguite con la versione di .NET Framework con cui sono state compilate.</span><span class="sxs-lookup"><span data-stu-id="f9c16-111">Applications run against the version of the .NET Framework that they were built with.</span></span> <span data-ttu-id="f9c16-112">Non usano la nuova versione di .NET Framework a meno che non venga espressamente data istruzione in tal senso.</span><span class="sxs-lookup"><span data-stu-id="f9c16-112">They do not use the new version of the .NET Framework unless expressly directed to do so.</span></span> <span data-ttu-id="f9c16-113">Tuttavia, per le applicazioni è più facile passare all'uso di una nuova versione di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f9c16-113">However, it is easier for applications to transition to using a new version of the .NET Framework.</span></span>  
  
## <a name="effects-on-users-and-developers"></a><span data-ttu-id="f9c16-114">Effetti su utenti e sviluppatori</span><span class="sxs-lookup"><span data-stu-id="f9c16-114">Effects on Users and Developers</span></span>  
  
- <span data-ttu-id="f9c16-115">**Utenti finali e amministratori di sistema**.</span><span class="sxs-lookup"><span data-stu-id="f9c16-115">**End users and system administrators**.</span></span> <span data-ttu-id="f9c16-116">Tali utenti possono ora avere maggiore certezza che quando installano una nuova versione del runtime, in modo indipendente o con un'applicazione, ciò non avrà alcun impatto sui computer.</span><span class="sxs-lookup"><span data-stu-id="f9c16-116">These users can now have greater confidence that when they install a new version of the runtime, either independently or with an application, it will have no impact on their computers.</span></span> <span data-ttu-id="f9c16-117">Le applicazioni esistenti continueranno a essere eseguite come in precedenza.</span><span class="sxs-lookup"><span data-stu-id="f9c16-117">Existing applications will continue to run as they did before.</span></span>  
  
- <span data-ttu-id="f9c16-118">**Sviluppatori di applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="f9c16-118">**Application developers**.</span></span> <span data-ttu-id="f9c16-119">L'hosting side-by-side non ha praticamente alcun effetto che possa interessare gli sviluppatori di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="f9c16-119">Side-by-side hosting has almost no effect on application developers.</span></span> <span data-ttu-id="f9c16-120">Per impostazione predefinita, le applicazioni vengono sempre eseguite con la versione di .NET Framework con cui sono state compilate. Questo non è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="f9c16-120">By default, applications always run against the version of the .NET Framework they were built on; this has not changed.</span></span> <span data-ttu-id="f9c16-121">Tuttavia, gli sviluppatori possono eseguire l'override di questo comportamento e indirizzare l'applicazione per l'esecuzione in una versione più recente di .NET Framework. Vedere [Scenario 2](#scenarios).</span><span class="sxs-lookup"><span data-stu-id="f9c16-121">However, developers can override this behavior and direct the application to run under a newer version of the .NET Framework (see [scenario 2](#scenarios)).</span></span>  
  
- <span data-ttu-id="f9c16-122">**Sviluppatori di librerie e consumer**.</span><span class="sxs-lookup"><span data-stu-id="f9c16-122">**Library developers and consumers**.</span></span> <span data-ttu-id="f9c16-123">L'hosting side-by-side non risolve i problemi di compatibilità che devono affrontare gli sviluppatori di librerie.</span><span class="sxs-lookup"><span data-stu-id="f9c16-123">Side-by-side hosting does not solve the compatibility problems that library developers face.</span></span> <span data-ttu-id="f9c16-124">Una libreria che viene caricata direttamente da un'applicazione, tramite un riferimento diretto o mediante una chiamata a <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>, continua a usare il runtime di <xref:System.AppDomain> in cui viene caricata.</span><span class="sxs-lookup"><span data-stu-id="f9c16-124">A library that is directly loaded by an application -- either through a direct reference or through an <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> call -- continues to use the runtime of the <xref:System.AppDomain> it is loaded into.</span></span> <span data-ttu-id="f9c16-125">È consigliabile testare le librerie con tutte le versioni di .NET Framework che si vuole supportare.</span><span class="sxs-lookup"><span data-stu-id="f9c16-125">You should test your libraries against all versions of the .NET Framework that you want to support.</span></span> <span data-ttu-id="f9c16-126">Se un'applicazione viene compilata usando il runtime di .NET Framework 4, ma include una libreria che è stata compilata usando un runtime precedente, tale libreria userà anche il runtime di .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="f9c16-126">If an application is compiled using the .NET Framework 4 runtime but includes a library that was built using an earlier runtime, that library will use the .NET Framework 4 runtime as well.</span></span> <span data-ttu-id="f9c16-127">Tuttavia, se si ha un'applicazione compilata con un runtime precedente e una libreria compilata usando .NET Framework 4, è necessario forzare l'applicazione a usare anche .NET Framework 4. Vedere [scenario 3](#scenarios).</span><span class="sxs-lookup"><span data-stu-id="f9c16-127">However, if you have an application that was built using an earlier runtime and a library that was built using the .NET Framework 4, you must force your application to also use the .NET Framework 4 (see [scenario 3](#scenarios)).</span></span>  
  
- <span data-ttu-id="f9c16-128">**Sviluppatori di componenti COM gestiti**.</span><span class="sxs-lookup"><span data-stu-id="f9c16-128">**Managed COM component developers**.</span></span> <span data-ttu-id="f9c16-129">In passato, i componenti COM gestiti venivano eseguiti automaticamente usando la versione più recente del runtime installato nel computer.</span><span class="sxs-lookup"><span data-stu-id="f9c16-129">In the past, managed COM components automatically ran using the latest version of the runtime installed on the computer.</span></span> <span data-ttu-id="f9c16-130">È ora possibile eseguire i componenti COM con la versione del runtime con cui sono stati compilati.</span><span class="sxs-lookup"><span data-stu-id="f9c16-130">You can now execute COM components against the version of the runtime they were built with.</span></span>  
  
     <span data-ttu-id="f9c16-131">Come illustrato nella tabella seguente, i componenti compilati con .NET Framework versione 1.1 possono essere eseguiti side-by-side con i componenti della versione 4, ma non possono essere eseguiti con i componenti della versione 2.0, 3.0 o 3.5, perché l'hosting side-by-side non è disponibile per tali versioni.</span><span class="sxs-lookup"><span data-stu-id="f9c16-131">As shown by the following table, components that were built with the .NET Framework version 1.1 can run side by side with version 4 components, but they cannot run with version 2.0, 3.0, or 3.5 components, because side-by-side hosting is not available for those versions.</span></span>  
  
    |<span data-ttu-id="f9c16-132">Versione di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f9c16-132">.NET Framework version</span></span>|<span data-ttu-id="f9c16-133">1.1</span><span class="sxs-lookup"><span data-stu-id="f9c16-133">1.1</span></span>|<span data-ttu-id="f9c16-134">2.0 - 3.5</span><span class="sxs-lookup"><span data-stu-id="f9c16-134">2.0 - 3.5</span></span>|<span data-ttu-id="f9c16-135">4</span><span class="sxs-lookup"><span data-stu-id="f9c16-135">4</span></span>|  
    |----------------------------|---------|----------------|-------|  
    |<span data-ttu-id="f9c16-136">1.1</span><span class="sxs-lookup"><span data-stu-id="f9c16-136">1.1</span></span>|<span data-ttu-id="f9c16-137">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="f9c16-137">Not applicable</span></span>|<span data-ttu-id="f9c16-138">No</span><span class="sxs-lookup"><span data-stu-id="f9c16-138">No</span></span>|<span data-ttu-id="f9c16-139">Sì</span><span class="sxs-lookup"><span data-stu-id="f9c16-139">Yes</span></span>|  
    |<span data-ttu-id="f9c16-140">2.0 - 3.5</span><span class="sxs-lookup"><span data-stu-id="f9c16-140">2.0 - 3.5</span></span>|<span data-ttu-id="f9c16-141">No</span><span class="sxs-lookup"><span data-stu-id="f9c16-141">No</span></span>|<span data-ttu-id="f9c16-142">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="f9c16-142">Not applicable</span></span>|<span data-ttu-id="f9c16-143">Sì</span><span class="sxs-lookup"><span data-stu-id="f9c16-143">Yes</span></span>|  
    |<span data-ttu-id="f9c16-144">4</span><span class="sxs-lookup"><span data-stu-id="f9c16-144">4</span></span>|<span data-ttu-id="f9c16-145">Sì</span><span class="sxs-lookup"><span data-stu-id="f9c16-145">Yes</span></span>|<span data-ttu-id="f9c16-146">Sì</span><span class="sxs-lookup"><span data-stu-id="f9c16-146">Yes</span></span>|<span data-ttu-id="f9c16-147">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="f9c16-147">Not applicable</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="f9c16-148">Le versioni di .NET framework 3.0 e 3.5 sono state compilate in modo incrementale dalla versione 2.0 e non necessitano dell'esecuzione side-by-side.</span><span class="sxs-lookup"><span data-stu-id="f9c16-148">.NET Framework versions 3.0 and 3.5 are built incrementally on version 2.0, and do not need to run side by side.</span></span> <span data-ttu-id="f9c16-149">Sono praticamente la stessa versione.</span><span class="sxs-lookup"><span data-stu-id="f9c16-149">These are inherently the same version.</span></span>  
  
<a name="scenarios"></a>   
## <a name="common-side-by-side-hosting-scenarios"></a><span data-ttu-id="f9c16-150">Scenari comuni di hosting side-by-side</span><span class="sxs-lookup"><span data-stu-id="f9c16-150">Common Side-by-Side Hosting Scenarios</span></span>  
  
- <span data-ttu-id="f9c16-151">**Scenario 1:** applicazione nativa che usa i componenti COM compilati con versioni precedenti di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f9c16-151">**Scenario 1:** Native application that uses COM components built with earlier versions of the .NET Framework.</span></span>  
  
     <span data-ttu-id="f9c16-152">.NET Framework versioni installate: .NET Framework 4 e tutte le altre versioni del .NET Framework utilizzate dai componenti COM.</span><span class="sxs-lookup"><span data-stu-id="f9c16-152">.NET Framework versions installed: The .NET Framework 4 and all other versions of the .NET Framework used by the COM components.</span></span>  
  
     <span data-ttu-id="f9c16-153">Cosa fare: in questo scenario, non eseguire alcuna operazione.</span><span class="sxs-lookup"><span data-stu-id="f9c16-153">What to do: In this scenario, do nothing.</span></span> <span data-ttu-id="f9c16-154">I componenti COM verranno eseguiti con la versione di .NET Framework con la quale sono stati registrati.</span><span class="sxs-lookup"><span data-stu-id="f9c16-154">The COM components will run with the version of the .NET Framework they were registered with.</span></span>  
  
- <span data-ttu-id="f9c16-155">**Scenario 2**: applicazione gestita compilata con la .NET Framework 2,0 SP1 che è preferibile eseguire con l'.NET Framework 2,0, ma che è disponibile per l'esecuzione in .NET Framework 4 se la versione 2,0 non è presente.</span><span class="sxs-lookup"><span data-stu-id="f9c16-155">**Scenario 2**: Managed application built with the .NET Framework 2.0 SP1 that you would prefer to run with the .NET Framework 2.0, but are willing to run on the .NET Framework 4 if version 2.0 is not present.</span></span>  
  
     <span data-ttu-id="f9c16-156">.NET Framework versioni installate: una versione precedente del .NET Framework e il .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="f9c16-156">.NET Framework versions installed: An earlier version of the .NET Framework and the .NET Framework 4.</span></span>  
  
     <span data-ttu-id="f9c16-157">Cosa fare: nel [file di configurazione dell'applicazione](../configure-apps/index.md) contenuto nella directory dell'applicazione usare [l'elemento \<startup>](../configure-apps/file-schema/startup/startup-element.md) e [l'elemento \<supportedRuntime>](../configure-apps/file-schema/startup/supportedruntime-element.md) impostati nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="f9c16-157">What to do: In the [application configuration file](../configure-apps/index.md) in the application directory, use the [\<startup> element](../configure-apps/file-schema/startup/startup-element.md) and the [\<supportedRuntime> element](../configure-apps/file-schema/startup/supportedruntime-element.md) set as follows:</span></span>  
  
    ```xml  
    <configuration>  
      <startup >  
        <supportedRuntime version="v2.0.50727" />  
        <supportedRuntime version="v4.0" />  
      </startup>  
    </configuration>  
    ```  
  
- <span data-ttu-id="f9c16-158">**Scenario 3:** Applicazione nativa che usa componenti COM compilati con le versioni precedenti del .NET Framework che si vuole eseguire con la .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="f9c16-158">**Scenario 3:** Native application that uses COM components built with earlier versions of the .NET Framework that you want to run with the .NET Framework 4.</span></span>  
  
     <span data-ttu-id="f9c16-159">.NET Framework versioni installate: .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="f9c16-159">.NET Framework versions installed: The .NET Framework 4.</span></span>  
  
     <span data-ttu-id="f9c16-160">Cosa fare: nel file di configurazione dell'applicazione contenuto nella directory dell'applicazione usare l'elemento `<startup>` con l'attributo `useLegacyV2RuntimeActivationPolicy` impostato su `true` e l'elemento `<supportedRuntime>` impostato nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="f9c16-160">What to do: In the application configuration file in the application directory, use the `<startup>` element with the `useLegacyV2RuntimeActivationPolicy` attribute set to `true` and the `<supportedRuntime>` element set as follows:</span></span>  
  
    ```xml  
    <configuration>  
      <startup useLegacyV2RuntimeActivationPolicy="true">  
        <supportedRuntime version="v4.0" />  
      </startup>  
    </configuration>  
    ```  
  
## <a name="example"></a><span data-ttu-id="f9c16-161">Esempio</span><span class="sxs-lookup"><span data-stu-id="f9c16-161">Example</span></span>  
 <span data-ttu-id="f9c16-162">Nell'esempio seguente viene illustrato un host COM non gestito che esegue un componente COM gestito usando la versione di .NET Framework con cui è stato compilato il componente da usare.</span><span class="sxs-lookup"><span data-stu-id="f9c16-162">The following example demonstrates an unmanaged COM host that is running a managed COM component by using the version of the .NET Framework that the component was compiled to use.</span></span>  
  
 <span data-ttu-id="f9c16-163">Per eseguire l'esempio riportato di seguito, compilare e registrare il seguente componente COM gestito usando .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="f9c16-163">To run the following example, compile and register the following managed COM component using the .NET Framework 3.5.</span></span> <span data-ttu-id="f9c16-164">Per registrare il componente, nel menu **Progetto** scegliere **Proprietà**, fare clic sulla scheda **Build**, quindi selezionare la casella di controllo **Registra per interoperabilità COM**.</span><span class="sxs-lookup"><span data-stu-id="f9c16-164">To register the component, on the **Project** menu, click **Properties**, click the **Build** tab, and then select the **Register for COM interop** check box.</span></span>  
  
```csharp
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
  
 <span data-ttu-id="f9c16-165">Compilare la seguente applicazione C++ non gestita, che attiva l'oggetto COM che viene creato dall'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="f9c16-165">Compile the following unmanaged C++ application, which activates the COM object that is created by the previous example.</span></span>  
  
```cpp
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
  
## <a name="see-also"></a><span data-ttu-id="f9c16-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f9c16-166">See also</span></span>

- [<span data-ttu-id="f9c16-167">Elemento \<startup</span><span class="sxs-lookup"><span data-stu-id="f9c16-167">\<startup> Element</span></span>](../configure-apps/file-schema/startup/startup-element.md)
- [<span data-ttu-id="f9c16-168">Elemento \<supportedRuntime></span><span class="sxs-lookup"><span data-stu-id="f9c16-168">\<supportedRuntime> Element</span></span>](../configure-apps/file-schema/startup/supportedruntime-element.md)
