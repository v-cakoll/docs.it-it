---
title: <serviceHostingEnvironment>
ms.date: 03/30/2017
ms.assetid: 4f8a7c4f-e735-4987-979a-b74fcdae2652
ms.openlocfilehash: 165dbed1b78d00f8d4dd3e482b9fee8a23db60da
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399620"
---
# \<serviceHostingEnvironment>
<span data-ttu-id="bb321-101">Questo elemento definisce il tipo di cui l'ambiente host del servizio crea un'istanza per un determinato trasporto.</span><span class="sxs-lookup"><span data-stu-id="bb321-101">This element defines the type the service hosting environment instantiates for a particular transport.</span></span> <span data-ttu-id="bb321-102">Se questo elemento è vuoto, viene usato il tipo predefinito.</span><span class="sxs-lookup"><span data-stu-id="bb321-102">If this element is empty, the default type is used.</span></span> <span data-ttu-id="bb321-103">Questo elemento può essere usato solo nei file di configurazione a livello di applicazione o computer.</span><span class="sxs-lookup"><span data-stu-id="bb321-103">This element can only be used at the application or machine level configuration files.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceHostingEnvironment>**  
  
## <a name="syntax"></a><span data-ttu-id="bb321-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bb321-104">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment aspNetCompatibilityEnabled="Boolean"
                           minFreeMemoryPercentageToActivateService="Integer"
                           multipleSiteBindingsEnabled="Boolean">
  <baseAddressPrefixFilters>
    <add prefix="string" />
  </baseAddressPrefixFilters>
  <serviceActivations>
    <add factory="String"
         service="String" />
  </serviceActivations>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bb321-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="bb321-105">Attributes and Elements</span></span>  
 <span data-ttu-id="bb321-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="bb321-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bb321-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="bb321-107">Attributes</span></span>  
  
