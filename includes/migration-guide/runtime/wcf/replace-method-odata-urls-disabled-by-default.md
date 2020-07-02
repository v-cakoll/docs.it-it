---
ms.openlocfilehash: b2fcacdb02c411c4dcb12051bf0c6759faccdea2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620391"
---
### <a name="the-replace-method-in-odata-urls-is-disabled-by-default"></a>Il metodo Replace negli URL OData è disabilitato per impostazione predefinita

#### <a name="details"></a>Dettagli

A partire da .NET Framework 4.5, il metodo Replace negli URL OData è disabilitato per impostazione predefinita. Quando il metodo Replace è disabilitato per OData, ora per impostazione predefinita, le eventuali richieste utente che includono funzioni di sostituzione (non comuni) avranno esito negativo.

#### <a name="suggestion"></a>Suggerimento

Se il metodo Replace è necessario (situazione non comune) è possibile riabilitarlo tramite le impostazioni di configurazione (<xref:System.Data.Services.Configuration.DataServicesFeaturesSection.ReplaceFunction?displayProperty=fullName>). L'abilitazione di un metodo Replace, tuttavia, può introdurre vulnerabilità per la sicurezza ed è consigliabile usarlo solo dopo attente valutazioni.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.5|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Data.Services.DataService%601?displayProperty=nameWithType></li></ul>|
