---
title: Conversione di un'applicazione NetTcpBinding in un'applicazione del canale peer
ms.date: 03/30/2017
ms.assetid: d4137292-a923-4b8f-8594-42276f2d3ce2
ms.openlocfilehash: 362945959a781fac360c42475148fee1e47a1183
ms.sourcegitcommit: ffd7dd79468a81bbb0d6449f6d65513e050c04c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2019
ms.locfileid: "65960130"
---
# <a name="converting-a-nettcpbinding-application-to-a-peer-channel-application"></a><span data-ttu-id="6618e-102">Conversione di un'applicazione NetTcpBinding in un'applicazione del canale peer</span><span class="sxs-lookup"><span data-stu-id="6618e-102">Converting a NetTcpBinding Application to a Peer Channel Application</span></span>
<span data-ttu-id="6618e-103">È possibile creare connessioni tra i client che usano il WinFX usando associazioni che descrivono i parametri della connessione.</span><span class="sxs-lookup"><span data-stu-id="6618e-103">You can create connections between clients using the WinFX by using bindings that describe the parameters of the connection.</span></span> <span data-ttu-id="6618e-104">Conversione di un'applicazione .NET Framework di usare connessioni peer-to-peer richiede un'associazione che supporta tale tecnologia quando si effettuano le connessioni client.</span><span class="sxs-lookup"><span data-stu-id="6618e-104">Converting a .NET Framework application to use peer-to-peer connections requires a binding that supports this technology when making client connections.</span></span> <span data-ttu-id="6618e-105">Il canale peer fornisce un'associazione denominata <xref:System.ServiceModel.NetPeerTcpBinding>utilizzabile in modo analogo a <xref:System.ServiceModel.NetTcpBinding>.</span><span class="sxs-lookup"><span data-stu-id="6618e-105">Peer Channel provides a binding called <xref:System.ServiceModel.NetPeerTcpBinding>, which you can use in a similar way to the <xref:System.ServiceModel.NetTcpBinding>.</span></span> <span data-ttu-id="6618e-106">Le differenze principali includono la specifica di un servizio resolver e la definizione di impostazioni di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="6618e-106">Key differences include specifying a resolver service and defining security settings.</span></span>  
  
 <span data-ttu-id="6618e-107">Se per un'applicazione si usano il resolver e le impostazioni di sicurezza predefinite, la conversione di un'applicazione client/server normale per l'uso del canale peer comporta la modifica del nome dell'associazione da "NetTcpBinding" a "NetPeerTcpBinding" nel file di configurazione dell'applicazione. Non è necessario modificare la codebase dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6618e-107">If an application is using the default resolver and security settings, converting a normal client/server-based application to use Peer Channel entails changing the name of the binding from "NetTcpBinding" to "NetPeerTcpBinding" in the application’s configuration file—you do not have to change the application code base.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6618e-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6618e-108">See also</span></span>

- [<span data-ttu-id="6618e-109">Creazione di un'applicazione del canale peer</span><span class="sxs-lookup"><span data-stu-id="6618e-109">Building a Peer Channel Application</span></span>](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md)
- [<span data-ttu-id="6618e-110">Associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="6618e-110">System-Provided Bindings</span></span>](../../../../docs/framework/wcf/system-provided-bindings.md)
