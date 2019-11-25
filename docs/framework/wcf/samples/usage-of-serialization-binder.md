---
title: Utilizzo del gestore di associazione della serializzazione
ms.date: 03/30/2017
ms.assetid: ab46c087-200c-45bf-9c95-5a6cda6e8b98
ms.openlocfilehash: bfce2a14c8757250c520919c8ff2a4d7048a9d5c
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/16/2019
ms.locfileid: "74138656"
---
# <a name="usage-of-serialization-binder"></a><span data-ttu-id="20b6a-102">Utilizzo del gestore di associazione della serializzazione</span><span class="sxs-lookup"><span data-stu-id="20b6a-102">Usage of Serialization Binder</span></span>
<span data-ttu-id="20b6a-103">In questo esempio viene illustrato come utilizzare <xref:System.Runtime.Serialization.SerializationBinder> per modificare la versione di un tipo generico quando è serializzato.</span><span class="sxs-lookup"><span data-stu-id="20b6a-103">This sample shows how to use the <xref:System.Runtime.Serialization.SerializationBinder> to change the version of a generic type when it is serialized.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="20b6a-104">Dimostrazione</span><span class="sxs-lookup"><span data-stu-id="20b6a-104">Demonstrates</span></span>  
 <span data-ttu-id="20b6a-105"><xref:System.Runtime.Serialization.SerializationBinder>, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter></span><span class="sxs-lookup"><span data-stu-id="20b6a-105"><xref:System.Runtime.Serialization.SerializationBinder>, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter></span></span>  
  
## <a name="discussion"></a><span data-ttu-id="20b6a-106">Discussione</span><span class="sxs-lookup"><span data-stu-id="20b6a-106">Discussion</span></span>  
 <span data-ttu-id="20b6a-107">In questo esempio viene illustrato come due entità destinate a versioni diverse del .NET Framework possono comunicare utilizzando il formattatore binario e il binder di serializzazione.</span><span class="sxs-lookup"><span data-stu-id="20b6a-107">This sample shows how two entities that are targeting different versions of the .NET Framework can communicate using the binary formatter and the serialization binder.</span></span>  
  
<span data-ttu-id="20b6a-108">Questo esempio è stato sviluppato con .NET Remoting.</span><span class="sxs-lookup"><span data-stu-id="20b6a-108">This sample was developed using .NET Remoting.</span></span> <span data-ttu-id="20b6a-109">È costituito da un server di destinazione .NET Framework 4, che implementa un contratto con tipi generici e due client diversi, uno destinato .NET Framework 2,0 e un altro destinato .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="20b6a-109">It consists of a server targeting .NET Framework 4, which implements a contract with generic types, and two different clients, one targeting .NET Framework 2.0 and another targeting .NET Framework 4.</span></span>  
  
 <span data-ttu-id="20b6a-110">Il server allega un oggetto <xref:System.Runtime.Serialization.SerializationBinder> al formattatore binario per essere in grado di modificare di conseguenza la versione dei tipi durante la serializzazione, consentendo a entrambi i client di deserializzare correttamente tali tipi.</span><span class="sxs-lookup"><span data-stu-id="20b6a-110">The server attaches a <xref:System.Runtime.Serialization.SerializationBinder> to the binary formatter to be able to change the version of the types accordingly on serialization, so both clients can deserialize those types properly.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="20b6a-111">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="20b6a-111">To set up, build and run the sample</span></span>  
  
1. <span data-ttu-id="20b6a-112">Per eseguire il client, fare clic con il pulsante destro del mouse sulla soluzione SBGenericsVTS (6 progetti), quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="20b6a-112">To execute the client, right-click the solution, SBGenericsVTS (6 projects) and then select **Properties**.</span></span>  
  
2. <span data-ttu-id="20b6a-113">In **Proprietà comuni**selezionare **progetto di avvio**, quindi selezionare **progetti di avvio multipli**.</span><span class="sxs-lookup"><span data-stu-id="20b6a-113">In **Common Properties**, select **Startup Project**, then select **Multiple Startup Projects**.</span></span>  
  
3. <span data-ttu-id="20b6a-114">Selezionare innanzitutto **Server** , quindi **Client20** e infine **Client40**.</span><span class="sxs-lookup"><span data-stu-id="20b6a-114">Select **Server** first, then **Client20** and then **Client40**.</span></span> <span data-ttu-id="20b6a-115">Selezionare l'azione **Avvia** per questi tre progetti e lasciare invariato il resto impostato su **nessuno**.</span><span class="sxs-lookup"><span data-stu-id="20b6a-115">Select the **Start** action to these three projects and leave the rest set to **None**.</span></span>  
  
4. <span data-ttu-id="20b6a-116">Fare clic su **OK** e premere F5 per eseguire l'esempio.</span><span class="sxs-lookup"><span data-stu-id="20b6a-116">Click **OK** and then press F5 to run the sample.</span></span>
