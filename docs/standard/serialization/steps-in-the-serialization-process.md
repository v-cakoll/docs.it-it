---
title: Passaggi del processo di serializzazione
description: Il processo di serializzazione inizia quando il metodo Serialize viene chiamato in un formattatore. Questo articolo descrive la sequenza di eventi.
ms.date: 08/07/2017
helpviewer_keywords:
- binary serialization, steps
- serialization, steps
ms.assetid: 4bcbc883-2a91-418f-b968-6c86a25e9737
ms.openlocfilehash: 1f749b9102182e78bc3fda436cf386a9f5759d5a
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379105"
---
# <a name="steps-in-the-serialization-process"></a>Passaggi del processo di serializzazione
Quando viene chiamato il metodo <xref:System.Runtime.Serialization.Formatter.Serialize%2A> su un [formattatore](xref:System.Runtime.Serialization.Formatter), la serializzazione dell'oggetto continua secondo la sequenza di regole riportata di seguito:

- Viene effettuato un controllo per determinare se il formattatore dispone di un selettore di surrogati. In caso affermativo, controllare se il selettore di surrogati gestisce oggetti del tipo specificato. Se il selettore gestisce il tipo di oggetto, viene chiamato <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=nameWithType> sul selettore di surrogati.

- Se non è presente alcun selettore di surrogati o il tipo di oggetto non viene gestito, viene effettuato un controllo per determinare se l'oggetto è contrassegnato con l'attributo [Serializable](xref:System.SerializableAttribute). Se l'oggetto non è contrassegnato, viene generata una <xref:System.Runtime.Serialization.SerializationException>.

- Se l'oggetto è contrassegnato in modo appropriato, controllare se l'oggetto implementa l'interfaccia <xref:System.Runtime.Serialization.ISerializable>. In caso affermativo, <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> viene chiamato sull'oggetto.
  
- Se l'oggetto non implementa <xref:System.Runtime.Serialization.ISerializable>, vengono usati i criteri di serializzazione predefiniti, che serializzano tutti i campi non contrassegnati come [NonSerialized](xref:System.NonSerializedAttribute).

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]
  
## <a name="see-also"></a>Vedere anche

- [Serializzazione binaria](binary-serialization.md)
- [Serializzazione SOAP e XML](xml-and-soap-serialization.md)
