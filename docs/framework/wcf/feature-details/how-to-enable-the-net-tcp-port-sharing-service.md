---
title: 'Procedura: attivare il servizio di condivisione delle porte Net.TCP'
ms.date: 03/30/2017
helpviewer_keywords:
- port sharing [WCF]
- activation services [WCF]
ms.assetid: c9175af4-c27c-4765-bf45-b8f7528a7282
ms.openlocfilehash: 4b5a18e11d9fc15f23b5353883a63d838face58a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33490760"
---
# <a name="how-to-enable-the-nettcp-port-sharing-service"></a><span data-ttu-id="0ef56-102">Procedura: attivare il servizio di condivisione delle porte Net.TCP</span><span class="sxs-lookup"><span data-stu-id="0ef56-102">How to: Enable the Net.TCP Port Sharing Service</span></span>
<span data-ttu-id="0ef56-103">Windows Communication Foundation (WCF) usa un servizio Windows denominato il servizio di condivisione porte Net. TCP per facilitare la condivisione delle porte TCP tra più processi.</span><span class="sxs-lookup"><span data-stu-id="0ef56-103">Windows Communication Foundation (WCF) uses a Windows service called the Net.TCP Port Sharing Service to facilitate the sharing of TCP ports across multiple processes.</span></span> <span data-ttu-id="0ef56-104">Questo servizio viene installato come parte di WCF, ma il servizio non è abilitato per impostazione predefinita come misura di sicurezza e pertanto è necessario abilitare manualmente prima di primo utilizzo.</span><span class="sxs-lookup"><span data-stu-id="0ef56-104">This service is installed as part of WCF, but the service is not enabled by default as a security precaution and so must be manually enabled prior to first use.</span></span> <span data-ttu-id="0ef56-105">In questo argomento viene illustrato come configurare il servizio di condivisione delle porte Net TCP usando lo snap-in MMC (Microsoft Management Console).</span><span class="sxs-lookup"><span data-stu-id="0ef56-105">This topic describes how to configure the Net TCP Port Sharing Service using the Microsoft Management Console (MMC) snap-In.</span></span>  
  
 <span data-ttu-id="0ef56-106">Dopo aver abilitato il servizio di condivisione porta Net. TCP e avviarlo manualmente, vedere [procedura: configurare un servizio WCF di utilizzare la condivisione delle porte](../../../../docs/framework/wcf/feature-details/how-to-configure-a-wcf-service-to-use-port-sharing.md) per informazioni su come configurare il servizio per l'utilizzo di questo servizio.</span><span class="sxs-lookup"><span data-stu-id="0ef56-106">After you enable the Net.TCP Port Sharing Service and start it manually, see [How to: Configure a WCF Service to Use Port Sharing](../../../../docs/framework/wcf/feature-details/how-to-configure-a-wcf-service-to-use-port-sharing.md) for information about how to configure your service to use this service.</span></span>  
  
 <span data-ttu-id="0ef56-107">Per un esempio che utilizza la condivisione delle porte net.tcp://, vedere il [esempio di condivisione porta Net. TCP](../../../../docs/framework/wcf/samples/net-tcp-port-sharing-sample.md).</span><span class="sxs-lookup"><span data-stu-id="0ef56-107">For a sample that uses net.tcp:// port sharing, see the [Net.TCP Port Sharing Sample](../../../../docs/framework/wcf/samples/net-tcp-port-sharing-sample.md).</span></span>  
  
### <a name="to-enable-the-nettcp-port-sharing-service-using-mmc"></a><span data-ttu-id="0ef56-108">Per attivare il servizio di condivisione delle porte Net.TCP tramite MMC</span><span class="sxs-lookup"><span data-stu-id="0ef56-108">To enable the Net.TCP Port Sharing Service using MMC</span></span>  
  
1.  <span data-ttu-id="0ef56-109">Dal menu Start, aprire la Console di gestione dei servizi aprendo una finestra del prompt dei comandi e digitando `services.msc` o aprendo Esegui e digitando `services.msc` nella casella Apri.</span><span class="sxs-lookup"><span data-stu-id="0ef56-109">From the Start menu, open the Services Management Console either by opening a Command Prompt window and typing `services.msc` or by opening Run and typing `services.msc` into the Open box.</span></span>  
  
2.  <span data-ttu-id="0ef56-110">Nel **nome** colonna dell'elenco di servizi, fare doppio clic su di **servizio di condivisione porte Net. TCP**e selezionare **proprietà** dal menu.</span><span class="sxs-lookup"><span data-stu-id="0ef56-110">In the **Name** column of the list of services, right-click the **Net.Tcp Port Sharing Service**, and select **Properties** from the menu.</span></span>  
  
3.  <span data-ttu-id="0ef56-111">Per abilitare l'avvio manuale del servizio, nel **proprietà** finestra selezionare il **generale** scheda e il **tipo di avvio** casella selezionare manuale e quindi fare clic su **Applicare**.</span><span class="sxs-lookup"><span data-stu-id="0ef56-111">To enable the manual start-up of the service, in the **Properties** window select the **General** tab, and in the **Startup type** box select Manual, and then click **Apply**.</span></span>  
  
4.  <span data-ttu-id="0ef56-112">Per avviare il servizio, nell'area di stato del servizio, fare clic su di **avviare** pulsante.</span><span class="sxs-lookup"><span data-stu-id="0ef56-112">To start the service,  in the Service status area, click the **Start** button.</span></span> <span data-ttu-id="0ef56-113">Lo stato del servizio dovrebbe ora essere "Avviato".</span><span class="sxs-lookup"><span data-stu-id="0ef56-113">The service status should now display "Started".</span></span>  
  
5.  <span data-ttu-id="0ef56-114">Per tornare all'elenco dei servizi, fare clic su di **OK**e uscire dalla Console di MMC.</span><span class="sxs-lookup"><span data-stu-id="0ef56-114">To return to the list of services, click the **OK**, and exit the MMC Console.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ef56-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="0ef56-115">Example</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ef56-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ef56-116">See Also</span></span>  
 [<span data-ttu-id="0ef56-117">Condivisione delle porte Net.TCP</span><span class="sxs-lookup"><span data-stu-id="0ef56-117">Net.TCP Port Sharing</span></span>](../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)  
 [<span data-ttu-id="0ef56-118">Configurazione del servizio di condivisione delle porte Net.TCP</span><span class="sxs-lookup"><span data-stu-id="0ef56-118">Configuring the Net.TCP Port Sharing Service</span></span>](../../../../docs/framework/wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)
