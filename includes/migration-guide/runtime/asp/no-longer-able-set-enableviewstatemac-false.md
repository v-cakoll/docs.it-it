---
ms.openlocfilehash: cecb7b2abd4f57fdaacb0ea373cc19dc3cd9b24a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620167"
---
### <a name="no-longer-able-to-set-enableviewstatemac-to-false"></a>Non è più possibile impostare EnableViewStateMac su false

#### <a name="details"></a>Dettagli

ASP.NET non consente più agli sviluppatori di specificare <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> o <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code>. L'algoritmo Message Authentication Code (MAC) dello stato di visualizzazione viene ora applicato per tutte le richieste con stato di visualizzazione incorporato. Riguarda solo le app che impostano in modo esplicito la proprietà EnableViewStateMac su <code>false</code>.

#### <a name="suggestion"></a>Suggerimento

EnableViewStateMac deve essere impostato su true e tutti gli errori MAC risultanti devono essere risolti (come illustrato in [questa guida](https://support.microsoft.com/kb/2915218), che contiene più risoluzioni a seconda delle specifiche di ciò che causa errori Mac).

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Principale|
|Version|4.5.2|
|Type|Runtime|
