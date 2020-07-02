---
ms.openlocfilehash: f8e5dee9e97956cea78b7c8ec999af1afe9ac66b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620364"
---
### <a name="minfreememorypercentagetoactiveservice-is-now-respected"></a>L'impostazione MinFreeMemoryPercentageToActiveService viene ora rispettata

#### <a name="details"></a>Dettagli

Questa impostazione consente di stabilire la quantità minima di memoria che deve essere disponibile nel server per poter attivare un servizio WCF. È progettata in modo da prevenire le eccezioni <xref:System.OutOfMemoryException?displayProperty=fullName>. In .NET Framework 4.5 questa impostazione non ha alcun effetto. In .NET Framework 4.5.1 questa impostazione viene applicata.

#### <a name="suggestion"></a>Suggerimento

Viene generata un'eccezione se la quantità di memoria libera disponibile sul server Web è inferiore alla percentuale definita dall'impostazione di configurazione. Alcuni servizi WCF correttamente avviati ed eseguiti in un ambiente di memoria limitato potrebbero avere esito negativo.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Minorenne|
|Version|4.5.1|
|Type|Runtime|
