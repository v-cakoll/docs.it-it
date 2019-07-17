---
ms.openlocfilehash: 770e303ab261b97efb49a3e0865a015d8de33247
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802621"
---
### <a name="improvements-to-grid-star-rows-space-allocating-algorithm"></a>Miglioramenti all'algoritmo di allocazione dello spazio per le righe con ridimensionamento proporzionale (Star) della griglia

|   |   |
|---|---|
|Dettagli|È stato corretto un bug nell'[algoritmo per l'allocazione delle dimensioni](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md) in un elemento <xref:System.Windows.Controls.Grid> introdotto in .NET Framework 4.7.  In alcuni casi, ad esempio una griglia con <code>Height=&quot;Auto&quot;</code> contenente righe vuote, le righe venivano disposte nella posizione errata, anche totalmente all'esterno della griglia.|
|Suggerimento|Perché l'applicazione possa usufruire di queste modifiche, è necessario che sia eseguita in .NET Framework 4.8 o versione successiva.|
|Ambito|Principale|
|Versione|4.8|
|Tipo|Runtime|

