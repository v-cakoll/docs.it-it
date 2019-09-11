---
title: Strumento per la configurazione del modello di servizio di COM+ (ComSvcConfig.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, COM+ integration
- WCF, COM+ integration
ms.assetid: 7717c6c2-85fc-418b-a8ed-bad8e61cec5c
ms.openlocfilehash: 98c8e50ea4a9efe1c69a0c7b959b228a045dfca1
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855660"
---
# <a name="com-service-model-configuration-tool-comsvcconfigexe"></a><span data-ttu-id="c5bbb-102">Strumento per la configurazione del modello di servizio di COM+ (ComSvcConfig.exe)</span><span class="sxs-lookup"><span data-stu-id="c5bbb-102">COM+ Service Model Configuration Tool (ComSvcConfig.exe)</span></span>
<span data-ttu-id="c5bbb-103">Lo strumento da riga di comando per la configurazione del modello del servizio di COM+ (ComSvcConfig.exe) consente di configurare le interfacce COM+ che si desidera siano esposte come servizi Web.</span><span class="sxs-lookup"><span data-stu-id="c5bbb-103">The COM+ Service Model Configuration command-line tool (ComSvcConfig.exe) enables you to configure COM+ interfaces to be exposed as Web services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5bbb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c5bbb-104">Syntax</span></span>  
  
```console  
ComSvcConfig.exe /install | /uninstall | /list [/application:<ApplicationID | ApplicationName>] [/contract:<ClassID | ProgID | *,InterfaceID | InterfaceName | *>] [/hosting:<complus | was>] [/webSite:<WebsiteName>] [/webDirectory:<WebDirectoryName>] [/mex] [/id] [/nologo] [/verbose] [/help] [/partial]  
```  
  
## <a name="remarks"></a><span data-ttu-id="c5bbb-105">Note</span><span class="sxs-lookup"><span data-stu-id="c5bbb-105">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c5bbb-106">Per utilizzare ComSvcConfig.exe è necessario disporre dei privilegi di amministratore per il computer.</span><span class="sxs-lookup"><span data-stu-id="c5bbb-106">You must be an administrator on the local computer to use ComSvcConfig.exe.</span></span>  
  
 <span data-ttu-id="c5bbb-107">Lo strumento si trova nel percorso seguente</span><span class="sxs-lookup"><span data-stu-id="c5bbb-107">The tool can be found in the following location</span></span>  
  
 <span data-ttu-id="c5bbb-108">%SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="c5bbb-108">%SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation</span></span>\  
  
 <span data-ttu-id="c5bbb-109">Per ulteriori informazioni su ComSvcConfig. exe, vedere [procedura: Utilizzare lo strumento](../../../docs/framework/wcf/feature-details/how-to-use-the-com-service-model-configuration-tool.md)di configurazione del modello di servizi com+.</span><span class="sxs-lookup"><span data-stu-id="c5bbb-109">For more information about ComSvcConfig.exe, see [How to: Use the COM+ Service Model Configuration Tool](../../../docs/framework/wcf/feature-details/how-to-use-the-com-service-model-configuration-tool.md).</span></span>  
  
 <span data-ttu-id="c5bbb-110">Nella tabella riportata di seguito sono descritti le modalità di utilizzo di ComSvcConfig.exe.</span><span class="sxs-lookup"><span data-stu-id="c5bbb-110">The following table describes the modes that can be used with ComSvcConfig.exe.</span></span>  
  
|<span data-ttu-id="c5bbb-111">Opzione</span><span class="sxs-lookup"><span data-stu-id="c5bbb-111">Option</span></span>|<span data-ttu-id="c5bbb-112">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="c5bbb-112">Description</span></span>|  
|------------|-----------------|  
|`install`|<span data-ttu-id="c5bbb-113">Installa una configurazione per un'interfaccia COM+ per l'integrazione del Modello di servizio.</span><span class="sxs-lookup"><span data-stu-id="c5bbb-113">Installs a configuration for a COM+ interface for Service Model integration.</span></span><br /><br /> <span data-ttu-id="c5bbb-114">Forma abbreviata `/i`.</span><span class="sxs-lookup"><span data-stu-id="c5bbb-114">Short form `/i`.</span></span>|  
|`uninstall`|<span data-ttu-id="c5bbb-115">Disinstalla una configurazione per un'interfaccia COM+ dall'integrazione del Modello di servizio.</span><span class="sxs-lookup"><span data-stu-id="c5bbb-115">Uninstalls a configuration for a COM+ interface from Service Model integration.</span></span><br /><br /> <span data-ttu-id="c5bbb-116">Forma abbreviata `/u`.</span><span class="sxs-lookup"><span data-stu-id="c5bbb-116">Short form `/u`.</span></span>|  
|`list`|<span data-ttu-id="c5bbb-117">Elenca le informazioni su applicazioni e componenti COM+ dotati di interfacce configurate per l'integrazione del Modello di servizio.</span><span class="sxs-lookup"><span data-stu-id="c5bbb-117">Lists information about COM+ applications and components that have interfaces that are configured for Service Model integration.</span></span><br /><br /> <span data-ttu-id="c5bbb-118">Forma abbreviata `/l`.</span><span class="sxs-lookup"><span data-stu-id="c5bbb-118">Short form `/l`.</span></span>|  
  
 <span data-ttu-id="c5bbb-119">Nella tabella riportata di seguito sono descritti i flag che possono essere utilizzati con ComSvcConfig.exe.</span><span class="sxs-lookup"><span data-stu-id="c5bbb-119">The following table describes the flags that can be used with ComSvcConfig.exe.</span></span>  
  
|<span data-ttu-id="c5bbb-120">Opzione</span><span class="sxs-lookup"><span data-stu-id="c5bbb-120">Option</span></span>|<span data-ttu-id="c5bbb-121">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="c5bbb-121">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="c5bbb-122">`/application:` \<*ApplicationID* &#124; *ApplicationName*\></span><span class="sxs-lookup"><span data-stu-id="c5bbb-122">`/application:` \<*ApplicationID* &#124; *ApplicationName*\></span></span>|<span data-ttu-id="c5bbb-123">Specifica l'applicazione COM+ da configurare.</span><span class="sxs-lookup"><span data-stu-id="c5bbb-123">Specifies the COM+ application to configure.</span></span><br /><br /> <span data-ttu-id="c5bbb-124">Forma abbreviata `/a`.</span><span class="sxs-lookup"><span data-stu-id="c5bbb-124">Short form `/a`.</span></span>|  
|<span data-ttu-id="c5bbb-125">`/contract:` \<*ClassID*  &#124; *ProgID*  &#124; \*,*InterfaceID* &#124; *InterfaceName* &#124; \*\></span><span class="sxs-lookup"><span data-stu-id="c5bbb-125">`/contract:` \<*ClassID*  &#124; *ProgID*  &#124; \*,*InterfaceID* &#124; *InterfaceName* &#124; \*\></span></span>|<span data-ttu-id="c5bbb-126">Specifica componente e interfaccia COM+ che verranno configurati come contratto del servizio.</span><span class="sxs-lookup"><span data-stu-id="c5bbb-126">Specifies the COM+ component and interface that will be configured as the contract for the service.</span></span><br /><br /> <span data-ttu-id="c5bbb-127">Forma abbreviata `/c`.</span><span class="sxs-lookup"><span data-stu-id="c5bbb-127">Short form `/c`.</span></span><br /><br /> <span data-ttu-id="c5bbb-128">Sebbene sia possibile utilizzare il\*carattere jolly () quando si specificano i nomi dei componenti e delle interfacce, è consigliabile non utilizzarlo perché è possibile esporre interfacce che non si intendevano.</span><span class="sxs-lookup"><span data-stu-id="c5bbb-128">While the wildcard character (\*) can be used when you specify the component and interface names, we recommend that you do not use it, because you might expose interfaces that you did not intend to.</span></span>|  
|<span data-ttu-id="c5bbb-129">`/hosting:` \<*complus*  &#124; *was*\></span><span class="sxs-lookup"><span data-stu-id="c5bbb-129">`/hosting:` \<*complus*  &#124; *was*\></span></span>|<span data-ttu-id="c5bbb-130">Specifica se utilizzare la modalità di hosting COM+ o Web.</span><span class="sxs-lookup"><span data-stu-id="c5bbb-130">Specifies whether to use the COM+ hosting mode or the Web hosting mode.</span></span><br /><br /> <span data-ttu-id="c5bbb-131">Forma abbreviata `/h`.</span><span class="sxs-lookup"><span data-stu-id="c5bbb-131">Short form `/h`.</span></span><br /><br /> <span data-ttu-id="c5bbb-132">L'utilizzo della modalità di hosting COM+ richiede l’attivazione esplicita dell'applicazione COM+.</span><span class="sxs-lookup"><span data-stu-id="c5bbb-132">Using the COM+ hosting mode requires explicit activation of the COM+ application.</span></span> <span data-ttu-id="c5bbb-133">L'utilizzo della modalità di hosting Web, consente l’attivazione automatica dell’applicazione COM+ come necessario.</span><span class="sxs-lookup"><span data-stu-id="c5bbb-133">Using the Web hosting mode allows the COM+ application to be automatically activated as required.</span></span> <span data-ttu-id="c5bbb-134">Se l'applicazione COM+ è un'applicazione della libreria, essa viene eseguita nel processo di Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="c5bbb-134">If the COM+ application is a library application, it runs in the Internet Information Services (IIS) process.</span></span> <span data-ttu-id="c5bbb-135">Se l'applicazione COM+ è un'applicazione server, essa viene eseguita nel processo di Dllhost.exe.</span><span class="sxs-lookup"><span data-stu-id="c5bbb-135">If the COM+ application is a server application, it runs in the Dllhost.exe process.</span></span>|  
|<span data-ttu-id="c5bbb-136">`/webSite:`\< *Sito Web*\></span><span class="sxs-lookup"><span data-stu-id="c5bbb-136">`/webSite:` \<*WebsiteName*\></span></span>|<span data-ttu-id="c5bbb-137">Specifica il sito Web per l’hosting quando viene utilizzata la modalità di hosting Web (vedere il flag `/hosting` ).</span><span class="sxs-lookup"><span data-stu-id="c5bbb-137">Specifies the Web site for hosting when Web hosting mode is used (see the `/hosting` flag).</span></span><br /><br /> <span data-ttu-id="c5bbb-138">Forma abbreviata `/w`.</span><span class="sxs-lookup"><span data-stu-id="c5bbb-138">Short form `/w`.</span></span><br /><br /> <span data-ttu-id="c5bbb-139">Se non viene specificato nessun sito Web, verrà utilizzato il sito Web predefinito.</span><span class="sxs-lookup"><span data-stu-id="c5bbb-139">If no Web site is specified, the default Web site is used.</span></span>|  
|<span data-ttu-id="c5bbb-140">`/webDirectory:` \<*WebDirectoryName*\></span><span class="sxs-lookup"><span data-stu-id="c5bbb-140">`/webDirectory:` \<*WebDirectoryName*\></span></span>|<span data-ttu-id="c5bbb-141">Specifica la directory virtuale per l’hosting quando viene utilizzata la modalità di hosting Web (vedere il flag `/hosting` ).</span><span class="sxs-lookup"><span data-stu-id="c5bbb-141">Specifies the virtual directory for hosting when Web hosting is used (see the `/hosting` flag).</span></span><br /><br /> <span data-ttu-id="c5bbb-142">Forma abbreviata `/d`.</span><span class="sxs-lookup"><span data-stu-id="c5bbb-142">Short form `/d`.</span></span>|  
|`/mex`|<span data-ttu-id="c5bbb-143">Aggiunge l'endpoint del servizio MEX (Metadata Exchange) alla configurazione del servizio predefinita per supportare client che desiderano recuperare una definizione del contratto dal servizio.</span><span class="sxs-lookup"><span data-stu-id="c5bbb-143">Adds a Metadata Exchange (MEX) service endpoint to the default service configuration to support clients that want to retrieve a contract definition from the service.</span></span><br /><br /> <span data-ttu-id="c5bbb-144">Forma abbreviata `/x`.</span><span class="sxs-lookup"><span data-stu-id="c5bbb-144">Short form `/x`.</span></span>|  
|`/id`|<span data-ttu-id="c5bbb-145">Visualizza applicazione, componente e informazioni sull'interfaccia come ID.</span><span class="sxs-lookup"><span data-stu-id="c5bbb-145">Displays the application, component, and interface information as IDs.</span></span><br /><br /> <span data-ttu-id="c5bbb-146">Forma abbreviata `/k`.</span><span class="sxs-lookup"><span data-stu-id="c5bbb-146">Short form `/k`.</span></span>|  
|`/nologo`|<span data-ttu-id="c5bbb-147">Impedisce la visualizzazione del logo di ComSvcConfig.exe.</span><span class="sxs-lookup"><span data-stu-id="c5bbb-147">Prevents ComSvcConfig.exe from displaying its logo.</span></span><br /><br /> <span data-ttu-id="c5bbb-148">Forma abbreviata `/n`.</span><span class="sxs-lookup"><span data-stu-id="c5bbb-148">Short form `/n`.</span></span>|  
|`/verbose`|<span data-ttu-id="c5bbb-149">Restituisce tutti gli avvisi o testo informativo oltre a qualsiasi errore incontrato.</span><span class="sxs-lookup"><span data-stu-id="c5bbb-149">Outputs all warnings or informational text in addition to any errors encountered.</span></span><br /><br /> <span data-ttu-id="c5bbb-150">Forma abbreviata `/v`.</span><span class="sxs-lookup"><span data-stu-id="c5bbb-150">Short form `/v`.</span></span>|  
|`/help`|<span data-ttu-id="c5bbb-151">Il messaggio di utilizzo viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="c5bbb-151">Displays the usage message.</span></span><br /><br /> <span data-ttu-id="c5bbb-152">Forma abbreviata `/?`.</span><span class="sxs-lookup"><span data-stu-id="c5bbb-152">Short form `/?`.</span></span>|  
|`/partial`|<span data-ttu-id="c5bbb-153">Genera una configurazione del servizio quando l'interfaccia specificata include una o più firme del metodo che possono essere esposte.</span><span class="sxs-lookup"><span data-stu-id="c5bbb-153">Generates a service configuration when the specified interface includes one or more method signatures that can be exposed.</span></span> <span data-ttu-id="c5bbb-154">In corrispondenza dell’ora di inizializzazione del servizio, metodi compatibili vengono visualizzati come operazioni sul contratto di servizio, mentre i metodi non compatibili vengono ignorati e non sono presenti nel contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="c5bbb-154">At service initialization time, compatible methods appear as operations on the service contract, and non-compatible methods are ignored and absent from the service contract.</span></span><br /><br /> <span data-ttu-id="c5bbb-155">Se questo flag manca, lo strumento non genererà una configurazione del servizio quando l'interfaccia specificata include uno o più metodi incompatibili.</span><span class="sxs-lookup"><span data-stu-id="c5bbb-155">If this flag is missing, the tool will not generate a service configuration when the specified interface includes one or more incompatible methods.</span></span>|  
  
## <a name="examples"></a><span data-ttu-id="c5bbb-156">Esempi</span><span class="sxs-lookup"><span data-stu-id="c5bbb-156">Examples</span></span>  
  
### <a name="description"></a><span data-ttu-id="c5bbb-157">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c5bbb-157">Description</span></span>  
 <span data-ttu-id="c5bbb-158">Nell'esempio seguente viene aggiunta l'interfaccia `IFinances` del componente `ItemOrders.IFinancial` (dall'applicazione OnlineStore COM+) al set di interfacce esposte come servizi Web, utilizzando la modalità di hosting COM+.</span><span class="sxs-lookup"><span data-stu-id="c5bbb-158">The following example adds the `IFinances` interface of the `ItemOrders.IFinancial` component (from the OnlineStore COM+ application) to the set of interfaces that are exposed as Web services, using the COM+ hosting mode.</span></span> <span data-ttu-id="c5bbb-159">Tutti gli avvisi verranno restituiti oltre a qualsiasi errore incontrato.</span><span class="sxs-lookup"><span data-stu-id="c5bbb-159">All warnings will be output in addition to any errors encountered.</span></span>  
  
### <a name="code"></a><span data-ttu-id="c5bbb-160">Codice</span><span class="sxs-lookup"><span data-stu-id="c5bbb-160">Code</span></span>  
  
```console  
ComSvcConfig.exe /install /application:OnlineStore /contract:ItemOrders.Financial,IFinances /hosting:complus /verbose  
```  
  
### <a name="description"></a><span data-ttu-id="c5bbb-161">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="c5bbb-161">Description</span></span>  
 <span data-ttu-id="c5bbb-162">Nell'esempio seguente viene aggiunta l'interfaccia `IStockLevels` del componente `ItemInventory.Warehouse` (dall'applicazione OnlineWarehouse COM+) al set di interfacce esposte come servizi Web, utilizzando la modalità di hosting Web.</span><span class="sxs-lookup"><span data-stu-id="c5bbb-162">The following example adds the `IStockLevels` interface of the `ItemInventory.Warehouse` component (from the OnlineWarehouse COM+ application) to the set of interfaces that are exposed as Web services, using the Web hosting mode.</span></span> <span data-ttu-id="c5bbb-163">Il Servizio Web è ospitato sul Web nella directory virtuale OnlineWarehouse di IIS.</span><span class="sxs-lookup"><span data-stu-id="c5bbb-163">The Web service is Web hosted in the OnlineWarehouse virtual directory of IIS.</span></span>  
  
### <a name="code"></a><span data-ttu-id="c5bbb-164">Codice</span><span class="sxs-lookup"><span data-stu-id="c5bbb-164">Code</span></span>  
  
```console  
ComSvcConfig.exe /install /application:OnlineWarehouse /contract:ItemInventory.Warehouse,IStockLevels /hosting:was /webDirectory:root/OnlineWarehouse  
```  
  
### <a name="description"></a><span data-ttu-id="c5bbb-165">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c5bbb-165">Description</span></span>  
 <span data-ttu-id="c5bbb-166">Nell'esempio seguente viene rimossa l'interfaccia `IFinances` del componente `ItemOrders.Financial` (dall'applicazione OnlineStore COM+) dal set di interfacce esposte come servizi Web, utilizzando la modalità di hosting COM+.</span><span class="sxs-lookup"><span data-stu-id="c5bbb-166">The following example removes the `IFinances` interface of the `ItemOrders.Financial` component (from the OnlineStore COM+ application) from the set of interfaces that are exposed as Web services.</span></span>  
  
### <a name="code"></a><span data-ttu-id="c5bbb-167">Codice</span><span class="sxs-lookup"><span data-stu-id="c5bbb-167">Code</span></span>  
  
```console  
ComSvcConfig.exe /uninstall /application:OnlineStore /interface:ItemOrders.Financial,IFinances /hosting:complus  
```  
  
### <a name="description"></a><span data-ttu-id="c5bbb-168">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="c5bbb-168">Description</span></span>  
 <span data-ttu-id="c5bbb-169">L’esempio di seguito riportato elenca le interfacce ospitate COM+ attualmente esposte, insieme all'indirizzo corrispondente e ai dettagli di associazione, per l'applicazione OnlineStore COM+ sul computer locale.</span><span class="sxs-lookup"><span data-stu-id="c5bbb-169">The following example lists currently exposed COM+ hosted interfaces, along with the corresponding address and binding details, for the OnlineStore COM+ application on the local machine.</span></span>  
  
### <a name="code"></a><span data-ttu-id="c5bbb-170">Codice</span><span class="sxs-lookup"><span data-stu-id="c5bbb-170">Code</span></span>  
  
```console  
ComSvcConfig.exe /list /application:OnlineStore /hosting:complus  
```  
  
## <a name="see-also"></a><span data-ttu-id="c5bbb-171">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5bbb-171">See also</span></span>

- [<span data-ttu-id="c5bbb-172">Procedura: Utilizzare lo strumento di configurazione del modello di servizi COM+</span><span class="sxs-lookup"><span data-stu-id="c5bbb-172">How to: Use the COM+ Service Model Configuration Tool</span></span>](../../../docs/framework/wcf/feature-details/how-to-use-the-com-service-model-configuration-tool.md)
