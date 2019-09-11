---
title: <add> di <serviceActivations>
ms.date: 03/30/2017
ms.assetid: e5b01fc8-ee84-48b7-95fd-95ab54fa871f
ms.openlocfilehash: a0f68717f765482f53e675458fae63d1a374d6fb
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850324"
---
# <a name="add-of-serviceactivations"></a><span data-ttu-id="0370a-102">\<aggiungere > di \<serviceActivations ></span><span class="sxs-lookup"><span data-stu-id="0370a-102">\<add> of \<serviceActivations></span></span>

<span data-ttu-id="0370a-103">Elemento di configurazione che consente di definire le impostazioni di attivazione del servizio virtuale che vengono mappate ai tipi di servizio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="0370a-103">A configuration element that allows you to define virtual service activation settings that map to your Windows Communication Foundation (WCF) service types.</span></span> <span data-ttu-id="0370a-104">In questo modo è possibile attivare servizi ospitati in WAS/IIS senza un file con estensione svc.</span><span class="sxs-lookup"><span data-stu-id="0370a-104">This makes it possible to activate services hosted in WAS/IIS without an .svc file.</span></span>

<span data-ttu-id="0370a-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0370a-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0370a-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="0370a-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="0370a-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> serviceHostingEnvironment**](servicehostingenvironment.md)</span><span class="sxs-lookup"><span data-stu-id="0370a-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)</span></span>\
<span data-ttu-id="0370a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> serviceActivations**](serviceactivations.md)</span><span class="sxs-lookup"><span data-stu-id="0370a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceActivations>**](serviceactivations.md)</span></span>\
<span data-ttu-id="0370a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Aggiungi >**</span><span class="sxs-lookup"><span data-stu-id="0370a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="0370a-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0370a-110">Syntax</span></span>

