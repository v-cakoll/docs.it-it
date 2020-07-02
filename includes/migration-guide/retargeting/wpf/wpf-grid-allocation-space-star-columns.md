---
ms.openlocfilehash: 3709b9e694011666cebcb0ae09fbc838f65967af
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614868"
---
### <a name="wpf-grid-allocation-of-space-to-star-columns"></a>Allocazione di spazio della griglia di WPF per le colonne a stella

#### <a name="details"></a>Dettagli

A partire da .NET Framework 4.7, WPF sostituisce l'algoritmo usato dal controllo <xref:System.Windows.Controls.Grid> per allocare spazio alle colonne a stella (colonne \*). Questo modifica la larghezza effettiva assegnata alle colonne \* in diversi casi:

- Quando una o più \* colonne hanno anche una larghezza minima o massima che esegue l'override dell'allocazione proporzionale per tale Colum. (La larghezza minima può derivare da una dichiarazione esplicita MinWidth o da un minimo implicito ottenuto dal contenuto della colonna. La larghezza massima può essere definita solo in modo esplicito da una dichiarazione MaxWidth.)
- Quando una o più colonne \* dichiarano un peso \* estremamente elevato, maggiore di 10^298.
- Quando i pesi \* sono diversi al punto da far sì che si verifichi un'instabilità a virgola mobile (overflow, underflow, perdita di precisione).
- Quando è abilitato l'arrotondamento del layout e il DPI effettivamente visualizzato è sufficientemente elevato.
Nei primi due casi, le larghezze generate dal nuovo algoritmo possono essere notevolmente diverse da quelle generate dal vecchio algoritmo; nell'ultimo caso, la differenza sarà di uno o due pixel al massimo.<p/>Il nuovo algoritmo consente di risolvere diversi bug presenti nell'algoritmo precedente:

- L'allocazione totale alle colonne può superare la larghezza della griglia. Ciò può verificarsi quando si alloca spazio a una colonna la cui quota proporzionale è minore rispetto alle dimensioni minime. L'algoritmo alloca le dimensioni minime, riducendo lo spazio disponibile per le altre colonne. Se non sono presenti colonne \* da allocare, l'allocazione totale potrebbe essere troppo grande.
- L'allocazione totale può non raggiungere la larghezza della griglia. Questo è il doppio problema di # 1, che si verifica quando si effettua l'allocazione a una colonna la cui quota proporzionale è maggiore rispetto alle sue dimensioni massime, senza alcuna colonna \* per sfruttare la flessibilità.
- Due colonne \* possono ricevere le allocazioni in modo non proporzionale ai loro pesi \*. Questa è una versione più lieve di #1/#2, che si verifica durante l'allocazione alle colonne \* A, B e C (in questo ordine), dove la quota proporzionale di B viola il suo vincolo minimo o massimo. Come in precedenza, lo spazio disponibile alla colonna C si riduce e questa ottiene un'allocazione proporzionale inferiore o superiore rispetto ad A,
- Le colonne con pesi estremamente alti (&gt; 10^298) vengono considerate tutte come se avessero un peso di 10^298. Le differenze proporzionali tra di esse (e tra le colonne con pesi leggermente inferiori) non vengono rispettate.
- Le colonne con pesi infiniti non vengono gestite correttamente. [In realtà non è possibile impostare un peso su infinito, ma si tratta di una limitazione artificiale. Il codice di allocazione stava tentando di gestirlo, ma in un processo non valido.]
- Diversi problemi minori mentre si evita l'overflow, l'underflow, la perdita di precisione e altri problemi analoghi della virgola mobile.
- Le modifiche per l'arrotondamento del layout con un DPI sufficientemente elevato non sono corrette.
Il nuovo algoritmo produce risultati che soddisfano i criteri seguenti:<p/>R. La larghezza effettiva assegnata a una colonna * non è mai minore della larghezza minima né maggiore della larghezza massima.<br/>B. <em>A ogni colonna a cui non è assegnata la larghezza minima o massima viene assegnata una larghezza proporzionale al relativo <em>peso. Per essere precisi, se due colonne sono dichiarate rispettivamente con larghezza x</em> e y</em> e se nessuna delle colonne riceve la larghezza minima o massima, le larghezze effettive v e w assegnate alle colonne hanno la stessa proporzione: v/w = = x/y.<br/>C. La larghezza totale allocata alle &quot; colonne proporzionali &quot; \* è uguale allo spazio disponibile dopo l'allocazione alle colonne vincolate (fisse, automatiche e colonne a \* cui viene allocata la larghezza minima o massima). Potrebbe essere pari a zero, ad esempio se la somma delle larghezze minime è superiore alla larghezza disponibile della griglia.<br/>D. Tutte queste istruzioni devono essere interpretate in base al layout &quot;ideale&quot;. Quando l'arrotondamento del layout è attivo, le larghezze effettive possono differire dalle larghezze ideali per un massimo di un pixel.<br/>L'algoritmo precedente rispettava (A) ma non gli altri criteri nei casi descritti in precedenza.<p/>Quanto detto sulle colonne e sulle relative larghezze in questo articolo si applica anche a righe e altezza.

#### <a name="suggestion"></a>Suggerimento

Per impostazione predefinita, le app che usano versioni di .NET Framework successive alla versione 4.7 visualizzeranno il nuovo algoritmo, mentre le applicazioni che usano .NET Framework 4.6.2 o versioni precedenti visualizzeranno l'algoritmo precedente.<p/>Per ignorare l'impostazione predefinita, usare l'impostazione di configurazione seguente:

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

Con il valore `true` è possibile selezionare l'algoritmo precedente, mentre `false` consente di selezionare il nuovo algoritmo.

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Minorenne       |
| Version | 4.7         |
| Type    | Ridestinazione |
