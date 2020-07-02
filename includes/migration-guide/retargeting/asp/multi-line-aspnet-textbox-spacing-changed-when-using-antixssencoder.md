---
ms.openlocfilehash: 150b98255b3075a8fe8cad60ce234206b788a5f5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617187"
---
### <a name="multi-line-aspnet-textbox-spacing-changed-when-using-antixssencoder"></a>Modifica della spaziatura nel controllo TextBox ASP.Net multiriga quando si usa AntiXSSEncoder

#### <a name="details"></a>Dettagli

In .NET Framework 4.0 vengono inserite righe aggiuntive tra le righe di una casella di testo a più righe durante il postback, se si usa <xref:System.Web.Security.AntiXss.AntiXssEncoder?displayProperty=fullName>. In .NET Framework 4.5 queste interruzioni di riga aggiuntive non vengono incluse, ma solo se l'app Web è destinata a .NET Framework 4.5

#### <a name="suggestion"></a>Suggerimento

Tenere presente che le app Web 4.0 ridestinate a .NET Framework 4.5, possono avere caselle di testo a più righe migliorate in modo che non vengano più inserite interruzioni di riga aggiuntive. Se non è opportuno, l'app può avere il comportamento precedente quando viene eseguita in .NET Framework 4.5 usando .NET Framework 4.0 come destinazione.

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Minorenne       |
| Version | 4.5         |
| Type    | Ridestinazione |
