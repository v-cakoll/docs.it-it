---
title: Interfaccia ICLRStrongName
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName
helpviewer_keywords: ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 2fac66fd-6b3b-4dbd-8baf-86038bd85526
topic_type: apiref
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f8e8a3c9ff4ec3d6b124f95edd31e277db3eb872
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrstrongname-interface"></a>Interfaccia ICLRStrongName
Fornisce una base funzioni statiche globali per la firma degli assembly con nomi sicuri. Tutti `ICLRStrongName` restituiscono valori HRESULT COM standard.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[GetHashFromAssemblyFile (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)|Ottiene un hash del file di assembly specificato, usando l'algoritmo hash specificato.|  
|[GetHashFromAssemblyFileW (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)|Ottiene un hash del file di assembly specificato come stringa Unicode, utilizzando l'algoritmo hash specificato.|  
|[GetHashFromBlob (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md)|Ottiene un hash dell'assembly nell'indirizzo di memoria specificata, utilizzando l'algoritmo hash specificato.|  
|[GetHashFromFile (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)|Genera un hash per il contenuto del file specificato.|  
|[GetHashFromFileW (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)|Genera un hash per il contenuto del file specificato da una stringa Unicode.|  
|[GetHashFromHandle (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md)|Genera un hash per il contenuto del file con l'handle di file specificato, usando l'algoritmo hash specificato.|  
|[StrongNameCompareAssemblies (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md)|Determina se due assembly differiscono solo per le firme con nome sicuro.|  
|[StrongNameFreeBuffer (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)|Libera la memoria allocata con una precedente chiamata a un metodo con nome sicuro, ad esempio [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md), o [StrongNameSignatureGeneration ](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md).|  
|[StrongNameGetBlob (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)|Riempie il buffer specificato con la rappresentazione binaria del file eseguibile all'indirizzo specificato.|  
|[StrongNameGetBlobFromImage (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)|Ottiene una rappresentazione binaria dell'immagine di assembly in corrispondenza dell'indirizzo di memoria specificata.|  
|[StrongNameGetPublicKey (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)|Ottiene la chiave pubblica da una coppia di chiavi pubblica/privata.|  
|[StrongNameHashSize (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamehashsize-method.md)|Ottiene le dimensioni del buffer necessarie per generare un hash, utilizzando l'algoritmo hash specificato.|  
|[StrongNameKeyDelete (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)|Elimina il contenitore di chiavi specificato.|  
|[StrongNameKeyGen (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)|Crea una nuova coppia di chiavi pubblica/privata per l'utilizzo con nome sicuro.|  
|[StrongNameKeyGenEx (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)|Genera una nuova coppia di chiavi pubblica/privata con la dimensione della chiave specificata per l'utilizzo con nome sicuro.|  
|[StrongNameKeyInstall (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)|Importa una coppia di chiavi pubblica/privata in un contenitore.|  
|[StrongNameSignatureGeneration (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)|Genera una firma nome sicuro per l'assembly specificato.|  
|[StrongNameSignatureGenerationEx (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)|Genera una firma nome sicuro per l'assembly specificato, in base ai flag specificati.|  
|[StrongNameSignatureSize (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturesize-method.md)|Restituisce la dimensione della firma con nome sicuro.|  
|[StrongNameSignatureVerification (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)|Ottiene un valore che indica se il manifesto dell'assembly nel percorso specificato contiene una firma nome sicuro, che viene verificata in base ai flag specificati.|  
|[StrongNameSignatureVerificationEx (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)|Ottiene un valore che indica se il manifesto dell'assembly nel percorso specificato contiene una firma con nome sicuro.|  
|[StrongNameSignatureVerificationFromImage (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md)|Verifica che un assembly che è già stato mappato alla memoria sia valido per la chiave pubblica associata.|  
|[StrongNameTokenFromAssembly (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md)|Crea un token con nome sicuro dal file di assembly specificato.|  
|[StrongNameTokenFromAssemblyEx (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)|Crea un token con nome sicuro dal file di assembly specificato e restituisce la chiave pubblica.|  
|[StrongNameTokenFromPublicKey (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)|Ottiene un token che rappresenta una chiave pubblica.|  
  
## <a name="remarks"></a>Note  
 È possibile ottenere un'istanza di `ICLRStrongName` chiamando il [ICLRRuntimeInfo:: GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) metodo usando `CLSID_CLRStrongName` e `IID_ICLRStrongName` come parametri.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
