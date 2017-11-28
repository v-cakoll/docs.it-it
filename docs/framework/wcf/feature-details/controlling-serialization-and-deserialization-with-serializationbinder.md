---
title: Controllo di serializzazione e deserializzazione con SerializationBinder
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ba8dcecf-acc7-467c-939d-021bbac797d4
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1c3180d62824f94e27e02c80e09fdf32252f0a23
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="controlling-serialization-and-deserialization-with-serializationbinder"></a>Controllo di serializzazione e deserializzazione con SerializationBinder
Durante la serializzazione un formattatore trasmette le informazioni necessarie per la creazione di un'istanza di un oggetto di tipo e versione corretti. Tali informazioni comprendono in genere il nome completo del tipo e il nome dell'assembly dell'oggetto. Per impostazione predefinita, la deserializzazione usa queste informazioni per creare un'istanza di un oggetto identico. Per alcuni utenti potrebbe essere necessario controllare la classe da serializzare e deserializzare, in quanto la classe originale potrebbe non esistere sul computer che esegue la deserializzazione o si è spostata tra gli assembly oppure su server e client sono necessarie versioni diverse della classe. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Utilizzo del gestore di associazione della serializzazione](../../../../docs/framework/wcf/samples/usage-of-serialization-binder.md).  
  
> [!WARNING]
>  Questa funzionalità è disponibile solo se si usa <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> o <xref:System.Runtime.Serialization.NetDataContractSerializer>.  
  
## <a name="using-serializationbinder"></a>Uso di SerializationBinder  
 <xref:System.Runtime.Serialization.SerializationBinder> è una classe astratta usata per controllare i tipi effettivi usati durante la serializzazione e la deserializzazione. Per controllare i tipi utilizzati durante la serializzazione e la deserializzazione, derivare una classe da <xref:System.Runtime.Serialization.SerializationBinder> ed eseguire l'override di <xref:System.Runtime.Serialization.SerializationBinder.BindToName%2A> System. String, System.String)?qualifyHint=False & autoUpgrade = True e <xref:System.Runtime.Serialization.SerializationBinder.BindToType%2A> System. String)? qualifyHint = False & autoUpgrade = True metodi. Il <xref:System.Runtime.Serialization.SerializationBinder.BindToName%2A> System. String, System.String)?qualifyHint=False & autoUpgrade = True metodo accetta un <xref:System.Type> e restituisce un nome di tipo e assembly. Il <xref:System.Runtime.Serialization.SerializationBinder.BindToType%2A> System.String)?qualifyHint=False & autoUpgrade = True metodo accetta un assembly e nome del tipo e restituisce un <xref:System.Type>.  
  
## <a name="see-also"></a>Vedere anche  
 [La serializzazione e deserializzazione](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md)  
 [Utilizzo del gestore di associazione della serializzazione](../../../../docs/framework/wcf/samples/usage-of-serialization-binder.md)
