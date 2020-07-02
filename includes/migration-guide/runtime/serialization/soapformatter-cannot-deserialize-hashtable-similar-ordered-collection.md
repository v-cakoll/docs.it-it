---
ms.openlocfilehash: 5a3370e71488e4f9d8d933b504d1d771c78e0385
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620381"
---
### <a name="soapformatter-cannot-deserialize-hashtable-and-similar-ordered-collection-objects"></a><span data-ttu-id="83bb1-101">SoapFormatter non è in grado di deserializzare Hashtable e simili oggetti di raccolta ordinati</span><span class="sxs-lookup"><span data-stu-id="83bb1-101">SoapFormatter cannot deserialize Hashtable and similar ordered collection objects</span></span>

#### <a name="details"></a><span data-ttu-id="83bb1-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="83bb1-102">Details</span></span>

<span data-ttu-id="83bb1-103"><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=fullName> non garantisce che gli oggetti serializzati nell'ambito di una versione di .NET Framework possano essere deserializzati correttamente in una versione diversa.</span><span class="sxs-lookup"><span data-stu-id="83bb1-103">The <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=fullName> does not guarantee that objects serialized under one .NET Framework version will successfully deserialize under a different version.</span></span> <span data-ttu-id="83bb1-104">In particolare, in alcune raccolte ordinate, come <xref:System.Collections.Hashtable?displayProperty=fullName>, sono stati aggiunti membri tra le versioni 4.0 e 4.5 e ne consegue che questi oggetti non possono essere deserializzati con .NET Framework 4.0 se vengono serializzati con .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="83bb1-104">Specifically, some ordered collections (like <xref:System.Collections.Hashtable?displayProperty=fullName>) added members between 4.0 and 4.5 such that objects of these types cannot deserialize with .NET Framework 4.0 if they were serialized with .NET Framework 4.5.</span></span> <span data-ttu-id="83bb1-105">Si noti che, se i dati serializzati vengono sia serializzati che deserializzati con la stessa versione di .NET Framework, non si verificherà alcun problema.</span><span class="sxs-lookup"><span data-stu-id="83bb1-105">Note that if the serialized data is both serialized and deserialized with the same .NET Framework version, no issue will occur.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="83bb1-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="83bb1-106">Suggestion</span></span>

<span data-ttu-id="83bb1-107">La serializzazione di <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=fullName> deve essere sostituita con la serializzazione di <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> o di <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> per essere adattabile alle modifiche di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="83bb1-107"><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=fullName> serialization should be replaced with <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> serialization or <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> to be resilient to .NET Framework changes.</span></span>

| <span data-ttu-id="83bb1-108">Nome</span><span class="sxs-lookup"><span data-stu-id="83bb1-108">Name</span></span>    | <span data-ttu-id="83bb1-109">Valore</span><span class="sxs-lookup"><span data-stu-id="83bb1-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="83bb1-110">Scope</span><span class="sxs-lookup"><span data-stu-id="83bb1-110">Scope</span></span>   |<span data-ttu-id="83bb1-111">Minorenne</span><span class="sxs-lookup"><span data-stu-id="83bb1-111">Minor</span></span>|
|<span data-ttu-id="83bb1-112">Version</span><span class="sxs-lookup"><span data-stu-id="83bb1-112">Version</span></span>|<span data-ttu-id="83bb1-113">4.5</span><span class="sxs-lookup"><span data-stu-id="83bb1-113">4.5</span></span>|
|<span data-ttu-id="83bb1-114">Type</span><span class="sxs-lookup"><span data-stu-id="83bb1-114">Type</span></span>|<span data-ttu-id="83bb1-115">Runtime</span><span class="sxs-lookup"><span data-stu-id="83bb1-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="83bb1-116">API interessate</span><span class="sxs-lookup"><span data-stu-id="83bb1-116">Affected APIs</span></span>

-<xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object,System.Runtime.Remoting.Messaging.Header[])?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)?displayProperty=nameWithType></li></ul>|
