---
ms.openlocfilehash: 6dc3669433804a4524c18d5a932f9879343ab508
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235456"
---
### <a name="the-replace-method-in-odata-urls-is-disabled-by-default"></a>Il metodo Replace negli URL OData è disabilitato per impostazione predefinita

|   |   |
|---|---|
|Dettagli|A partire da .NET Framework 4.5, il metodo Replace negli URL OData è disabilitato per impostazione predefinita. Quando il metodo Replace è disabilitato per OData, ora per impostazione predefinita, le eventuali richieste utente che includono funzioni di sostituzione (non comuni) avranno esito negativo.|
|Suggerimento|Se il metodo Replace è necessario (situazione non comune) è possibile riabilitarlo tramite le impostazioni di configurazione (<xref:System.Data.Services.Configuration.DataServicesFeaturesSection.ReplaceFunction?displayProperty=name>). L'abilitazione di un metodo Replace, tuttavia, può introdurre vulnerabilità per la sicurezza ed è consigliabile usarlo solo dopo attente valutazioni.|
|Ambito|Microsoft Edge|
|Versione|4.5|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Data.Services.DataService%601?displayProperty=nameWithType></li></ul>|
