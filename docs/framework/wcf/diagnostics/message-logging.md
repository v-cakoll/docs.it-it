---
title: Registrazione messaggi
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6bce0682-75ef-4d65-a659-b328fba4a8b5
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 04e1b881d9aab1c35195794394cddf5172288cc1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="message-logging"></a><span data-ttu-id="2cf9a-102">Registrazione messaggi</span><span class="sxs-lookup"><span data-stu-id="2cf9a-102">Message Logging</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="2cf9a-103"> offre una funzionalità di registrazione dei messaggi in ingresso e in uscita per consentire di utilizzarli quando non si è in linea.</span><span class="sxs-lookup"><span data-stu-id="2cf9a-103"> provides the capability to log incoming and outgoing messages for offline consumption.</span></span> <span data-ttu-id="2cf9a-104">La registrazione dei messaggi consente di visualizzare l'aspetto dei messaggi e dei corpi dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="2cf9a-104">Message logging enables you to see what the message and message body looks like.</span></span> <span data-ttu-id="2cf9a-105">Questo tipo di registrazione è particolarmente utile per conoscere gli argomenti passati e il modo in cui l'endpoint di destinazione ha interpretato il formato XML di tali argomenti.</span><span class="sxs-lookup"><span data-stu-id="2cf9a-105">This type of logging is particularly helpful in letting you know what arguments were passed in and how the receiving endpoint saw the arguments expressed as XML.</span></span> <span data-ttu-id="2cf9a-106">Inoltre, la registrazione dei messaggi al momento della ricezione consente di individuare i motivi per cui il formato di un messaggio non è valido nonché il percorso di arrivo di un messaggio.</span><span class="sxs-lookup"><span data-stu-id="2cf9a-106">In addition, logging the message as it was received allows you to diagnose malformed messages as well as to see how the message arrived.</span></span> <span data-ttu-id="2cf9a-107">È inoltre possibile esaminare i token di sicurezza utilizzati, le parti che sono state crittografate e firmate nonché le parti inalterate.</span><span class="sxs-lookup"><span data-stu-id="2cf9a-107">You can also examine the security tokens used, parts encrypted and signed, and parts left intact.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2cf9a-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="2cf9a-108">In This Section</span></span>  
 [<span data-ttu-id="2cf9a-109">Panoramica del flusso messaggi</span><span class="sxs-lookup"><span data-stu-id="2cf9a-109">Message Flow Overview</span></span>](../../../../docs/framework/wcf/diagnostics/message-flow-overview.md)  
  
 <span data-ttu-id="2cf9a-110">In questo argomento viene descritto come i messaggi del registro eventi corrispondono agli eventi del servizio e del client.</span><span class="sxs-lookup"><span data-stu-id="2cf9a-110">This topic describes how event log messages correspond to client and service events.</span></span>  
  
 [<span data-ttu-id="2cf9a-111">Configurazione di registrazione dei messaggi</span><span class="sxs-lookup"><span data-stu-id="2cf9a-111">Configuring Message Logging</span></span>](../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md)  
  
 <span data-ttu-id="2cf9a-112">In questo argomento viene illustrato come configurare la registrazione dei messaggi per scenari differenti.</span><span class="sxs-lookup"><span data-stu-id="2cf9a-112">This topic describes how you can configure message logging for different scenarios.</span></span>  
  
 [<span data-ttu-id="2cf9a-113">Visualizzazione dei log di messaggio</span><span class="sxs-lookup"><span data-stu-id="2cf9a-113">Viewing Message Logs</span></span>](../../../../docs/framework/wcf/diagnostics/viewing-message-logs.md)  
  
 <span data-ttu-id="2cf9a-114">In questo argomento viene illustrato come visualizzare i log dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="2cf9a-114">This topic describes how you can view message logs.</span></span>  
  
 [<span data-ttu-id="2cf9a-115">Problemi di sicurezza per la registrazione dei messaggi</span><span class="sxs-lookup"><span data-stu-id="2cf9a-115">Security Concerns for Message Logging</span></span>](../../../../docs/framework/wcf/diagnostics/security-concerns-for-message-logging.md)  
  
 <span data-ttu-id="2cf9a-116">In questo argomento viene illustrato come evitare che i dati riservati vengano esposti nei log dei messaggi e come proteggere gli eventi generati dalla registrazione dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="2cf9a-116">This topic describes how you can protect sensitive data from being exposed in message logs, as well as events generated by message logging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cf9a-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2cf9a-117">See Also</span></span>  
 [<span data-ttu-id="2cf9a-118">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="2cf9a-118">Administration and Diagnostics</span></span>](../../../../docs/framework/wcf/diagnostics/index.md)
