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
# <a name="usage-of-serialization-binder"></a>Utilizzo del gestore di associazione della serializzazione
In questo esempio viene illustrato come utilizzare <xref:System.Runtime.Serialization.SerializationBinder> per modificare la versione di un tipo generico quando è serializzato.  
  
## <a name="demonstrates"></a>Dimostrazione  
 <xref:System.Runtime.Serialization.SerializationBinder>, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>  
  
## <a name="discussion"></a>Discussione  
 In questo esempio viene illustrato come due entità destinate a versioni diverse del .NET Framework possono comunicare utilizzando il formattatore binario e il binder di serializzazione.  
  
Questo esempio è stato sviluppato con .NET Remoting. È costituito da un server di destinazione .NET Framework 4, che implementa un contratto con tipi generici e due client diversi, uno destinato .NET Framework 2,0 e un altro destinato .NET Framework 4.  
  
 Il server allega un oggetto <xref:System.Runtime.Serialization.SerializationBinder> al formattatore binario per essere in grado di modificare di conseguenza la versione dei tipi durante la serializzazione, consentendo a entrambi i client di deserializzare correttamente tali tipi.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Per eseguire il client, fare clic con il pulsante destro del mouse sulla soluzione SBGenericsVTS (6 progetti), quindi scegliere **Proprietà**.  
  
2. In **Proprietà comuni**selezionare **progetto di avvio**, quindi selezionare **progetti di avvio multipli**.  
  
3. Selezionare innanzitutto **Server** , quindi **Client20** e infine **Client40**. Selezionare l'azione **Avvia** per questi tre progetti e lasciare invariato il resto impostato su **nessuno**.  
  
4. Fare clic su **OK** e premere F5 per eseguire l'esempio.
