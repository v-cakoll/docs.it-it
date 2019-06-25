---
title: Utilizzo del gestore di associazione della serializzazione
ms.date: 03/30/2017
ms.assetid: ab46c087-200c-45bf-9c95-5a6cda6e8b98
ms.openlocfilehash: 10900950b935b484053fe8e37263f0dfc25eba99
ms.sourcegitcommit: 127343afce8422bfa944c8b0c4ecc8f79f653255
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2019
ms.locfileid: "67348451"
---
# <a name="usage-of-serialization-binder"></a>Utilizzo del gestore di associazione della serializzazione
In questo esempio viene illustrato come utilizzare <xref:System.Runtime.Serialization.SerializationBinder> per modificare la versione di un tipo generico quando è serializzato.  
  
## <a name="demonstrates"></a>Dimostrazione  
 <xref:System.Runtime.Serialization.SerializationBinder>, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>  
  
## <a name="discussion"></a>Discussione  
 Questo esempio viene illustrato come due entità che sono targeting versioni diverse dell'oggetto può di .NET Framework di comunicare utilizzando il formattatore binario e lo strumento di associazione della serializzazione.  
  
In questo esempio è stato sviluppato utilizzando .NET Remoting. È costituito da un server di destinazione [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)], che implementa un contratto con tipi generici e due client diversi, una destinazione .NET Framework 2.0 e un altro destinato a [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)].  
  
 Il server allega un oggetto <xref:System.Runtime.Serialization.SerializationBinder> al formattatore binario per essere in grado di modificare di conseguenza la versione dei tipi durante la serializzazione, consentendo a entrambi i client di deserializzare correttamente tali tipi.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Per eseguire il client, fare clic sulla soluzione SBGenericsVTS (6 progetti) e quindi selezionare **proprietà**.  
  
2. Nelle **proprietà comuni**, selezionare **progetto di avvio**, quindi selezionare **progetti di avvio multipli**.  
  
3. Selezionare **Server** primo, quindi **Client20** e quindi **Client40**. Selezionare il **avviare** azione per questi tre progetti e lasciare i restanti vengono impostati su **None**.  
  
4. Fare clic su **OK** e quindi premere F5 per eseguire l'esempio.
