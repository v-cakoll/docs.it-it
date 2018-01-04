---
title: Estensione di WCF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF, extensibility
- extensibility [WCF]
- Windows Communication Foundation, extensibility
ms.assetid: c145e2f6-f402-41f5-8b5a-eee03978737b
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2c84f25dfd5d3066f9c5d0b62bc0b28bc98c283d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="extending-wcf"></a><span data-ttu-id="093bc-102">Estensione di WCF</span><span class="sxs-lookup"><span data-stu-id="093bc-102">Extending WCF</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="093bc-103"> consente di modificare ed estendere i componenti di runtime per controllare in modo accurato ed estendere le applicazioni basate sui servizi.</span><span class="sxs-lookup"><span data-stu-id="093bc-103"> allows you to modify and extend run time components to precisely control and extend service-based applications.</span></span> <span data-ttu-id="093bc-104">Negli argomenti di questa sezione viene esaminata in modo approfondito l'architettura di estendibilità.</span><span class="sxs-lookup"><span data-stu-id="093bc-104">The topics in this section go in depth about the extensibility architecture.</span></span> <span data-ttu-id="093bc-105">Per ulteriori informazioni sulla programmazione di base, vedere [programmazione WCF di base](../../../../docs/framework/wcf/basic-wcf-programming.md).</span><span class="sxs-lookup"><span data-stu-id="093bc-105">For more information about basic programming, see [Basic WCF Programming](../../../../docs/framework/wcf/basic-wcf-programming.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="093bc-106">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="093bc-106">In This Section</span></span>  
 [<span data-ttu-id="093bc-107">Estensione di ServiceHost e del livello del modello di servizi</span><span class="sxs-lookup"><span data-stu-id="093bc-107">Extending ServiceHost and the Service Model Layer</span></span>](../../../../docs/framework/wcf/extending/extending-servicehost-and-the-service-model-layer.md)  
 <span data-ttu-id="093bc-108">Il livello del modello di servizi è responsabile del pull dei messaggi in arrivo dai canali sottostanti, della loro conversione in chiamate al metodo nel codice dell'applicazione e della restituzione dei risultati al chiamante.</span><span class="sxs-lookup"><span data-stu-id="093bc-108">The service model layer is responsible for pulling incoming messages out of the underlying channels, translating them into method invocations in application code, and sending the results back to the caller.</span></span>  <span data-ttu-id="093bc-109">Le estensioni del modello di servizi modificano o implementano il comportamento e le funzionalità dell'esecuzione o della comunicazione relativamente a funzionalità del dispatcher, comportamenti personalizzati, intercettazione di messaggi e parametri e altre funzionalità di estendibilità.</span><span class="sxs-lookup"><span data-stu-id="093bc-109">Service model extensions modify or implement execution or communication behavior and features involving dispatcher functionality, custom behaviors, message and parameter interception, and other extensibility functionality.</span></span>  
  
 [<span data-ttu-id="093bc-110">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="093bc-110">Extending Bindings</span></span>](../../../../docs/framework/wcf/extending/extending-bindings.md)  
 <span data-ttu-id="093bc-111">Le associazioni sono oggetti che descrivono i dettagli di comunicazione necessari per connettersi a un endpoint.</span><span class="sxs-lookup"><span data-stu-id="093bc-111">Bindings are objects that describe the communication details required to connect to an endpoint.</span></span> <span data-ttu-id="093bc-112">Le estensioni di associazione o le associazioni personalizzate implementano le funzionalità personalizzate di comunicazione necessarie per supportare le funzionalità dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="093bc-112">Binding extensions or custom bindings implement custom communication functionality required to support application features.</span></span>  
  
 [<span data-ttu-id="093bc-113">Estensione del livello del canale</span><span class="sxs-lookup"><span data-stu-id="093bc-113">Extending the Channel Layer</span></span>](../../../../docs/framework/wcf/extending/extending-the-channel-layer.md)  
 <span data-ttu-id="093bc-114">Il livello del canale è posto sotto il livello del modello di servizio ed è responsabile dello scambio dei messaggi tra client e servizi.</span><span class="sxs-lookup"><span data-stu-id="093bc-114">The channel layer sits beneath the service model layer and is responsible for the exchange of messages between clients and services.</span></span> <span data-ttu-id="093bc-115">Le estensioni del canale possono implementare nuove funzionalità del protocollo, ad esempio la protezione.</span><span class="sxs-lookup"><span data-stu-id="093bc-115">Channel extensions can implement new protocol functionality, such as security.</span></span> <span data-ttu-id="093bc-116">Possono inoltre implementare funzionalità di trasporto, ad esempio, implementando un nuovo trasporto di rete per il trasporto di messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="093bc-116">Channel extensions also transport functionality, such as implementing a new network transport to carry SOAP messages.</span></span>  
  
 [<span data-ttu-id="093bc-117">Estensione della sicurezza</span><span class="sxs-lookup"><span data-stu-id="093bc-117">Extending Security</span></span>](../../../../docs/framework/wcf/extending/extending-security.md)  
 <span data-ttu-id="093bc-118">La protezione in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] è costituita dalla protezione del trasferimento (integrità, riservatezza e autenticazione), dal controllo dell'accesso (autorizzazione) e dal controllo.</span><span class="sxs-lookup"><span data-stu-id="093bc-118">Security in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] consists of transfer security (integrity, confidentiality, and authentication), access control (authorization) and auditing.</span></span> <span data-ttu-id="093bc-119">Le classi disponibili nello spazio dei nomi `IdentityModel` vengono usate da [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] per il controllo dell'accesso.</span><span class="sxs-lookup"><span data-stu-id="093bc-119">The classes found in the `IdentityModel` namespace are used by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] for access control.</span></span> <span data-ttu-id="093bc-120">Se si comprendono tutti gli aspetti dell'architettura di sicurezza è possibile creare tipi di attestazione personalizzati per adattare sistemi di controllo dell'accesso personalizzati.</span><span class="sxs-lookup"><span data-stu-id="093bc-120">Understanding the security architecture allows you to create custom claim types to accommodate custom access control systems.</span></span>  
  
 [<span data-ttu-id="093bc-121">Estensione del sistema di metadati</span><span class="sxs-lookup"><span data-stu-id="093bc-121">Extending the Metadata System</span></span>](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md)  
 <span data-ttu-id="093bc-122">Il sistema dei metadati di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] è un gruppo di classi e interfacce che rappresentano i metadati necessari per implementare applicazioni basate sul servizio.</span><span class="sxs-lookup"><span data-stu-id="093bc-122">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] metadata system is a group of classes and interfaces that represent metadata required to implement service-based applications.</span></span> <span data-ttu-id="093bc-123">Modificare o estendere le classi o implementare e configurare le interfacce per esportare e importare metadati personalizzati quali estensioni WSDL (Web Services Description Language) o asserzioni di WS-PolicyAttachments personalizzate.</span><span class="sxs-lookup"><span data-stu-id="093bc-123">Modify or extend the classes or implement and configure the interfaces to export and import custom metadata such as Web Services Description Language (WSDL) extensions or custom WS-PolicyAttachments assertions.</span></span>  
  
 [<span data-ttu-id="093bc-124">Estensione di codificatori e serializzatori</span><span class="sxs-lookup"><span data-stu-id="093bc-124">Extending Encoders and Serializers</span></span>](../../../../docs/framework/wcf/extending/extending-encoders-and-serializers.md)  
 <span data-ttu-id="093bc-125">I codificatori e i serializzatori convertono i dati da uno modulo a un altro.</span><span class="sxs-lookup"><span data-stu-id="093bc-125">Encoders and serializers translate data from one form to another.</span></span> <span data-ttu-id="093bc-126">Negli argomenti di questa sezione viene illustrato come estendere le classi fornite per soddisfare requisiti speciali.</span><span class="sxs-lookup"><span data-stu-id="093bc-126">The topics in this section discuss how to extend the supplied classes to meet special requirements.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="093bc-127">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="093bc-127">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Selectors>  
  
 <xref:System.IdentityModel.Tokens>  
  
## <a name="related-sections"></a><span data-ttu-id="093bc-128">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="093bc-128">Related Sections</span></span>  
 [<span data-ttu-id="093bc-129">Programmazione WCF di base</span><span class="sxs-lookup"><span data-stu-id="093bc-129">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)  
  
 [<span data-ttu-id="093bc-130">Dettagli delle funzionalità di WCF</span><span class="sxs-lookup"><span data-stu-id="093bc-130">WCF Feature Details</span></span>](../../../../docs/framework/wcf/feature-details/index.md)  
  
 [<span data-ttu-id="093bc-131">Linee guida e procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="093bc-131">Guidelines and Best Practices</span></span>](../../../../docs/framework/wcf/guidelines-and-best-practices.md)
