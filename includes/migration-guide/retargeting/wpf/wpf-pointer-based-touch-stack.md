---
ms.openlocfilehash: eb89cbc72d8b09fd1aa5bc775a6c539eb208fa70
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614896"
---
### <a name="wpf-pointer-based-touch-stack"></a>Stack per input tocco WPF basato sul puntatore

#### <a name="details"></a>Dettagli

Questa modifica aggiunge la possibilità di attivare uno stack facoltativo per l'input tocco/stilo WPF basato su WM_POINTER.  Gli sviluppatori che non attivano in modo esplicito questo supporto non dovrebbero riscontrare alcuna modifica nel comportamento dell'input tocco/stilo WPF. Problemi noti correnti relativi allo stack facoltativo per l'input tocco/stilo basato su WM_POINTER:

- Nessun supporto per l'input penna in tempo reale.
- Anche se i plug-in dello stilo e dell'input penna continuano a funzionare, essi vengono elaborati nel thread dell'interfaccia utente, il che può comportare un peggioramento delle prestazioni.
- Modifiche del comportamento dovute alla promozione da eventi di tocco/stilo agli eventi del mouse
- La modifica potrebbe avere un comportamento diverso
- L'opzione Trascina selezione non dà la risposta appropriata per l'input tocco
- Questa operazione non influisce sull'input dello stilo
- L'opzione Trascina selezione non può essere avviata per gli eventi di tocco/stilo
- Questo può potenzialmente bloccare l'applicazione fino a quando non viene rilevato l'input del mouse.
- Gli sviluppatori dovranno quindi avviare l'opzione di trascinamento della selezione dagli eventi del mouse.

#### <a name="suggestion"></a>Suggerimento

Gli sviluppatori che desiderano abilitare questo stack possono aggiungere o unire quanto segue al file App.config dell'applicazione:

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Input.Stylus.EnablePointerSupport=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

Se si rimuove questo elemento o se ne imposta il valore su False si disattiva lo stack facoltativo. Si noti che lo stack è disponibile solo in Windows 10 Creators Update e versioni successive.

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| Version | 4.7         |
| Type    | Ridestinazione |
