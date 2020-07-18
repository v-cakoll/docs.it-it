---
title: Controllo di serializzazione e deserializzazione con SerializationBinder
ms.date: 07/14/2020
ms.assetid: ba8dcecf-acc7-467c-939d-021bbac797d4
ms.openlocfilehash: 5a7d0bf2aabfcdf789a77cf0fcfeb26357575806
ms.sourcegitcommit: 2543a78be6e246aa010a01decf58889de53d1636
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/17/2020
ms.locfileid: "86444482"
---
# <a name="controlling-serialization-and-deserialization-with-serializationbinder"></a>Controllo di serializzazione e deserializzazione con SerializationBinder

> [!WARNING]
> <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>non è protetto e ***non*** può essere reso sicuro. Per ulteriori informazioni, vedere la [Guida alla sicurezza di BinaryFormatter](../../../standard/serialization/binaryformatter-security-guide.md).

Durante la serializzazione un formattatore trasmette le informazioni necessarie per la creazione di un'istanza di un oggetto di tipo e versione corretti. Tali informazioni comprendono in genere il nome completo del tipo e il nome dell'assembly dell'oggetto. Per impostazione predefinita, la deserializzazione usa queste informazioni per creare un'istanza di un oggetto identico. Per alcuni utenti potrebbe essere necessario controllare la classe da serializzare e deserializzare, in quanto la classe originale potrebbe non esistere sul computer che esegue la deserializzazione o si è spostata tra gli assembly oppure su server e client sono necessarie versioni diverse della classe. Per ulteriori informazioni, vedere [utilizzo del gestore di associazione della serializzazione](../samples/usage-of-serialization-binder.md).  
  
> [!WARNING]
> Questa funzionalità è disponibile solo se si usa <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> o <xref:System.Runtime.Serialization.NetDataContractSerializer>.  
  
## <a name="using-serializationbinder"></a>Uso di SerializationBinder  
 <xref:System.Runtime.Serialization.SerializationBinder> è una classe astratta usata per controllare i tipi effettivi usati durante la serializzazione e la deserializzazione. Per controllare i tipi usati durante la serializzazione e la deserializzazione, derivare una classe da <xref:System.Runtime.Serialization.SerializationBinder> ed eseguire l'override dei metodi <xref:System.Runtime.Serialization.SerializationBinder.BindToName(System.Type,System.String@,System.String@)> e <xref:System.Runtime.Serialization.SerializationBinder.BindToType(System.String,System.String)>. Il metodo <xref:System.Runtime.Serialization.SerializationBinder.BindToName(System.Type,System.String@,System.String@)> usa un elemento <xref:System.Type> e restituisce un nome tipo e assembly. Il metodo <xref:System.Runtime.Serialization.SerializationBinder.BindToType(System.String,System.String)> usa un nome tipo e assembly e restituisce un elemento <xref:System.Type>.  
  
## <a name="see-also"></a>Vedere anche

- [Serializzazione e deserializzazione](serialization-and-deserialization.md)
- [Utilizzo del gestore di associazione della serializzazione](../samples/usage-of-serialization-binder.md)
