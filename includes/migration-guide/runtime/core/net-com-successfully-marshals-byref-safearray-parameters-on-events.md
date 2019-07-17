---
ms.openlocfilehash: 2f4f92c8615b328caee2ad0b90028c76048026f4
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802600"
---
### <a name="net-com-successfully-marshals-byref-safearray-parameters-on-events"></a>.NET COM esegue correttamente il marshalling dei parametri ByRef SafeArray negli eventi

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.7.2 e versioni precedenti, un parametro ByRef [SafeArray](https://docs.microsoft.com/en-us/windows/desktop/api/oaidl/ns-oaidl-safearray) su un evento COM non sarebbe in grado di eseguire di nuovo il marshalling al codice nativo.  Con questa modifica il marshalling di [SafeArray](https://docs.microsoft.com/en-us/windows/desktop/api/oaidl/ns-oaidl-safearray) viene ora eseguito correttamente.<ul><li>[ x ] Anomalo</li></ul>|
|Suggerimento|Se la corretta esecuzione del marshalling dei parametri ByRef SafeArray negli eventi COM interrompe l'esecuzione, è possibile disabilitare questo codice aggiungendo l'opzione di configurazione seguente alla configurazione dell'applicazione:<pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.Runtime.InteropServices.DoNotMarshalOutByrefSafeArrayOnInvoke&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>|
|Ambito|Secondario|
|Versione|4.8|
|Tipo|Runtime|

