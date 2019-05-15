---
title: Utilizzo del gestore di associazione della serializzazione
ms.date: 03/30/2017
ms.assetid: ab46c087-200c-45bf-9c95-5a6cda6e8b98
ms.openlocfilehash: 677decebcf444fed95311bd02acf8a96e0a4eca9
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591773"
---
# <a name="usage-of-serialization-binder"></a><span data-ttu-id="fce04-102">Utilizzo del gestore di associazione della serializzazione</span><span class="sxs-lookup"><span data-stu-id="fce04-102">Usage of Serialization Binder</span></span>
<span data-ttu-id="fce04-103">In questo esempio viene illustrato come utilizzare <xref:System.Runtime.Serialization.SerializationBinder> per modificare la versione di un tipo generico quando è serializzato.</span><span class="sxs-lookup"><span data-stu-id="fce04-103">This sample shows how to use the <xref:System.Runtime.Serialization.SerializationBinder> to change the version of a generic type when it is serialized.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="fce04-104">Dimostrazione</span><span class="sxs-lookup"><span data-stu-id="fce04-104">Demonstrates</span></span>  
 <span data-ttu-id="fce04-105"><xref:System.Runtime.Serialization.SerializationBinder>, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter></span><span class="sxs-lookup"><span data-stu-id="fce04-105"><xref:System.Runtime.Serialization.SerializationBinder>, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter></span></span>  
  
## <a name="discussion"></a><span data-ttu-id="fce04-106">Discussione</span><span class="sxs-lookup"><span data-stu-id="fce04-106">Discussion</span></span>  
 <span data-ttu-id="fce04-107">Questo esempio viene illustrato come due entità che sono targeting versioni diverse dell'oggetto può di .NET Framework di comunicare utilizzando il formattatore binario e lo strumento di associazione della serializzazione.</span><span class="sxs-lookup"><span data-stu-id="fce04-107">This sample shows how two entities that are targeting different versions of the .NET Framework can communicate using the binary formatter and the serialization binder.</span></span>  
  
 <span data-ttu-id="fce04-108">Lo sviluppo di questo esempio è stato realizzato tramite .NET Remoting.</span><span class="sxs-lookup"><span data-stu-id="fce04-108">The development of this sample has been done using .NET Remoting.</span></span> <span data-ttu-id="fce04-109">L'esempio è costituito da un server destinato a [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] che implementa un contratto con tipi generici e due client diversi, uno destinato a [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)] e un altro destinato a [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fce04-109">The sample consists of a server targeting [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)], which implements a contract with generic types, and two different clients, one targeting [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)] and another targeting [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)].</span></span>  
  
 <span data-ttu-id="fce04-110">Il server allega un oggetto <xref:System.Runtime.Serialization.SerializationBinder> al formattatore binario per essere in grado di modificare di conseguenza la versione dei tipi durante la serializzazione, consentendo a entrambi i client di deserializzare correttamente tali tipi.</span><span class="sxs-lookup"><span data-stu-id="fce04-110">The server attaches a <xref:System.Runtime.Serialization.SerializationBinder> to the binary formatter to be able to change the version of the types accordingly on serialization, so both clients can deserialize those types properly.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="fce04-111">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="fce04-111">To set up, build and run the sample</span></span>  
  
1. <span data-ttu-id="fce04-112">Per eseguire il client, fare clic sulla soluzione SBGenericsVTS (6 progetti) e quindi selezionare **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="fce04-112">To execute the client, right-click the solution, SBGenericsVTS (6 projects) and then select **Properties**.</span></span>  
  
2. <span data-ttu-id="fce04-113">Nelle **proprietà comuni**, selezionare **progetto di avvio**, quindi selezionare **progetti di avvio multipli**.</span><span class="sxs-lookup"><span data-stu-id="fce04-113">In **Common Properties**, select **Startup Project**, then select **Multiple Startup Projects**.</span></span>  
  
3. <span data-ttu-id="fce04-114">Selezionare **Server** primo, quindi **Client20** e quindi **Client40**.</span><span class="sxs-lookup"><span data-stu-id="fce04-114">Select **Server** first, then **Client20** and then **Client40**.</span></span> <span data-ttu-id="fce04-115">Selezionare il **avviare** azione per questi tre progetti e lasciare i restanti vengono impostati su **None**.</span><span class="sxs-lookup"><span data-stu-id="fce04-115">Select the **Start** action to these three projects and leave the rest set to **None**.</span></span>  
  
4. <span data-ttu-id="fce04-116">Fare clic su **OK** e quindi premere F5 per eseguire l'esempio.</span><span class="sxs-lookup"><span data-stu-id="fce04-116">Click **OK** and then press F5 to run the sample.</span></span>
