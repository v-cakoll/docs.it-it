---
ms.openlocfilehash: a3f5f512fd17ab2b076f868be24e5c73d8698c49
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67802487"
---
### <a name="objectdisposedexception-thrown-by-wpf-spellchecker"></a>ObjectDisposedException generata dal controllo ortografico WPF

|   |   |
|---|---|
|Dettagli|Può verificarsi l'arresto anomalo di applicazioni WPF con un <xref:System.ObjectDisposedException?displayProperty=name> generato dal controllo ortografico. Questo problema è risolto in .NET Framework 4.7 WPF, dove l'eccezione viene gestita in modo normale e pertanto si evitano effetti avversi sulle applicazioni. Si noti che potranno essere rilevate eccezioni first-chance occasionali nelle applicazioni in esecuzione in un debugger.|
|Suggerimento|Effettuare l'aggiornamento a .NET Framework 4.7|
|Scope|Microsoft Edge|
|Versione|4.6.1|
|Type|Runtime|
