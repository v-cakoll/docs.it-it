---
title: Utilizzo del gestore di associazione della serializzazione
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ab46c087-200c-45bf-9c95-5a6cda6e8b98
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 77f5c2914051c4310102a57b7181333bab6811b6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="usage-of-serialization-binder"></a>Utilizzo del gestore di associazione della serializzazione
In questo esempio viene illustrato come utilizzare <xref:System.Runtime.Serialization.SerializationBinder> per modificare la versione di un tipo generico quando è serializzato.  
  
## <a name="demonstrates"></a>Dimostrazione  
 <xref:System.Runtime.Serialization.SerializationBinder>, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>  
  
## <a name="discussion"></a>Discussione  
 In questo esempio viene illustrato come due entità destinate a versioni diverse di [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] possono comunicare utilizzando il formattatore binario e il gestore di associazione della serializzazione.  
  
 Lo sviluppo di questo esempio è stato realizzato tramite .NET Remoting. L'esempio è costituito da un server destinato a [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] che implementa un contratto con tipi generici e due client diversi, uno destinato a [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)] e un altro destinato a [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)].  
  
 Il server allega un oggetto <xref:System.Runtime.Serialization.SerializationBinder> al formattatore binario per essere in grado di modificare di conseguenza la versione dei tipi durante la serializzazione, consentendo a entrambi i client di deserializzare correttamente tali tipi.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1.  Per eseguire il client, fare clic sulla soluzione SBGenericsVTS (6 progetti), quindi selezionare **proprietà**.  
  
2.  In **proprietà comuni**selezionare **progetto di avvio**, quindi selezionare **più progetti di avvio**.  
  
3.  Selezionare **Server** prima, quindi **Client20** e quindi **Client40**. Selezionare il **avviare** azione per questi tre progetti e lasciare gli altri impostati su **Nessuno**.  
  
4.  Fare clic su **OK** e quindi premere F5 per eseguire l'esempio.
