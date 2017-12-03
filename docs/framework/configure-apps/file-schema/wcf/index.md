---
title: Schema di configurazione di WCF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c282aeb5-91f0-4522-8e2f-704c1ef3651f
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 84e211a0ecd68634a08965a1a4cc1494e0df0713
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="wcf-configuration-schema"></a><span data-ttu-id="32a6f-102">Schema di configurazione di WCF</span><span class="sxs-lookup"><span data-stu-id="32a6f-102">WCF Configuration Schema</span></span>
<span data-ttu-id="32a6f-103">Gli elementi di configurazione di [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] consentono di configurare applicazioni [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] server e client.</span><span class="sxs-lookup"><span data-stu-id="32a6f-103">[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] configuration elements enable you to configure [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] service and client applications.</span></span> <span data-ttu-id="32a6f-104">È possibile usare lo [Strumento Editor di configurazione (SvcConfigEditor.exe)](../../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) per creare e modificare i file di configurazione di client e servizi.</span><span class="sxs-lookup"><span data-stu-id="32a6f-104">You can use the [Configuration Editor Tool (SvcConfigEditor.exe)](../../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) to create and modify configuration files for clients and services.</span></span> <span data-ttu-id="32a6f-105">Poiché i file di configurazione sono in formato XML, per modificarli manualmente usando un editor di testo è necessario avere familiarità con il linguaggio XML.</span><span class="sxs-lookup"><span data-stu-id="32a6f-105">Since the configuration files are formatted as XML, you must be familiar with XML if you want to manually edit them using a text editor.</span></span> <span data-ttu-id="32a6f-106">In caso contrario, è possibile che si verifichino problemi. È ad esempio possibile che un tag di elemento XML o un attributo venga digitato in modo errato.</span><span class="sxs-lookup"><span data-stu-id="32a6f-106">Otherwise, you may run into issues such as an unfound XML element tag or attribute.</span></span> <span data-ttu-id="32a6f-107">Per i tag di elemento XML e gli attributi viene applicata la distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="32a6f-107">This is because XML element tags and attributes are case-sensitive.</span></span>  
  
 <span data-ttu-id="32a6f-108">Il sistema di configurazione di [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] si basa sullo spazio dei nomi <xref:System.Configuration>.</span><span class="sxs-lookup"><span data-stu-id="32a6f-108">The [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] configuration system is based on the <xref:System.Configuration> namespace.</span></span> <span data-ttu-id="32a6f-109">È pertanto possibile usare tutte le funzionalità standard fornite dallo spazio dei nomi <xref:System.Configuration>, ad esempio il blocco, la crittografia e l'unione delle impostazioni di configurazione, allo scopo di aumentare la sicurezza dell'applicazione e della relativa configurazione.</span><span class="sxs-lookup"><span data-stu-id="32a6f-109">Therefore, you can use all the standard features provided by the <xref:System.Configuration> namespace, such as configuration locking, encryption and merging to increase the security of your application and its configuration.</span></span> <span data-ttu-id="32a6f-110">Per altre informazioni su questi concetti, vedere gli argomenti seguenti.</span><span class="sxs-lookup"><span data-stu-id="32a6f-110">For more information on these concepts, see the following topics.</span></span>  
  
 [<span data-ttu-id="32a6f-111">Crittografia delle informazioni di configurazione</span><span class="sxs-lookup"><span data-stu-id="32a6f-111">Encrypting Configuration Information</span></span>](http://go.microsoft.com/fwlink/?LinkId=95337)  
  
 [<span data-ttu-id="32a6f-112">Blocco delle impostazioni di configurazione</span><span class="sxs-lookup"><span data-stu-id="32a6f-112">Locking Configuration Settings</span></span>](http://go.microsoft.com/fwlink/?LinkId=95338)  
  
 <span data-ttu-id="32a6f-113">Questa sezione descrive tutti i valori possibili di ogni elemento di configurazione e le relative interazioni con gli altri elementi di configurazione di WCF.</span><span class="sxs-lookup"><span data-stu-id="32a6f-113">This section describes all possible values of each configuration item, and how it interacts with other WCF configuration elements.</span></span> <span data-ttu-id="32a6f-114">Nella mappa seguente viene illustrato lo schema di configurazione di WCF.</span><span class="sxs-lookup"><span data-stu-id="32a6f-114">The following map illustrates the WCF configuration schema.</span></span>  
  
 <span data-ttu-id="32a6f-115">![Schema di configurazione di WCF](../../../../../docs/framework/configure-apps/file-schema/wcf/media/orcasconfigschema.gif "OrcasConfigSchema")</span><span class="sxs-lookup"><span data-stu-id="32a6f-115">![WCF Configuration Schema](../../../../../docs/framework/configure-apps/file-schema/wcf/media/orcasconfigschema.gif "OrcasConfigSchema")</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="32a6f-116">Per evitare qualsiasi possibile rischio di sicurezza, è necessario usare gli elenchi di controllo di accesso (ACL, Access Control List) appropriati per proteggere le sezioni di configurazione di [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] nei file di configurazione dell'applicazione (app.config).</span><span class="sxs-lookup"><span data-stu-id="32a6f-116">You should protect [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] configuration sections in your application configuration files (app.config) with appropriate Access Control Lists (ACL) to prevent any potential security threats.</span></span>  <span data-ttu-id="32a6f-117">Ad esempio, è necessario garantire che solo gli utenti appropriati siano in grado di accedere o apportare modifiche alla sezione del modello dei servizi del file di configurazione di un servizio o alle impostazioni di sicurezza relative alle associazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="32a6f-117">For example, you should make sure that only the appropriate people can access or modify the security settings on application bindings, or the service model section of the configuration file for a service.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="32a6f-118">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="32a6f-118">In This Section</span></span>  
 [<span data-ttu-id="32a6f-119">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="32a6f-119">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)  
 <span data-ttu-id="32a6f-120">Descrive l'elemento `ServiceModel`.</span><span class="sxs-lookup"><span data-stu-id="32a6f-120">Describes the `ServiceModel` element.</span></span>  
  
 [<span data-ttu-id="32a6f-121">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="32a6f-121">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)  
 <span data-ttu-id="32a6f-122">Configura lo strumento SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="32a6f-122">Configures the SMSvcHost.exe tool.</span></span>  
  
 [<span data-ttu-id="32a6f-123">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="32a6f-123">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)  
 <span data-ttu-id="32a6f-124">Descrive l'elemento di livello superiore per l'impostazione delle opzioni quando si usano serializzatori quali <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="32a6f-124">The top-level element for setting options when using serializers such as the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="32a6f-125">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="32a6f-125">Related Sections</span></span>  
 [<span data-ttu-id="32a6f-126">Configurazione di applicazioni Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="32a6f-126">Configuring Windows Communication Foundation Applications</span></span>](http://msdn.microsoft.com/en-us/13cb368e-88d4-4c61-8eed-2af0361c6d7a)  
 <span data-ttu-id="32a6f-127">Descrive come configurare i servizi e i client [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32a6f-127">Describes how to configure [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services and clients.</span></span>