|<span data-ttu-id="bb321-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="bb321-108">Attribute</span></span>|<span data-ttu-id="bb321-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bb321-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bb321-110">aspNetCompatibilityEnabled</span><span class="sxs-lookup"><span data-stu-id="bb321-110">aspNetCompatibilityEnabled</span></span>|<span data-ttu-id="bb321-111">Valore booleano che indica se la modalità di compatibilità con ASP.NET è stata attivata per l'applicazione corrente.</span><span class="sxs-lookup"><span data-stu-id="bb321-111">A Boolean value indicating whether the ASP.NET compatibility mode has been turned on for the current application.</span></span> <span data-ttu-id="bb321-112">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="bb321-112">The default is `false`.</span></span><br /><br /> <span data-ttu-id="bb321-113">Quando questo attributo è impostato su `true` , le richieste ai servizi Windows Communication Foundation (WCF) passano attraverso la pipeline HTTP ASP.NET e la comunicazione su protocolli non http non è consentita.</span><span class="sxs-lookup"><span data-stu-id="bb321-113">When this attribute is set to `true`, requests to Windows Communication Foundation (WCF) services flow through the ASP.NET HTTP pipeline, and communication over non-HTTP protocols is prohibited.</span></span> <span data-ttu-id="bb321-114">Per ulteriori informazioni, vedere [servizi WCF e ASP.NET](../../../wcf/feature-details/wcf-services-and-aspnet.md).</span><span class="sxs-lookup"><span data-stu-id="bb321-114">For more information, see [WCF Services and ASP.NET](../../../wcf/feature-details/wcf-services-and-aspnet.md).</span></span>|  
|<span data-ttu-id="bb321-115">minFreeMemoryPercentageToActivateService</span><span class="sxs-lookup"><span data-stu-id="bb321-115">minFreeMemoryPercentageToActivateService</span></span>|<span data-ttu-id="bb321-116">Intero che specifica la quantità minima di memoria libera che deve essere disponibile per il sistema, prima che un servizio WCF possa essere attivato.</span><span class="sxs-lookup"><span data-stu-id="bb321-116">An integer that specifies the minimum amount of free memory that should be available to the system, before a WCF service can be activated.</span></span> <span data-ttu-id="bb321-117">**Attenzione:**  Se si specifica questo attributo con attendibilità parziale nel file Web. config di un servizio WCF, verrà generato un oggetto <xref:System.Security.SecurityException> quando il servizio viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="bb321-117">**Caution:**  Specifying this attribute along with partial trust in the web.config file of a WCF service will result in a <xref:System.Security.SecurityException> when the service is run.</span></span>|  
|<span data-ttu-id="bb321-118">multipleSiteBindingsEnabled</span><span class="sxs-lookup"><span data-stu-id="bb321-118">multipleSiteBindingsEnabled</span></span>|<span data-ttu-id="bb321-119">Valore booleano che specifica se sono abilitate più associazioni IIS per sito.</span><span class="sxs-lookup"><span data-stu-id="bb321-119">A Boolean value that specifies whether multiple IIS bindings per site is enabled.</span></span><br /><br /> <span data-ttu-id="bb321-120">IIS è costituito da siti Web contenitori di applicazioni virtuali che includono directory virtuali.</span><span class="sxs-lookup"><span data-stu-id="bb321-120">IIS consists of web sites, which are containers for virtual applications containing virtual directories.</span></span> <span data-ttu-id="bb321-121">È possibile accedere all'applicazione in un sito tramite una o più associazioni IIS.</span><span class="sxs-lookup"><span data-stu-id="bb321-121">The application in a site can be accessed through one or more IIS binding.</span></span> <span data-ttu-id="bb321-122">Un'associazione IIS fornisce due tipi di informazioni: un protocollo di associazione e delle informazioni di associazione.</span><span class="sxs-lookup"><span data-stu-id="bb321-122">An IIS binding provides two pieces of information: a binding protocol and binding information.</span></span> <span data-ttu-id="bb321-123">Il protocollo di associazione definisce lo schema in base al quale ha luogo la comunicazione, mentre le informazioni di associazione sono usate per accedere al sito.</span><span class="sxs-lookup"><span data-stu-id="bb321-123">Binding protocol defines the scheme over which communication occurs, and binding information is the information used to access the site.</span></span> <span data-ttu-id="bb321-124">Un esempio di protocollo di associazione è HTTP. Le informazioni di associazione possono contenere un indirizzo IP, una porta, un'intestazione host, e così via.</span><span class="sxs-lookup"><span data-stu-id="bb321-124">An example of a binding protocol can be HTTP, whereas binding information can contain an IP address, Port, host header, etc.</span></span><br /><br /> <span data-ttu-id="bb321-125">In IIS è disponibile il supporto per specificare più associazioni per sito, questo comporta la presenza di più indirizzi di base per schema.</span><span class="sxs-lookup"><span data-stu-id="bb321-125">IIS supports specifying multiple IIS bindings per site, which results in multiple base addresses per scheme.</span></span> <span data-ttu-id="bb321-126">Tuttavia, un servizio Windows Communication Foundation (WCF) ospitato in un sito consente l'associazione a un solo baseAddress per schema.</span><span class="sxs-lookup"><span data-stu-id="bb321-126">However, a Windows Communication Foundation (WCF) service hosted under a site allows binding to only one baseAddress per scheme.</span></span><br /><br /> <span data-ttu-id="bb321-127">Per abilitare più associazioni IIS per sito per un servizio Windows Communication Foundation (WCF), impostare questo attributo su `true` .</span><span class="sxs-lookup"><span data-stu-id="bb321-127">To enable multiple IIS bindings per site for a Windows Communication Foundation (WCF) service, set this attribute to `true`.</span></span> <span data-ttu-id="bb321-128">Si noti che l'associazione di più siti è supportata solo per il protocollo HTTP.</span><span class="sxs-lookup"><span data-stu-id="bb321-128">Notice that multiple site binding is supported only for the HTTP protocol.</span></span> <span data-ttu-id="bb321-129">L'indirizzo degli endpoint nel file di configurazione deve essere un URI completo.</span><span class="sxs-lookup"><span data-stu-id="bb321-129">The address of endpoints in the configuration file needs to be a complete URI.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bb321-130">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="bb321-130">Child Elements</span></span>  
  
