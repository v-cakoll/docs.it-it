---
ms.openlocfilehash: 2278d82d5362fe217ca4bce02a052d4b440843c2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236654"
---
### <a name="aspnet-mvc-now-escapes-spaces-in-strings-passed-in-via-route-parameters"></a>ASP.NET MVC usa ora caratteri di escape per gli spazi nelle stringhe passate tramite i parametri di una route

|   |   |
|---|---|
|Dettagli|Per conformità allo standard RFC 2396, vengono ora usati caratteri di escape per gli spazi nei percorsi di route durante il popolamento dei parametri di azione da una route. Pertanto, mentre <code>/controller/action/some data</code> in precedenza corrispondeva alla route <code>/controller/action/{data}</code> e forniva il parametro dati <code>some data</code>, ora fornisce invece <code>some%20data</code>.|
|Suggerimento|È necessario aggiornare il codice per rimuovere i caratteri di escape dai parametri stringa da una route. Se è necessario l'URI originale, è possibile accedervi con l'API <xref:System.Net.HttpWebRequest.RequestUri>.OriginalString.|
|Ambito|Secondario|
|Versione|4.5.2|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Web.Mvc.RouteAttribute.%23ctor(System.String)?displayProperty=nameWithType></li></ul>|
