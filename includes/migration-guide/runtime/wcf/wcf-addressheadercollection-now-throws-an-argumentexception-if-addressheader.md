---
ms.openlocfilehash: d29be721b50d1c93723b325774a06e86f77dbebf
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621223"
---
### <a name="wcf-addressheadercollection-now-throws-an-argumentexception-if-an-addressheader-element-is-null"></a><span data-ttu-id="cd39f-101">L'oggetto AddressHeaderCollection di WCF ora genera un'eccezione ArgumentException se un elemento addressHeader è Null</span><span class="sxs-lookup"><span data-stu-id="cd39f-101">WCF AddressHeaderCollection now throws an ArgumentException if an addressHeader element is null</span></span>

#### <a name="details"></a><span data-ttu-id="cd39f-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="cd39f-102">Details</span></span>

<span data-ttu-id="cd39f-103">A partire da .NET Framework 4.7.1 il costruttore <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> genera un'eccezione <xref:System.ArgumentException> se uno degli elementi è <code>null</code>.</span><span class="sxs-lookup"><span data-stu-id="cd39f-103">Starting with the .NET Framework 4.7.1, the <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> constructor throws an <xref:System.ArgumentException> if one of the elements is <code>null</code>.</span></span> <span data-ttu-id="cd39f-104">In .NET Framework 4.7 e versioni precedenti non viene generata alcuna eccezione.</span><span class="sxs-lookup"><span data-stu-id="cd39f-104">In the .NET Framework 4.7 and earlier versions, no exception is thrown.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="cd39f-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="cd39f-105">Suggestion</span></span>

<span data-ttu-id="cd39f-106">Se si riscontrano problemi di compatibilità con questa modifica in .NET Framework 4.7.1 o versione successiva, è possibile rifiutarla esplicitamente aggiungendo la riga seguente alla sezione <code>&lt;runtime&gt;</code> del file app.config:</span><span class="sxs-lookup"><span data-stu-id="cd39f-106">If you encounter compatibility issues with this change on the .NET Framework 4.7.1 or a later version, you can opt-out of it by adding the following line to the <code>&lt;runtime&gt;</code> section of the app.config file::</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.DisableAddressHeaderCollectionValidation=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="cd39f-107">Nome</span><span class="sxs-lookup"><span data-stu-id="cd39f-107">Name</span></span>    | <span data-ttu-id="cd39f-108">Valore</span><span class="sxs-lookup"><span data-stu-id="cd39f-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="cd39f-109">Scope</span><span class="sxs-lookup"><span data-stu-id="cd39f-109">Scope</span></span>   |<span data-ttu-id="cd39f-110">Minorenne</span><span class="sxs-lookup"><span data-stu-id="cd39f-110">Minor</span></span>|
|<span data-ttu-id="cd39f-111">Version</span><span class="sxs-lookup"><span data-stu-id="cd39f-111">Version</span></span>|<span data-ttu-id="cd39f-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="cd39f-112">4.7.1</span></span>|
|<span data-ttu-id="cd39f-113">Type</span><span class="sxs-lookup"><span data-stu-id="cd39f-113">Type</span></span>|<span data-ttu-id="cd39f-114">Runtime</span><span class="sxs-lookup"><span data-stu-id="cd39f-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="cd39f-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="cd39f-115">Affected APIs</span></span>

-<xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})></li></ul>|
