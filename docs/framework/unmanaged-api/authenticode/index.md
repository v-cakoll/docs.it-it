---
title: Authenticode (riferimenti alle API non gestite)
ms.date: 03/30/2017
ms.assetid: 7e8cc303-6e77-4116-aa8b-7ea297a3a467
author: rpetrusha
ms.author: ronpet
---
# <a name="authenticode-unmanaged-api-reference"></a><span data-ttu-id="b5769-102">Authenticode (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="b5769-102">Authenticode (Unmanaged API Reference)</span></span>
<span data-ttu-id="b5769-103">Supporta il modulo di creazione e verifica delle licenze Authenticode XrML.</span><span class="sxs-lookup"><span data-stu-id="b5769-103">Supports the Authenticode XrML license creation and verification module.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b5769-104">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="b5769-104">In This Section</span></span>  
 [<span data-ttu-id="b5769-105">Funzione _AxlGetIssuerPublicKeyHash</span><span class="sxs-lookup"><span data-stu-id="b5769-105">_AxlGetIssuerPublicKeyHash Function</span></span>](../../../../docs/framework/unmanaged-api/authenticode/axlgetissuerpublickeyhash-function.md)  
 <span data-ttu-id="b5769-106">Recupera l'hash SHA-1 della chiave pubblica associata alla chiave privata usata per firmare il certificato specificato.</span><span class="sxs-lookup"><span data-stu-id="b5769-106">Retrieves the SHA-1 hash of the public key associated with the private key that is used to sign the specified certificate.</span></span>  
  
 [<span data-ttu-id="b5769-107">Funzione _AxlPublicKeyBlobToPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="b5769-107">_AxlPublicKeyBlobToPublicKeyToken Function</span></span>](../../../../docs/framework/unmanaged-api/authenticode/axlpublickeyblobtopublickeytoken-function.md)  
 <span data-ttu-id="b5769-108">Calcola il token di chiave pubblica con nome sicuro da un formato CSP PUBLICKEYBLOB.</span><span class="sxs-lookup"><span data-stu-id="b5769-108">Computes the strong name public key token from a CSP PUBLICKEYBLOB format.</span></span>  
  
 [<span data-ttu-id="b5769-109">Funzione _AxlRSAKeyValueToPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="b5769-109">_AxlRSAKeyValueToPublicKeyToken Function</span></span>](../../../../docs/framework/unmanaged-api/authenticode/axlrsakeyvaluetopublickeytoken-function.md)  
 <span data-ttu-id="b5769-110">Converte un elemento Modulus e un elemento Exponent in un token di chiave pubblica con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="b5769-110">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
 [<span data-ttu-id="b5769-111">Funzione CertFreeAuthenticodeSignerInfo</span><span class="sxs-lookup"><span data-stu-id="b5769-111">CertFreeAuthenticodeSignerInfo Function</span></span>](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodesignerinfo-function.md)  
 <span data-ttu-id="b5769-112">Libera le risorse allocate per la struttura AXL_AUTHENTICODE_SIGNER_INFO.</span><span class="sxs-lookup"><span data-stu-id="b5769-112">Frees resources allocated for the AXL_AUTHENTICODE_SIGNER_INFO structure.</span></span>  
  
 [<span data-ttu-id="b5769-113">Funzione CertFreeAuthenticodeTimestamperInfo</span><span class="sxs-lookup"><span data-stu-id="b5769-113">CertFreeAuthenticodeTimestamperInfo Function</span></span>](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodetimestamperinfo-function.md)  
 <span data-ttu-id="b5769-114">Libera le risorse allocate per la struttura AXL_AUTHENTICODE_TIMESTAMPER_INFO.</span><span class="sxs-lookup"><span data-stu-id="b5769-114">Frees resources allocated for the AXL_AUTHENTICODE_TIMESTAMPER_INFO structure.</span></span>  
  
 [<span data-ttu-id="b5769-115">Funzione CertTimestampAuthenticodeLicense</span><span class="sxs-lookup"><span data-stu-id="b5769-115">CertTimestampAuthenticodeLicense Function</span></span>](../../../../docs/framework/unmanaged-api/authenticode/certtimestampauthenticodelicense-function.md)  
 <span data-ttu-id="b5769-116">Aggiunge un timestamp a una licenza Authenticode XrML creata da CertCreateAuthenticodeLicense.</span><span class="sxs-lookup"><span data-stu-id="b5769-116">Time stamps an Authenticode XrML license created by CertCreateAuthenticodeLicense.</span></span>  
  
 [<span data-ttu-id="b5769-117">Funzione CertVerifyAuthenticodeLicense</span><span class="sxs-lookup"><span data-stu-id="b5769-117">CertVerifyAuthenticodeLicense Function</span></span>](../../../../docs/framework/unmanaged-api/authenticode/certverifyauthenticodelicense-function.md)  
 <span data-ttu-id="b5769-118">Verifica la validità di una licenza Authenticode XrML.</span><span class="sxs-lookup"><span data-stu-id="b5769-118">Verifies the validity of an Authenticode XrML license.</span></span>  
  
 [<span data-ttu-id="b5769-119">Struttura AXL_AUTHENTICODE_SIGNER_INFO</span><span class="sxs-lookup"><span data-stu-id="b5769-119">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md)  
 <span data-ttu-id="b5769-120">Definisce le informazioni su chi ha apposto la firma Authenticode.</span><span class="sxs-lookup"><span data-stu-id="b5769-120">Defines the Authenticode signer information.</span></span>  
  
 [<span data-ttu-id="b5769-121">Struttura AXL_AUTHENTICODE_TIMESTAMPER_INFO</span><span class="sxs-lookup"><span data-stu-id="b5769-121">AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure</span></span>](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md)  
 <span data-ttu-id="b5769-122">Definisce le informazioni su chi ha apposto il timestamp Authenticode.</span><span class="sxs-lookup"><span data-stu-id="b5769-122">Defines the Authenticode time stamper information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5769-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5769-123">See also</span></span>
- [<span data-ttu-id="b5769-124">Riferimenti alle API non gestite</span><span class="sxs-lookup"><span data-stu-id="b5769-124">Unmanaged API Reference</span></span>](../../../../docs/framework/unmanaged-api/index.md)
