---
title: Aggiunta dello stato in linea e non in linea
ms.date: 03/30/2017
ms.assetid: 05e5f51d-81b6-4c17-b364-9dda447a5fce
ms.openlocfilehash: da170bbc22d04dcbf5f7cd4ac084a004bb4b026e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597683"
---
# <a name="adding-online-and-offline-status"></a><span data-ttu-id="e7c47-102">Aggiunta dello stato in linea e non in linea</span><span class="sxs-lookup"><span data-stu-id="e7c47-102">Adding Online and Offline Status</span></span>
<span data-ttu-id="e7c47-103">In molti casi, per un'applicazione è importante monitorare dettagli specifici riguardanti lo stato di una connessione del canale peer.</span><span class="sxs-lookup"><span data-stu-id="e7c47-103">In many cases, it is important for an application to monitor specific details about the status of a Peer Channel connection.</span></span> <span data-ttu-id="e7c47-104">È possibile ottenere queste informazioni chiamando il metodo `GetProperty` su un'implementazione dell'interfaccia <xref:System.ServiceModel.IOnlineStatus>.</span><span class="sxs-lookup"><span data-stu-id="e7c47-104">You can obtain this information by calling the `GetProperty` method on an implementation of the <xref:System.ServiceModel.IOnlineStatus> interface.</span></span> <span data-ttu-id="e7c47-105">Un oggetto con un'implementazione di questa interfaccia può monitorare lo stato della connessione o registrarsi per gestori eventi, ad esempio `OnOnline` e `OnOffline`, e reagire immediatamente quando si verificano modifiche allo stato in linea.</span><span class="sxs-lookup"><span data-stu-id="e7c47-105">An object with an implementation of this interface can monitor connection status or register for event handlers, such as `OnOnline` and `OnOffline`, and react immediately as changes to online status occur.</span></span>  
  
 <span data-ttu-id="e7c47-106">Nell'infrastruttura del canale peer un client viene considerato in linea se è connesso ad almeno un altro peer, e non in linea in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="e7c47-106">In the Peer Channel infrastructure, a client is considered to be online if it is connected to at least one other peer and offline otherwise.</span></span> <span data-ttu-id="e7c47-107">Questo può essere particolarmente utile durante il debug di applicazioni in fase di sviluppo o la visualizzazione di informazioni dettagliate all'utente finale.</span><span class="sxs-lookup"><span data-stu-id="e7c47-107">This can be particularly useful in both debugging a developing applications or displaying detailed information to the end user.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e7c47-108">Un gestore eventi in linea deve innanzitutto assicurarsi che il nodo sia aperto prima dell'invio di qualsiasi messaggio.</span><span class="sxs-lookup"><span data-stu-id="e7c47-108">An online event handler should first ensure that the node is open before sending any messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7c47-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7c47-109">See also</span></span>

- [<span data-ttu-id="e7c47-110">Creazione di un'applicazione del canale peer</span><span class="sxs-lookup"><span data-stu-id="e7c47-110">Building a Peer Channel Application</span></span>](building-a-peer-channel-application.md)
