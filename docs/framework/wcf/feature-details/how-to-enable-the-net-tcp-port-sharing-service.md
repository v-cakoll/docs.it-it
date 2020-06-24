---
title: 'Procedura: attivare il servizio di condivisione delle porte Net.TCP'
description: Informazioni su come configurare il servizio di condivisione porte net TCP utilizzando MMC per abilitare net. TCP, che è disabilitato per impostazione predefinita.
ms.date: 03/30/2017
helpviewer_keywords:
- port sharing [WCF]
- activation services [WCF]
ms.assetid: c9175af4-c27c-4765-bf45-b8f7528a7282
ms.openlocfilehash: 0292559e3befde7f0b00b36aa10a2d9615daf049
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247000"
---
# <a name="how-to-enable-the-nettcp-port-sharing-service"></a><span data-ttu-id="26d8d-103">Procedura: attivare il servizio di condivisione delle porte Net.TCP</span><span class="sxs-lookup"><span data-stu-id="26d8d-103">How to: Enable the Net.TCP Port Sharing Service</span></span>
<span data-ttu-id="26d8d-104">Windows Communication Foundation (WCF) utilizza un servizio Windows denominato servizio di condivisione porte net. TCP per facilitare la condivisione delle porte TCP tra più processi.</span><span class="sxs-lookup"><span data-stu-id="26d8d-104">Windows Communication Foundation (WCF) uses a Windows service called the Net.TCP Port Sharing Service to facilitate the sharing of TCP ports across multiple processes.</span></span> <span data-ttu-id="26d8d-105">Questo servizio viene installato come parte di WCF, ma il servizio non è abilitato per impostazione predefinita come misura di sicurezza e pertanto deve essere abilitato manualmente prima del primo utilizzo.</span><span class="sxs-lookup"><span data-stu-id="26d8d-105">This service is installed as part of WCF, but the service is not enabled by default as a security precaution and so must be manually enabled prior to first use.</span></span> <span data-ttu-id="26d8d-106">In questo argomento viene illustrato come configurare il servizio di condivisione delle porte Net TCP usando lo snap-in MMC (Microsoft Management Console).</span><span class="sxs-lookup"><span data-stu-id="26d8d-106">This topic describes how to configure the Net TCP Port Sharing Service using the Microsoft Management Console (MMC) snap-In.</span></span>  
  
 <span data-ttu-id="26d8d-107">Dopo aver abilitato il servizio di condivisione porte net. TCP e averlo avviato manualmente, vedere [procedura: configurare un servizio WCF per l'uso della condivisione delle porte](how-to-configure-a-wcf-service-to-use-port-sharing.md) per informazioni su come configurare il servizio per l'uso di questo servizio.</span><span class="sxs-lookup"><span data-stu-id="26d8d-107">After you enable the Net.TCP Port Sharing Service and start it manually, see [How to: Configure a WCF Service to Use Port Sharing](how-to-configure-a-wcf-service-to-use-port-sharing.md) for information about how to configure your service to use this service.</span></span>  
  
 <span data-ttu-id="26d8d-108">Per un esempio che usa la condivisione delle porte net. TCP://, vedere l' [esempio di condivisione delle porte net. TCP](../samples/net-tcp-port-sharing-sample.md).</span><span class="sxs-lookup"><span data-stu-id="26d8d-108">For a sample that uses net.tcp:// port sharing, see the [Net.TCP Port Sharing Sample](../samples/net-tcp-port-sharing-sample.md).</span></span>  
  
### <a name="to-enable-the-nettcp-port-sharing-service-using-mmc"></a><span data-ttu-id="26d8d-109">Per attivare il servizio di condivisione delle porte Net.TCP tramite MMC</span><span class="sxs-lookup"><span data-stu-id="26d8d-109">To enable the Net.TCP Port Sharing Service using MMC</span></span>  
  
1. <span data-ttu-id="26d8d-110">Dal menu Start aprire la console di gestione dei servizi aprendo una finestra del prompt dei comandi e digitando `services.msc` o aprendo Esegui e digitando `services.msc` nella casella Apri.</span><span class="sxs-lookup"><span data-stu-id="26d8d-110">From the Start menu, open the Services Management Console either by opening a Command Prompt window and typing `services.msc` or by opening Run and typing `services.msc` into the Open box.</span></span>  
  
2. <span data-ttu-id="26d8d-111">Nella colonna **nome** dell'elenco dei servizi fare clic con il pulsante destro del mouse sul **servizio di condivisione porte net. TCP**e scegliere **proprietà** dal menu.</span><span class="sxs-lookup"><span data-stu-id="26d8d-111">In the **Name** column of the list of services, right-click the **Net.Tcp Port Sharing Service**, and select **Properties** from the menu.</span></span>  
  
3. <span data-ttu-id="26d8d-112">Per abilitare l'avvio manuale del servizio, nella finestra **Proprietà** selezionare la scheda **generale** e nella casella **tipo di avvio** selezionare manuale, quindi fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="26d8d-112">To enable the manual start-up of the service, in the **Properties** window select the **General** tab, and in the **Startup type** box select Manual, and then click **Apply**.</span></span>  
  
4. <span data-ttu-id="26d8d-113">Per avviare il servizio, nell'area stato servizio fare clic sul pulsante **Avvia** .</span><span class="sxs-lookup"><span data-stu-id="26d8d-113">To start the service,  in the Service status area, click the **Start** button.</span></span> <span data-ttu-id="26d8d-114">Lo stato del servizio dovrebbe ora essere "Avviato".</span><span class="sxs-lookup"><span data-stu-id="26d8d-114">The service status should now display "Started".</span></span>  
  
5. <span data-ttu-id="26d8d-115">Per tornare all'elenco dei servizi, fare clic su **OK**e chiudere la console MMC.</span><span class="sxs-lookup"><span data-stu-id="26d8d-115">To return to the list of services, click the **OK**, and exit the MMC Console.</span></span>  
  
## <a name="example"></a><span data-ttu-id="26d8d-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="26d8d-116">Example</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26d8d-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="26d8d-117">See also</span></span>

- [<span data-ttu-id="26d8d-118">Condivisione delle porte Net.TCP</span><span class="sxs-lookup"><span data-stu-id="26d8d-118">Net.TCP Port Sharing</span></span>](net-tcp-port-sharing.md)
- [<span data-ttu-id="26d8d-119">Configurazione del servizio di condivisione delle porte Net.TCP</span><span class="sxs-lookup"><span data-stu-id="26d8d-119">Configuring the Net.TCP Port Sharing Service</span></span>](configuring-the-net-tcp-port-sharing-service.md)
