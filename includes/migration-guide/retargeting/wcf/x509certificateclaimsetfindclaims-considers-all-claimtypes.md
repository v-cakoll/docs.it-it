---
ms.openlocfilehash: abef47c64a7cfd99c5b50bf2100401a2d5fcc5c3
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614496"
---
### <a name="x509certificateclaimsetfindclaims-considers-all-claimtypes"></a><span data-ttu-id="d2cbf-101">X509CertificateClaimSet.FindClaims considera tutti gli argomenti claimType</span><span class="sxs-lookup"><span data-stu-id="d2cbf-101">X509CertificateClaimSet.FindClaims Considers All claimTypes</span></span>

#### <a name="details"></a><span data-ttu-id="d2cbf-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="d2cbf-102">Details</span></span>

<span data-ttu-id="d2cbf-103">Nelle app destinate a .NET Framework 4.6.1, se un set di attestazioni X509 viene inizializzato da un certificato con più voci DNS nel proprio campo SAN, il metodo <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=fullName> cerca di stabilire una corrispondenza con l'argomento claimType con tutte le voci DNS. Per le app destinate a versioni precedenti di .NET Framework, il metodo <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=fullName> tenta di stabilire una corrispondenza con l'argomento claimType solo con l'ultima voce DNS.</span><span class="sxs-lookup"><span data-stu-id="d2cbf-103">In apps that target the .NET Framework 4.6.1, if an X509 claim set is initialized from a certificate that has multiple DNS entries in its SAN field, the <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=fullName> method attempts to match the claimType argument with all the DNS entries.For apps that target previous versions of the .NET Framework, the <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=fullName> method attempts to match the claimType argument only with the last DNS entry.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d2cbf-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="d2cbf-104">Suggestion</span></span>

<span data-ttu-id="d2cbf-105">Questa modifica riguarda solo le applicazioni destinate a .NET Framework 4.6.1.</span><span class="sxs-lookup"><span data-stu-id="d2cbf-105">This change only affects applications targeting the .NET Framework 4.6.1.</span></span> <span data-ttu-id="d2cbf-106">Questa modifica può essere disabilitata (o abilitata se la destinazione è una versione precedente la 4.6.1) con l'opzione di compatibilità [DisableMultipleDNSEntries](~/docs/framework/migration-guide/mitigation-x509certificateclaimset-findclaims-method.md#mitigation).</span><span class="sxs-lookup"><span data-stu-id="d2cbf-106">This change may be disabled (or enabled if targeting pre-4.6.1) with the [DisableMultipleDNSEntries](~/docs/framework/migration-guide/mitigation-x509certificateclaimset-findclaims-method.md#mitigation) compatibility switch.</span></span>

| <span data-ttu-id="d2cbf-107">Nome</span><span class="sxs-lookup"><span data-stu-id="d2cbf-107">Name</span></span>    | <span data-ttu-id="d2cbf-108">Valore</span><span class="sxs-lookup"><span data-stu-id="d2cbf-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d2cbf-109">Scope</span><span class="sxs-lookup"><span data-stu-id="d2cbf-109">Scope</span></span>   | <span data-ttu-id="d2cbf-110">Minorenne</span><span class="sxs-lookup"><span data-stu-id="d2cbf-110">Minor</span></span>       |
| <span data-ttu-id="d2cbf-111">Version</span><span class="sxs-lookup"><span data-stu-id="d2cbf-111">Version</span></span> | <span data-ttu-id="d2cbf-112">4.6.1</span><span class="sxs-lookup"><span data-stu-id="d2cbf-112">4.6.1</span></span>       |
| <span data-ttu-id="d2cbf-113">Type</span><span class="sxs-lookup"><span data-stu-id="d2cbf-113">Type</span></span>    | <span data-ttu-id="d2cbf-114">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="d2cbf-114">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="d2cbf-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="d2cbf-115">Affected APIs</span></span>

- <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=nameWithType>
