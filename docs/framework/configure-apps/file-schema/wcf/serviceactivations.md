---
title: '&lt;serviceActivations&gt;'
ms.date: 03/30/2017
ms.assetid: 97e665b6-1c51-410b-928a-9bb42c954ddb
ms.openlocfilehash: c62f2bd1a34aca31ea9f9d5de17840f2967b269c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32748529"
---
# <a name="ltserviceactivationsgt"></a><span data-ttu-id="c99cb-102">&lt;serviceActivations&gt;</span><span class="sxs-lookup"><span data-stu-id="c99cb-102">&lt;serviceActivations&gt;</span></span>
<span data-ttu-id="c99cb-103">Un elemento di configurazione che consente di aggiungere impostazioni che definiscono le impostazioni di attivazione di servizi virtuali che eseguono il mapping a tipi di servizi Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="c99cb-103">A configuration element that allows you to add settings that define virtual service activation settings that map to your Windows Communication Foundation (WCF) service types.</span></span> <span data-ttu-id="c99cb-104">In questo modo è possibile attivare servizi ospitati in WAS/IIS senza un file con estensione svc.</span><span class="sxs-lookup"><span data-stu-id="c99cb-104">This makes it possible to activate services hosted in WAS/IIS without an .svc file.</span></span>  
  
 <span data-ttu-id="c99cb-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c99cb-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="c99cb-106">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="c99cb-106">\<serviceHostingEnvironment></span></span>  
<span data-ttu-id="c99cb-107">\<serviceActivations ></span><span class="sxs-lookup"><span data-stu-id="c99cb-107">\<serviceActivations></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c99cb-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c99cb-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>   
   <serviceActivations>  
      <add factory="String"  
           service="String"/>  
   </serviceActivations>  
</serviceHostingEnvironment>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c99cb-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c99cb-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c99cb-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c99cb-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c99cb-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="c99cb-111">Attributes</span></span>  
 <span data-ttu-id="c99cb-112">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="c99cb-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c99cb-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c99cb-113">Child Elements</span></span>  
  
|<span data-ttu-id="c99cb-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="c99cb-114">Element</span></span>|<span data-ttu-id="c99cb-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c99cb-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c99cb-116">\<add></span><span class="sxs-lookup"><span data-stu-id="c99cb-116">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-serviceactivations.md)|<span data-ttu-id="c99cb-117">Aggiunge un elemento di configurazione che specifica l'attivazione di un'applicazione di servizio.</span><span class="sxs-lookup"><span data-stu-id="c99cb-117">Adds a configuration element that specifies the activation of a service application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c99cb-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c99cb-118">Parent Elements</span></span>  
  
|<span data-ttu-id="c99cb-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="c99cb-119">Element</span></span>|<span data-ttu-id="c99cb-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c99cb-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c99cb-121">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="c99cb-121">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="c99cb-122">Definisce il tipo del quale l'ambiente host del servizio crea un'istanza per un determinato trasporto.</span><span class="sxs-lookup"><span data-stu-id="c99cb-122">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c99cb-123">Note</span><span class="sxs-lookup"><span data-stu-id="c99cb-123">Remarks</span></span>  
 <span data-ttu-id="c99cb-124">Nell'esempio seguente viene illustrato come configurare le impostazioni di attivazione all'interno del file web.config.</span><span class="sxs-lookup"><span data-stu-id="c99cb-124">The following example shows how to configure activation settings within your web.config file.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <serviceHostingEnvironment>  
      <serviceActivations>  
        <add service="GreetingService"/>  
      </serviceActivations>  
    </serviceHostingEnvironment>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="c99cb-125">L'utilizzo di questa configurazione consente di attivare GreetingService senza usare un file con estensione svc.</span><span class="sxs-lookup"><span data-stu-id="c99cb-125">Using this configuration, you can activate the GreetingService without using an .svc file.</span></span>  
  
 <span data-ttu-id="c99cb-126">Si noti che `<serviceHostingEnvironment>` è una configurazione a livello di applicazione.</span><span class="sxs-lookup"><span data-stu-id="c99cb-126">Note that `<serviceHostingEnvironment>` is an application level configuration.</span></span> <span data-ttu-id="c99cb-127">È necessario posizionare il file `web.config` contenente la configurazione nella radice dell'applicazione virtuale.</span><span class="sxs-lookup"><span data-stu-id="c99cb-127">You have to place the `web.config` containing the configuration under the root of the virtual Application.</span></span> <span data-ttu-id="c99cb-128">Inoltre, `serviceHostingEnvironment` è una sezione ereditabile di machinetoApplication.</span><span class="sxs-lookup"><span data-stu-id="c99cb-128">In addition, `serviceHostingEnvironment` is a machinetoApplication inheritable section.</span></span> <span data-ttu-id="c99cb-129">Se si registra un servizio nella radice del computer, ogni servizio dell'applicazione erediterà tale servizio.</span><span class="sxs-lookup"><span data-stu-id="c99cb-129">If you register a single service in the root of the machine, every service in the application will inherit this service.</span></span>  
  
 <span data-ttu-id="c99cb-130">L'attivazione basata sulla configurazione supporta l'attivazione sul protocollo http e non http.</span><span class="sxs-lookup"><span data-stu-id="c99cb-130">Configuration-based activation supports activation over both http and non-http protocol.</span></span> <span data-ttu-id="c99cb-131">A tale scopo sono necessarie le estensioni nell'indirizzo relativo, ovvero nei file con estensione svc, xoml o xamlx.</span><span class="sxs-lookup"><span data-stu-id="c99cb-131">It requires extensions in the relatativeAddress i.e. .svc, .xoml or .xamlx.</span></span> <span data-ttu-id="c99cb-132">È possibile eseguire il mapping di estensioni personalizzate ai provider di compilazione noti, consentendo in tal modo l'attivazione di servizi su qualsiasi estensione.</span><span class="sxs-lookup"><span data-stu-id="c99cb-132">You can map your own extensions to the know buildProviders, which will then enable you to activate service over any extension.</span></span> <span data-ttu-id="c99cb-133">In caso di conflitto, la sezione `<serviceActivations>` esegue l'override delle registrazioni nel file con estensione svc.</span><span class="sxs-lookup"><span data-stu-id="c99cb-133">Upon conflict, the `<serviceActivations>` section overrides .svc registrations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c99cb-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c99cb-134">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceActivationElementCollection>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>
