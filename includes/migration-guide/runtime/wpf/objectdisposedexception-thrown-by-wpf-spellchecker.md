---
ms.openlocfilehash: a3f5f512fd17ab2b076f868be24e5c73d8698c49
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234207"
---
### <a name="objectdisposedexception-thrown-by-wpf-spellchecker"></a>ObjectDisposedException generata dal controllo ortografico WPF

|   |   |
|---|---|
|Dettagli|Può verificarsi l'arresto anomalo di applicazioni WPF con un <xref:System.ObjectDisposedException?displayProperty=name> generato dal controllo ortografico. Questo problema è risolto in .NET Framework 4.7 WPF, dove l'eccezione viene gestita in modo normale e pertanto si evitano effetti avversi sulle applicazioni. Si noti che potranno essere rilevate eccezioni first-chance occasionali nelle applicazioni in esecuzione in un debugger.|
|Suggerimento|Effettuare l'aggiornamento a .NET Framework 4.7|
|Ambito|Microsoft Edge|
|Versione|4.6.1|
|Tipo|Runtime|
