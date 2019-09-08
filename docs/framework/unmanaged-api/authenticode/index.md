---
title: Authenticode (riferimenti alle API non gestite)
ms.date: 03/30/2017
ms.assetid: 7e8cc303-6e77-4116-aa8b-7ea297a3a467
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d2c0163d03a19a7bc00ae705fd633ef4f0880082
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70776563"
---
# <a name="authenticode-unmanaged-api-reference"></a>Authenticode (riferimenti alle API non gestite)
Supporta il modulo di creazione e verifica delle licenze Authenticode XrML.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Funzione _AxlGetIssuerPublicKeyHash](axlgetissuerpublickeyhash-function.md)  
 Recupera l'hash SHA-1 della chiave pubblica associata alla chiave privata usata per firmare il certificato specificato.  
  
 [Funzione _AxlPublicKeyBlobToPublicKeyToken](axlpublickeyblobtopublickeytoken-function.md)  
 Calcola il token di chiave pubblica con nome sicuro da un formato CSP PUBLICKEYBLOB.  
  
 [Funzione _AxlRSAKeyValueToPublicKeyToken](axlrsakeyvaluetopublickeytoken-function.md)  
 Converte un elemento Modulus e un elemento Exponent in un token di chiave pubblica con nome sicuro.  
  
 [Funzione CertFreeAuthenticodeSignerInfo](certfreeauthenticodesignerinfo-function.md)  
 Libera le risorse allocate per la struttura AXL_AUTHENTICODE_SIGNER_INFO.  
  
 [Funzione CertFreeAuthenticodeTimestamperInfo](certfreeauthenticodetimestamperinfo-function.md)  
 Libera le risorse allocate per la struttura AXL_AUTHENTICODE_TIMESTAMPER_INFO.  
  
 [Funzione CertTimestampAuthenticodeLicense](certtimestampauthenticodelicense-function.md)  
 Aggiunge un timestamp a una licenza Authenticode XrML creata da CertCreateAuthenticodeLicense.  
  
 [Funzione CertVerifyAuthenticodeLicense](certverifyauthenticodelicense-function.md)  
 Verifica la validità di una licenza Authenticode XrML.  
  
 [Struttura AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md)  
 Definisce le informazioni su chi ha apposto la firma Authenticode.  
  
 [Struttura AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md)  
 Definisce le informazioni su chi ha apposto il timestamp Authenticode.  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti alle API non gestite](../index.md)
