---
title: '&lt;add&gt; di &lt;serviceActivations&gt;'
ms.date: 03/30/2017
ms.assetid: e5b01fc8-ee84-48b7-95fd-95ab54fa871f
ms.openlocfilehash: d0e1f45cc8ff5b544eff5ff5dae33d5989aaf405
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587635"
---
# <a name="ltaddgt-of-ltserviceactivationsgt"></a><span data-ttu-id="d9418-102">&lt;add&gt; di &lt;serviceActivations&gt;</span><span class="sxs-lookup"><span data-stu-id="d9418-102">&lt;add&gt; of &lt;serviceActivations&gt;</span></span>
<span data-ttu-id="d9418-103">Elemento di configurazione che consente di definire impostazioni di attivazione di servizi virtuali che eseguono il mapping ai tipi di servizio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="d9418-103">A configuration element that allows you to define virtual service activation settings that map to your Windows Communication Foundation (WCF) service types.</span></span> <span data-ttu-id="d9418-104">In questo modo è possibile attivare servizi ospitati in WAS/IIS senza un file con estensione svc.</span><span class="sxs-lookup"><span data-stu-id="d9418-104">This makes it possible to activate services hosted in WAS/IIS without an .svc file.</span></span>  
  
 <span data-ttu-id="d9418-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d9418-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="d9418-106">\<ServiceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="d9418-106">\<ServiceHostingEnvironment></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9418-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d9418-107">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
    <serviceActivations>
      <add factory="String"
           service="String" />
  </serviceActivations>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d9418-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d9418-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d9418-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d9418-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d9418-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="d9418-110">Attributes</span></span>  
  
|<span data-ttu-id="d9418-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="d9418-111">Attribute</span></span>|<span data-ttu-id="d9418-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d9418-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d9418-113">factory</span><span class="sxs-lookup"><span data-stu-id="d9418-113">factory</span></span>|<span data-ttu-id="d9418-114">Stringa che specifica il tipo CLR della factory che genera un elemento di attivazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="d9418-114">A string that specifies the CLR type name of the factory that generates a service activation element.</span></span>|  
|<span data-ttu-id="d9418-115">service</span><span class="sxs-lookup"><span data-stu-id="d9418-115">service</span></span>|<span data-ttu-id="d9418-116">ServiceType che implementa il servizio, ossia il Typename completo o il Typename breve, quando viene inserito nella cartella App_Code.</span><span class="sxs-lookup"><span data-stu-id="d9418-116">The ServiceType that implements the service (either the full qualified Typename or the short Typename (when it is placed in the App_Code folder).</span></span>|  
|<span data-ttu-id="d9418-117">relativeAddress</span><span class="sxs-lookup"><span data-stu-id="d9418-117">relativeAddress</span></span>|<span data-ttu-id="d9418-118">Indirizzo relativo all'interno dell'applicazione IIS corrente, ad esempio “Service.svc".</span><span class="sxs-lookup"><span data-stu-id="d9418-118">The relative address within the current IIS application - for example "Service.svc".</span></span> <span data-ttu-id="d9418-119">In WCF 4.0 questo indirizzo relativo deve contenere una delle estensioni di file note (svc, xamlx, ecc.). Nessun file fisico deve esistere per l'URL relativo</span><span class="sxs-lookup"><span data-stu-id="d9418-119">In WCF 4.0 this relative address has to contain one of the known file extensions (.svc, .xamlx, ...). No physical file has to exist for the relativeUrl</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d9418-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d9418-120">Child Elements</span></span>  
 <span data-ttu-id="d9418-121">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="d9418-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d9418-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d9418-122">Parent Elements</span></span>  
  
|<span data-ttu-id="d9418-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="d9418-123">Element</span></span>|<span data-ttu-id="d9418-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d9418-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d9418-125">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="d9418-125">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="d9418-126">Sezione di configurazione in cui vengono descritte le impostazioni di attivazione.</span><span class="sxs-lookup"><span data-stu-id="d9418-126">A configuration section that describes activation settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d9418-127">Note</span><span class="sxs-lookup"><span data-stu-id="d9418-127">Remarks</span></span>  
 <span data-ttu-id="d9418-128">Nell'esempio seguente viene illustrato come configurare le impostazioni di attivazione all'interno del file web.config.</span><span class="sxs-lookup"><span data-stu-id="d9418-128">The following example shows how to configure activation settings within your web.config file.</span></span>  
  
```xml  
<configuration>
  <system.serviceModel>
    <serviceHostingEnvironment>
      <serviceActivations>
        <add service="GreetingService" />
      </serviceActivations>
    </serviceHostingEnvironment>
  </system.serviceModel>
</configuration>
```  
  
 <span data-ttu-id="d9418-129">L'utilizzo di questa configurazione consente di attivare GreetingService senza usare un file con estensione svc.</span><span class="sxs-lookup"><span data-stu-id="d9418-129">Using this configuration, you can activate the GreetingService without using an .svc file.</span></span>  
  
 <span data-ttu-id="d9418-130">Si noti che `<serviceHostingEnvironment>` è una configurazione a livello di applicazione.</span><span class="sxs-lookup"><span data-stu-id="d9418-130">Note that `<serviceHostingEnvironment>` is an application level configuration.</span></span> <span data-ttu-id="d9418-131">È necessario posizionare il file `web.config` contenente la configurazione nella radice dell'applicazione virtuale.</span><span class="sxs-lookup"><span data-stu-id="d9418-131">You have to place the `web.config` containing the configuration under the root of the virtual Application.</span></span> <span data-ttu-id="d9418-132">Inoltre, `serviceHostingEnvironment` è una sezione ereditabile di machinetoApplication.</span><span class="sxs-lookup"><span data-stu-id="d9418-132">In addition, `serviceHostingEnvironment` is a machinetoApplication inheritable section.</span></span> <span data-ttu-id="d9418-133">Se si registra un servizio nella radice del computer, ogni servizio dell'applicazione erediterà tale servizio.</span><span class="sxs-lookup"><span data-stu-id="d9418-133">If you register a single service in the root of the machine, every service in the application will inherit this service.</span></span>  
  
 <span data-ttu-id="d9418-134">L'attivazione basata sulla configurazione supporta l'attivazione sul protocollo http e non http.</span><span class="sxs-lookup"><span data-stu-id="d9418-134">Configuration-based activation supports activation over both http and non-http protocol.</span></span> <span data-ttu-id="d9418-135">A tale scopo sono necessarie le estensioni nell'indirizzo relativo, ovvero nei file con estensione svc, xoml o xamlx.</span><span class="sxs-lookup"><span data-stu-id="d9418-135">It requires extensions in the relatativeAddress, i.e. .svc, .xoml or .xamlx.</span></span> <span data-ttu-id="d9418-136">È possibile eseguire il mapping di estensioni personalizzate ai provider di compilazione noti, consentendo in tal modo l'attivazione di servizi su qualsiasi estensione.</span><span class="sxs-lookup"><span data-stu-id="d9418-136">You can map your own extensions to the know buildProviders, which will then enable you to activate service over any extension.</span></span> <span data-ttu-id="d9418-137">In caso di conflitto, la sezione `<serviceActivations>` esegue l'override delle registrazioni nel file con estensione svc.</span><span class="sxs-lookup"><span data-stu-id="d9418-137">Upon conflict, the `<serviceActivations>` section overrides .svc registrations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9418-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9418-138">See also</span></span>
- <xref:System.ServiceModel.Configuration.ServiceActivationElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
