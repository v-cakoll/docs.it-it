---
ms.openlocfilehash: 958a89015420ce5632d596688963d576c40b4cb6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235584"
---
### <a name="sharing-session-state-with-aspnet-stateserver-requires-all-servers-in-the-web-farm-to-use-the-same-net-framework-version"></a>Lo stato della sessione di condivisione con Asp.Net StateServer richiede che tutti i server nella Web farm usino la stessa versione di .NET Framework

|   |   |
|---|---|
|Dettagli|Quando si abilita lo stato della sessione <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=name>, tutti i server nella Web farm specificata devono usare la stessa versione di .NET Framework affinché lo stato venga condiviso correttamente.|
|Suggerimento|Verificare di aggiornare le versioni di .NET Framework nei server Web che condividono lo stato nello stesso momento.|
|Ambito|Microsoft Edge|
|Versione|4.5|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=nameWithType></li></ul>|
