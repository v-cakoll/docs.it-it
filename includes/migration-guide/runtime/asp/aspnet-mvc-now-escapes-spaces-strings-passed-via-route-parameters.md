---
ms.openlocfilehash: 7444ddbdd4a7c5f731fba8528ee2334374fc254e
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2020
ms.locfileid: "81275001"
---
### <a name="aspnet-mvc-now-escapes-spaces-in-strings-passed-in-via-route-parameters"></a>ASP.NET MVC usa ora caratteri di escape per gli spazi nelle stringhe passate tramite i parametri di una route

|   |   |
|---|---|
|Dettagli|Per conformità allo standard RFC 2396, vengono ora usati caratteri di escape per gli spazi nei percorsi di route durante il popolamento dei parametri di azione da una route. Pertanto, mentre <code>/controller/action/some data</code> in precedenza corrispondeva alla route <code>/controller/action/{data}</code> e forniva il parametro dati <code>some data</code>, ora fornisce invece <code>some%20data</code>.|
|Suggerimento|È necessario aggiornare il codice per rimuovere i caratteri di escape dai parametri stringa da una route. Se è necessario l'URI originale, è possibile accedervi con l'API <xref:System.Net.HttpWebRequest.RequestUri>.OriginalString.|
|Scope|Minorenne|
|Versione|4.5.2|
|Type|Runtime|
|API interessate|<ul><li><xref:System.Web.Mvc.RouteAttribute.%23ctor(System.String)></li></ul>|
