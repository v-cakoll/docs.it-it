---
title: '&lt;serviceHostingEnvironment&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4f8a7c4f-e735-4987-979a-b74fcdae2652
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a08df7c620065bb483d276e3ead2c179040f1c9a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltservicehostingenvironmentgt"></a><span data-ttu-id="e7b00-102">&lt;serviceHostingEnvironment&gt;</span><span class="sxs-lookup"><span data-stu-id="e7b00-102">&lt;serviceHostingEnvironment&gt;</span></span>
<span data-ttu-id="e7b00-103">Questo elemento definisce il tipo di cui l'ambiente host del servizio crea un'istanza per un determinato trasporto.</span><span class="sxs-lookup"><span data-stu-id="e7b00-103">This element defines the type the service hosting environment instantiates for a particular transport.</span></span> <span data-ttu-id="e7b00-104">Se questo elemento è vuoto, viene usato il tipo predefinito.</span><span class="sxs-lookup"><span data-stu-id="e7b00-104">If this element is empty, the default type is used.</span></span> <span data-ttu-id="e7b00-105">Questo elemento può essere usato solo nei file di configurazione a livello di applicazione o computer.</span><span class="sxs-lookup"><span data-stu-id="e7b00-105">This element can only be used at the application or machine level configuration files.</span></span>  
  
 <span data-ttu-id="e7b00-106">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="e7b00-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="e7b00-107">\<ServiceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="e7b00-107">\<ServiceHostingEnvironment></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7b00-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e7b00-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment aspNetCompatibilityEnabled="Boolean" 
                           minFreeMemoryPercentageToActivateService="Integer" 
                           multipleSiteBindingsEnabled="Boolean">
  <baseAddressPrefixFilters>
    <add prefix="string" />
  </baseAddressPrefixFilters>
  <serviceActivations>
    <add factory="String" service="String" />
  </serviceActivations>
  <transportConfigurationTypes>
    <add name="String" transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e7b00-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e7b00-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e7b00-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e7b00-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e7b00-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="e7b00-111">Attributes</span></span>  
  
