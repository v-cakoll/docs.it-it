---
ms.openlocfilehash: 0056baa1e5f0cdc5bfcf8b0e83c9490ec5722926
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235705"
---
### <a name="httputilityjavascriptstringencode-escapes-ampersand"></a>HttpUtility.JavaScriptStringEncode esegue l'escape del carattere e commerciale

|   |   |
|---|---|
|Dettagli|A partire da .NET Framework 4.5, <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=name> esegue l'escape del carattere e commerciale (&amp;).|
|Suggerimento|Se l'app dipende dal comportamento precedente di questo metodo, è possibile aggiungere un'impostazione aspnet:JavaScriptDoNotEncodeAmpersand all'[elemento appSettings di ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/hh975440(v=vs.120)) nel file di configurazione.|
|Ambito|Secondario|
|Versione|4.5|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=nameWithType></li><li><xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)?displayProperty=nameWithType></li></ul>|
