---
ms.openlocfilehash: 62702de022656e45466a45f4150e518226a3fecc
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621994"
---
### <a name="improvements-to-grid-star-rows-space-allocating-algorithm"></a>Miglioramenti all'algoritmo di allocazione dello spazio per le righe con ridimensionamento proporzionale (Star) della griglia

#### <a name="details"></a>Dettagli

È stato corretto un bug nell'[algoritmo per l'allocazione delle dimensioni](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md) in un elemento <xref:System.Windows.Controls.Grid> introdotto in .NET Framework 4.7.  In alcuni casi, ad esempio una griglia con <code>Height=&quot;Auto&quot;</code> contenente righe vuote, le righe venivano disposte nella posizione errata, anche totalmente all'esterno della griglia.

#### <a name="suggestion"></a>Suggerimento

Perché l'applicazione possa usufruire di queste modifiche, è necessario che sia eseguita in .NET Framework 4.8 o versione successiva.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Principale|
|Version|4.8|
|Type|Runtime|
