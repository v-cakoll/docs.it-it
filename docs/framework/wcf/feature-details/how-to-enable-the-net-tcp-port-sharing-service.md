---
title: 'Procedura: Abilitare il servizio di condivisione delle porte Net. TCP'
ms.date: 03/30/2017
helpviewer_keywords:
- port sharing [WCF]
- activation services [WCF]
ms.assetid: c9175af4-c27c-4765-bf45-b8f7528a7282
ms.openlocfilehash: 490c0d8c4c95eeb2b1cd9b43134720c9e44467ac
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54619597"
---
# <a name="how-to-enable-the-nettcp-port-sharing-service"></a><span data-ttu-id="f71b8-102">Procedura: Abilitare il servizio di condivisione delle porte Net. TCP</span><span class="sxs-lookup"><span data-stu-id="f71b8-102">How to: Enable the Net.TCP Port Sharing Service</span></span>
<span data-ttu-id="f71b8-103">Windows Communication Foundation (WCF) usano un servizio Windows denominato il servizio di condivisione porte Net. TCP per semplificare la condivisione delle porte TCP tra più processi.</span><span class="sxs-lookup"><span data-stu-id="f71b8-103">Windows Communication Foundation (WCF) uses a Windows service called the Net.TCP Port Sharing Service to facilitate the sharing of TCP ports across multiple processes.</span></span> <span data-ttu-id="f71b8-104">Questo servizio viene installato come parte di WCF, ma il servizio non è abilitato per impostazione predefinita come misura di sicurezza e pertanto è necessario abilitare manualmente prima del primo utilizzo.</span><span class="sxs-lookup"><span data-stu-id="f71b8-104">This service is installed as part of WCF, but the service is not enabled by default as a security precaution and so must be manually enabled prior to first use.</span></span> <span data-ttu-id="f71b8-105">In questo argomento viene illustrato come configurare il servizio di condivisione delle porte Net TCP usando lo snap-in MMC (Microsoft Management Console).</span><span class="sxs-lookup"><span data-stu-id="f71b8-105">This topic describes how to configure the Net TCP Port Sharing Service using the Microsoft Management Console (MMC) snap-In.</span></span>  
  
 <span data-ttu-id="f71b8-106">Dopo aver abilitato il servizio di condivisione porte Net. TCP e avviarlo manualmente, vedere [come: Configurare un servizio WCF di utilizzare la condivisione delle porte](../../../../docs/framework/wcf/feature-details/how-to-configure-a-wcf-service-to-use-port-sharing.md) per informazioni su come configurare il servizio per usare questo servizio.</span><span class="sxs-lookup"><span data-stu-id="f71b8-106">After you enable the Net.TCP Port Sharing Service and start it manually, see [How to: Configure a WCF Service to Use Port Sharing](../../../../docs/framework/wcf/feature-details/how-to-configure-a-wcf-service-to-use-port-sharing.md) for information about how to configure your service to use this service.</span></span>  
  
 <span data-ttu-id="f71b8-107">Per un esempio che usa net.tcp:// condivisione delle porte, vedere la [esempio di condivisione porta Net. TCP](../../../../docs/framework/wcf/samples/net-tcp-port-sharing-sample.md).</span><span class="sxs-lookup"><span data-stu-id="f71b8-107">For a sample that uses net.tcp:// port sharing, see the [Net.TCP Port Sharing Sample](../../../../docs/framework/wcf/samples/net-tcp-port-sharing-sample.md).</span></span>  
  
### <a name="to-enable-the-nettcp-port-sharing-service-using-mmc"></a><span data-ttu-id="f71b8-108">Per attivare il servizio di condivisione delle porte Net.TCP tramite MMC</span><span class="sxs-lookup"><span data-stu-id="f71b8-108">To enable the Net.TCP Port Sharing Service using MMC</span></span>  
  
1.  <span data-ttu-id="f71b8-109">Dal menu Start, aprire la Console di Gestione servizi aprendo una finestra del prompt dei comandi e digitando `services.msc` o aprendo Esegui e digitando `services.msc` nella casella Apri.</span><span class="sxs-lookup"><span data-stu-id="f71b8-109">From the Start menu, open the Services Management Console either by opening a Command Prompt window and typing `services.msc` or by opening Run and typing `services.msc` into the Open box.</span></span>  
  
2.  <span data-ttu-id="f71b8-110">Nel **Name** colonna dell'elenco dei servizi, fare doppio clic sui **servizio di condivisione porte Net. TCP**e selezionare **proprietà** dal menu di scelta.</span><span class="sxs-lookup"><span data-stu-id="f71b8-110">In the **Name** column of the list of services, right-click the **Net.Tcp Port Sharing Service**, and select **Properties** from the menu.</span></span>  
  
3.  <span data-ttu-id="f71b8-111">Per abilitare l'avvio manuale del servizio, nel **proprietà** finestra selezionare il **generali** della scheda e nella **tipo di avvio** finestra selezionare manuale e quindi fare clic su **Applicare**.</span><span class="sxs-lookup"><span data-stu-id="f71b8-111">To enable the manual start-up of the service, in the **Properties** window select the **General** tab, and in the **Startup type** box select Manual, and then click **Apply**.</span></span>  
  
4.  <span data-ttu-id="f71b8-112">Per avviare il servizio, nell'area dello stato del servizio, scegliere il **avviare** pulsante.</span><span class="sxs-lookup"><span data-stu-id="f71b8-112">To start the service,  in the Service status area, click the **Start** button.</span></span> <span data-ttu-id="f71b8-113">Lo stato del servizio dovrebbe ora essere "Avviato".</span><span class="sxs-lookup"><span data-stu-id="f71b8-113">The service status should now display "Started".</span></span>  
  
5.  <span data-ttu-id="f71b8-114">Per tornare all'elenco dei servizi, scegliere il **OK**e chiudere la Console MMC.</span><span class="sxs-lookup"><span data-stu-id="f71b8-114">To return to the list of services, click the **OK**, and exit the MMC Console.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f71b8-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="f71b8-115">Example</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f71b8-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f71b8-116">See also</span></span>
- [<span data-ttu-id="f71b8-117">Condivisione delle porte Net.TCP</span><span class="sxs-lookup"><span data-stu-id="f71b8-117">Net.TCP Port Sharing</span></span>](../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)
- [<span data-ttu-id="f71b8-118">Configurazione del servizio di condivisione delle porte Net.TCP</span><span class="sxs-lookup"><span data-stu-id="f71b8-118">Configuring the Net.TCP Port Sharing Service</span></span>](../../../../docs/framework/wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)
