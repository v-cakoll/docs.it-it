---
ms.openlocfilehash: 3b7309347c643d89a28331c6ef3cac36085a969a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858424"
---
### <a name="wpf-windows-are-rendered-without-clipping-when-extending-outside-a-single-monitor"></a>Il rendering delle finestre WPF viene eseguito senza ritaglio quando le finestre si estendono oltre un singolo monitor

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.6 in esecuzione su Windows 8 e versioni successive viene eseguito il rendering dell'intera finestra senza ritaglio quando la finestra si estende al di fuori di un singolo schermo in uno scenario d'uso di più monitor. Questo comportamento è diverso rispetto a quello delle versioni precedenti di .NET Framework in cui le finestre WPF che si estendevano oltre un singolo schermo venivano ritagliate.|
|Suggerimento|Questo funzionamento (applicazione o non applicazione del ritaglio) può essere impostato esplicitamente tramite l'elemento <code>&lt;EnableMultiMonitorDisplayClipping&gt;</code> in <code>&lt;appSettings&gt;</code> nel file di configurazione di un'applicazione oppure impostando la proprietà <code>EnableMultiMonitorDisplayClipping</code> all'avvio dell'app.|
|Scope|Minorenne|
|Versione|4.6|
|Type|Runtime|
