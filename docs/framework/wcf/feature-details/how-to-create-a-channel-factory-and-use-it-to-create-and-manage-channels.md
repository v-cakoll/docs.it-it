---
title: 'Procedura: Creare una Channel Factory e usarlo per creare e gestire canali'
ms.date: 03/30/2017
ms.assetid: 018dcc30-9f61-419e-af8e-412a85e8d282
ms.openlocfilehash: 37ba8db3084f8d90aab33a08f6b52ddaee4545f8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54649531"
---
# <a name="how-to-create-a-channel-factory-and-use-it-to-create-and-manage-channels"></a><span data-ttu-id="d10b9-102">Procedura: Creare una Channel Factory e usarlo per creare e gestire canali</span><span class="sxs-lookup"><span data-stu-id="d10b9-102">How to: Create a Channel Factory and Use it to Create and Manage Channels</span></span>
<span data-ttu-id="d10b9-103">La classe <xref:System.ServiceModel.DuplexChannelFactory%601> fornisce i mezzi per creare e gestire canali duplex di diversi tipi utilizzati dai client per scambiare messaggi con gli endpoint di servizio.</span><span class="sxs-lookup"><span data-stu-id="d10b9-103">The <xref:System.ServiceModel.DuplexChannelFactory%601> class provides the means to create and manage duplex channels of different types that clients use to send and receive messages to and from service endpoints.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d10b9-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="d10b9-104">Example</span></span>  
 <span data-ttu-id="d10b9-105">Nel codice seguente viene illustrato come creare una channel factory e come utilizzarla per creare e gestire canali.</span><span class="sxs-lookup"><span data-stu-id="d10b9-105">The following code shows how to create a channel factory and use it to create and manage channels.</span></span>  
  
 [!code-csharp[S_CustomAuthentication#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_customauthentication/cs/instance.cs#1)]  
  
## <a name="see-also"></a><span data-ttu-id="d10b9-106">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d10b9-106">See also</span></span>
- <xref:System.ServiceModel.DuplexChannelFactory%601>
