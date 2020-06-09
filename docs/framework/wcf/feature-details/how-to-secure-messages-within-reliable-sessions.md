---
title: 'Procedura: proteggere i messaggi in sessioni affidabili'
ms.date: 03/30/2017
ms.assetid: aee33e50-936f-4486-9ca8-c1520c19a62d
ms.openlocfilehash: 306d0f96b5163fe5c24d270b4b9a7c1d3f499e7e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596955"
---
# <a name="how-to-secure-messages-within-reliable-sessions"></a><span data-ttu-id="1800d-102">Procedura: proteggere i messaggi in sessioni affidabili</span><span class="sxs-lookup"><span data-stu-id="1800d-102">How to: Secure Messages within Reliable Sessions</span></span>

<span data-ttu-id="1800d-103">In questo argomento vengono delineati i passaggi necessari per attivare la protezione a livello di messaggio per i messaggi scambiati all'interno di una sessione affidabile utilizzando una delle associazioni fornite dal sistema che supportano tale sessione, ma non per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="1800d-103">This topic outlines the steps required to enable message-level security for messages exchanged within a reliable session using one of the system-provided bindings that support such a session, but not by default.</span></span> <span data-ttu-id="1800d-104">Abilitare una sessione sicura e affidabile in modo imperativo tramite codice o in modo dichiarativo nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="1800d-104">Enable a secure, reliable session either imperatively by using code or declaratively in the configuration file.</span></span> <span data-ttu-id="1800d-105">In questa procedura vengono utilizzati i file di configurazione del client e del servizio per attivare la sessione affidabile protetta.</span><span class="sxs-lookup"><span data-stu-id="1800d-105">This procedure uses the client and service configuration files to enable the secure, reliable session.</span></span>

<span data-ttu-id="1800d-106">Questa procedura è costituita dalle tre attività chiave seguenti:</span><span class="sxs-lookup"><span data-stu-id="1800d-106">This procedure consists of the following three key tasks:</span></span>

1. <span data-ttu-id="1800d-107">Specificare che il client e il servizio si scambiano messaggi in una sessione affidabile.</span><span class="sxs-lookup"><span data-stu-id="1800d-107">Specify that the client and service exchange messages within a reliable session.</span></span>

1. <span data-ttu-id="1800d-108">Richiedere la protezione a livello di messaggio all'interno della sessione affidabile.</span><span class="sxs-lookup"><span data-stu-id="1800d-108">Require message-level security within the reliable session.</span></span>

1. <span data-ttu-id="1800d-109">Specificare il tipo di credenziale client che il client deve utilizzare per essere autenticato con il servizio.</span><span class="sxs-lookup"><span data-stu-id="1800d-109">Specify the client credential type that the client must use to be authenticated with the service.</span></span>

<span data-ttu-id="1800d-110">È importante nella prima attività che l'elemento di configurazione dell'endpoint contenga un `bindingConfiguration` attributo che fa riferimento a una configurazione di associazione denominata (in questo esempio) `MessageSecurity` .</span><span class="sxs-lookup"><span data-stu-id="1800d-110">It's important in the first task that the endpoint configuration element contain a `bindingConfiguration` attribute that references a binding configuration named (in this example) `MessageSecurity`.</span></span> <span data-ttu-id="1800d-111">L' [**\<binding>**](../../configure-apps/file-schema/wcf/bindings.md) elemento di configurazione fa quindi riferimento a questo nome per abilitare le sessioni affidabili impostando l' `enabled` attributo dell' [**\<reliableSession>**](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90)) elemento su `true` .</span><span class="sxs-lookup"><span data-stu-id="1800d-111">The [**\<binding>**](../../configure-apps/file-schema/wcf/bindings.md) configuration element then references this name to enable reliable sessions by setting the `enabled` attribute of the [**\<reliableSession>**](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90)) element to `true`.</span></span> <span data-ttu-id="1800d-112">È possibile richiedere che le garanzie di recapito ordinato siano disponibili all'interno di una sessione affidabile impostando l'attributo `ordered` su `true`.</span><span class="sxs-lookup"><span data-stu-id="1800d-112">You can require that the ordered delivery assurances are available within a reliable session by setting the `ordered` attribute to `true`.</span></span>

<span data-ttu-id="1800d-113">Per la copia di origine dell'esempio su cui si basa questa procedura di configurazione, vedere la [sessione WS Reliable](../samples/ws-reliable-session.md).</span><span class="sxs-lookup"><span data-stu-id="1800d-113">For the source copy of the example on which this configuration procedure is based, see the [WS Reliable Session](../samples/ws-reliable-session.md).</span></span>

<span data-ttu-id="1800d-114">Gli elementi essenziali della seconda attività vengono eseguiti impostando l' `mode` attributo dell' **\<security>** elemento contenuto nell' **\<binding>** elemento del client e del servizio su `Message` .</span><span class="sxs-lookup"><span data-stu-id="1800d-114">The essential items of the second task are accomplished by setting the `mode` attribute of the **\<security>** element contained in the **\<binding>** element of the client and service to `Message`.</span></span>

