---
ms.openlocfilehash: 5f1a8af37a305ab0904801002dd99e17e8eca62e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616122"
---
### <a name="two-way-data-binding-to-a-property-with-a-non-public-setter-is-not-supported"></a>Il data binding bidirezionale con una proprietà senza un setter pubblico non è supportato

#### <a name="details"></a>Dettagli

Il data binding per una proprietà senza un setter pubblico non è mai stata uno scenario supportato. A partire da .NET Framework 4.5.1, questo scenario genererà una <xref:System.InvalidOperationException?displayProperty=fullName>. Si noti che la nuova eccezione verrà generata soltanto per le app destinate specificamente a .NET Framework 4.5.1. Per le app destinate a .NET Framework 4.5, la chiamata sarà consentita. Se l'app non è destinata a una versione specifica di .NET Framework, l'associazione verrà considerata unidirezionale.

#### <a name="suggestion"></a>Suggerimento

È consigliabile aggiornare l'app per usare l'associazione unidirezionale o esporre pubblicamente il setter della proprietà. In alternativa, è possibile destinare l'app a .NET Framework 4.5 per ottenere il comportamento precedente.

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Minorenne       |
| Version | 4.5.1       |
| Type    | Ridestinazione |

#### <a name="affected-apis"></a>API interessate

- <xref:System.Windows.Data.BindingMode.TwoWay?displayProperty=nameWithType>
