---
title: Authenticode (riferimenti alle API non gestite)
ms.date: 03/30/2017
ms.assetid: 7e8cc303-6e77-4116-aa8b-7ea297a3a467
ms.openlocfilehash: 1b8b2222950c75f7f9d2ec2704f722087645cd7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73132461"
---
# <a name="authenticode-unmanaged-api-reference"></a>Authenticode (riferimenti alle API non gestite)
Supporta il modulo di creazione e verifica delle licenze Authenticode XrML.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
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

- [Informazioni di riferimento sulle API non gestiteUnmanaged API Reference](../index.md)
