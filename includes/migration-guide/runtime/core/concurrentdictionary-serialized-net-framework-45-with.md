---
ms.openlocfilehash: ae0f68a19d6eae53998d61e924cfef3aaaec1784
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620231"
---
### <a name="a-concurrentdictionary-serialized-in-net-framework-45-with-netdatacontractserializer-cannot-be-deserialized-by-net-framework-451-or-452"></a>Un oggetto ConcurrentDictionary serializzato in .NET Framework 4.5 con NetDataContractSerializer non può essere deserializzato da .NET Framework 4.5.1 o 4.5.2

#### <a name="details"></a>Dettagli

A causa di modifiche interne al tipo, non è possibile deserializzare in .NET Framework 4.5.1 o in .NET Framework 4.5.2 gli oggetti <xref:System.Collections.Concurrent.ConcurrentDictionary%602> serializzati con .NET Framework 4.5 usando <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName>. L'operazione nella direzione opposta, ovvero la serializzazione con .NET Framework 4.5.x e la deserializzazione con .NET Framework 4.5, invece funziona. In modo analogo, tutte le operazioni di serializzazione tra le diverse versioni 4.x funziona con .NET Framework 4.6. La serializzazione e la deserializzazione con una singola versione di .NET Framework non è interessata.

#### <a name="suggestion"></a>Suggerimento

Se è necessario serializzare e deserializzare un oggetto <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName> tra .NET Framework 4.5 e .NET Framework 4.5.1/4.5.2, usare un serializzatore alternativo, ad esempio <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=fullName> o <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName>, invece di <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName>. In alternativa, poiché il problema è stato risolto in .NET Framework 4.6, eseguire l'aggiornamento a questa versione.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Minorenne|
|Version|4.5.1|
|Type|Runtime|
