---
ms.openlocfilehash: d48519443aeee05617538cf2cc12bea49ad3e16d
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2019
ms.locfileid: "67858426"
---
### <a name="x509certificate2tostringboolean-does-not-throw-now-when-net-cannot-handle-the-certificate"></a><span data-ttu-id="3c945-101">X509Certificate2.ToString(Boolean) ora non genera un'eccezione quando .NET non è in grado di gestire il certificato</span><span class="sxs-lookup"><span data-stu-id="3c945-101">X509Certificate2.ToString(Boolean) does not throw now when .NET cannot handle the certificate</span></span>

|   |   |
|---|---|
|<span data-ttu-id="3c945-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="3c945-102">Details</span></span>|<span data-ttu-id="3c945-103">In .NET Framework 4.5.2 e versioni precedenti, questo metodo generava un'eccezione se veniva passato il valore <code>true</code> per il parametro verbose e se erano presenti certificati installati non supportati da .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3c945-103">In .NET Framework 4.5.2 and earlier versions, this method would throw if <code>true</code> was passed for the verbose parameter and there were certificates installed that weren't supported by the .NET Framework.</span></span> <span data-ttu-id="3c945-104">Ora il metodo ha esito positivo e restituisce una stringa valida che omette le parti inaccessibili del certificato.</span><span class="sxs-lookup"><span data-stu-id="3c945-104">Now, the method will succeed and return a valid string that omits the inaccessible portions of the certificate.</span></span>|
|<span data-ttu-id="3c945-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="3c945-105">Suggestion</span></span>|<span data-ttu-id="3c945-106">È consigliabile aggiornare qualsiasi codice che dipende da <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType> in modo da prevedere che la stringa restituita possa escludere alcuni dati del certificato, ad esempio la chiave pubblica, la chiave privata e le estensioni, in alcuni casi in cui l'API avrebbe precedentemente generato un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="3c945-106">Any code depending on <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType> should be updated to expect that the returned string may exclude some certificate data (such as public key, private key, and extensions) in some cases in which the API would have previously thrown.</span></span>|
|<span data-ttu-id="3c945-107">Ambito</span><span class="sxs-lookup"><span data-stu-id="3c945-107">Scope</span></span>|<span data-ttu-id="3c945-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="3c945-108">Edge</span></span>|
|<span data-ttu-id="3c945-109">Versione</span><span class="sxs-lookup"><span data-stu-id="3c945-109">Version</span></span>|<span data-ttu-id="3c945-110">4.6</span><span class="sxs-lookup"><span data-stu-id="3c945-110">4.6</span></span>|
|<span data-ttu-id="3c945-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="3c945-111">Type</span></span>|<span data-ttu-id="3c945-112">Runtime</span><span class="sxs-lookup"><span data-stu-id="3c945-112">Runtime</span></span>|
|<span data-ttu-id="3c945-113">API interessate</span><span class="sxs-lookup"><span data-stu-id="3c945-113">Affected APIs</span></span>|<ul><li><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType></li></ul>|