|<span data-ttu-id="e7b00-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="e7b00-112">Attribute</span></span>|<span data-ttu-id="e7b00-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e7b00-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e7b00-114">aspNetCompatibilityEnabled</span><span class="sxs-lookup"><span data-stu-id="e7b00-114">aspNetCompatibilityEnabled</span></span>|<span data-ttu-id="e7b00-115">Valore booleano che indica se la modalità di compatibilità con ASP.NET è stata attivata per l'applicazione corrente.</span><span class="sxs-lookup"><span data-stu-id="e7b00-115">A Boolean value indicating whether the ASP.NET compatibility mode has been turned on for the current application.</span></span> <span data-ttu-id="e7b00-116">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="e7b00-116">The default is `false`.</span></span><br /><br /> <span data-ttu-id="e7b00-117">Quando questo attributo è impostato su `true`, le richieste ai servizi [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] passano attraverso la pipeline HTTP ASP.NET. Viene inoltre impedita la comunicazione tra protocolli non HTTP.</span><span class="sxs-lookup"><span data-stu-id="e7b00-117">When this attribute is set to `true`, requests to [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] services flow through the ASP.NET HTTP pipeline, and communication over non-HTTP protocols is prohibited.</span></span> <span data-ttu-id="e7b00-118">Per ulteriori informazioni, vedere [servizi WCF e ASP.NET](../../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).</span><span class="sxs-lookup"><span data-stu-id="e7b00-118">For more information, see [WCF Services and ASP.NET](../../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).</span></span>|  
|<span data-ttu-id="e7b00-119">minFreeMemoryPercentageToActivateService</span><span class="sxs-lookup"><span data-stu-id="e7b00-119">minFreeMemoryPercentageToActivateService</span></span>|<span data-ttu-id="e7b00-120">Numero intero che specifica la quantità minima di memoria libera che deve essere disponibile per il sistema, prima che un servizio [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] possa essere attivato.</span><span class="sxs-lookup"><span data-stu-id="e7b00-120">An integer that specifies the minimum amount of free memory that should be available to the system, before a [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] service can be activated.</span></span> <span data-ttu-id="e7b00-121">**Attenzione:** specificare questo attributo con attendibilità parziale nel file Web. config di un [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] servizio comporterà un <xref:System.Security.SecurityException> quando si esegue il servizio.</span><span class="sxs-lookup"><span data-stu-id="e7b00-121">**Caution:**  Specifying this attribute along with partial trust in the web.config file of a [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] service will result in a <xref:System.Security.SecurityException> when the service is run.</span></span>|  
|<span data-ttu-id="e7b00-122">multipleSiteBindingsEnabled</span><span class="sxs-lookup"><span data-stu-id="e7b00-122">multipleSiteBindingsEnabled</span></span>|<span data-ttu-id="e7b00-123">Valore booleano che specifica se sono abilitate più associazioni IIS per sito.</span><span class="sxs-lookup"><span data-stu-id="e7b00-123">A Boolean value that specifies whether multiple IIS bindings per site is enabled.</span></span><br /><br /> <span data-ttu-id="e7b00-124">IIS è costituito da siti Web contenitori di applicazioni virtuali che includono directory virtuali.</span><span class="sxs-lookup"><span data-stu-id="e7b00-124">IIS consists of web sites, which are containers for virtual applications containing virtual directories.</span></span> <span data-ttu-id="e7b00-125">È possibile accedere all'applicazione in un sito tramite una o più associazioni IIS.</span><span class="sxs-lookup"><span data-stu-id="e7b00-125">The application in a site can be accessed through one or more IIS binding.</span></span> <span data-ttu-id="e7b00-126">Un'associazione IIS fornisce due tipi di informazioni: un protocollo di associazione e delle informazioni di associazione.</span><span class="sxs-lookup"><span data-stu-id="e7b00-126">An IIS binding provides two pieces of information: a binding protocol and binding information.</span></span> <span data-ttu-id="e7b00-127">Il protocollo di associazione definisce lo schema in base al quale ha luogo la comunicazione, mentre le informazioni di associazione sono usate per accedere al sito.</span><span class="sxs-lookup"><span data-stu-id="e7b00-127">Binding protocol defines the scheme over which communication occurs, and binding information is the information used to access the site.</span></span> <span data-ttu-id="e7b00-128">Un esempio di protocollo di associazione è HTTP. Le informazioni di associazione possono contenere un indirizzo IP, una porta, un'intestazione host, e così via.</span><span class="sxs-lookup"><span data-stu-id="e7b00-128">An example of a binding protocol can be HTTP, whereas binding information can contain an IP address, Port, host header, etc.</span></span><br /><br /> <span data-ttu-id="e7b00-129">In IIS è disponibile il supporto per specificare più associazioni per sito, questo comporta la presenza di più indirizzi di base per schema.</span><span class="sxs-lookup"><span data-stu-id="e7b00-129">IIS supports specifying multiple IIS bindings per site, which results in multiple base addresses per scheme.</span></span> <span data-ttu-id="e7b00-130">Tuttavia, un servizio [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] ospitato su un sito consente l'associazione di un solo indirizzo di base per schema.</span><span class="sxs-lookup"><span data-stu-id="e7b00-130">However, a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] service hosted under a site allows binding to only one baseAddress per scheme.</span></span><br /><br /> <span data-ttu-id="e7b00-131">Per abilitare più associazioni IIS per sito in un servizio [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)], impostare questo attributo su `true`.</span><span class="sxs-lookup"><span data-stu-id="e7b00-131">To enable multiple IIS bindings per site for a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] service, set this attribute to `true`.</span></span> <span data-ttu-id="e7b00-132">Si noti che l'associazione di più siti è supportata solo per il protocollo HTTP.</span><span class="sxs-lookup"><span data-stu-id="e7b00-132">Notice that multiple site binding is supported only for the HTTP protocol.</span></span> <span data-ttu-id="e7b00-133">L'indirizzo degli endpoint nel file di configurazione deve essere un URI completo.</span><span class="sxs-lookup"><span data-stu-id="e7b00-133">The address of endpoints in the configuration file needs to be a complete URI.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e7b00-134">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e7b00-134">Child Elements</span></span>  
  
