---
title: System.ServiceModel.Channels.HttpsClientCertificateNotPresent
ms.date: 03/30/2017
ms.assetid: b13ef1b6-e340-401d-93ca-2710c3842205
ms.openlocfilehash: f58d4dd9e0d3be8813cb9b08394cb084a9f66f88
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54684097"
---
# <a name="systemservicemodelchannelshttpsclientcertificatenotpresent"></a><span data-ttu-id="6c211-102">System.ServiceModel.Channels.HttpsClientCertificateNotPresent</span><span class="sxs-lookup"><span data-stu-id="6c211-102">System.ServiceModel.Channels.HttpsClientCertificateNotPresent</span></span>
<span data-ttu-id="6c211-103">È necessario specificare il certificato client.</span><span class="sxs-lookup"><span data-stu-id="6c211-103">Client certificate is required.</span></span> <span data-ttu-id="6c211-104">Nessun certificato è disponibile nella richiesta.</span><span class="sxs-lookup"><span data-stu-id="6c211-104">No certificate was found in the request.</span></span>  
  
## <a name="description"></a><span data-ttu-id="6c211-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6c211-105">Description</span></span>  
 <span data-ttu-id="6c211-106">Questa traccia indica che il listener HTTPS ha ricevuto una richiesta HTTPS non associata al certificato client.</span><span class="sxs-lookup"><span data-stu-id="6c211-106">This trace indicates that the HTTPS listener received an HTTPS request that was not associated with a client certificate.</span></span> <span data-ttu-id="6c211-107">Poiché il listener è stato configurato per richiedere i certificati client per tutte le richieste HTTPS, l'autenticità del client non è stata convalidata dal listener.</span><span class="sxs-lookup"><span data-stu-id="6c211-107">Since the listener was configured to require client certificates on all HTTPS requests, the listener failed to validate the client’s authenticity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c211-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6c211-108">See also</span></span>
- [<span data-ttu-id="6c211-109">Traccia</span><span class="sxs-lookup"><span data-stu-id="6c211-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="6c211-110">Uso delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="6c211-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="6c211-111">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="6c211-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
