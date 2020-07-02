---
ms.openlocfilehash: 424e8ff704b888aa3d2c1254ac712da4034f59b8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616121"
---
### <a name="obsoleteattribute-exports-as-both-obsoleteattribute-and-deprecatedattribute-in-winmd-scenarios"></a>L'attributo ObsoleteAttribute viene esportato sia come ObsoleteAttribute che come DeprecatedAttribute negli scenari WinMD

#### <a name="details"></a>Dettagli

Quando si crea una raccolta di metadati Windows (file con estensione winmd), l'attributo <xref:System.ObsoleteAttribute?displayProperty=fullName> viene esportato sia come <xref:System.ObsoleteAttribute?displayProperty=fullName> che come [Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute).

#### <a name="suggestion"></a>Suggerimento

La ricompilazione del codice sorgente esistente che usa l'attributo <xref:System.ObsoleteAttribute?displayProperty=fullName> può generare avvisi quando si utilizza tale codice da C++/CX o JavaScript. È sconsigliabile applicare sia <xref:System.ObsoleteAttribute?displayProperty=fullName> che [ Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute) al codice negli assembly gestiti, perché potrebbero essere generati avvisi di compilazione.

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| Version | 4.5.1       |
| Type    | Ridestinazione |
