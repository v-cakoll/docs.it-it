---
title: Uso di WS-AtomicTransaction
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WS-AT protocol [WCF]
ms.assetid: 04a4c200-0af0-4c5d-a3d9-87cb7339e054
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 124c5dc0f6db94ae459fe140bd7a4290aa56e04a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="using-ws-atomictransaction"></a><span data-ttu-id="59826-102">Uso di WS-AtomicTransaction</span><span class="sxs-lookup"><span data-stu-id="59826-102">Using WS-AtomicTransaction</span></span>
<span data-ttu-id="59826-103">WS-AtomicTransaction (WS-AT) è un protocollo di transazione interoperativo.</span><span class="sxs-lookup"><span data-stu-id="59826-103">WS-AtomicTransaction (WS-AT) is an interoperable transaction protocol.</span></span> <span data-ttu-id="59826-104">Consente di propagare transazioni distribuite utilizzando i messaggi dei servizi Web e di eseguire il coordinamento in modo interoperativo tra infrastrutture di transazioni eterogenee.</span><span class="sxs-lookup"><span data-stu-id="59826-104">It enables you to flow distributed transactions by using Web service messages, and coordinate in an interoperable manner between heterogeneous transaction infrastructures.</span></span> <span data-ttu-id="59826-105">WS-AT utilizza il protocollo di commit a due fasi per condurre un risultato atomico tra applicazioni distribuite, gestori di transazioni e gestori di risorse.</span><span class="sxs-lookup"><span data-stu-id="59826-105">WS-AT uses the two-phase commit protocol to drive an atomic outcome between distributed applications, transaction managers, and resource managers.</span></span>  
  
 <span data-ttu-id="59826-106">L'implementazione di WS-AT fornita da [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] comprende un servizio di protocollo incorporato nel gestore di transazioni MSDTC (Microsoft Distributed Transaction Coordinator).</span><span class="sxs-lookup"><span data-stu-id="59826-106">The WS-AT implementation [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] provides includes a protocol service built into the Microsoft Distributed Transaction Coordinator (MSDTC) transaction manager.</span></span> <span data-ttu-id="59826-107">Utilizzando WS-AT, le applicazioni [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] possono propagare le transazioni ad altre applicazioni, compresi servizi Web interoperativi creati mediante tecnologie di terze parti.</span><span class="sxs-lookup"><span data-stu-id="59826-107">Using WS-AT, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications can flow transactions to other applications, including interoperable Web services built using third-party technology.</span></span>  
  
 <span data-ttu-id="59826-108">Durante la propagazione di una transazione tra un'applicazione client e un'applicazione server, il protocollo di transazione utilizzato viene determinato dall'associazione esposta dal server sull'endpoint selezionato dal client.</span><span class="sxs-lookup"><span data-stu-id="59826-108">When flowing a transaction between a client application and a server application, the transaction protocol used is determined by the binding that the server exposes on the endpoint the client selected.</span></span> <span data-ttu-id="59826-109">Alcune associazioni fornite dal sistema [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] specificano per impostazione predefinita il protocollo `OleTransactions` come formato di propagazione delle transazioni, mentre altre specificano il protocollo WS-AT.</span><span class="sxs-lookup"><span data-stu-id="59826-109">Some [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] system-provided bindings default to specifying the `OleTransactions` protocol as the transaction propagation format, while others default to specifying WS-AT.</span></span> <span data-ttu-id="59826-110">La scelta del protocollo di transazione può anche essere modificata a livello di codice all'interno di una determinata associazione.</span><span class="sxs-lookup"><span data-stu-id="59826-110">You can also programmatically modify the choice of transaction protocol inside a given binding.</span></span>  
  
 <span data-ttu-id="59826-111">La scelta del protocollo influisce sugli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="59826-111">The choice of protocol influences:</span></span>  
  
-   <span data-ttu-id="59826-112">Formato delle intestazioni dei messaggi utilizzate propagare la transazione dal client al server.</span><span class="sxs-lookup"><span data-stu-id="59826-112">The format of the message headers used to flow the transaction from client to server.</span></span>  
  
-   <span data-ttu-id="59826-113">Protocollo di rete utilizzato per eseguire il protocollo di commit a due fasi tra il gestore di transazioni del client e la transazione del server, al fine di risolvere il risultato della transazione.</span><span class="sxs-lookup"><span data-stu-id="59826-113">The network protocol used to run the two-phase commit protocol between the client's transaction manager and the server's transaction, in order to resolve the outcome of the transaction.</span></span>  
  
 <span data-ttu-id="59826-114">Se il server e il client vengono scritti utilizzando [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], non è necessario utilizzare WS-AT.</span><span class="sxs-lookup"><span data-stu-id="59826-114">If the server and client are written using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], you do not need to use WS-AT.</span></span> <span data-ttu-id="59826-115">È possibile invece utilizzare le impostazioni predefinite di `NetTcpBinding` con l'attributo `TransactionFlow` abilitato, in modo da utilizzare il protocollo `OleTransactions`.</span><span class="sxs-lookup"><span data-stu-id="59826-115">Instead, you can use the default settings of `NetTcpBinding` with the `TransactionFlow` attribute enabled, which will use the `OleTransactions` protocol instead.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="59826-116">[ \<netTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="59826-116"> [\<netTcpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span></span> <span data-ttu-id="59826-117">In caso contrario, se le transazioni vengono propagate a servizi Web basati su tecnologie di terze parti, sarà necessario utilizzare WS-AT.</span><span class="sxs-lookup"><span data-stu-id="59826-117">Otherwise, if you are flowing transactions to Web services built on third-party technologies, you must use WS-AT.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59826-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="59826-118">See Also</span></span>  
 [<span data-ttu-id="59826-119">Configurazione del supporto di transazioni WS-Atomic</span><span class="sxs-lookup"><span data-stu-id="59826-119">Configuring WS-Atomic Transaction Support</span></span>](../../../../docs/framework/wcf/feature-details/configuring-ws-atomic-transaction-support.md)
