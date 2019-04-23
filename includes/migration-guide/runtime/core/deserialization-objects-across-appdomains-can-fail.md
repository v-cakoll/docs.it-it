---
ms.openlocfilehash: 891c29b731214fb0028e960256b79cfc267d86b9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235465"
---
### <a name="deserialization-of-objects-across-appdomains-can-fail"></a>La deserializzazione di oggetti tra domini app può non riuscire

|   |   |
|---|---|
|Dettagli|In alcuni casi, quando un'app usa due o più domini di app con diverse basi dell'applicazione, il tentativo di deserializzare gli oggetti nel contesto di una chiamata logica tra domini di app genera un'eccezione.|
|Suggerimento|Vedere [Mitigazione: deserializzazione di oggetti tra domini app](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)|
|Ambito|Microsoft Edge|
|Versione|4.5.1|
|Tipo|Runtime|
