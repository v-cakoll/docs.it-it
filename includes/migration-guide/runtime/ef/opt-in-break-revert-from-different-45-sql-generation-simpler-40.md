---
ms.openlocfilehash: e5d81d791e1a2f1a2dbdafc787dec1227423883d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67803179"
---
### <a name="opt-in-break-to-revert-from-different-45-sql-generation-to-simpler-40-sql-generation"></a>Interruzione del consenso esplicito per tornare alla generazione di codice SQL più semplice della versione 4.0 dalla versione 4.5

|   |   |
|---|---|
|Dettagli|Le query che producono istruzioni JSON e contengono una chiamata a un'operazione di limitazione senza prima usare OrderBy producono ora codice SQL più semplice. Dopo l'aggiornamento a .NET Framework 4.5, queste query producevano codice SQL più complesso rispetto alle versioni precedenti.|
|Suggerimento|Questa funzionalità è disabilitata per impostazione predefinita. Se Entity Framework genera istruzioni JOIN aggiuntive che causano una riduzione del livello delle prestazioni, è possibile abilitare questa funzionalità aggiungendo la voce seguente alla sezione <code>&lt;appSettings&gt;</code> del file di configurazione dell'applicazione (app.config):<pre><code class="lang-xml">&lt;add key=&quot;EntityFramework_SimplifyLimitOperations&quot; value=&quot;true&quot; /&gt;&#13;&#10;</code></pre>|
|Scope|Trasparente|
|Versione|4.5.2|
|Type|Runtime|
