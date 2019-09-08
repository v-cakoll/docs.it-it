---
title: Estensione di WCF
ms.date: 03/30/2017
helpviewer_keywords:
- WCF, extensibility
- extensibility [WCF]
- Windows Communication Foundation, extensibility
ms.assetid: c145e2f6-f402-41f5-8b5a-eee03978737b
ms.openlocfilehash: 037182a3cb105f544e15a05f955c142ba57f62f3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795533"
---
# <a name="extending-wcf"></a><span data-ttu-id="7232b-102">Estensione di WCF</span><span class="sxs-lookup"><span data-stu-id="7232b-102">Extending WCF</span></span>
<span data-ttu-id="7232b-103">Windows Communication Foundation (WCF) consente di modificare ed estendere i componenti di runtime per controllare e estendere con precisione le applicazioni basate su servizi.</span><span class="sxs-lookup"><span data-stu-id="7232b-103">Windows Communication Foundation (WCF) allows you to modify and extend run time components to precisely control and extend service-based applications.</span></span> <span data-ttu-id="7232b-104">Negli argomenti di questa sezione viene esaminata in modo approfondito l'architettura di estendibilità.</span><span class="sxs-lookup"><span data-stu-id="7232b-104">The topics in this section go in depth about the extensibility architecture.</span></span> <span data-ttu-id="7232b-105">Per ulteriori informazioni sulla programmazione di base, vedere [programmazione WCF di base](../basic-wcf-programming.md).</span><span class="sxs-lookup"><span data-stu-id="7232b-105">For more information about basic programming, see [Basic WCF Programming](../basic-wcf-programming.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7232b-106">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="7232b-106">In This Section</span></span>  
 [<span data-ttu-id="7232b-107">Estensione di ServiceHost e del livello del modello di servizi</span><span class="sxs-lookup"><span data-stu-id="7232b-107">Extending ServiceHost and the Service Model Layer</span></span>](extending-servicehost-and-the-service-model-layer.md)  
 <span data-ttu-id="7232b-108">Il livello del modello di servizi è responsabile del pull dei messaggi in arrivo dai canali sottostanti, della loro conversione in chiamate al metodo nel codice dell'applicazione e della restituzione dei risultati al chiamante.</span><span class="sxs-lookup"><span data-stu-id="7232b-108">The service model layer is responsible for pulling incoming messages out of the underlying channels, translating them into method invocations in application code, and sending the results back to the caller.</span></span>  <span data-ttu-id="7232b-109">Le estensioni del modello di servizi modificano o implementano il comportamento e le funzioni dell'esecuzione o della comunicazione relativamente a funzionalità del dispatcher, comportamenti personalizzati, intercettazione di messaggi e parametri e altre funzionalità di estendibilità.</span><span class="sxs-lookup"><span data-stu-id="7232b-109">Service model extensions modify or implement execution or communication behavior and features involving dispatcher functionality, custom behaviors, message and parameter interception, and other extensibility functionality.</span></span>  
  
 [<span data-ttu-id="7232b-110">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="7232b-110">Extending Bindings</span></span>](extending-bindings.md)  
 <span data-ttu-id="7232b-111">Le associazioni sono oggetti che descrivono i dettagli di comunicazione necessari per connettersi a un endpoint.</span><span class="sxs-lookup"><span data-stu-id="7232b-111">Bindings are objects that describe the communication details required to connect to an endpoint.</span></span> <span data-ttu-id="7232b-112">Le estensioni di associazione o le associazioni personalizzate implementano le funzionalità personalizzate di comunicazione necessarie per supportare le funzionalità dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7232b-112">Binding extensions or custom bindings implement custom communication functionality required to support application features.</span></span>  
  
 [<span data-ttu-id="7232b-113">Estensione del livello del canale</span><span class="sxs-lookup"><span data-stu-id="7232b-113">Extending the Channel Layer</span></span>](extending-the-channel-layer.md)  
 <span data-ttu-id="7232b-114">Il livello del canale è posto sotto il livello del modello di servizio ed è responsabile dello scambio dei messaggi tra client e servizi.</span><span class="sxs-lookup"><span data-stu-id="7232b-114">The channel layer sits beneath the service model layer and is responsible for the exchange of messages between clients and services.</span></span> <span data-ttu-id="7232b-115">Le estensioni del canale possono implementare nuove funzionalità del protocollo, ad esempio la protezione.</span><span class="sxs-lookup"><span data-stu-id="7232b-115">Channel extensions can implement new protocol functionality, such as security.</span></span> <span data-ttu-id="7232b-116">Possono inoltre implementare funzionalità di trasporto, ad esempio, implementando un nuovo trasporto di rete per il trasporto di messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="7232b-116">Channel extensions also transport functionality, such as implementing a new network transport to carry SOAP messages.</span></span>  
  
 [<span data-ttu-id="7232b-117">Estensione della sicurezza</span><span class="sxs-lookup"><span data-stu-id="7232b-117">Extending Security</span></span>](extending-security.md)  
 <span data-ttu-id="7232b-118">La sicurezza in WCF è costituita dalla sicurezza del trasferimento (integrità, riservatezza e autenticazione), dal controllo di accesso (autorizzazione) e dal controllo.</span><span class="sxs-lookup"><span data-stu-id="7232b-118">Security in WCF consists of transfer security (integrity, confidentiality, and authentication), access control (authorization) and auditing.</span></span> <span data-ttu-id="7232b-119">Le classi disponibili nello `IdentityModel` spazio dei nomi vengono utilizzate da WCF per il controllo di accesso.</span><span class="sxs-lookup"><span data-stu-id="7232b-119">The classes found in the `IdentityModel` namespace are used by WCF for access control.</span></span> <span data-ttu-id="7232b-120">Se si comprendono tutti gli aspetti dell'architettura di sicurezza è possibile creare tipi di attestazione personalizzati per adattare sistemi di controllo dell'accesso personalizzati.</span><span class="sxs-lookup"><span data-stu-id="7232b-120">Understanding the security architecture allows you to create custom claim types to accommodate custom access control systems.</span></span>  
  
 [<span data-ttu-id="7232b-121">Estensione del sistema di metadati</span><span class="sxs-lookup"><span data-stu-id="7232b-121">Extending the Metadata System</span></span>](extending-the-metadata-system.md)  
 <span data-ttu-id="7232b-122">Il sistema di metadati WCF è un gruppo di classi e interfacce che rappresentano i metadati necessari per implementare applicazioni basate su servizi.</span><span class="sxs-lookup"><span data-stu-id="7232b-122">The WCF metadata system is a group of classes and interfaces that represent metadata required to implement service-based applications.</span></span> <span data-ttu-id="7232b-123">Modificare o estendere le classi o implementare e configurare le interfacce per esportare e importare metadati personalizzati quali estensioni WSDL (Web Services Description Language) o asserzioni di WS-PolicyAttachments personalizzate.</span><span class="sxs-lookup"><span data-stu-id="7232b-123">Modify or extend the classes or implement and configure the interfaces to export and import custom metadata such as Web Services Description Language (WSDL) extensions or custom WS-PolicyAttachments assertions.</span></span>  
  
 [<span data-ttu-id="7232b-124">Estensione di codificatori e serializzatori</span><span class="sxs-lookup"><span data-stu-id="7232b-124">Extending Encoders and Serializers</span></span>](extending-encoders-and-serializers.md)  
 <span data-ttu-id="7232b-125">I codificatori e i serializzatori convertono i dati da uno modulo a un altro.</span><span class="sxs-lookup"><span data-stu-id="7232b-125">Encoders and serializers translate data from one form to another.</span></span> <span data-ttu-id="7232b-126">Negli argomenti di questa sezione viene illustrato come estendere le classi fornite per soddisfare requisiti speciali.</span><span class="sxs-lookup"><span data-stu-id="7232b-126">The topics in this section discuss how to extend the supplied classes to meet special requirements.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="7232b-127">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="7232b-127">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Selectors>  
  
 <xref:System.IdentityModel.Tokens>  
  
## <a name="related-sections"></a><span data-ttu-id="7232b-128">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="7232b-128">Related Sections</span></span>  
 [<span data-ttu-id="7232b-129">Programmazione WCF di base</span><span class="sxs-lookup"><span data-stu-id="7232b-129">Basic WCF Programming</span></span>](../basic-wcf-programming.md)  
  
 [<span data-ttu-id="7232b-130">Dettagli delle funzionalità di WCF</span><span class="sxs-lookup"><span data-stu-id="7232b-130">WCF Feature Details</span></span>](../feature-details/index.md)  
  
 [<span data-ttu-id="7232b-131">Linee guida e procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="7232b-131">Guidelines and Best Practices</span></span>](../guidelines-and-best-practices.md)
