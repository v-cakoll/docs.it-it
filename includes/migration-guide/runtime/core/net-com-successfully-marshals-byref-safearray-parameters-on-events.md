---
ms.openlocfilehash: 6ff23bbe8c48235770d39cb7d35a1df7de6c5201
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "68440270"
---
### <a name="net-com-successfully-marshals-byref-safearray-parameters-on-events"></a>.NET COM esegue correttamente il marshalling dei parametri ByRef SafeArray negli eventi

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.7.2 e versioni precedenti, un parametro ByRef [SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray) su un evento COM non sarebbe in grado di eseguire di nuovo il marshalling al codice nativo.  Con questa modifica il marshalling di [SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray) viene ora eseguito correttamente.<ul><li>[ x ] Anomalo</li></ul>|
|Suggerimento|Se la corretta esecuzione del marshalling dei parametri ByRef SafeArray negli eventi COM interrompe l'esecuzione, è possibile disabilitare questo codice aggiungendo l'opzione di configurazione seguente alla configurazione dell'applicazione:<pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.Runtime.InteropServices.DoNotMarshalOutByrefSafeArrayOnInvoke&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>|
|Scope|Minorenne|
|Versione|4.8|
|Type|Runtime|
