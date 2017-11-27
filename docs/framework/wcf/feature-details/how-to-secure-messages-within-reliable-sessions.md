---
title: 'Procedura: proteggere i messaggi in sessioni affidabili'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aee33e50-936f-4486-9ca8-c1520c19a62d
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 3f27b1a4de2019660e0facb081300a79eae65b99
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-secure-messages-within-reliable-sessions"></a><span data-ttu-id="c617e-102">Procedura: proteggere i messaggi in sessioni affidabili</span><span class="sxs-lookup"><span data-stu-id="c617e-102">How to: Secure Messages within Reliable Sessions</span></span>

<span data-ttu-id="c617e-103">In questo argomento vengono delineati i passaggi necessari per attivare la protezione a livello di messaggio per i messaggi scambiati all'interno di una sessione affidabile utilizzando una delle associazioni fornite dal sistema che supportano tale sessione, ma non per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="c617e-103">This topic outlines the steps required to enable message-level security for messages exchanged within a reliable session using one of the system-provided bindings that support such a session, but not by default.</span></span> <span data-ttu-id="c617e-104">Abilitare una sessione protetta e affidabile in modo imperativo tramite codice o in modo dichiarativo nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="c617e-104">Enable a secure, reliable session either imperatively by using code or declaratively in the configuration file.</span></span> <span data-ttu-id="c617e-105">In questa procedura vengono utilizzati i file di configurazione del client e del servizio per attivare la sessione affidabile protetta.</span><span class="sxs-lookup"><span data-stu-id="c617e-105">This procedure uses the client and service configuration files to enable the secure, reliable session.</span></span>

<span data-ttu-id="c617e-106">Questa procedura è costituita dalle tre attività chiave seguenti:</span><span class="sxs-lookup"><span data-stu-id="c617e-106">This procedure consists of the following three key tasks:</span></span>

1. <span data-ttu-id="c617e-107">Specificare che il client e il servizio si scambiano messaggi in una sessione affidabile.</span><span class="sxs-lookup"><span data-stu-id="c617e-107">Specify that the client and service exchange messages within a reliable session.</span></span>

1. <span data-ttu-id="c617e-108">Richiedere la protezione a livello di messaggio all'interno della sessione affidabile.</span><span class="sxs-lookup"><span data-stu-id="c617e-108">Require message-level security within the reliable session.</span></span>

1. <span data-ttu-id="c617e-109">Specificare il tipo di credenziale client che il client deve utilizzare per essere autenticato con il servizio.</span><span class="sxs-lookup"><span data-stu-id="c617e-109">Specify the client credential type that the client must use to be authenticated with the service.</span></span>

<span data-ttu-id="c617e-110">È importante nell'attività prima che l'elemento di configurazione endpoint contenga un `bindingConfiguration` attributo che fa riferimento a una configurazione di associazione denominata (in questo esempio) `MessageSecurity`.</span><span class="sxs-lookup"><span data-stu-id="c617e-110">It's important in the first task that the endpoint configuration element contain a `bindingConfiguration` attribute that references a binding configuration named (in this example) `MessageSecurity`.</span></span> <span data-ttu-id="c617e-111">Il [  **\<associazione >** ](../../../../docs/framework/misc/binding.md) elemento di configurazione fa quindi riferimento a questo nome per abilitare sessioni affidabili impostando il `enabled` attributo del [  **\<reliableSession >** ](http://msdn.microsoft.com/en-us/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b) elemento `true`.</span><span class="sxs-lookup"><span data-stu-id="c617e-111">The [**\<binding>**](../../../../docs/framework/misc/binding.md) configuration element then references this name to enable reliable sessions by setting the `enabled` attribute of the [**\<reliableSession>**](http://msdn.microsoft.com/en-us/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b) element to `true`.</span></span> <span data-ttu-id="c617e-112">È possibile richiedere che le garanzie di recapito ordinato siano disponibili all'interno di una sessione affidabile impostando l'attributo `ordered` su `true`.</span><span class="sxs-lookup"><span data-stu-id="c617e-112">You can require that the ordered delivery assurances are available within a reliable session by setting the `ordered` attribute to `true`.</span></span>

<span data-ttu-id="c617e-113">Per la copia origine dell'esempio in cui è basato su questa procedura di configurazione, vedere il [sessione affidabile WS](../../../../docs/framework/wcf/samples/ws-reliable-session.md).</span><span class="sxs-lookup"><span data-stu-id="c617e-113">For the source copy of the example on which this configuration procedure is based, see the [WS Reliable Session](../../../../docs/framework/wcf/samples/ws-reliable-session.md).</span></span>

