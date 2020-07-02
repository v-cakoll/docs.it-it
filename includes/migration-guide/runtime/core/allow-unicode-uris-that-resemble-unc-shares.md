---
ms.openlocfilehash: 3e8601ba76dfb05e3d70b3af7440bd7e228768d0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621172"
---
### <a name="allow-unicode-in-uris-that-resemble-unc-shares"></a>Consentire Unicode negli URI simili a condivisioni UNC

#### <a name="details"></a>Dettagli

In <xref:System.Uri?displayProperty=fullName>, la costruzione dell'URI di un file contenente sia un nome condivisione URI che caratteri Unicode non ha più come risultato un URI con stato interno non valido. Il comportamento cambia solo se tutte le condizioni seguenti sono vere:<ul><li>Lo schema dell'URI è <code>file:</code> ed è seguito da almeno quattro barre.</li><li>Il nome host inizia con un carattere di sottolineatura o con un altro simbolo non riservato.</li><li>L'URI contiene caratteri Unicode.</li></ul>

#### <a name="suggestion"></a>Suggerimento

Le applicazioni che utilizzano URI contenenti Unicode in modo coerente avrebbero presumibilmente potuto usare questo comportamento per impedire riferimenti a condivisioni UNC. Tali applicazioni devono invece usare <xref:System.Uri.IsUnc>.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.7.2|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Uri?displayProperty=nameWithType></li></ul>|
