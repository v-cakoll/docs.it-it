---
ms.openlocfilehash: c6c897c13c84ce4b2be21da18e5702365518f286
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620324"
---
### <a name="ef-no-longer-throws-for-queryviews-with-specific-characteristics"></a>Entity Framework non genera più eccezioni per QueryView con caratteristiche specifiche

#### <a name="details"></a>Dettagli

Entity Framework non genera più un'eccezione <xref:System.StackOverflowException?displayProperty=fullName> quando un'app esegue una query che coinvolge un elemento QueryView con una proprietà di navigazione 0..1 che tenta di includere le entità correlate nella query. Ad esempio, chiamando <code>.Include(e =&gt; e.RelatedNavProp)</code>.

#### <a name="suggestion"></a>Suggerimento

Questa modifica riguarda solo il codice che usa elementi QueryView con relazioni 1-0..1 in caso di esecuzione di query che chiamano .Include. Migliora l'affidabilità e dovrebbe essere trasparente a quasi tutte le app. Se tuttavia questa modifica causa un comportamento imprevisto, è possibile disabilitarla aggiungendo la voce seguente alla sezione <code>&lt;appSettings&gt;</code> del file di configurazione dell'app:<pre><code class="lang-xml">&lt;add key=&quot;EntityFramework_SimplifyUserSpecifiedViews&quot; value=&quot;false&quot; /&gt;&#13;&#10;</code></pre>

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.5.2|
|Type|Runtime|
