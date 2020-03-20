---
ms.openlocfilehash: 8e0c934cd8c3cb8c08a526c7e145436db6ecf4a5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "68237599"
---
### <a name="improvements-to-grid-star-rows-space-allocating-algorithm"></a>Miglioramenti all'algoritmo di allocazione dello spazio per le righe con ridimensionamento proporzionale (Star) della griglia

|   |   |
|---|---|
|Dettagli|È stato corretto un bug nell'[algoritmo per l'allocazione delle dimensioni](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md) in un elemento <xref:System.Windows.Controls.Grid> introdotto in .NET Framework 4.7.  In alcuni casi, ad esempio una griglia con <code>Height=&quot;Auto&quot;</code> contenente righe vuote, le righe venivano disposte nella posizione errata, anche totalmente all'esterno della griglia.|
|Suggerimento|Perché l'applicazione possa usufruire di queste modifiche, è necessario che sia eseguita in .NET Framework 4.8 o versione successiva.|
|Scope|Principale|
|Versione|4.8|
|Type|Runtime|
