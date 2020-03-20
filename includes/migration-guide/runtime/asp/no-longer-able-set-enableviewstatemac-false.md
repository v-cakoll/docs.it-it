---
ms.openlocfilehash: dbe96abebdc61fae469f7727673e6fcb93cbc739
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67803176"
---
### <a name="no-longer-able-to-set-enableviewstatemac-to-false"></a>Non è più possibile impostare EnableViewStateMac su false

|   |   |
|---|---|
|Dettagli|ASP.NET non consente più agli sviluppatori di specificare <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> o <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code>. L'algoritmo Message Authentication Code (MAC) dello stato di visualizzazione viene ora applicato per tutte le richieste con stato di visualizzazione incorporato. Riguarda solo le app che impostano in modo esplicito la proprietà EnableViewStateMac su <code>false</code>.|
|Suggerimento|EnableViewStateMac deve essere considerato true e tutti gli errori MAC risultanti devono essere risolti (come spiegato in [questa guida](https://support.microsoft.com/kb/2915218), che contiene più risoluzioni a seconda delle specifiche di ciò che causa gli errori MAC).|
|Scope|Principale|
|Versione|4.5.2|
|Type|Runtime|
