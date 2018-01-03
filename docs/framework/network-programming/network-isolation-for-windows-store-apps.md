---
title: Isolamento rete per app di Windows Store
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b064497c-d956-46b8-838d-7a0223c7e200
caps.latest.revision: "7"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: ba7e480f50d3a339648229f17152eb28b28ec159
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="network-isolation-for-windows-store-apps"></a><span data-ttu-id="4b7e1-102">Isolamento rete per app di Windows Store</span><span class="sxs-lookup"><span data-stu-id="4b7e1-102">Network Isolation for Windows Store Apps</span></span>
<span data-ttu-id="4b7e1-103">Le classi negli spazi dei nomi <xref:System.Net>, <xref:System.Net.Http> e <xref:System.Net.Http.Headers> possono essere usate per sviluppare app di Windows Store o app desktop.</span><span class="sxs-lookup"><span data-stu-id="4b7e1-103">Classes in the <xref:System.Net>,  <xref:System.Net.Http>, and <xref:System.Net.Http.Headers> namespaces can be used to develop Windows Store  apps  or desktop apps.</span></span> <span data-ttu-id="4b7e1-104">Quando vengono usate in un'app di Windows Store, le classi in questi spazi dei nomi sono interessate dall'isolamento rete, parte del modello di sicurezza delle applicazioni usato da [!INCLUDE[win8](../../../includes/win8-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4b7e1-104">When used in a Windows Store app, classes in these namespaces are affected by network isolation, part of the application security model used by the [!INCLUDE[win8](../../../includes/win8-md.md)].</span></span> <span data-ttu-id="4b7e1-105">Le funzionalità di rete appropriate devono essere abilitate nel manifesto dell'app per un'app di Windows Store affinché il sistema consenta l'accesso alla rete.</span><span class="sxs-lookup"><span data-stu-id="4b7e1-105">The appropriate network capabilities must be enabled in the app manifest for a Windows Store app for the system to allow network access.</span></span>  
  
## <a name="checklist-for-network-isolation"></a><span data-ttu-id="4b7e1-106">Elenco di controllo per l'isolamento rete</span><span class="sxs-lookup"><span data-stu-id="4b7e1-106">Checklist for Network Isolation</span></span>  
 <span data-ttu-id="4b7e1-107">Usare questo elenco di controllo per assicurarsi che l'isolamento rete sia configurato per l'app di Windows Store.</span><span class="sxs-lookup"><span data-stu-id="4b7e1-107">Use this checklist to be sure that network isolation is configured for your Windows Store app.</span></span>  
  
1.  <span data-ttu-id="4b7e1-108">Determinare la direzione delle richieste di accesso alla rete necessaria per l'app.</span><span class="sxs-lookup"><span data-stu-id="4b7e1-108">Determine the direction of network access requests needed by the app.</span></span> <span data-ttu-id="4b7e1-109">Può trattarsi di richieste in uscita avviate dal client o di richieste in ingresso non sollecitate oppure di una combinazione di entrambi i tipi di richiesta di rete.</span><span class="sxs-lookup"><span data-stu-id="4b7e1-109">This can be either outbound client-initiated requests or inbound unsolicited requests or it could be a combination of both of these network request types.</span></span>  
  
2.  <span data-ttu-id="4b7e1-110">Determinare il tipo di risorse di rete con cui comunicherà l'app.</span><span class="sxs-lookup"><span data-stu-id="4b7e1-110">Determine the type of network resources that that app will communicate with.</span></span> <span data-ttu-id="4b7e1-111">Un'app potrebbe avere l'esigenza di comunicare con risorse attendibili in una rete domestica o aziendale.</span><span class="sxs-lookup"><span data-stu-id="4b7e1-111">An app may need to communicate with trusted resources on a Home or Work network.</span></span> <span data-ttu-id="4b7e1-112">Per un'app potrebbe essere necessario comunicare con risorse su Internet.</span><span class="sxs-lookup"><span data-stu-id="4b7e1-112">An app might need to communicate with resources on the Internet.</span></span> <span data-ttu-id="4b7e1-113">Un'app potrebbe dover disporre dell'accesso a entrambi i tipi di risorse di rete.</span><span class="sxs-lookup"><span data-stu-id="4b7e1-113">An app might need access to both types of network resources.</span></span>  
  
3.  <span data-ttu-id="4b7e1-114">Configurare le funzionalità di isolamento rete minime richieste nel manifesto dell'app.</span><span class="sxs-lookup"><span data-stu-id="4b7e1-114">Configure the minimum-required networking isolation capabilities in the app manifest.</span></span>  
  
4.  <span data-ttu-id="4b7e1-115">Distribuire ed eseguire l'app per testarla usando gli strumenti di isolamento rete forniti per la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="4b7e1-115">Deploy and run your app to test it using the network isolation tools provided for troubleshooting.</span></span>  
  
 <span data-ttu-id="4b7e1-116">Per informazioni più dettagliate su come configurare le funzionalità di rete e gli strumenti di isolamento usati per la risoluzione dei problemi dell'isolamento rete, vedere [Come impostare le funzionalità di rete](http://go.microsoft.com/fwlink/?LinkID=228265) nella documentazione per gli sviluppatori di [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4b7e1-116">For more detailed information on how to configure network capabilities and isolation tools used for troubleshooting network isolation, see [How to configure network isolation capabilities](http://go.microsoft.com/fwlink/?LinkID=228265) in the [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] developer documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b7e1-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4b7e1-117">See Also</span></span>  
 [<span data-ttu-id="4b7e1-118">Connessione a un servizio web</span><span class="sxs-lookup"><span data-stu-id="4b7e1-118">Connecting to a web service</span></span>](http://go.microsoft.com/fwlink/?LinkID=245696)  
 [<span data-ttu-id="4b7e1-119">Linee guida e l'elenco di controllo per l'isolamento rete</span><span class="sxs-lookup"><span data-stu-id="4b7e1-119">Guidelines and checklist for network isolation</span></span>](http://go.microsoft.com/fwlink/?LinkID=228265)  
 [<span data-ttu-id="4b7e1-120">Guida introduttiva: Connessione tramite HttpClient</span><span class="sxs-lookup"><span data-stu-id="4b7e1-120">Quickstart: Connecting using HttpClient</span></span>](http://go.microsoft.com/fwlink/?LinkId=245697)  
 [<span data-ttu-id="4b7e1-121">Come utilizzare i gestori di HttpClient</span><span class="sxs-lookup"><span data-stu-id="4b7e1-121">How to use HttpClient handlers</span></span>](http://go.microsoft.com/fwlink/?LinkId=245699)  
 [<span data-ttu-id="4b7e1-122">Come proteggere le connessioni di HttpClient</span><span class="sxs-lookup"><span data-stu-id="4b7e1-122">How to secure HttpClient connections</span></span>](http://go.microsoft.com/fwlink/?LinkId=245698)  
 <span data-ttu-id="4b7e1-123">[HttpClient Sample](http://go.microsoft.com/fwlink/?LinkId=242550) (Esempio con HttpClient)</span><span class="sxs-lookup"><span data-stu-id="4b7e1-123">[HttpClient Sample](http://go.microsoft.com/fwlink/?LinkId=242550)</span></span>
