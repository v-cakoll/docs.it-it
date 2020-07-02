---
ms.openlocfilehash: f955e270f709ddf6eea2e44bbcf386e372b9f6e3
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621316"
---
### <a name="targetframeworkname-for-default-app-domain-no-longer-defaults-to-null-if-not-set"></a>L'impostazione predefinita di TargetFrameworkName per il dominio app predefinito non è più Null, se non impostata

#### <a name="details"></a>Dettagli

<xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName> era precedentemente Null nel dominio app predefinito, se non impostata in modo esplicito. A partire dalla versione 4.6, la proprietà <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName> per il dominio app predefinito avrà un valore predefinito derivato da TargetFrameworkAttribute, se presente. I domini app non predefiniti continueranno a ereditare la proprietà <xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName> dal dominio app predefinito (che non avrà per impostazione predefinita il valore Null nella versione 4.6), a meno che non sia sottoposta a override in modo esplicito.

#### <a name="suggestion"></a>Suggerimento

Il codice deve essere aggiornato in modo che non dipenda dal fatto che l'impostazione predefinita di <xref:System.AppDomainSetup.TargetFrameworkName> sia null. Se è necessario che questa proprietà continui a restituire null, è possibile impostarla in modo esplicito su tale valore.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.6|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=nameWithType></li></ul>|
