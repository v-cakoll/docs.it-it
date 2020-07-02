---
ms.openlocfilehash: 77e9d28d79a92cf1523e4ef5779d78394b00ae80
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621984"
---
### <a name="net-com-successfully-marshals-byref-safearray-parameters-on-events"></a>.NET COM esegue correttamente il marshalling dei parametri ByRef SafeArray negli eventi

#### <a name="details"></a>Dettagli

In .NET Framework 4.7.2 e versioni precedenti, un parametro ByRef [SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray) su un evento COM non sarebbe in grado di eseguire di nuovo il marshalling al codice nativo.  Con questa modifica il marshalling di [SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray) viene ora eseguito correttamente.<ul><li>[ x ] Anomalo</li></ul>

#### <a name="suggestion"></a>Suggerimento

Se la corretta esecuzione del marshalling dei parametri ByRef SafeArray negli eventi COM interrompe l'esecuzione, è possibile disabilitare questo codice aggiungendo l'opzione di configurazione seguente alla configurazione dell'applicazione:<pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.Runtime.InteropServices.DoNotMarshalOutByrefSafeArrayOnInvoke&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Minorenne|
|Version|4.8|
|Type|Runtime|
