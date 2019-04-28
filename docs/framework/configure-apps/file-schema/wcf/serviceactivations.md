---
title: <serviceActivations>
ms.date: 03/30/2017
ms.assetid: 97e665b6-1c51-410b-928a-9bb42c954ddb
ms.openlocfilehash: 7506cce61966a4a4650ff591cd6106dfd4a33b67
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670365"
---
# <a name="serviceactivations"></a><span data-ttu-id="60655-101">\<serviceActivations></span><span class="sxs-lookup"><span data-stu-id="60655-101">\<serviceActivations></span></span>

<span data-ttu-id="60655-102">Elemento di configurazione che consente di aggiungere le impostazioni che definiscono le impostazioni di attivazione di servizi virtuali che eseguono il mapping ai tipi di servizio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="60655-102">A configuration element that allows you to add settings that define virtual service activation settings that map to your Windows Communication Foundation (WCF) service types.</span></span> <span data-ttu-id="60655-103">In questo modo è possibile attivare servizi ospitati in WAS/IIS senza un file con estensione svc.</span><span class="sxs-lookup"><span data-stu-id="60655-103">This makes it possible to activate services hosted in WAS/IIS without an .svc file.</span></span>

<span data-ttu-id="60655-104">\<system.ServiceModel>\\</span><span class="sxs-lookup"><span data-stu-id="60655-104">\<system.ServiceModel>\\</span></span>
<span data-ttu-id="60655-105">\<serviceHostingEnvironment>\\</span><span class="sxs-lookup"><span data-stu-id="60655-105">\<serviceHostingEnvironment>\\</span></span>
<span data-ttu-id="60655-106">\<serviceActivations></span><span class="sxs-lookup"><span data-stu-id="60655-106">\<serviceActivations></span></span>

## <a name="syntax"></a><span data-ttu-id="60655-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="60655-107">Syntax</span></span>

```xml
<serviceHostingEnvironment>
  <serviceActivations>
    <add factory="String"
         service="String" />
  </serviceActivations>
</serviceHostingEnvironment>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="60655-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="60655-108">Attributes and Elements</span></span>

<span data-ttu-id="60655-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="60655-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="60655-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="60655-110">Attributes</span></span>

<span data-ttu-id="60655-111">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="60655-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="60655-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="60655-112">Child Elements</span></span>

|<span data-ttu-id="60655-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="60655-113">Element</span></span>|<span data-ttu-id="60655-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="60655-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="60655-115">\<add></span><span class="sxs-lookup"><span data-stu-id="60655-115">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-serviceactivations.md)|<span data-ttu-id="60655-116">Aggiunge un elemento di configurazione che specifica l'attivazione di un'applicazione di servizio.</span><span class="sxs-lookup"><span data-stu-id="60655-116">Adds a configuration element that specifies the activation of a service application.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="60655-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="60655-117">Parent Elements</span></span>

|<span data-ttu-id="60655-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="60655-118">Element</span></span>|<span data-ttu-id="60655-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="60655-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="60655-120">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="60655-120">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="60655-121">Definisce il tipo del quale l'ambiente host del servizio crea un'istanza per un determinato trasporto.</span><span class="sxs-lookup"><span data-stu-id="60655-121">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|

## <a name="remarks"></a><span data-ttu-id="60655-122">Note</span><span class="sxs-lookup"><span data-stu-id="60655-122">Remarks</span></span>

<span data-ttu-id="60655-123">Nell'esempio seguente viene illustrato come configurare le impostazioni di attivazione all'interno del file web.config.</span><span class="sxs-lookup"><span data-stu-id="60655-123">The following example shows how to configure activation settings within your web.config file.</span></span>

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

<span data-ttu-id="60655-124">L'utilizzo di questa configurazione consente di attivare GreetingService senza usare un file con estensione svc.</span><span class="sxs-lookup"><span data-stu-id="60655-124">Using this configuration, you can activate the GreetingService without using an .svc file.</span></span>

<span data-ttu-id="60655-125">Si noti che `<serviceHostingEnvironment>` è una configurazione a livello di applicazione.</span><span class="sxs-lookup"><span data-stu-id="60655-125">Note that `<serviceHostingEnvironment>` is an application level configuration.</span></span> <span data-ttu-id="60655-126">È necessario posizionare il file `web.config` contenente la configurazione nella radice dell'applicazione virtuale.</span><span class="sxs-lookup"><span data-stu-id="60655-126">You have to place the `web.config` containing the configuration under the root of the virtual Application.</span></span> <span data-ttu-id="60655-127">Inoltre, `serviceHostingEnvironment` è una sezione ereditabile di machineToApplication.</span><span class="sxs-lookup"><span data-stu-id="60655-127">In addition, `serviceHostingEnvironment` is a machineToApplication inheritable section.</span></span> <span data-ttu-id="60655-128">Se si registra un servizio nella radice del computer, ogni servizio dell'applicazione erediterà tale servizio.</span><span class="sxs-lookup"><span data-stu-id="60655-128">If you register a single service in the root of the machine, every service in the application will inherit this service.</span></span>

<span data-ttu-id="60655-129">L'attivazione basata sulla configurazione supporta l'attivazione sul protocollo http e non http.</span><span class="sxs-lookup"><span data-stu-id="60655-129">Configuration-based activation supports activation over both http and non-http protocol.</span></span> <span data-ttu-id="60655-130">Richiede le estensioni in relativeAddress, ovvero file con estensione svc, xoml o xamlx.</span><span class="sxs-lookup"><span data-stu-id="60655-130">It requires extensions in the relativeAddress i.e. .svc, .xoml or .xamlx.</span></span> <span data-ttu-id="60655-131">È possibile eseguire il mapping di estensioni personalizzate ai provider di compilazione noti, consentendo in tal modo l'attivazione di servizi su qualsiasi estensione.</span><span class="sxs-lookup"><span data-stu-id="60655-131">You can map your own extensions to the know buildProviders, which will then enable you to activate service over any extension.</span></span> <span data-ttu-id="60655-132">In caso di conflitto, la sezione `<serviceActivations>` esegue l'override delle registrazioni nel file con estensione svc.</span><span class="sxs-lookup"><span data-stu-id="60655-132">Upon conflict, the `<serviceActivations>` section overrides .svc registrations.</span></span>

## <a name="see-also"></a><span data-ttu-id="60655-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60655-133">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceActivationElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
