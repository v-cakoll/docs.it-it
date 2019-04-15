---
ms.openlocfilehash: 84f570cbbd97be79426e117d4c97ec182a397fd4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235537"
---
### <a name="ipad-should-not-be-used-in-custom-capabilities-file-because-it-is-now-a-browser-capability"></a>IPad non deve essere usato nel file di funzionalità personalizzato perché ora è una funzionalità del browser

|   |   |
|---|---|
|Dettagli|A partire da .NET Framework 4.5, iPad è un identificatore nel file di funzionalità del browser predefinito di ASP.NET, quindi non deve essere usato in un file di funzionalità personalizzato|
|Suggerimento|Se sono richieste funzionalità specifiche per iPad, è necessario modificare il comportamento di iPad impostando le funzionalità sul refID &quot;IPad&quot; predefinito del gateway anziché generando un nuovo ID &quot;IPad&quot; in base alla corrispondenza dell'agente utente.|
|Ambito|Microsoft Edge|
|Versione|4.5|
|Tipo|Runtime|