```xml
<serviceHostingEnvironment>
    <serviceActivations>
      <add factory="String"
           service="String" />
  </serviceActivations>
</serviceHostingEnvironment>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0370a-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="0370a-111">Attributes and Elements</span></span>

<span data-ttu-id="0370a-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="0370a-112">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="0370a-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="0370a-113">Attributes</span></span>

|<span data-ttu-id="0370a-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="0370a-114">Attribute</span></span>|<span data-ttu-id="0370a-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0370a-115">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="0370a-116">factory</span><span class="sxs-lookup"><span data-stu-id="0370a-116">factory</span></span>|<span data-ttu-id="0370a-117">Stringa che specifica il tipo CLR della factory che genera un elemento di attivazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="0370a-117">A string that specifies the CLR type name of the factory that generates a service activation element.</span></span>|
|<span data-ttu-id="0370a-118">servizio</span><span class="sxs-lookup"><span data-stu-id="0370a-118">service</span></span>|<span data-ttu-id="0370a-119">ServiceType che implementa il servizio, ossia il Typename completo o il Typename breve, quando viene inserito nella cartella App_Code.</span><span class="sxs-lookup"><span data-stu-id="0370a-119">The ServiceType that implements the service (either the full qualified Typename or the short Typename (when it is placed in the App_Code folder).</span></span>|
|<span data-ttu-id="0370a-120">relativeAddress</span><span class="sxs-lookup"><span data-stu-id="0370a-120">relativeAddress</span></span>|<span data-ttu-id="0370a-121">Indirizzo relativo all'interno dell'applicazione IIS corrente, ad esempio “Service.svc".</span><span class="sxs-lookup"><span data-stu-id="0370a-121">The relative address within the current IIS application - for example "Service.svc".</span></span> <span data-ttu-id="0370a-122">In WCF 4.0 questo indirizzo relativo deve contenere una delle estensioni di file note (svc, xamlx, ecc.). Nessun file fisico deve esistere per l'URL relativo</span><span class="sxs-lookup"><span data-stu-id="0370a-122">In WCF 4.0 this relative address has to contain one of the known file extensions (.svc, .xamlx, ...). No physical file has to exist for the relativeUrl</span></span>|

### <a name="child-elements"></a><span data-ttu-id="0370a-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="0370a-123">Child Elements</span></span>

<span data-ttu-id="0370a-124">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="0370a-124">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0370a-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="0370a-125">Parent Elements</span></span>

|<span data-ttu-id="0370a-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="0370a-126">Element</span></span>|<span data-ttu-id="0370a-127">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="0370a-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0370a-128">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="0370a-128">\<serviceHostingEnvironment></span></span>](servicehostingenvironment.md)|<span data-ttu-id="0370a-129">Sezione di configurazione in cui vengono descritte le impostazioni di attivazione.</span><span class="sxs-lookup"><span data-stu-id="0370a-129">A configuration section that describes activation settings.</span></span>|

## <a name="remarks"></a><span data-ttu-id="0370a-130">Note</span><span class="sxs-lookup"><span data-stu-id="0370a-130">Remarks</span></span>

<span data-ttu-id="0370a-131">Nell'esempio seguente viene illustrato come configurare le impostazioni di attivazione all'interno del file web.config.</span><span class="sxs-lookup"><span data-stu-id="0370a-131">The following example shows how to configure activation settings within your web.config file.</span></span>

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

<span data-ttu-id="0370a-132">L'utilizzo di questa configurazione consente di attivare GreetingService senza usare un file con estensione svc.</span><span class="sxs-lookup"><span data-stu-id="0370a-132">Using this configuration, you can activate the GreetingService without using an .svc file.</span></span>

<span data-ttu-id="0370a-133">Si noti che `<serviceHostingEnvironment>` è una configurazione a livello di applicazione.</span><span class="sxs-lookup"><span data-stu-id="0370a-133">Note that `<serviceHostingEnvironment>` is an application level configuration.</span></span> <span data-ttu-id="0370a-134">È necessario posizionare il file `web.config` contenente la configurazione nella radice dell'applicazione virtuale.</span><span class="sxs-lookup"><span data-stu-id="0370a-134">You have to place the `web.config` containing the configuration under the root of the virtual Application.</span></span> <span data-ttu-id="0370a-135">Inoltre, `serviceHostingEnvironment` è una sezione ereditabile machineToApplication.</span><span class="sxs-lookup"><span data-stu-id="0370a-135">In addition, `serviceHostingEnvironment` is a machineToApplication inheritable section.</span></span> <span data-ttu-id="0370a-136">Se si registra un servizio nella radice del computer, ogni servizio dell'applicazione erediterà tale servizio.</span><span class="sxs-lookup"><span data-stu-id="0370a-136">If you register a single service in the root of the machine, every service in the application will inherit this service.</span></span>

<span data-ttu-id="0370a-137">L'attivazione basata sulla configurazione supporta l'attivazione sul protocollo http e non http.</span><span class="sxs-lookup"><span data-stu-id="0370a-137">Configuration-based activation supports activation over both http and non-http protocol.</span></span> <span data-ttu-id="0370a-138">Sono necessarie le estensioni in relativeAddress, ad esempio SVC, xoml o xamlx.</span><span class="sxs-lookup"><span data-stu-id="0370a-138">It requires extensions in the relativeAddress, i.e. .svc, .xoml or .xamlx.</span></span> <span data-ttu-id="0370a-139">È possibile eseguire il mapping di estensioni personalizzate ai provider di compilazione noti, consentendo in tal modo l'attivazione di servizi su qualsiasi estensione.</span><span class="sxs-lookup"><span data-stu-id="0370a-139">You can map your own extensions to the know buildProviders, which will then enable you to activate service over any extension.</span></span> <span data-ttu-id="0370a-140">In caso di conflitto, la sezione `<serviceActivations>` esegue l'override delle registrazioni nel file con estensione svc.</span><span class="sxs-lookup"><span data-stu-id="0370a-140">Upon conflict, the `<serviceActivations>` section overrides .svc registrations.</span></span>

## <a name="see-also"></a><span data-ttu-id="0370a-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0370a-141">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceActivationElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