<span data-ttu-id="1800d-115">Gli elementi essenziali della terza attività vengono eseguiti impostando l' `clientCredentialType` attributo dell' **\<message>** elemento contenuto nell' **\<security>** elemento del client e del servizio su `Certificate` .</span><span class="sxs-lookup"><span data-stu-id="1800d-115">The essential items of the third task are accomplished by setting the `clientCredentialType` attribute of the **\<message>** element contained in the **\<security>** element of the client and service to `Certificate`.</span></span>

> [!NOTE]
> <span data-ttu-id="1800d-116">Quando si utilizza la sicurezza dei messaggi con sessioni affidabili, la messaggistica affidabile tenta di autenticare un client non autenticato fino a quando non si verifica un timeout anziché generare un'eccezione al primo errore.</span><span class="sxs-lookup"><span data-stu-id="1800d-116">When using message security with reliable sessions, Reliable Messaging attempts to authenticate an unauthenticated client until a timeout occurs instead of throwing an exception upon first failure.</span></span>

### <a name="configure-the-service-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="1800d-117">Configurare il servizio con WSHttpBinding per l'utilizzo di una sessione affidabile</span><span class="sxs-lookup"><span data-stu-id="1800d-117">Configure the service with a WSHttpBinding to use a reliable session</span></span>

<span data-ttu-id="1800d-118">Questa procedura è descritta in [procedura: scambiare messaggi in una sessione affidabile](how-to-exchange-messages-within-a-reliable-session.md).</span><span class="sxs-lookup"><span data-stu-id="1800d-118">This procedure is described in [How to: Exchange Messages Within a Reliable Session](how-to-exchange-messages-within-a-reliable-session.md).</span></span>

### <a name="configure-the-client-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="1800d-119">Configurare il client con WSHttpBinding per l'utilizzo di una sessione affidabile</span><span class="sxs-lookup"><span data-stu-id="1800d-119">Configure the client with a WSHttpBinding to use a reliable session</span></span>

<span data-ttu-id="1800d-120">Questa procedura è descritta in [procedura: scambiare messaggi in una sessione affidabile](how-to-exchange-messages-within-a-reliable-session.md).</span><span class="sxs-lookup"><span data-stu-id="1800d-120">This procedure is described in [How to: Exchange Messages Within a Reliable Session](how-to-exchange-messages-within-a-reliable-session.md).</span></span>

### <a name="set-the-mode-and-clientcredentialtype-in-configuration"></a><span data-ttu-id="1800d-121">Impostare la modalità e ClientCredentialType nella configurazione</span><span class="sxs-lookup"><span data-stu-id="1800d-121">Set the mode and ClientCredentialType in configuration</span></span>

1. <span data-ttu-id="1800d-122">Aggiungere un elemento di associazione appropriato all' [**\<bindings>**](../../configure-apps/file-schema/wcf/bindings.md) elemento del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="1800d-122">Add an appropriate binding element to the [**\<bindings>**](../../configure-apps/file-schema/wcf/bindings.md) element of the configuration file.</span></span> <span data-ttu-id="1800d-123">Nell'esempio seguente viene aggiunto un [**\<wsHttpBinding>**](../../configure-apps/file-schema/wcf/wshttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="1800d-123">The following example adds a [**\<wsHttpBinding>**](../../configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>

1. <span data-ttu-id="1800d-124">Aggiungere un **\<binding>** elemento e impostare il relativo `name` attributo su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="1800d-124">Add a **\<binding>** element and set its `name` attribute to an appropriate value.</span></span> <span data-ttu-id="1800d-125">Nell'esempio viene usato il nome `MessageSecurity` .</span><span class="sxs-lookup"><span data-stu-id="1800d-125">The example uses the name `MessageSecurity`.</span></span>

1. <span data-ttu-id="1800d-126">Aggiungere un **\<security>** elemento e impostare l' `mode` attributo su `Message` .</span><span class="sxs-lookup"><span data-stu-id="1800d-126">Add a **\<security>** element and set the `mode` attribute to `Message`.</span></span>

1. <span data-ttu-id="1800d-127">All'interno dell' **\<security>** elemento aggiungere un **\<message>** elemento e impostare l' `clientCredentialType` attributo su `Certificate` .</span><span class="sxs-lookup"><span data-stu-id="1800d-127">Within the **\<security>** element, add a **\<message>** element and set the `clientCredentialType` attribute to `Certificate`.</span></span>

```xml
<wsHttpBinding>
  <binding name="MessageSecurity">
    <security mode="Message">
      <message clientCredentialType="Certificate" />
    </security>
  </binding>
</wsHttpBinding>
```
