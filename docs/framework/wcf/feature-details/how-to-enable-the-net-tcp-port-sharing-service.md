---
title: 'Procedura: attivare il servizio di condivisione delle porte Net.TCP'
ms.date: 03/30/2017
helpviewer_keywords:
- port sharing [WCF]
- activation services [WCF]
ms.assetid: c9175af4-c27c-4765-bf45-b8f7528a7282
ms.openlocfilehash: 8b305b98d620636328866bce848411f395053485
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84593133"
---
# <a name="how-to-enable-the-nettcp-port-sharing-service"></a><span data-ttu-id="65b3e-102">Procedura: attivare il servizio di condivisione delle porte Net.TCP</span><span class="sxs-lookup"><span data-stu-id="65b3e-102">How to: Enable the Net.TCP Port Sharing Service</span></span>
<span data-ttu-id="65b3e-103">Windows Communication Foundation (WCF) utilizza un servizio Windows denominato servizio di condivisione porte net. TCP per facilitare la condivisione delle porte TCP tra più processi.</span><span class="sxs-lookup"><span data-stu-id="65b3e-103">Windows Communication Foundation (WCF) uses a Windows service called the Net.TCP Port Sharing Service to facilitate the sharing of TCP ports across multiple processes.</span></span> <span data-ttu-id="65b3e-104">Questo servizio viene installato come parte di WCF, ma il servizio non è abilitato per impostazione predefinita come misura di sicurezza e pertanto deve essere abilitato manualmente prima del primo utilizzo.</span><span class="sxs-lookup"><span data-stu-id="65b3e-104">This service is installed as part of WCF, but the service is not enabled by default as a security precaution and so must be manually enabled prior to first use.</span></span> <span data-ttu-id="65b3e-105">In questo argomento viene illustrato come configurare il servizio di condivisione delle porte Net TCP usando lo snap-in MMC (Microsoft Management Console).</span><span class="sxs-lookup"><span data-stu-id="65b3e-105">This topic describes how to configure the Net TCP Port Sharing Service using the Microsoft Management Console (MMC) snap-In.</span></span>  
  
 <span data-ttu-id="65b3e-106">Dopo aver abilitato il servizio di condivisione porte net. TCP e averlo avviato manualmente, vedere [procedura: configurare un servizio WCF per l'uso della condivisione delle porte](how-to-configure-a-wcf-service-to-use-port-sharing.md) per informazioni su come configurare il servizio per l'uso di questo servizio.</span><span class="sxs-lookup"><span data-stu-id="65b3e-106">After you enable the Net.TCP Port Sharing Service and start it manually, see [How to: Configure a WCF Service to Use Port Sharing](how-to-configure-a-wcf-service-to-use-port-sharing.md) for information about how to configure your service to use this service.</span></span>  
  
 <span data-ttu-id="65b3e-107">Per un esempio che usa la condivisione delle porte net. TCP://, vedere l' [esempio di condivisione delle porte net. TCP](../samples/net-tcp-port-sharing-sample.md).</span><span class="sxs-lookup"><span data-stu-id="65b3e-107">For a sample that uses net.tcp:// port sharing, see the [Net.TCP Port Sharing Sample](../samples/net-tcp-port-sharing-sample.md).</span></span>  
  
### <a name="to-enable-the-nettcp-port-sharing-service-using-mmc"></a><span data-ttu-id="65b3e-108">Per attivare il servizio di condivisione delle porte Net.TCP tramite MMC</span><span class="sxs-lookup"><span data-stu-id="65b3e-108">To enable the Net.TCP Port Sharing Service using MMC</span></span>  
  
1. <span data-ttu-id="65b3e-109">Dal menu Start aprire la console di gestione dei servizi aprendo una finestra del prompt dei comandi e digitando `services.msc` o aprendo Esegui e digitando `services.msc` nella casella Apri.</span><span class="sxs-lookup"><span data-stu-id="65b3e-109">From the Start menu, open the Services Management Console either by opening a Command Prompt window and typing `services.msc` or by opening Run and typing `services.msc` into the Open box.</span></span>  
  
2. <span data-ttu-id="65b3e-110">Nella colonna **nome** dell'elenco dei servizi fare clic con il pulsante destro del mouse sul **servizio di condivisione porte net. TCP**e scegliere **proprietà** dal menu.</span><span class="sxs-lookup"><span data-stu-id="65b3e-110">In the **Name** column of the list of services, right-click the **Net.Tcp Port Sharing Service**, and select **Properties** from the menu.</span></span>  
  
3. <span data-ttu-id="65b3e-111">Per abilitare l'avvio manuale del servizio, nella finestra **Proprietà** selezionare la scheda **generale** e nella casella **tipo di avvio** selezionare manuale, quindi fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="65b3e-111">To enable the manual start-up of the service, in the **Properties** window select the **General** tab, and in the **Startup type** box select Manual, and then click **Apply**.</span></span>  
  
4. <span data-ttu-id="65b3e-112">Per avviare il servizio, nell'area stato servizio fare clic sul pulsante **Avvia** .</span><span class="sxs-lookup"><span data-stu-id="65b3e-112">To start the service,  in the Service status area, click the **Start** button.</span></span> <span data-ttu-id="65b3e-113">Lo stato del servizio dovrebbe ora essere "Avviato".</span><span class="sxs-lookup"><span data-stu-id="65b3e-113">The service status should now display "Started".</span></span>  
  
5. <span data-ttu-id="65b3e-114">Per tornare all'elenco dei servizi, fare clic su **OK**e chiudere la console MMC.</span><span class="sxs-lookup"><span data-stu-id="65b3e-114">To return to the list of services, click the **OK**, and exit the MMC Console.</span></span>  
  
## <a name="example"></a><span data-ttu-id="65b3e-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="65b3e-115">Example</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65b3e-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65b3e-116">See also</span></span>

- [<span data-ttu-id="65b3e-117">Condivisione delle porte Net.TCP</span><span class="sxs-lookup"><span data-stu-id="65b3e-117">Net.TCP Port Sharing</span></span>](net-tcp-port-sharing.md)
- [<span data-ttu-id="65b3e-118">Configurazione del servizio di condivisione delle porte Net.TCP</span><span class="sxs-lookup"><span data-stu-id="65b3e-118">Configuring the Net.TCP Port Sharing Service</span></span>](configuring-the-net-tcp-port-sharing-service.md)
