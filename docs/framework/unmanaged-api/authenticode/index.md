---
title: Authenticode (riferimenti alle API non gestite)
ms.date: 03/30/2017
ms.assetid: 7e8cc303-6e77-4116-aa8b-7ea297a3a467
ms.openlocfilehash: 1b8b2222950c75f7f9d2ec2704f722087645cd7e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132461"
---
# <a name="authenticode-unmanaged-api-reference"></a><span data-ttu-id="32552-102">Authenticode (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="32552-102">Authenticode (Unmanaged API Reference)</span></span>
<span data-ttu-id="32552-103">Supporta il modulo di creazione e verifica delle licenze Authenticode XrML.</span><span class="sxs-lookup"><span data-stu-id="32552-103">Supports the Authenticode XrML license creation and verification module.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="32552-104">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="32552-104">In This Section</span></span>  
 [<span data-ttu-id="32552-105">Funzione _AxlGetIssuerPublicKeyHash</span><span class="sxs-lookup"><span data-stu-id="32552-105">_AxlGetIssuerPublicKeyHash Function</span></span>](axlgetissuerpublickeyhash-function.md)  
 <span data-ttu-id="32552-106">Recupera l'hash SHA-1 della chiave pubblica associata alla chiave privata usata per firmare il certificato specificato.</span><span class="sxs-lookup"><span data-stu-id="32552-106">Retrieves the SHA-1 hash of the public key associated with the private key that is used to sign the specified certificate.</span></span>  
  
 [<span data-ttu-id="32552-107">Funzione _AxlPublicKeyBlobToPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="32552-107">_AxlPublicKeyBlobToPublicKeyToken Function</span></span>](axlpublickeyblobtopublickeytoken-function.md)  
 <span data-ttu-id="32552-108">Calcola il token di chiave pubblica con nome sicuro da un formato CSP PUBLICKEYBLOB.</span><span class="sxs-lookup"><span data-stu-id="32552-108">Computes the strong name public key token from a CSP PUBLICKEYBLOB format.</span></span>  
  
 [<span data-ttu-id="32552-109">Funzione _AxlRSAKeyValueToPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="32552-109">_AxlRSAKeyValueToPublicKeyToken Function</span></span>](axlrsakeyvaluetopublickeytoken-function.md)  
 <span data-ttu-id="32552-110">Converte un elemento Modulus e un elemento Exponent in un token di chiave pubblica con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="32552-110">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
 [<span data-ttu-id="32552-111">Funzione CertFreeAuthenticodeSignerInfo</span><span class="sxs-lookup"><span data-stu-id="32552-111">CertFreeAuthenticodeSignerInfo Function</span></span>](certfreeauthenticodesignerinfo-function.md)  
 <span data-ttu-id="32552-112">Libera le risorse allocate per la struttura AXL_AUTHENTICODE_SIGNER_INFO.</span><span class="sxs-lookup"><span data-stu-id="32552-112">Frees resources allocated for the AXL_AUTHENTICODE_SIGNER_INFO structure.</span></span>  
  
 [<span data-ttu-id="32552-113">Funzione CertFreeAuthenticodeTimestamperInfo</span><span class="sxs-lookup"><span data-stu-id="32552-113">CertFreeAuthenticodeTimestamperInfo Function</span></span>](certfreeauthenticodetimestamperinfo-function.md)  
 <span data-ttu-id="32552-114">Libera le risorse allocate per la struttura AXL_AUTHENTICODE_TIMESTAMPER_INFO.</span><span class="sxs-lookup"><span data-stu-id="32552-114">Frees resources allocated for the AXL_AUTHENTICODE_TIMESTAMPER_INFO structure.</span></span>  
  
 [<span data-ttu-id="32552-115">Funzione CertTimestampAuthenticodeLicense</span><span class="sxs-lookup"><span data-stu-id="32552-115">CertTimestampAuthenticodeLicense Function</span></span>](certtimestampauthenticodelicense-function.md)  
 <span data-ttu-id="32552-116">Aggiunge un timestamp a una licenza Authenticode XrML creata da CertCreateAuthenticodeLicense.</span><span class="sxs-lookup"><span data-stu-id="32552-116">Time stamps an Authenticode XrML license created by CertCreateAuthenticodeLicense.</span></span>  
  
 [<span data-ttu-id="32552-117">Funzione CertVerifyAuthenticodeLicense</span><span class="sxs-lookup"><span data-stu-id="32552-117">CertVerifyAuthenticodeLicense Function</span></span>](certverifyauthenticodelicense-function.md)  
 <span data-ttu-id="32552-118">Verifica la validità di una licenza Authenticode XrML.</span><span class="sxs-lookup"><span data-stu-id="32552-118">Verifies the validity of an Authenticode XrML license.</span></span>  
  
 [<span data-ttu-id="32552-119">Struttura AXL_AUTHENTICODE_SIGNER_INFO</span><span class="sxs-lookup"><span data-stu-id="32552-119">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>](axl-authenticode-signer-info-structure.md)  
 <span data-ttu-id="32552-120">Definisce le informazioni su chi ha apposto la firma Authenticode.</span><span class="sxs-lookup"><span data-stu-id="32552-120">Defines the Authenticode signer information.</span></span>  
  
 [<span data-ttu-id="32552-121">Struttura AXL_AUTHENTICODE_TIMESTAMPER_INFO</span><span class="sxs-lookup"><span data-stu-id="32552-121">AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure</span></span>](axl-authenticode-timestamper-info-structure.md)  
 <span data-ttu-id="32552-122">Definisce le informazioni su chi ha apposto il timestamp Authenticode.</span><span class="sxs-lookup"><span data-stu-id="32552-122">Defines the Authenticode time stamper information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32552-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="32552-123">See also</span></span>

- [<span data-ttu-id="32552-124">Riferimenti alle API non gestite</span><span class="sxs-lookup"><span data-stu-id="32552-124">Unmanaged API Reference</span></span>](../index.md)
