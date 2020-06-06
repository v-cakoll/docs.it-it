---
title: <add> di <serviceActivations>
ms.date: 03/30/2017
ms.assetid: e5b01fc8-ee84-48b7-95fd-95ab54fa871f
ms.openlocfilehash: a0f68717f765482f53e675458fae63d1a374d6fb
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850324"
---
# <a name="add-of-serviceactivations"></a><span data-ttu-id="1b63f-102">\<add> di \<serviceActivations></span><span class="sxs-lookup"><span data-stu-id="1b63f-102">\<add> of \<serviceActivations></span></span>

<span data-ttu-id="1b63f-103">Elemento di configurazione che consente di definire le impostazioni di attivazione del servizio virtuale che vengono mappate ai tipi di servizio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="1b63f-103">A configuration element that allows you to define virtual service activation settings that map to your Windows Communication Foundation (WCF) service types.</span></span> <span data-ttu-id="1b63f-104">In questo modo è possibile attivare servizi ospitati in WAS/IIS senza un file con estensione svc.</span><span class="sxs-lookup"><span data-stu-id="1b63f-104">This makes it possible to activate services hosted in WAS/IIS without an .svc file.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceActivations>**](serviceactivations.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  

## <a name="syntax"></a><span data-ttu-id="1b63f-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1b63f-105">Syntax</span></span>

```xml
<serviceHostingEnvironment>
    <serviceActivations>
      <add factory="String"
           service="String" />
  </serviceActivations>
</serviceHostingEnvironment>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1b63f-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1b63f-106">Attributes and Elements</span></span>

<span data-ttu-id="1b63f-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1b63f-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="1b63f-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="1b63f-108">Attributes</span></span>

|<span data-ttu-id="1b63f-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="1b63f-109">Attribute</span></span>|<span data-ttu-id="1b63f-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1b63f-110">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="1b63f-111">factory</span><span class="sxs-lookup"><span data-stu-id="1b63f-111">factory</span></span>|<span data-ttu-id="1b63f-112">Stringa che specifica il tipo CLR della factory che genera un elemento di attivazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="1b63f-112">A string that specifies the CLR type name of the factory that generates a service activation element.</span></span>|
|<span data-ttu-id="1b63f-113">service</span><span class="sxs-lookup"><span data-stu-id="1b63f-113">service</span></span>|<span data-ttu-id="1b63f-114">ServiceType che implementa il servizio, ossia il Typename completo o il Typename breve, quando viene inserito nella cartella App_Code.</span><span class="sxs-lookup"><span data-stu-id="1b63f-114">The ServiceType that implements the service (either the full qualified Typename or the short Typename (when it is placed in the App_Code folder).</span></span>|
|<span data-ttu-id="1b63f-115">relativeAddress</span><span class="sxs-lookup"><span data-stu-id="1b63f-115">relativeAddress</span></span>|<span data-ttu-id="1b63f-116">Indirizzo relativo all'interno dell'applicazione IIS corrente, ad esempio “Service.svc".</span><span class="sxs-lookup"><span data-stu-id="1b63f-116">The relative address within the current IIS application - for example "Service.svc".</span></span> <span data-ttu-id="1b63f-117">In WCF 4,0 questo indirizzo relativo deve contenere una delle estensioni di file note (SVC, xamlx,...). Nessun file fisico deve esistere per relativeUrl</span><span class="sxs-lookup"><span data-stu-id="1b63f-117">In WCF 4.0 this relative address has to contain one of the known file extensions (.svc, .xamlx, ...). No physical file has to exist for the relativeUrl</span></span>|

### <a name="child-elements"></a><span data-ttu-id="1b63f-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1b63f-118">Child Elements</span></span>

<span data-ttu-id="1b63f-119">No.</span><span class="sxs-lookup"><span data-stu-id="1b63f-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="1b63f-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1b63f-120">Parent Elements</span></span>

|<span data-ttu-id="1b63f-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="1b63f-121">Element</span></span>|<span data-ttu-id="1b63f-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1b63f-122">Description</span></span>|
|-------------|-----------------|
|[\<serviceHostingEnvironment>](servicehostingenvironment.md)|<span data-ttu-id="1b63f-123">Sezione di configurazione in cui vengono descritte le impostazioni di attivazione.</span><span class="sxs-lookup"><span data-stu-id="1b63f-123">A configuration section that describes activation settings.</span></span>|

## <a name="remarks"></a><span data-ttu-id="1b63f-124">Commenti</span><span class="sxs-lookup"><span data-stu-id="1b63f-124">Remarks</span></span>

<span data-ttu-id="1b63f-125">Nell'esempio seguente viene illustrato come configurare le impostazioni di attivazione all'interno del file web.config.</span><span class="sxs-lookup"><span data-stu-id="1b63f-125">The following example shows how to configure activation settings within your web.config file.</span></span>

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

<span data-ttu-id="1b63f-126">L'utilizzo di questa configurazione consente di attivare GreetingService senza usare un file con estensione svc.</span><span class="sxs-lookup"><span data-stu-id="1b63f-126">Using this configuration, you can activate the GreetingService without using an .svc file.</span></span>

<span data-ttu-id="1b63f-127">Si noti che `<serviceHostingEnvironment>` è una configurazione a livello di applicazione.</span><span class="sxs-lookup"><span data-stu-id="1b63f-127">Note that `<serviceHostingEnvironment>` is an application level configuration.</span></span> <span data-ttu-id="1b63f-128">È necessario posizionare il file `web.config` contenente la configurazione nella radice dell'applicazione virtuale.</span><span class="sxs-lookup"><span data-stu-id="1b63f-128">You have to place the `web.config` containing the configuration under the root of the virtual Application.</span></span> <span data-ttu-id="1b63f-129">Inoltre, `serviceHostingEnvironment` è una sezione ereditabile machineToApplication.</span><span class="sxs-lookup"><span data-stu-id="1b63f-129">In addition, `serviceHostingEnvironment` is a machineToApplication inheritable section.</span></span> <span data-ttu-id="1b63f-130">Se si registra un servizio nella radice del computer, ogni servizio dell'applicazione erediterà tale servizio.</span><span class="sxs-lookup"><span data-stu-id="1b63f-130">If you register a single service in the root of the machine, every service in the application will inherit this service.</span></span>

<span data-ttu-id="1b63f-131">L'attivazione basata sulla configurazione supporta l'attivazione sul protocollo http e non http.</span><span class="sxs-lookup"><span data-stu-id="1b63f-131">Configuration-based activation supports activation over both http and non-http protocol.</span></span> <span data-ttu-id="1b63f-132">Sono necessarie le estensioni in relativeAddress, ad esempio SVC, xoml o xamlx.</span><span class="sxs-lookup"><span data-stu-id="1b63f-132">It requires extensions in the relativeAddress, i.e. .svc, .xoml or .xamlx.</span></span> <span data-ttu-id="1b63f-133">È possibile eseguire il mapping di estensioni personalizzate ai provider di compilazione noti, consentendo in tal modo l'attivazione di servizi su qualsiasi estensione.</span><span class="sxs-lookup"><span data-stu-id="1b63f-133">You can map your own extensions to the know buildProviders, which will then enable you to activate service over any extension.</span></span> <span data-ttu-id="1b63f-134">In caso di conflitto, la sezione `<serviceActivations>` esegue l'override delle registrazioni nel file con estensione svc.</span><span class="sxs-lookup"><span data-stu-id="1b63f-134">Upon conflict, the `<serviceActivations>` section overrides .svc registrations.</span></span>

## <a name="see-also"></a><span data-ttu-id="1b63f-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b63f-135">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceActivationElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
