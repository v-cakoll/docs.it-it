---
ms.openlocfilehash: 2f4f92c8615b328caee2ad0b90028c76048026f4
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802600"
---
### <a name="net-com-successfully-marshals-byref-safearray-parameters-on-events"></a><span data-ttu-id="dc7ea-101">.NET COM esegue correttamente il marshalling dei parametri ByRef SafeArray negli eventi</span><span class="sxs-lookup"><span data-stu-id="dc7ea-101">.NET COM successfully marshals ByRef SafeArray parameters on events</span></span>

|   |   |
|---|---|
|<span data-ttu-id="dc7ea-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="dc7ea-102">Details</span></span>|<span data-ttu-id="dc7ea-103">In .NET Framework 4.7.2 e versioni precedenti, un parametro ByRef [SafeArray](https://docs.microsoft.com/en-us/windows/desktop/api/oaidl/ns-oaidl-safearray) su un evento COM non sarebbe in grado di eseguire di nuovo il marshalling al codice nativo.</span><span class="sxs-lookup"><span data-stu-id="dc7ea-103">In the .NET Framework 4.7.2 and earlier versions, a ByRef [SafeArray](https://docs.microsoft.com/en-us/windows/desktop/api/oaidl/ns-oaidl-safearray) parameter on a COM event would fail to marshal back to native code.</span></span>  <span data-ttu-id="dc7ea-104">Con questa modifica il marshalling di [SafeArray](https://docs.microsoft.com/en-us/windows/desktop/api/oaidl/ns-oaidl-safearray) viene ora eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="dc7ea-104">With this change the [SafeArray](https://docs.microsoft.com/en-us/windows/desktop/api/oaidl/ns-oaidl-safearray) is now marshalled successfully.</span></span><ul><li><span data-ttu-id="dc7ea-105">[ x ] Anomalo</span><span class="sxs-lookup"><span data-stu-id="dc7ea-105">[ x ] Quirked</span></span></li></ul>|
|<span data-ttu-id="dc7ea-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="dc7ea-106">Suggestion</span></span>|<span data-ttu-id="dc7ea-107">Se la corretta esecuzione del marshalling dei parametri ByRef SafeArray negli eventi COM interrompe l'esecuzione, è possibile disabilitare questo codice aggiungendo l'opzione di configurazione seguente alla configurazione dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="dc7ea-107">If properly marshalling ByRef SafeArray parameters on COM Events breaks execution, you can disable this code by adding the following configuration switch to your application config:</span></span><pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.Runtime.InteropServices.DoNotMarshalOutByrefSafeArrayOnInvoke&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="dc7ea-108">Ambito</span><span class="sxs-lookup"><span data-stu-id="dc7ea-108">Scope</span></span>|<span data-ttu-id="dc7ea-109">Secondario</span><span class="sxs-lookup"><span data-stu-id="dc7ea-109">Minor</span></span>|
|<span data-ttu-id="dc7ea-110">Versione</span><span class="sxs-lookup"><span data-stu-id="dc7ea-110">Version</span></span>|<span data-ttu-id="dc7ea-111">4.8</span><span class="sxs-lookup"><span data-stu-id="dc7ea-111">4.8</span></span>|
|<span data-ttu-id="dc7ea-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="dc7ea-112">Type</span></span>|<span data-ttu-id="dc7ea-113">Runtime</span><span class="sxs-lookup"><span data-stu-id="dc7ea-113">Runtime</span></span>|