<span data-ttu-id="c617e-114">Gli elementi essenziali della seconda attività vengono eseguiti tramite l'impostazione di `mode` attributo del  **\<sicurezza >** elemento contenuto nel  **\<associazione >** elemento del client e servizio `Message`.</span><span class="sxs-lookup"><span data-stu-id="c617e-114">The essential items of the second task are accomplished by setting the `mode` attribute of the **\<security>** element contained in the **\<binding>** element of the client and service to `Message`.</span></span>

<span data-ttu-id="c617e-115">Gli elementi essenziali della terza attività vengono eseguiti tramite l'impostazione di `clientCredentialType` attributo del  **\<messaggio >** elemento contenuto nel  **\<sicurezza >** elemento del client e servizio `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="c617e-115">The essential items of the third task are accomplished by setting the `clientCredentialType` attribute of the **\<message>** element contained in the **\<security>** element of the client and service to `Certificate`.</span></span>

> [!NOTE]
> <span data-ttu-id="c617e-116">Quando si utilizza la sicurezza dei messaggi con sessioni affidabili, messaggistica affidabile tenta di autenticare un client non autenticato fino a quando non si verifica un timeout anziché generare un'eccezione al primo errore.</span><span class="sxs-lookup"><span data-stu-id="c617e-116">When using message security with reliable sessions, Reliable Messaging attempts to authenticate an unauthenticated client until a timeout occurs instead of throwing an exception upon first failure.</span></span>

### <a name="configure-the-service-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="c617e-117">Configurare il servizio con una classe WSHttpBinding per utilizzare una sessione affidabile</span><span class="sxs-lookup"><span data-stu-id="c617e-117">Configure the service with a WSHttpBinding to use a reliable session</span></span>

<span data-ttu-id="c617e-118">Questa procedura è descritta [come: Exchange messaggi all'interno di una sessione affidabile](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md).</span><span class="sxs-lookup"><span data-stu-id="c617e-118">This procedure is described in [How to: Exchange Messages Within a Reliable Session](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md).</span></span>

### <a name="configure-the-client-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="c617e-119">Configurare il client con una classe WSHttpBinding per utilizzare una sessione affidabile</span><span class="sxs-lookup"><span data-stu-id="c617e-119">Configure the client with a WSHttpBinding to use a reliable session</span></span>

<span data-ttu-id="c617e-120">Questa procedura è descritta [come: Exchange messaggi all'interno di una sessione affidabile](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md).</span><span class="sxs-lookup"><span data-stu-id="c617e-120">This procedure is described in [How to: Exchange Messages Within a Reliable Session](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md).</span></span>

### <a name="set-the-mode-and-clientcredentialtype-in-configuration"></a><span data-ttu-id="c617e-121">Impostare la modalità e la proprietà ClientCredentialType nella configurazione</span><span class="sxs-lookup"><span data-stu-id="c617e-121">Set the mode and ClientCredentialType in configuration</span></span>

1. <span data-ttu-id="c617e-122">Aggiungere un elemento di associazione appropriata di [  **\<associazioni >** ](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) elemento del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="c617e-122">Add an appropriate binding element to the [**\<bindings>**](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element of the configuration file.</span></span> <span data-ttu-id="c617e-123">L'esempio seguente aggiunge un [  **\<wsHttpBinding >** ](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="c617e-123">The following example adds a [**\<wsHttpBinding>**](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>

1. <span data-ttu-id="c617e-124">Aggiungere un  **\<associazione >** elemento e impostare il relativo `name` attributo su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="c617e-124">Add a **\<binding>** element and set its `name` attribute to an appropriate value.</span></span> <span data-ttu-id="c617e-125">Nell'esempio viene utilizzato il nome `MessageSecurity`.</span><span class="sxs-lookup"><span data-stu-id="c617e-125">The example uses the name `MessageSecurity`.</span></span>

1. <span data-ttu-id="c617e-126">Aggiungere un  **\<sicurezza >** elemento e impostare il `mode` attributo `Message`.</span><span class="sxs-lookup"><span data-stu-id="c617e-126">Add a **\<security>** element and set the `mode` attribute to `Message`.</span></span>

1. <span data-ttu-id="c617e-127">All'interno di  **\<sicurezza >** elemento, aggiungere un  **\<messaggio >** elemento e impostare il `clientCredentialType` attributo `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="c617e-127">Within the **\<security>** element, add a **\<message>** element and set the `clientCredentialType` attribute to `Certificate`.</span></span>

```xml
<wsHttpBinding>
  <binding name="MessageSecurity">
    <security mode="Message">
      <message clientCredentialType="Certificate" />
    </security>
  </binding>
</wsHttpBinding>
```
