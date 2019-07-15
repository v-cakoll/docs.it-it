---
ms.openlocfilehash: d3c6818861f8b0261a9a71a4654029143d928d08
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2019
ms.locfileid: "67856987"
---
### <a name="allow-unicode-in-uris-that-resemble-unc-shares"></a>Consentire Unicode negli URI simili a condivisioni UNC

|   |   |
|---|---|
|Dettagli|In <xref:System.Uri?displayProperty=fullName>, la costruzione dell'URI di un file contenente sia un nome condivisione URI che caratteri Unicode non ha più come risultato un URI con stato interno non valido. Il comportamento cambia solo se tutte le condizioni seguenti sono vere:<ul><li>Lo schema dell'URI è <code>file:</code> ed è seguito da almeno quattro barre.</li><li>Il nome host inizia con un carattere di sottolineatura o con un altro simbolo non riservato.</li><li>L'URI contiene caratteri Unicode.</li></ul>|
|Suggerimento|Le applicazioni che utilizzano URI contenenti Unicode in modo coerente avrebbero presumibilmente potuto usare questo comportamento per impedire riferimenti a condivisioni UNC. Tali applicazioni devono invece usare <xref:System.Uri.IsUnc>.|
|Ambito|Microsoft Edge|
|Versione|4.7.2|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Uri?displayProperty=nameWithType></li></ul>|

