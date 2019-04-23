---
title: Aggiunta dello stato in linea e non in linea
ms.date: 03/30/2017
ms.assetid: 05e5f51d-81b6-4c17-b364-9dda447a5fce
ms.openlocfilehash: 15a963d4de0dcf1d7f0162b0a3266e17d4073ecd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59147693"
---
# <a name="adding-online-and-offline-status"></a><span data-ttu-id="26c92-102">Aggiunta dello stato in linea e non in linea</span><span class="sxs-lookup"><span data-stu-id="26c92-102">Adding Online and Offline Status</span></span>
<span data-ttu-id="26c92-103">In molti casi, per un'applicazione è importante monitorare dettagli specifici riguardanti lo stato di una connessione del canale peer.</span><span class="sxs-lookup"><span data-stu-id="26c92-103">In many cases, it is important for an application to monitor specific details about the status of a Peer Channel connection.</span></span> <span data-ttu-id="26c92-104">È possibile ottenere queste informazioni chiamando il metodo `GetProperty` su un'implementazione dell'interfaccia <xref:System.ServiceModel.IOnlineStatus>.</span><span class="sxs-lookup"><span data-stu-id="26c92-104">You can obtain this information by calling the `GetProperty` method on an implementation of the <xref:System.ServiceModel.IOnlineStatus> interface.</span></span> <span data-ttu-id="26c92-105">Un oggetto con un'implementazione di questa interfaccia può monitorare lo stato della connessione o registrarsi per gestori eventi, ad esempio `OnOnline` e `OnOffline`, e reagire immediatamente quando si verificano modifiche allo stato in linea.</span><span class="sxs-lookup"><span data-stu-id="26c92-105">An object with an implementation of this interface can monitor connection status or register for event handlers, such as `OnOnline` and `OnOffline`, and react immediately as changes to online status occur.</span></span>  
  
 <span data-ttu-id="26c92-106">Nell'infrastruttura del canale peer un client viene considerato in linea se è connesso ad almeno un altro peer, e non in linea in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="26c92-106">In the Peer Channel infrastructure, a client is considered to be online if it is connected to at least one other peer and offline otherwise.</span></span> <span data-ttu-id="26c92-107">Questo può essere particolarmente utile durante il debug di applicazioni in fase di sviluppo o la visualizzazione di informazioni dettagliate all'utente finale.</span><span class="sxs-lookup"><span data-stu-id="26c92-107">This can be particularly useful in both debugging a developing applications or displaying detailed information to the end user.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="26c92-108">Un gestore eventi in linea deve innanzitutto assicurarsi che il nodo sia aperto prima dell'invio di qualsiasi messaggio.</span><span class="sxs-lookup"><span data-stu-id="26c92-108">An online event handler should first ensure that the node is open before sending any messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26c92-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="26c92-109">See also</span></span>

- [<span data-ttu-id="26c92-110">Creazione di un'applicazione del canale peer</span><span class="sxs-lookup"><span data-stu-id="26c92-110">Building a Peer Channel Application</span></span>](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md)
