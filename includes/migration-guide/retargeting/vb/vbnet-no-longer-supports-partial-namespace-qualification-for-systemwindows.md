---
ms.openlocfilehash: cef8096c971da8ae245ff974697022f350cb9195
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616077"
---
### <a name="vbnet-no-longer-supports-partial-namespace-qualification-for-systemwindows-apis"></a>VB.NET non supporta più la qualificazione parziale dello spazio dei nomi per le API System.Windows

#### <a name="details"></a>Dettagli

A partire da .NET Framework 4.5.2, i progetti VB.NET non possono specificare API System.Windows con spazi dei nomi parzialmente qualificati. Ad esempio, un riferimento a `Windows.Forms.DialogResult` avrà esito negativo. Il codice deve invece fare riferimento al nome completo (<xref:System.Windows.Forms.DialogResult>) o importare lo spazio dei nomi specifico e fare semplicemente riferimento a <xref:System.Windows.Forms.DialogResult?displayProperty=fullName>.

#### <a name="suggestion"></a>Suggerimento

È consigliabile aggiornare il codice in modo che faccia riferimento alle API `System.Windows` tramite nomi semplici (e importare lo spazio dei nomi rilevante) o con nomi completi.

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Minorenne       |
| Version | 4.5.2       |
| Type    | Ridestinazione |
