---
title: Passaggi del processo di serializzazione
ms.date: 08/07/2017
ms.prod: .net
ms.topic: article
helpviewer_keywords:
- binary serialization, steps
- serialization, steps
ms.assetid: 4bcbc883-2a91-418f-b968-6c86a25e9737
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: cc6df422359826bc908bd412aaf89aa784be59ba
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="steps-in-the-serialization-process"></a>Passaggi del processo di serializzazione
Quando viene chiamato il metodo <xref:System.Runtime.Serialization.Formatter.Serialize*> su un [formattatore](xref:System.Runtime.Serialization.Formatter), la serializzazione dell'oggetto continua secondo la sequenza di regole riportata di seguito:

- Viene effettuato un controllo per determinare se il formattatore dispone di un selettore di surrogati. In caso affermativo, controllare se il selettore di surrogati gestisce oggetti del tipo specificato. Se il selettore gestisce il tipo di oggetto, viene chiamato <xref:System.Runtime.Serialization.ISerializable.GetObjectData*?displayProperty=nameWithType> sul selettore di surrogati.

- Se non è presente alcun selettore di surrogati o il tipo di oggetto non viene gestito, viene effettuato un controllo per determinare se l'oggetto è contrassegnato con l'attributo [Serializable](xref:System.SerializableAttribute). Se l'oggetto non è contrassegnato, viene generata una <xref:System.Runtime.Serialization.SerializationException>.

- Se l'oggetto è contrassegnato in modo appropriato, controllare se l'oggetto implementa l'interfaccia <xref:System.Runtime.Serialization.ISerializable>. In caso affermativo, <xref:System.Runtime.Serialization.ISerializable.GetObjectData*> viene chiamato sull'oggetto.
  
- Se l'oggetto non implementa <xref:System.Runtime.Serialization.ISerializable>, vengono usati i criteri di serializzazione predefiniti, che serializzano tutti i campi non contrassegnati come [NonSerialized](xref:System.NonSerializedAttribute).

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]
  
## <a name="see-also"></a>Vedere anche  
 [Serializzazione binaria](binary-serialization.md)  
 [Serializzazione SOAP e XML](xml-and-soap-serialization.md)