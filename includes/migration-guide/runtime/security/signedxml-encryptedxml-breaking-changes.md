---
ms.openlocfilehash: 8cc4f2ba2923774ef4e4e6861a89a7797ca988e1
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621199"
---
### <a name="signedxml-and-encryptedxml-breaking-changes"></a><span data-ttu-id="360ae-101">Modifiche di SignedXml ed EncryptedXml che causano interruzioni</span><span class="sxs-lookup"><span data-stu-id="360ae-101">SignedXml and EncryptedXml Breaking Changes</span></span>

#### <a name="details"></a><span data-ttu-id="360ae-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="360ae-102">Details</span></span>

<span data-ttu-id="360ae-103">In .NET Framework 4.6.2 , le correzioni per la sicurezza in <xref:System.Security.Cryptography.Xml.SignedXml?displayProperty=fullName> e <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=fullName> causano comportamenti diversi in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="360ae-103">In .NET Framework 4.6.2, Security fixes in <xref:System.Security.Cryptography.Xml.SignedXml?displayProperty=fullName> and <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=fullName> lead to different run-time behaviors.</span></span> <span data-ttu-id="360ae-104">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="360ae-104">For example,</span></span><ul><li><span data-ttu-id="360ae-105">se per un documento esistono più elementi con lo stesso attributo <code>id</code> e una firma fa riferimento a uno di tali elementi come radice della firma, il documento ora verrà considerato non valido.</span><span class="sxs-lookup"><span data-stu-id="360ae-105">If a document has multiple elements with the same <code>id</code> attribute and a signature targets one of those elements as the root of the signature, the document will now be considered invalid.</span></span></li><li><span data-ttu-id="360ae-106">I documenti che usano algoritmi di trasformazione XPath non canonici nei riferimenti ora vengono considerati non validi.</span><span class="sxs-lookup"><span data-stu-id="360ae-106">Documents using non-canonical XPath transform algorithms in references are now considered invalid.</span></span></li><li><span data-ttu-id="360ae-107">I documenti che usano algoritmi di trasformazione XSLT non canonici nei riferimenti ora vengono considerati non validi.</span><span class="sxs-lookup"><span data-stu-id="360ae-107">Documents using non-canonical XSLT transform algorithms in references are now consider invalid.</span></span></li><li><span data-ttu-id="360ae-108">Eventuali programmi che usano firme di risorse esterne scollegate non saranno in grado di eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="360ae-108">Any program making use of external resource detached signatures will be unable to do so.</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="360ae-109">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="360ae-109">Suggestion</span></span>

<span data-ttu-id="360ae-110">Gli sviluppatori devono esaminare l'uso di <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform> e <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform> nonché dei tipi derivati da <xref:System.Security.Cryptography.Xml.Transform>, poiché un destinatario del documento potrebbe non essere in grado di elaborarlo.</span><span class="sxs-lookup"><span data-stu-id="360ae-110">Developers might want to review the usage of <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform> and <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform>, as well as types derived from <xref:System.Security.Cryptography.Xml.Transform> since a document receiver may not be able to process it.</span></span>

| <span data-ttu-id="360ae-111">Nome</span><span class="sxs-lookup"><span data-stu-id="360ae-111">Name</span></span>    | <span data-ttu-id="360ae-112">Valore</span><span class="sxs-lookup"><span data-stu-id="360ae-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="360ae-113">Scope</span><span class="sxs-lookup"><span data-stu-id="360ae-113">Scope</span></span>   |<span data-ttu-id="360ae-114">Minorenne</span><span class="sxs-lookup"><span data-stu-id="360ae-114">Minor</span></span>|
|<span data-ttu-id="360ae-115">Version</span><span class="sxs-lookup"><span data-stu-id="360ae-115">Version</span></span>|<span data-ttu-id="360ae-116">4.6.2</span><span class="sxs-lookup"><span data-stu-id="360ae-116">4.6.2</span></span>|
|<span data-ttu-id="360ae-117">Type</span><span class="sxs-lookup"><span data-stu-id="360ae-117">Type</span></span>|<span data-ttu-id="360ae-118">Runtime</span><span class="sxs-lookup"><span data-stu-id="360ae-118">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="360ae-119">API interessate</span><span class="sxs-lookup"><span data-stu-id="360ae-119">Affected APIs</span></span>

-<xref:System.Security.Cryptography.Xml.Transform?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.Xml.XmlDsigXPathTransform?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform?displayProperty=nameWithType></li></ul>|
