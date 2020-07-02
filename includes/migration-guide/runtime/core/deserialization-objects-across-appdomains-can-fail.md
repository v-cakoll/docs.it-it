---
ms.openlocfilehash: 5c949b79eefa68ea6f8d4ad27c716c438e24f170
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620214"
---
### <a name="deserialization-of-objects-across-appdomains-can-fail"></a>La deserializzazione di oggetti tra domini app può non riuscire

#### <a name="details"></a>Dettagli

In alcuni casi, quando un'app usa due o più domini di app con diverse basi dell'applicazione, il tentativo di deserializzare gli oggetti nel contesto di una chiamata logica tra domini di app genera un'eccezione.

#### <a name="suggestion"></a>Suggerimento

Vedere [Mitigazione: deserializzazione di oggetti tra domini app](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.5.1|
|Type|Runtime|
