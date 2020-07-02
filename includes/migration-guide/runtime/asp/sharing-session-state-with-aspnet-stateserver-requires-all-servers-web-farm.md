---
ms.openlocfilehash: 0fe07ac21effacffc56d37ccb46a121f443acd20
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620176"
---
### <a name="sharing-session-state-with-aspnet-stateserver-requires-all-servers-in-the-web-farm-to-use-the-same-net-framework-version"></a>Lo stato della sessione di condivisione con Asp.Net StateServer richiede che tutti i server nella Web farm usino la stessa versione di .NET Framework

#### <a name="details"></a>Dettagli

Quando si abilita lo stato della sessione <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=fullName>, tutti i server nella Web farm specificata devono usare la stessa versione di .NET Framework affinché lo stato venga condiviso correttamente.

#### <a name="suggestion"></a>Suggerimento

Verificare di aggiornare le versioni di .NET Framework nei server Web che condividono lo stato nello stesso momento.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.5|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=nameWithType></li></ul>|
