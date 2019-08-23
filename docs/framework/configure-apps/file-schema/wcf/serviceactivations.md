---
title: <serviceActivations>
ms.date: 03/30/2017
ms.assetid: 97e665b6-1c51-410b-928a-9bb42c954ddb
ms.openlocfilehash: fb7c699612ef12aae39aaeadaf170d0e8f2553cd
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936439"
---
# <a name="serviceactivations"></a><span data-ttu-id="adf54-101">\<serviceActivations></span><span class="sxs-lookup"><span data-stu-id="adf54-101">\<serviceActivations></span></span>

<span data-ttu-id="adf54-102">Elemento di configurazione che consente di aggiungere impostazioni che definiscono le impostazioni di attivazione del servizio virtuale che vengono mappate ai tipi di servizio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="adf54-102">A configuration element that allows you to add settings that define virtual service activation settings that map to your Windows Communication Foundation (WCF) service types.</span></span> <span data-ttu-id="adf54-103">In questo modo è possibile attivare servizi ospitati in WAS/IIS senza un file con estensione svc.</span><span class="sxs-lookup"><span data-stu-id="adf54-103">This makes it possible to activate services hosted in WAS/IIS without an .svc file.</span></span>

<span data-ttu-id="adf54-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="adf54-104">\<system.ServiceModel></span></span>\
<span data-ttu-id="adf54-105">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="adf54-105">\<serviceHostingEnvironment></span></span>\
<span data-ttu-id="adf54-106">\<serviceActivations></span><span class="sxs-lookup"><span data-stu-id="adf54-106">\<serviceActivations></span></span>

## <a name="syntax"></a><span data-ttu-id="adf54-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="adf54-107">Syntax</span></span>

```xml
<serviceHostingEnvironment>
  <serviceActivations>
    <add factory="String"
         service="String" />
  </serviceActivations>
</serviceHostingEnvironment>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="adf54-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="adf54-108">Attributes and Elements</span></span>

<span data-ttu-id="adf54-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="adf54-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="adf54-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="adf54-110">Attributes</span></span>

<span data-ttu-id="adf54-111">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="adf54-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="adf54-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="adf54-112">Child Elements</span></span>

|<span data-ttu-id="adf54-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="adf54-113">Element</span></span>|<span data-ttu-id="adf54-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="adf54-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="adf54-115">\<add></span><span class="sxs-lookup"><span data-stu-id="adf54-115">\<add></span></span>](add-of-serviceactivations.md)|<span data-ttu-id="adf54-116">Aggiunge un elemento di configurazione che specifica l'attivazione di un'applicazione di servizio.</span><span class="sxs-lookup"><span data-stu-id="adf54-116">Adds a configuration element that specifies the activation of a service application.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="adf54-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="adf54-117">Parent Elements</span></span>

|<span data-ttu-id="adf54-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="adf54-118">Element</span></span>|<span data-ttu-id="adf54-119">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="adf54-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="adf54-120">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="adf54-120">\<serviceHostingEnvironment></span></span>](servicehostingenvironment.md)|<span data-ttu-id="adf54-121">Definisce il tipo del quale l'ambiente host del servizio crea un'istanza per un determinato trasporto.</span><span class="sxs-lookup"><span data-stu-id="adf54-121">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|

## <a name="remarks"></a><span data-ttu-id="adf54-122">Note</span><span class="sxs-lookup"><span data-stu-id="adf54-122">Remarks</span></span>

<span data-ttu-id="adf54-123">Nell'esempio seguente viene illustrato come configurare le impostazioni di attivazione all'interno del file web.config.</span><span class="sxs-lookup"><span data-stu-id="adf54-123">The following example shows how to configure activation settings within your web.config file.</span></span>

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

<span data-ttu-id="adf54-124">L'utilizzo di questa configurazione consente di attivare GreetingService senza usare un file con estensione svc.</span><span class="sxs-lookup"><span data-stu-id="adf54-124">Using this configuration, you can activate the GreetingService without using an .svc file.</span></span>

<span data-ttu-id="adf54-125">Si noti che `<serviceHostingEnvironment>` è una configurazione a livello di applicazione.</span><span class="sxs-lookup"><span data-stu-id="adf54-125">Note that `<serviceHostingEnvironment>` is an application level configuration.</span></span> <span data-ttu-id="adf54-126">È necessario posizionare il file `web.config` contenente la configurazione nella radice dell'applicazione virtuale.</span><span class="sxs-lookup"><span data-stu-id="adf54-126">You have to place the `web.config` containing the configuration under the root of the virtual Application.</span></span> <span data-ttu-id="adf54-127">Inoltre, `serviceHostingEnvironment` è una sezione ereditabile machineToApplication.</span><span class="sxs-lookup"><span data-stu-id="adf54-127">In addition, `serviceHostingEnvironment` is a machineToApplication inheritable section.</span></span> <span data-ttu-id="adf54-128">Se si registra un servizio nella radice del computer, ogni servizio dell'applicazione erediterà tale servizio.</span><span class="sxs-lookup"><span data-stu-id="adf54-128">If you register a single service in the root of the machine, every service in the application will inherit this service.</span></span>

<span data-ttu-id="adf54-129">L'attivazione basata sulla configurazione supporta l'attivazione sul protocollo http e non http.</span><span class="sxs-lookup"><span data-stu-id="adf54-129">Configuration-based activation supports activation over both http and non-http protocol.</span></span> <span data-ttu-id="adf54-130">Richiede le estensioni in relativeAddress, ad esempio SVC, xoml o xamlx.</span><span class="sxs-lookup"><span data-stu-id="adf54-130">It requires extensions in the relativeAddress i.e. .svc, .xoml or .xamlx.</span></span> <span data-ttu-id="adf54-131">È possibile eseguire il mapping di estensioni personalizzate ai provider di compilazione noti, consentendo in tal modo l'attivazione di servizi su qualsiasi estensione.</span><span class="sxs-lookup"><span data-stu-id="adf54-131">You can map your own extensions to the know buildProviders, which will then enable you to activate service over any extension.</span></span> <span data-ttu-id="adf54-132">In caso di conflitto, la sezione `<serviceActivations>` esegue l'override delle registrazioni nel file con estensione svc.</span><span class="sxs-lookup"><span data-stu-id="adf54-132">Upon conflict, the `<serviceActivations>` section overrides .svc registrations.</span></span>

## <a name="see-also"></a><span data-ttu-id="adf54-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="adf54-133">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceActivationElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
