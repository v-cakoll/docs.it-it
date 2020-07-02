---
ms.openlocfilehash: af10716fe5f4c07091e8605cdf620e4a499fb1e8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620179"
---
### <a name="ipad-should-not-be-used-in-custom-capabilities-file-because-it-is-now-a-browser-capability"></a>IPad non deve essere usato nel file di funzionalità personalizzato perché ora è una funzionalità del browser

#### <a name="details"></a>Dettagli

A partire da .NET Framework 4.5, iPad è un identificatore nel file di funzionalità del browser predefinito di ASP.NET, quindi non deve essere usato in un file di funzionalità personalizzato

#### <a name="suggestion"></a>Suggerimento

Se sono richieste funzionalità specifiche per iPad, è necessario modificare il comportamento di iPad impostando le funzionalità sul refID &quot;IPad&quot; predefinito del gateway anziché generando un nuovo ID &quot;IPad&quot; in base alla corrispondenza dell'agente utente.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.5|
|Type|Runtime|
