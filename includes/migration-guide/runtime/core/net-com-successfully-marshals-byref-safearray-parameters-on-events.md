---
ms.openlocfilehash: 9c72bc686e014a0bffdf272e3813358d1b29cc66
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2019
ms.locfileid: "65199149"
---
### <a name="net-com-successfully-marshals-byref-safearray-parameters-on-events"></a>.NET COM esegue correttamente il marshalling dei parametri ByRef SafeArray negli eventi

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.7.2 e versioni precedenti, un parametro ByRef [SafeArray](https://docs.microsoft.com/en-us/windows/desktop/api/oaidl/ns-oaidl-safearray) su un evento COM non sarebbe in grado di eseguire di nuovo il marshalling al codice nativo.  Con questa modifica il marshalling di [SafeArray](https://docs.microsoft.com/en-us/windows/desktop/api/oaidl/ns-oaidl-safearray) viene ora eseguito correttamente.<ul><li>[ x ] Anomalo</li></ul>|
|Suggerimento|Se la corretta esecuzione del marshalling dei parametri ByRef SafeArray negli eventi COM interrompe l'esecuzione, è possibile disabilitare questo codice aggiungendo l'opzione di configurazione seguente alla configurazione dell'applicazione:<pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.Runtime.InteropServices.DoNotMarshalOutByrefSafeArrayOnInvoke&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>|
|Ambito|Secondario|
|Versione|4.8|
|Tipo|Runtime|