|<span data-ttu-id="e7b00-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="e7b00-135">Element</span></span>|<span data-ttu-id="e7b00-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e7b00-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e7b00-137">\<baseAddressPrefixFilters ></span><span class="sxs-lookup"><span data-stu-id="e7b00-137">\<baseAddressPrefixFilters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddressprefixfilters.md)|<span data-ttu-id="e7b00-138">Raccolta di elementi di configurazione che specificano i filtri di prefisso degli indirizzi di base usati dall'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="e7b00-138">A collection of configuration elements that specify prefix filters for the base addresses used by the service host.</span></span>|  
|[<span data-ttu-id="e7b00-139">\<serviceActivations ></span><span class="sxs-lookup"><span data-stu-id="e7b00-139">\<serviceActivations></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/serviceactivations.md)|<span data-ttu-id="e7b00-140">Sezione di configurazione in cui vengono descritte le impostazioni di attivazione.</span><span class="sxs-lookup"><span data-stu-id="e7b00-140">A configuration section that describes activation settings.</span></span>|  
|[<span data-ttu-id="e7b00-141">\<transportConfigurationTypes ></span><span class="sxs-lookup"><span data-stu-id="e7b00-141">\<transportConfigurationTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transportconfigurationtypes.md)|<span data-ttu-id="e7b00-142">Raccolta di elementi di configurazione che identificano il tipo di un determinato trasporto.</span><span class="sxs-lookup"><span data-stu-id="e7b00-142">A collection of configuration elements that identify the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e7b00-143">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e7b00-143">Parent Elements</span></span>  
  
|<span data-ttu-id="e7b00-144">Elemento</span><span class="sxs-lookup"><span data-stu-id="e7b00-144">Element</span></span>|<span data-ttu-id="e7b00-145">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e7b00-145">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e7b00-146">serviceModel</span><span class="sxs-lookup"><span data-stu-id="e7b00-146">serviceModel</span></span>|<span data-ttu-id="e7b00-147">L'elemento radice di tutti gli elementi di configurazione di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="e7b00-147">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7b00-148">Note</span><span class="sxs-lookup"><span data-stu-id="e7b00-148">Remarks</span></span>  
 <span data-ttu-id="e7b00-149">Per impostazione predefinita, i servizi WCF vengono eseguiti side-by-side con ASP.NET nei domini applicazioni ospitati.</span><span class="sxs-lookup"><span data-stu-id="e7b00-149">By default, WCF services run side-by-side with ASP.NET in hosted Application Domains (AppDomain).</span></span> <span data-ttu-id="e7b00-150">Benché WCF e ASP.NET possano coesistere nello stesso dominio applicazione, per impostazione predefinita le richieste WCF non vengono elaborate dalla pipeline HTTP ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="e7b00-150">Even though WCF and ASP.NET can coexist in the same AppDomain, WCF requests are not processed by the ASP.NET HTTP Pipeline by default.</span></span> <span data-ttu-id="e7b00-151">Di conseguenza, diversi elementi della piattaforma delle applicazioni ASP.NET non sono disponibili per i servizi WCF.</span><span class="sxs-lookup"><span data-stu-id="e7b00-151">As a result, several elements of the ASP.NET application platform are not available to WCF services.</span></span> <span data-ttu-id="e7b00-152">Segue un elenco di tali elementi.</span><span class="sxs-lookup"><span data-stu-id="e7b00-152">These include</span></span>  
  
-   <span data-ttu-id="e7b00-153">Autorizzazione file/URL di ASP.NET</span><span class="sxs-lookup"><span data-stu-id="e7b00-153">ASP.NET File/URL Authorization</span></span>  
  
-   <span data-ttu-id="e7b00-154">Rappresentazione di ASP.NET</span><span class="sxs-lookup"><span data-stu-id="e7b00-154">ASP.NET Impersonation</span></span>  
  
-   <span data-ttu-id="e7b00-155">Stato sessione basato su cookie</span><span class="sxs-lookup"><span data-stu-id="e7b00-155">Cookie-based Session State</span></span>  
  
-   <span data-ttu-id="e7b00-156">HttpContext.Current</span><span class="sxs-lookup"><span data-stu-id="e7b00-156">HttpContext.Current</span></span>  
  
-   <span data-ttu-id="e7b00-157">Estensibilità della pipeline tramite HttpModule personalizzato</span><span class="sxs-lookup"><span data-stu-id="e7b00-157">Pipeline Extensibility via custom HttpModule</span></span>  
  
 <span data-ttu-id="e7b00-158">Se i servizi WCF devono funzionare nel contesto ASP.NET e comunicano solo su HTTP, è possibile usare la modalità di compatibilità con ASP.NET di WCF.</span><span class="sxs-lookup"><span data-stu-id="e7b00-158">If your WCF services need to function in the ASP.NET context, and communicate only over HTTP, you can use WCF’s ASP.NET compatibility mode.</span></span> <span data-ttu-id="e7b00-159">Questa modalità viene attivata quando l'attributo `aspNetCompatibilityEnabled` è impostato su `true` a livello di applicazione.</span><span class="sxs-lookup"><span data-stu-id="e7b00-159">This mode is turned on when the `aspNetCompatibilityEnabled` attribute is set to `true` at the application level.</span></span> <span data-ttu-id="e7b00-160">Le implementazioni dei servizi devono usare la classe <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> per dichiarare la propria capacità di essere in esecuzione in tale modalità di compatibilità.</span><span class="sxs-lookup"><span data-stu-id="e7b00-160">Service implementations must declare their ability to run in compatibility mode using the <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> class.</span></span> <span data-ttu-id="e7b00-161">Quando la modalità di compatibilità è attiva si verifica quanto segue:</span><span class="sxs-lookup"><span data-stu-id="e7b00-161">When the compatibility mode is enabled,</span></span>  
  
