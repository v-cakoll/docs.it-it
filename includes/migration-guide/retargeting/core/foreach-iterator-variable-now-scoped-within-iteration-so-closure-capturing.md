---
ms.openlocfilehash: 1805c26f1eff46719f30de8a14ca6d35f01948a6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234758"
---
### <a name="foreach-iterator-variable-is-now-scoped-within-the-iteration-so-closure-capturing-semantics-are-different-in-c5"></a>L'ambito della variabile iteratore Foreach è ora all'interno dell'iterazione, quindi la semantica di acquisizione della chiusura è diversa (in C# 5)

|   |   |
|---|---|
|Dettagli|A partire da C# 5 (Visual Studio 2012), le variabili iteratore <code>foreach</code> hanno ambito limitato all'interno dell'iterazione. Ciò può causare interruzioni se il codice dipende dal fatto che le variabili non siano incluse nella chiusura di <code>foreach</code>. Il sintomo di questa modifica è che una variabile iteratore passata a un delegato viene gestita come avente il valore esistente al momento della creazione del delegato, invece del valore esistente al momento della chiamata del delegato.|
|Suggerimento|Idealmente, è consigliabile aggiornare il codice in modo che tenga conto del nuovo comportamento del compilatore. Se è richiesta la semantica precedente, la variabile iteratore può essere sostituita con una variabile separata che viene inserita in modo esplicito all'esterno dell'ambito del ciclo.|
|Ambito|Principale|
|Versione|4.5|
|Tipo|Ridestinazione|
