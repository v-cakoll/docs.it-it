---
ms.openlocfilehash: 64d540278544e74c46d46b77c97bccd26d4116dd
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2019
ms.locfileid: "67803179"
---
### <a name="opt-in-break-to-revert-from-different-45-sql-generation-to-simpler-40-sql-generation"></a>Interruzione del consenso esplicito per tornare alla generazione di codice SQL più semplice della versione 4.0 dalla versione 4.5

|   |   |
|---|---|
|Dettagli|Le query che producono istruzioni JSON e contengono una chiamata a un'operazione di limitazione senza prima usare OrderBy producono ora codice SQL più semplice. Dopo l'aggiornamento a .NET Framework 4.5, queste query producevano codice SQL più complesso rispetto alle versioni precedenti.|
|Suggerimento|Questa funzionalità è disabilitata per impostazione predefinita. Se Entity Framework genera istruzioni JOIN aggiuntive che causano una riduzione del livello delle prestazioni, è possibile abilitare questa funzionalità aggiungendo la voce seguente alla sezione <code>&lt;appSettings&gt;</code> del file di configurazione dell'applicazione (app.config):<pre><code class="lang-xml">&lt;add key=&quot;EntityFramework_SimplifyLimitOperations&quot; value=&quot;true&quot; /&gt;&#13;&#10;</code></pre>|
|Ambito|Trasparente|
|Versione|4.5.2|
|Tipo|Runtime|

