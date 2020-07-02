---
ms.openlocfilehash: eef5633ec8566f6d5216b7dca4387766cacb600d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620384"
---
### <a name="netdatacontractserializer-fails-to-deserialize-a-concurrentdictionary-serialized-with-a-different-net-version"></a>NetDataContractSerializer non riesce a deserializzare un elemento ConcurrentDictionary serializzato con una versione di .NET diversa

#### <a name="details"></a>Dettagli

Come da progettazione, la classe <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> può essere usata solo se le estremità di serializzazione e deserializzazione condividono gli stessi tipi CLR. La deserializzazione di un oggetto serializzato con una versione di .NET Framework da parte di una versione diversa non è quindi garantita. <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName> è un tipo che non viene deserializzato correttamente se serializzato con .NET Framework 4.5 o versioni precedenti e deserializzato con .NET Framework 4.5.1 o versioni successive.

#### <a name="suggestion"></a>Suggerimento

Per risolvere questo problema, sono disponibili alcune soluzioni alternative:<ul><li>Aggiornare anche il computer di serializzazione a .NET Framework 4.5.1.</li><li>Usare <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=fullName> anziché <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> poiché non prevede esattamente gli stessi tipi CLR a entrambe le estremità di serializzazione e deserializzazione.</li><li>Usare <xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName> anziché <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName> poiché non mostra questo particolare problema 4.5-&gt;4.5.1.</li></ul>

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Minorenne|
|Version|4.5.1|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Runtime.Serialization.NetDataContractSerializer.Deserialize(System.IO.Stream)?displayProperty=nameWithType></li></ul>|
