---
ms.openlocfilehash: 22b5abbe769733e8d5ca3e78dd9e6e13b2363737
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620311"
---
### <a name="opt-in-break-to-revert-from-different-45-sql-generation-to-simpler-40-sql-generation"></a>Interruzione del consenso esplicito per tornare alla generazione di codice SQL più semplice della versione 4.0 dalla versione 4.5

#### <a name="details"></a>Dettagli

Le query che producono istruzioni JSON e contengono una chiamata a un'operazione di limitazione senza prima usare OrderBy producono ora codice SQL più semplice. Dopo l'aggiornamento a .NET Framework 4.5, queste query producevano codice SQL più complesso rispetto alle versioni precedenti.

#### <a name="suggestion"></a>Suggerimento

Questa funzionalità è disabilitata per impostazione predefinita. Se Entity Framework genera istruzioni JOIN aggiuntive che causano una riduzione del livello delle prestazioni, è possibile abilitare questa funzionalità aggiungendo la voce seguente alla sezione <code>&lt;appSettings&gt;</code> del file di configurazione dell'applicazione (app.config):<pre><code class="lang-xml">&lt;add key=&quot;EntityFramework_SimplifyLimitOperations&quot; value=&quot;true&quot; /&gt;&#13;&#10;</code></pre>

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Modalità trasparente|
|Version|4.5.2|
|Type|Runtime|