|<span data-ttu-id="bb321-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="bb321-131">Element</span></span>|<span data-ttu-id="bb321-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bb321-132">Description</span></span>|  
|-------------|-----------------|  
|[\<baseAddressPrefixFilters>](baseaddressprefixfilters.md)|<span data-ttu-id="bb321-133">Raccolta di elementi di configurazione che specificano i filtri di prefisso degli indirizzi di base usati dall'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="bb321-133">A collection of configuration elements that specify prefix filters for the base addresses used by the service host.</span></span>|  
|[\<serviceActivations>](serviceactivations.md)|<span data-ttu-id="bb321-134">Sezione di configurazione in cui vengono descritte le impostazioni di attivazione.</span><span class="sxs-lookup"><span data-stu-id="bb321-134">A configuration section that describes activation settings.</span></span>|  
|[\<transportConfigurationTypes>](transportconfigurationtypes.md)|<span data-ttu-id="bb321-135">Raccolta di elementi di configurazione che identificano il tipo di un determinato trasporto.</span><span class="sxs-lookup"><span data-stu-id="bb321-135">A collection of configuration elements that identify the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bb321-136">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="bb321-136">Parent Elements</span></span>  
  
|<span data-ttu-id="bb321-137">Elemento</span><span class="sxs-lookup"><span data-stu-id="bb321-137">Element</span></span>|<span data-ttu-id="bb321-138">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bb321-138">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bb321-139">serviceModel</span><span class="sxs-lookup"><span data-stu-id="bb321-139">serviceModel</span></span>|<span data-ttu-id="bb321-140">L'elemento radice di tutti gli elementi di configurazione di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="bb321-140">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bb321-141">Commenti</span><span class="sxs-lookup"><span data-stu-id="bb321-141">Remarks</span></span>  
 <span data-ttu-id="bb321-142">Per impostazione predefinita, i servizi WCF vengono eseguiti side-by-side con ASP.NET nei domini applicazioni ospitati.</span><span class="sxs-lookup"><span data-stu-id="bb321-142">By default, WCF services run side-by-side with ASP.NET in hosted Application Domains (AppDomain).</span></span> <span data-ttu-id="bb321-143">Benché WCF e ASP.NET possano coesistere nello stesso dominio applicazione, per impostazione predefinita le richieste WCF non vengono elaborate dalla pipeline HTTP ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="bb321-143">Even though WCF and ASP.NET can coexist in the same AppDomain, WCF requests are not processed by the ASP.NET HTTP Pipeline by default.</span></span> <span data-ttu-id="bb321-144">Di conseguenza, diversi elementi della piattaforma delle applicazioni ASP.NET non sono disponibili per i servizi WCF.</span><span class="sxs-lookup"><span data-stu-id="bb321-144">As a result, several elements of the ASP.NET application platform are not available to WCF services.</span></span> <span data-ttu-id="bb321-145">Segue un elenco di tali elementi.</span><span class="sxs-lookup"><span data-stu-id="bb321-145">These include</span></span>  
  
- <span data-ttu-id="bb321-146">Autorizzazione file/URL di ASP.NET</span><span class="sxs-lookup"><span data-stu-id="bb321-146">ASP.NET File/URL Authorization</span></span>  
  
- <span data-ttu-id="bb321-147">Rappresentazione di ASP.NET</span><span class="sxs-lookup"><span data-stu-id="bb321-147">ASP.NET Impersonation</span></span>  
  
- <span data-ttu-id="bb321-148">Stato sessione basato su cookie</span><span class="sxs-lookup"><span data-stu-id="bb321-148">Cookie-based Session State</span></span>  
  
- <span data-ttu-id="bb321-149">HttpContext.Current</span><span class="sxs-lookup"><span data-stu-id="bb321-149">HttpContext.Current</span></span>  
  
- <span data-ttu-id="bb321-150">Estensibilità della pipeline tramite HttpModule personalizzato</span><span class="sxs-lookup"><span data-stu-id="bb321-150">Pipeline Extensibility via custom HttpModule</span></span>  
  
 <span data-ttu-id="bb321-151">Se i servizi WCF devono funzionare nel contesto ASP.NET e comunicano solo su HTTP, è possibile usare la modalità di compatibilità con ASP.NET di WCF.</span><span class="sxs-lookup"><span data-stu-id="bb321-151">If your WCF services need to function in the ASP.NET context, and communicate only over HTTP, you can use WCF’s ASP.NET compatibility mode.</span></span> <span data-ttu-id="bb321-152">Questa modalità viene attivata quando l'attributo `aspNetCompatibilityEnabled` è impostato su `true` a livello di applicazione.</span><span class="sxs-lookup"><span data-stu-id="bb321-152">This mode is turned on when the `aspNetCompatibilityEnabled` attribute is set to `true` at the application level.</span></span> <span data-ttu-id="bb321-153">Le implementazioni dei servizi devono usare la classe <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> per dichiarare la propria capacità di essere in esecuzione in tale modalità di compatibilità.</span><span class="sxs-lookup"><span data-stu-id="bb321-153">Service implementations must declare their ability to run in compatibility mode using the <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> class.</span></span> <span data-ttu-id="bb321-154">Quando la modalità di compatibilità è attiva si verifica quanto segue:</span><span class="sxs-lookup"><span data-stu-id="bb321-154">When the compatibility mode is enabled,</span></span>  
  
