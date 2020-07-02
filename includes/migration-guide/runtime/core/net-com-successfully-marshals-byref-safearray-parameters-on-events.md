---
ms.openlocfilehash: 77e9d28d79a92cf1523e4ef5779d78394b00ae80
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621984"
---
### <a name="net-com-successfully-marshals-byref-safearray-parameters-on-events"></a><span data-ttu-id="5664a-101">.NET COM esegue correttamente il marshalling dei parametri ByRef SafeArray negli eventi</span><span class="sxs-lookup"><span data-stu-id="5664a-101">.NET COM successfully marshals ByRef SafeArray parameters on events</span></span>

#### <a name="details"></a><span data-ttu-id="5664a-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="5664a-102">Details</span></span>

<span data-ttu-id="5664a-103">In .NET Framework 4.7.2 e versioni precedenti, un parametro ByRef [SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray) su un evento COM non sarebbe in grado di eseguire di nuovo il marshalling al codice nativo.</span><span class="sxs-lookup"><span data-stu-id="5664a-103">In the .NET Framework 4.7.2 and earlier versions, a ByRef [SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray) parameter on a COM event would fail to marshal back to native code.</span></span>  <span data-ttu-id="5664a-104">Con questa modifica il marshalling di [SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray) viene ora eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="5664a-104">With this change the [SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray) is now marshalled successfully.</span></span><ul><li><span data-ttu-id="5664a-105">[ x ] Anomalo</span><span class="sxs-lookup"><span data-stu-id="5664a-105">[ x ] Quirked</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="5664a-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="5664a-106">Suggestion</span></span>

<span data-ttu-id="5664a-107">Se la corretta esecuzione del marshalling dei parametri ByRef SafeArray negli eventi COM interrompe l'esecuzione, è possibile disabilitare questo codice aggiungendo l'opzione di configurazione seguente alla configurazione dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="5664a-107">If properly marshalling ByRef SafeArray parameters on COM Events breaks execution, you can disable this code by adding the following configuration switch to your application config:</span></span><pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.Runtime.InteropServices.DoNotMarshalOutByrefSafeArrayOnInvoke&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="5664a-108">Nome</span><span class="sxs-lookup"><span data-stu-id="5664a-108">Name</span></span>    | <span data-ttu-id="5664a-109">Valore</span><span class="sxs-lookup"><span data-stu-id="5664a-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="5664a-110">Scope</span><span class="sxs-lookup"><span data-stu-id="5664a-110">Scope</span></span>   |<span data-ttu-id="5664a-111">Minorenne</span><span class="sxs-lookup"><span data-stu-id="5664a-111">Minor</span></span>|
|<span data-ttu-id="5664a-112">Version</span><span class="sxs-lookup"><span data-stu-id="5664a-112">Version</span></span>|<span data-ttu-id="5664a-113">4.8</span><span class="sxs-lookup"><span data-stu-id="5664a-113">4.8</span></span>|
|<span data-ttu-id="5664a-114">Type</span><span class="sxs-lookup"><span data-stu-id="5664a-114">Type</span></span>|<span data-ttu-id="5664a-115">Runtime</span><span class="sxs-lookup"><span data-stu-id="5664a-115">Runtime</span></span>|