-   <span data-ttu-id="e7b00-162">L'autorizzazione file/URL di ASP.NET viene applicata prima dell'autorizzazione WCF.</span><span class="sxs-lookup"><span data-stu-id="e7b00-162">ASP.NET File/URL Authorization is enforced prior to WCF authorization.</span></span> <span data-ttu-id="e7b00-163">Le decisioni di autorizzazione si basano sull'identità a livello di trasporto della richiesta.</span><span class="sxs-lookup"><span data-stu-id="e7b00-163">An authorization decision is based on the transport-level identity of the request.</span></span> <span data-ttu-id="e7b00-164">Le identità a livello di messaggio vengono ignorate.</span><span class="sxs-lookup"><span data-stu-id="e7b00-164">Identities at the message level are ignored.</span></span>  
  
-   <span data-ttu-id="e7b00-165">L'esecuzione delle operazioni dei servizi WCF inizia nel contesto di rappresentazione di ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="e7b00-165">WCF service operations start to execute in the ASP.NET impersonation context.</span></span> <span data-ttu-id="e7b00-166">Se per un servizio specifico sono attivate sia la rappresentazione di ASP.NET sia la rappresentazione di WCF, il sistema applica il contesto di rappresentazione di WCF.</span><span class="sxs-lookup"><span data-stu-id="e7b00-166">If both ASP.NET impersonation and WCF impersonation are enabled for a specific service, the WCF impersonation context applies.</span></span>  
  
-   <span data-ttu-id="e7b00-167">HttpContext.Current può essere usato dal codice dei servizi WCF. Inoltre, ai servizi viene impedito di esporre endpoint non HTTP.</span><span class="sxs-lookup"><span data-stu-id="e7b00-167">HttpContext.Current can be used from WCF service code, and services are prevented from exposing non-HTTP endpoints.</span></span>  
  
-   <span data-ttu-id="e7b00-168">Le richieste WCF vengono elaborate dalla pipeline ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="e7b00-168">WCF requests are processed by the ASP.NET pipeline.</span></span> <span data-ttu-id="e7b00-169">Le richieste WCF possono inoltre essere elaborate dagli elementi HttpModules configurati per agire sulle richieste in ingresso.</span><span class="sxs-lookup"><span data-stu-id="e7b00-169">HttpModules that have been configured to act on incoming requests can also process WCF requests.</span></span> <span data-ttu-id="e7b00-170">Questi elementi possono includere componenti della piattaforma di ASP.NET (ad esempio <xref:System.Web.SessionState.SessionStateModule>) nonché moduli personalizzati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="e7b00-170">These can include ASP.NET platform components (e.g., <xref:System.Web.SessionState.SessionStateModule>), as well as custom third party modules.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7b00-171">Esempio</span><span class="sxs-lookup"><span data-stu-id="e7b00-171">Example</span></span>  
 <span data-ttu-id="e7b00-172">Nell'esempio di codice seguente viene mostrato come abilitare la modalità di compatibilità con ASP.</span><span class="sxs-lookup"><span data-stu-id="e7b00-172">The following code sample shows how to enable ASP Compatibility Mode.</span></span>  
  
## <a name="code"></a><span data-ttu-id="e7b00-173">Codice</span><span class="sxs-lookup"><span data-stu-id="e7b00-173">Code</span></span>  
  
```xml  
<serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e7b00-174">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7b00-174">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>  
 [<span data-ttu-id="e7b00-175">Hosting</span><span class="sxs-lookup"><span data-stu-id="e7b00-175">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)  
 [<span data-ttu-id="e7b00-176">Servizi WCF e ASP.NET</span><span class="sxs-lookup"><span data-stu-id="e7b00-176">WCF Services and ASP.NET</span></span>](../../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)
