---
ms.openlocfilehash: 51208762cea2a5688c5d43e5d444d4e014e5f0b4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621319"
---
### <a name="x509certificate2tostringboolean-does-not-throw-now-when-net-cannot-handle-the-certificate"></a><span data-ttu-id="44a2f-101">X509Certificate2.ToString(Boolean) ora non genera un'eccezione quando .NET non è in grado di gestire il certificato</span><span class="sxs-lookup"><span data-stu-id="44a2f-101">X509Certificate2.ToString(Boolean) does not throw now when .NET cannot handle the certificate</span></span>

#### <a name="details"></a><span data-ttu-id="44a2f-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="44a2f-102">Details</span></span>

<span data-ttu-id="44a2f-103">In .NET Framework 4.5.2 e versioni precedenti, questo metodo generava un'eccezione se veniva passato il valore <code>true</code> per il parametro verbose e se erano presenti certificati installati non supportati da .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="44a2f-103">In .NET Framework 4.5.2 and earlier versions, this method would throw if <code>true</code> was passed for the verbose parameter and there were certificates installed that weren't supported by the .NET Framework.</span></span> <span data-ttu-id="44a2f-104">Ora il metodo ha esito positivo e restituisce una stringa valida che omette le parti inaccessibili del certificato.</span><span class="sxs-lookup"><span data-stu-id="44a2f-104">Now, the method will succeed and return a valid string that omits the inaccessible portions of the certificate.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="44a2f-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="44a2f-105">Suggestion</span></span>

<span data-ttu-id="44a2f-106">È consigliabile aggiornare qualsiasi codice che dipende da <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType> in modo da prevedere che la stringa restituita possa escludere alcuni dati del certificato, ad esempio la chiave pubblica, la chiave privata e le estensioni, in alcuni casi in cui l'API avrebbe precedentemente generato un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="44a2f-106">Any code depending on <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType> should be updated to expect that the returned string may exclude some certificate data (such as public key, private key, and extensions) in some cases in which the API would have previously thrown.</span></span>

| <span data-ttu-id="44a2f-107">Nome</span><span class="sxs-lookup"><span data-stu-id="44a2f-107">Name</span></span>    | <span data-ttu-id="44a2f-108">Valore</span><span class="sxs-lookup"><span data-stu-id="44a2f-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="44a2f-109">Scope</span><span class="sxs-lookup"><span data-stu-id="44a2f-109">Scope</span></span>   |<span data-ttu-id="44a2f-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="44a2f-110">Edge</span></span>|
|<span data-ttu-id="44a2f-111">Version</span><span class="sxs-lookup"><span data-stu-id="44a2f-111">Version</span></span>|<span data-ttu-id="44a2f-112">4.6</span><span class="sxs-lookup"><span data-stu-id="44a2f-112">4.6</span></span>|
|<span data-ttu-id="44a2f-113">Type</span><span class="sxs-lookup"><span data-stu-id="44a2f-113">Type</span></span>|<span data-ttu-id="44a2f-114">Runtime</span><span class="sxs-lookup"><span data-stu-id="44a2f-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="44a2f-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="44a2f-115">Affected APIs</span></span>

-<xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType></li></ul>|
