---
ms.openlocfilehash: b836b26f3f52e9d0cc78feb764629bd2fa306657
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621803"
---
### <a name="objectdisposedexception-thrown-by-wpf-spellchecker"></a>ObjectDisposedException generata dal controllo ortografico WPF

#### <a name="details"></a>Dettagli

Può verificarsi l'arresto anomalo di applicazioni WPF con un <xref:System.ObjectDisposedException?displayProperty=fullName> generato dal controllo ortografico. Questo problema è risolto in .NET Framework 4.7 WPF, dove l'eccezione viene gestita in modo normale e pertanto si evitano effetti avversi sulle applicazioni. Si noti che potranno essere rilevate eccezioni first-chance occasionali nelle applicazioni in esecuzione in un debugger.

#### <a name="suggestion"></a>Suggerimento

Effettuare l'aggiornamento a .NET Framework 4.7

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.6.1|
|Type|Runtime|
