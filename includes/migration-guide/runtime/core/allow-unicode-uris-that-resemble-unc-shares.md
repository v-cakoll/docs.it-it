---
ms.openlocfilehash: fbc39b6e1cc19f6c2846caaabb9a8a721494b4e6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67856987"
---
### <a name="allow-unicode-in-uris-that-resemble-unc-shares"></a>Consentire Unicode negli URI simili a condivisioni UNC

|   |   |
|---|---|
|Dettagli|In <xref:System.Uri?displayProperty=fullName>, la costruzione dell'URI di un file contenente sia un nome condivisione URI che caratteri Unicode non ha più come risultato un URI con stato interno non valido. Il comportamento cambia solo se tutte le condizioni seguenti sono vere:<ul><li>Lo schema dell'URI è <code>file:</code> ed è seguito da almeno quattro barre.</li><li>Il nome host inizia con un carattere di sottolineatura o con un altro simbolo non riservato.</li><li>L'URI contiene caratteri Unicode.</li></ul>|
|Suggerimento|Le applicazioni che utilizzano URI contenenti Unicode in modo coerente avrebbero presumibilmente potuto usare questo comportamento per impedire riferimenti a condivisioni UNC. Tali applicazioni devono invece usare <xref:System.Uri.IsUnc>.|
|Scope|Microsoft Edge|
|Versione|4.7.2|
|Type|Runtime|
|API interessate|<ul><li><xref:System.Uri?displayProperty=nameWithType></li></ul>|
