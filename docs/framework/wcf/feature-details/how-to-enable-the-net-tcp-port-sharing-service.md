---
title: 'Procedura: attivare il servizio di condivisione delle porte Net.TCP'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- port sharing [WCF]
- activation services [WCF]
ms.assetid: c9175af4-c27c-4765-bf45-b8f7528a7282
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e9934d198b8f3e30a4dc350c968263851ebeab1e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enable-the-nettcp-port-sharing-service"></a><span data-ttu-id="6c42b-102">Procedura: attivare il servizio di condivisione delle porte Net.TCP</span><span class="sxs-lookup"><span data-stu-id="6c42b-102">How to: Enable the Net.TCP Port Sharing Service</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="6c42b-103"> usa un servizio di Windows denominato Servizio di condivisione porte Net.TCP per facilitare la condivisione delle porte TCP tra più processi.</span><span class="sxs-lookup"><span data-stu-id="6c42b-103"> uses a Windows service called the Net.TCP Port Sharing Service to facilitate the sharing of TCP ports across multiple processes.</span></span> <span data-ttu-id="6c42b-104">Il servizio viene installato come parte di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], ma, per motivi di sicurezza, non viene attivato per impostazione predefinita e deve quindi essere attivato manualmente al primo utilizzo.</span><span class="sxs-lookup"><span data-stu-id="6c42b-104">This service is installed as part of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], but the service is not enabled by default as a security precaution and so must be manually enabled prior to first use.</span></span> <span data-ttu-id="6c42b-105">In questo argomento viene illustrato come configurare il servizio di condivisione delle porte Net TCP usando lo snap-in MMC (Microsoft Management Console).</span><span class="sxs-lookup"><span data-stu-id="6c42b-105">This topic describes how to configure the Net TCP Port Sharing Service using the Microsoft Management Console (MMC) snap-In.</span></span>  
  
 <span data-ttu-id="6c42b-106">Dopo aver abilitato il servizio di condivisione porta Net. TCP e avviarlo manualmente, vedere [procedura: configurare un servizio WCF di utilizzare la condivisione delle porte](../../../../docs/framework/wcf/feature-details/how-to-configure-a-wcf-service-to-use-port-sharing.md) per informazioni su come configurare il servizio per l'utilizzo di questo servizio.</span><span class="sxs-lookup"><span data-stu-id="6c42b-106">After you enable the Net.TCP Port Sharing Service and start it manually, see [How to: Configure a WCF Service to Use Port Sharing](../../../../docs/framework/wcf/feature-details/how-to-configure-a-wcf-service-to-use-port-sharing.md) for information about how to configure your service to use this service.</span></span>  
  
 <span data-ttu-id="6c42b-107">Per un esempio che utilizza la condivisione delle porte net.tcp://, vedere il [esempio di condivisione porta Net. TCP](../../../../docs/framework/wcf/samples/net-tcp-port-sharing-sample.md).</span><span class="sxs-lookup"><span data-stu-id="6c42b-107">For a sample that uses net.tcp:// port sharing, see the [Net.TCP Port Sharing Sample](../../../../docs/framework/wcf/samples/net-tcp-port-sharing-sample.md).</span></span>  
  
### <a name="to-enable-the-nettcp-port-sharing-service-using-mmc"></a><span data-ttu-id="6c42b-108">Per attivare il servizio di condivisione delle porte Net.TCP tramite MMC</span><span class="sxs-lookup"><span data-stu-id="6c42b-108">To enable the Net.TCP Port Sharing Service using MMC</span></span>  
  
1.  <span data-ttu-id="6c42b-109">Dal menu Start, aprire la Console di gestione dei servizi aprendo una finestra del prompt dei comandi e digitando `services.msc` o aprendo Esegui e digitando `services.msc` nella casella Apri.</span><span class="sxs-lookup"><span data-stu-id="6c42b-109">From the Start menu, open the Services Management Console either by opening a Command Prompt window and typing `services.msc` or by opening Run and typing `services.msc` into the Open box.</span></span>  
  
2.  <span data-ttu-id="6c42b-110">Nel **nome** colonna dell'elenco di servizi, fare doppio clic su di **servizio di condivisione porte Net. TCP**e selezionare **proprietà** dal menu.</span><span class="sxs-lookup"><span data-stu-id="6c42b-110">In the **Name** column of the list of services, right-click the **Net.Tcp Port Sharing Service**, and select **Properties** from the menu.</span></span>  
  
3.  <span data-ttu-id="6c42b-111">Per abilitare l'avvio manuale del servizio, nel **proprietà** finestra selezionare il **generale** scheda e il **tipo di avvio** casella selezionare manuale e quindi fare clic su **Applicare**.</span><span class="sxs-lookup"><span data-stu-id="6c42b-111">To enable the manual start-up of the service, in the **Properties** window select the **General** tab, and in the **Startup type** box select Manual, and then click **Apply**.</span></span>  
  
4.  <span data-ttu-id="6c42b-112">Per avviare il servizio, nell'area di stato del servizio, fare clic su di **avviare** pulsante.</span><span class="sxs-lookup"><span data-stu-id="6c42b-112">To start the service,  in the Service status area, click the **Start** button.</span></span> <span data-ttu-id="6c42b-113">Lo stato del servizio dovrebbe ora essere "Avviato".</span><span class="sxs-lookup"><span data-stu-id="6c42b-113">The service status should now display "Started".</span></span>  
  
5.  <span data-ttu-id="6c42b-114">Per tornare all'elenco dei servizi, fare clic su di **OK**e uscire dalla Console di MMC.</span><span class="sxs-lookup"><span data-stu-id="6c42b-114">To return to the list of services, click the **OK**, and exit the MMC Console.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c42b-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="6c42b-115">Example</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c42b-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6c42b-116">See Also</span></span>  
 [<span data-ttu-id="6c42b-117">Condivisione porta Net. TCP</span><span class="sxs-lookup"><span data-stu-id="6c42b-117">Net.TCP Port Sharing</span></span>](../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)  
 [<span data-ttu-id="6c42b-118">Configurare il servizio di condivisione delle porte Net.TCP</span><span class="sxs-lookup"><span data-stu-id="6c42b-118">Configuring the Net.TCP Port Sharing Service</span></span>](../../../../docs/framework/wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)
