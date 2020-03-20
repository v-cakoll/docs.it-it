---
ms.openlocfilehash: f9d7b8d22818245b96cafffe3732bdfe82ff69d8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858449"
---
### <a name="a-concurrentdictionary-serialized-in-net-framework-45-with-netdatacontractserializer-cannot-be-deserialized-by-net-framework-451-or-452"></a>Un oggetto ConcurrentDictionary serializzato in .NET Framework 4.5 con NetDataContractSerializer non può essere deserializzato da .NET Framework 4.5.1 o 4.5.2

|   |   |
|---|---|
|Dettagli|A causa di modifiche interne al tipo, non è possibile deserializzare in .NET Framework 4.5.1 o in .NET Framework 4.5.2 gli oggetti <xref:System.Collections.Concurrent.ConcurrentDictionary%602> serializzati con .NET Framework 4.5 usando <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=name>. L'operazione nella direzione opposta, ovvero la serializzazione con .NET Framework 4.5.x e la deserializzazione con .NET Framework 4.5, invece funziona. In modo analogo, tutte le operazioni di serializzazione tra le diverse versioni 4.x funziona con .NET Framework 4.6. La serializzazione e la deserializzazione con una singola versione di .NET Framework non è interessata.|
|Suggerimento|Se è necessario serializzare e deserializzare un oggetto <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=name> tra .NET Framework 4.5 e .NET Framework 4.5.1/4.5.2, usare un serializzatore alternativo, ad esempio <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=name> o <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=name>, invece di <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=name>. In alternativa, poiché il problema è stato risolto in .NET Framework 4.6, eseguire l'aggiornamento a questa versione.|
|Scope|Minorenne|
|Versione|4.5.1|
|Type|Runtime|