- <span data-ttu-id="bb321-155">L'autorizzazione file/URL di ASP.NET viene applicata prima dell'autorizzazione WCF.</span><span class="sxs-lookup"><span data-stu-id="bb321-155">ASP.NET File/URL Authorization is enforced prior to WCF authorization.</span></span> <span data-ttu-id="bb321-156">Le decisioni di autorizzazione si basano sull'identità a livello di trasporto della richiesta.</span><span class="sxs-lookup"><span data-stu-id="bb321-156">An authorization decision is based on the transport-level identity of the request.</span></span> <span data-ttu-id="bb321-157">Le identità a livello di messaggio vengono ignorate.</span><span class="sxs-lookup"><span data-stu-id="bb321-157">Identities at the message level are ignored.</span></span>  
  
- <span data-ttu-id="bb321-158">L'esecuzione delle operazioni dei servizi WCF inizia nel contesto di rappresentazione di ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="bb321-158">WCF service operations start to execute in the ASP.NET impersonation context.</span></span> <span data-ttu-id="bb321-159">Se per un servizio specifico sono attivate sia la rappresentazione di ASP.NET sia la rappresentazione di WCF, il sistema applica il contesto di rappresentazione di WCF.</span><span class="sxs-lookup"><span data-stu-id="bb321-159">If both ASP.NET impersonation and WCF impersonation are enabled for a specific service, the WCF impersonation context applies.</span></span>  
  
- <span data-ttu-id="bb321-160">HttpContext.Current può essere usato dal codice dei servizi WCF. Inoltre, ai servizi viene impedito di esporre endpoint non HTTP.</span><span class="sxs-lookup"><span data-stu-id="bb321-160">HttpContext.Current can be used from WCF service code, and services are prevented from exposing non-HTTP endpoints.</span></span>  
  
- <span data-ttu-id="bb321-161">Le richieste WCF vengono elaborate dalla pipeline ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="bb321-161">WCF requests are processed by the ASP.NET pipeline.</span></span> <span data-ttu-id="bb321-162">Le richieste WCF possono inoltre essere elaborate dagli elementi HttpModules configurati per agire sulle richieste in ingresso.</span><span class="sxs-lookup"><span data-stu-id="bb321-162">HttpModules that have been configured to act on incoming requests can also process WCF requests.</span></span> <span data-ttu-id="bb321-163">Questi elementi possono includere componenti della piattaforma di ASP.NET (ad esempio <xref:System.Web.SessionState.SessionStateModule>) nonché moduli personalizzati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="bb321-163">These can include ASP.NET platform components (e.g., <xref:System.Web.SessionState.SessionStateModule>), as well as custom third party modules.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb321-164">Esempio</span><span class="sxs-lookup"><span data-stu-id="bb321-164">Example</span></span>  
 <span data-ttu-id="bb321-165">Nell'esempio di codice seguente viene mostrato come abilitare la modalità di compatibilità con ASP.</span><span class="sxs-lookup"><span data-stu-id="bb321-165">The following code sample shows how to enable ASP Compatibility Mode.</span></span>  
  
## <a name="code"></a><span data-ttu-id="bb321-166">Codice</span><span class="sxs-lookup"><span data-stu-id="bb321-166">Code</span></span>  
  
```xml  
<serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>
```  
  
## <a name="see-also"></a><span data-ttu-id="bb321-167">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="bb321-167">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="bb321-168">Hosting</span><span class="sxs-lookup"><span data-stu-id="bb321-168">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
- [<span data-ttu-id="bb321-169">Servizi WCF e ASP.NET</span><span class="sxs-lookup"><span data-stu-id="bb321-169">WCF Services and ASP.NET</span></span>](../../../wcf/feature-details/wcf-services-and-aspnet.md)
