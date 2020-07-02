---
ms.openlocfilehash: beb869208e8d48d762d94b5989a558fa2f1aaf29
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622011"
---
### <a name="data-binding-improvement-for-keyedcollection"></a><span data-ttu-id="da738-101">Miglioramento del data binding per KeyedCollection</span><span class="sxs-lookup"><span data-stu-id="da738-101">Data Binding improvement for KeyedCollection</span></span>

#### <a name="details"></a><span data-ttu-id="da738-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="da738-102">Details</span></span>

<span data-ttu-id="da738-103">Correzione <xref:System.Windows.Data.Binding> dell'uso errato dell'indicizzatore IList quando l'oggetto di origine dichiara un indicizzatore personalizzato con la stessa firma, ad esempio KeyedCollection &lt; int, TItem &gt; .</span><span class="sxs-lookup"><span data-stu-id="da738-103">Fixed <xref:System.Windows.Data.Binding> incorrect use of IList indexer when the source object declares a custom indexer with the same signature (for example, KeyedCollection&lt;int,TItem&gt;).</span></span>

#### <a name="suggestion"></a><span data-ttu-id="da738-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="da738-104">Suggestion</span></span>

<span data-ttu-id="da738-105">Per fare in modo che un'applicazione destinata a una versione precedente tragga vantaggio da questa modifica, deve essere eseguita nel .NET Framework 4,8 o versione successiva e deve acconsentire esplicitamente alla modifica aggiungendo l' [opzione AppContext](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) seguente alla <code>&lt;runtime&gt;</code> sezione del file di configurazione dell'app e impostandolo su <code>false</code> :</span><span class="sxs-lookup"><span data-stu-id="da738-105">In order for an application that targets an older version to benefit from this change, it must run on the .NET Framework 4.8 or later, and it must opt in to the change by adding the following [AppContext switch](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) to the <code>&lt;runtime&gt;</code> section of the app config file and setting it to <code>false</code>:</span></span><pre><code class="lang-xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;&#13;&#10;&lt;configuration&gt;&#13;&#10;&lt;startup&gt;&#13;&#10;&lt;supportedRuntime version=&quot;v4.0&quot; sku=&quot;.NETFramework,Version=v4.7&quot;/&gt;&#13;&#10;&lt;/startup&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;!-- AppContextSwitchOverrides value attribute is in the form of &#39;key1=true/false;key2=true/false  --&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Data.Binding.IListIndexerHidesCustomIndexer=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="da738-106">Nome</span><span class="sxs-lookup"><span data-stu-id="da738-106">Name</span></span>    | <span data-ttu-id="da738-107">Valore</span><span class="sxs-lookup"><span data-stu-id="da738-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="da738-108">Scope</span><span class="sxs-lookup"><span data-stu-id="da738-108">Scope</span></span>   |<span data-ttu-id="da738-109">Principale</span><span class="sxs-lookup"><span data-stu-id="da738-109">Major</span></span>|
|<span data-ttu-id="da738-110">Version</span><span class="sxs-lookup"><span data-stu-id="da738-110">Version</span></span>|<span data-ttu-id="da738-111">4.8</span><span class="sxs-lookup"><span data-stu-id="da738-111">4.8</span></span>|
|<span data-ttu-id="da738-112">Type</span><span class="sxs-lookup"><span data-stu-id="da738-112">Type</span></span>|<span data-ttu-id="da738-113">Runtime</span><span class="sxs-lookup"><span data-stu-id="da738-113">Runtime</span></span>|
