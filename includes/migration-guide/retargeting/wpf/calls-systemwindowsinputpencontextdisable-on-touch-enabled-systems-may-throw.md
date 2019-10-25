---
ms.openlocfilehash: 6bb8c87af66e744514fb43e628c6423487342ac2
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2019
ms.locfileid: "72887788"
---
### <a name="calls-to-systemwindowsinputpencontextdisable-on-touch-enabled-systems-may-throw-an-argumentexception"></a>Le chiamate a System.Windows.Input.PenContext.Disable nei sistemi abilitati per il tocco possono generare ArgumentException

|   |   |
|---|---|
|Dettagli|In alcuni casi, le chiamate al metodo **System.Windows.Intput.PenContext.Disable** interno nei sistemi abilitati per il tocco possono generare una <code>T:System.ArgumentException</code> non gestita a causa della reentrancy.|
|Suggerimento|Questo problema è stato risolto in .NET Framework 4.7. Per evitare l'eccezione, eseguire l'aggiornamento a una versione di .NET Framework a partire da .NET Framework 4.7.|
|Scope|Marginale|
|Versione|4.6.1|
|Digitare|Ridestinazione|
