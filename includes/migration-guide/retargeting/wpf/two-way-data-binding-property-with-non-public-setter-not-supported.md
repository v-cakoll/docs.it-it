---
ms.openlocfilehash: a70aca33d0830f3b23ff985f17c469cb7c4ff35c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234721"
---
### <a name="two-way-data-binding-to-a-property-with-a-non-public-setter-is-not-supported"></a>Il data binding bidirezionale con una proprietà senza un setter pubblico non è supportato

|   |   |
|---|---|
|Dettagli|Il data binding per una proprietà senza un setter pubblico non è mai stata uno scenario supportato. A partire da .NET Framework 4.5.1, questo scenario genererà una <xref:System.InvalidOperationException?displayProperty=name>. Si noti che la nuova eccezione verrà generata soltanto per le app destinate specificamente a .NET Framework 4.5.1. Per le app destinate a .NET Framework 4.5, la chiamata sarà consentita. Se l'app non è destinata a una versione specifica di .NET Framework, l'associazione verrà considerata unidirezionale.|
|Suggerimento|È consigliabile aggiornare l'app per usare l'associazione unidirezionale o esporre pubblicamente il setter della proprietà. In alternativa, è possibile destinare l'app a .NET Framework 4.5 per ottenere il comportamento precedente.|
|Ambito|Secondario|
|Versione|4.5.1|
|Tipo|Ridestinazione|
|API interessate|<ul><li><xref:System.Windows.Data.BindingMode.TwoWay?displayProperty=nameWithType></li></ul>|
