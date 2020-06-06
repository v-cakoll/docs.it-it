---
title: <serviceActivations>
ms.date: 03/30/2017
ms.assetid: 97e665b6-1c51-410b-928a-9bb42c954ddb
ms.openlocfilehash: 64ae0bfd90ae941fc78515c7936c998201c87485
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855142"
---
# \<serviceActivations>

<span data-ttu-id="11904-101">Elemento di configurazione che consente di aggiungere impostazioni che definiscono le impostazioni di attivazione del servizio virtuale che vengono mappate ai tipi di servizio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="11904-101">A configuration element that allows you to add settings that define virtual service activation settings that map to your Windows Communication Foundation (WCF) service types.</span></span> <span data-ttu-id="11904-102">In questo modo è possibile attivare servizi ospitati in WAS/IIS senza un file con estensione svc.</span><span class="sxs-lookup"><span data-stu-id="11904-102">This makes it possible to activate services hosted in WAS/IIS without an .svc file.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceActivations>**  

## <a name="syntax"></a><span data-ttu-id="11904-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="11904-103">Syntax</span></span>

```xml
<serviceHostingEnvironment>
  <serviceActivations>
    <add factory="String"
         service="String" />
  </serviceActivations>
</serviceHostingEnvironment>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="11904-104">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="11904-104">Attributes and Elements</span></span>

<span data-ttu-id="11904-105">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="11904-105">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="11904-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="11904-106">Attributes</span></span>

<span data-ttu-id="11904-107">No.</span><span class="sxs-lookup"><span data-stu-id="11904-107">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="11904-108">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="11904-108">Child Elements</span></span>

|<span data-ttu-id="11904-109">Elemento</span><span class="sxs-lookup"><span data-stu-id="11904-109">Element</span></span>|<span data-ttu-id="11904-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="11904-110">Description</span></span>|
|-------------|-----------------|
|[\<add>](add-of-serviceactivations.md)|<span data-ttu-id="11904-111">Aggiunge un elemento di configurazione che specifica l'attivazione di un'applicazione di servizio.</span><span class="sxs-lookup"><span data-stu-id="11904-111">Adds a configuration element that specifies the activation of a service application.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="11904-112">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="11904-112">Parent Elements</span></span>

|<span data-ttu-id="11904-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="11904-113">Element</span></span>|<span data-ttu-id="11904-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="11904-114">Description</span></span>|
|-------------|-----------------|
|[\<serviceHostingEnvironment>](servicehostingenvironment.md)|<span data-ttu-id="11904-115">Definisce il tipo del quale l'ambiente host del servizio crea un'istanza per un determinato trasporto.</span><span class="sxs-lookup"><span data-stu-id="11904-115">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|

## <a name="remarks"></a><span data-ttu-id="11904-116">Commenti</span><span class="sxs-lookup"><span data-stu-id="11904-116">Remarks</span></span>

<span data-ttu-id="11904-117">Nell'esempio seguente viene illustrato come configurare le impostazioni di attivazione all'interno del file web.config.</span><span class="sxs-lookup"><span data-stu-id="11904-117">The following example shows how to configure activation settings within your web.config file.</span></span>

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

<span data-ttu-id="11904-118">L'utilizzo di questa configurazione consente di attivare GreetingService senza usare un file con estensione svc.</span><span class="sxs-lookup"><span data-stu-id="11904-118">Using this configuration, you can activate the GreetingService without using an .svc file.</span></span>

<span data-ttu-id="11904-119">Si noti che `<serviceHostingEnvironment>` è una configurazione a livello di applicazione.</span><span class="sxs-lookup"><span data-stu-id="11904-119">Note that `<serviceHostingEnvironment>` is an application level configuration.</span></span> <span data-ttu-id="11904-120">È necessario posizionare il file `web.config` contenente la configurazione nella radice dell'applicazione virtuale.</span><span class="sxs-lookup"><span data-stu-id="11904-120">You have to place the `web.config` containing the configuration under the root of the virtual Application.</span></span> <span data-ttu-id="11904-121">Inoltre, `serviceHostingEnvironment` è una sezione ereditabile machineToApplication.</span><span class="sxs-lookup"><span data-stu-id="11904-121">In addition, `serviceHostingEnvironment` is a machineToApplication inheritable section.</span></span> <span data-ttu-id="11904-122">Se si registra un servizio nella radice del computer, ogni servizio dell'applicazione erediterà tale servizio.</span><span class="sxs-lookup"><span data-stu-id="11904-122">If you register a single service in the root of the machine, every service in the application will inherit this service.</span></span>

<span data-ttu-id="11904-123">L'attivazione basata sulla configurazione supporta l'attivazione sul protocollo http e non http.</span><span class="sxs-lookup"><span data-stu-id="11904-123">Configuration-based activation supports activation over both http and non-http protocol.</span></span> <span data-ttu-id="11904-124">Richiede le estensioni in relativeAddress, ad esempio SVC, xoml o xamlx.</span><span class="sxs-lookup"><span data-stu-id="11904-124">It requires extensions in the relativeAddress i.e. .svc, .xoml or .xamlx.</span></span> <span data-ttu-id="11904-125">È possibile eseguire il mapping di estensioni personalizzate ai provider di compilazione noti, consentendo in tal modo l'attivazione di servizi su qualsiasi estensione.</span><span class="sxs-lookup"><span data-stu-id="11904-125">You can map your own extensions to the know buildProviders, which will then enable you to activate service over any extension.</span></span> <span data-ttu-id="11904-126">In caso di conflitto, la sezione `<serviceActivations>` esegue l'override delle registrazioni nel file con estensione svc.</span><span class="sxs-lookup"><span data-stu-id="11904-126">Upon conflict, the `<serviceActivations>` section overrides .svc registrations.</span></span>

## <a name="see-also"></a><span data-ttu-id="11904-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="11904-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceActivationElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
