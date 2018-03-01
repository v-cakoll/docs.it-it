---
title: Interfaccia ICLRStrongName
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRStrongName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName
helpviewer_keywords:
- ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 2fac66fd-6b3b-4dbd-8baf-86038bd85526
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9b8859cf507fb81f07b85b055380ba86aae471b5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongname-interface"></a>Interfaccia ICLRStrongName
Fornisce una base funzioni statiche globali per la firma degli assembly con nomi sicuri. Tutti `ICLRStrongName` restituiscono valori HRESULT COM standard.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetHashFromAssemblyFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)|Ottiene un hash del file di assembly specificato, usando l'algoritmo hash specificato.|  
|[Metodo GetHashFromAssemblyFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)|Ottiene un hash del file di assembly specificato come stringa Unicode, utilizzando l'algoritmo hash specificato.|  
|[Metodo GetHashFromBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md)|Ottiene un hash dell'assembly nell'indirizzo di memoria specificata, utilizzando l'algoritmo hash specificato.|  
|[Metodo GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)|Genera un hash per il contenuto del file specificato.|  
|[Metodo GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)|Genera un hash per il contenuto del file specificato da una stringa Unicode.|  
|[Metodo GetHashFromHandle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md)|Genera un hash per il contenuto del file con l'handle di file specificato, usando l'algoritmo hash specificato.|  
|[Metodo StrongNameCompareAssemblies](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md)|Determina se due assembly differiscono solo per le firme con nome sicuro.|  
|[Metodo StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)|Libera la memoria allocata con una precedente chiamata a un metodo con nome sicuro, ad esempio [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md), o [StrongNameSignatureGeneration ](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md).|  
|[Metodo StrongNameGetBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)|Riempie il buffer specificato con la rappresentazione binaria del file eseguibile all'indirizzo specificato.|  
|[Metodo StrongNameGetBlobFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)|Ottiene una rappresentazione binaria dell'immagine di assembly in corrispondenza dell'indirizzo di memoria specificata.|  
|[Metodo StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)|Ottiene la chiave pubblica da una coppia di chiavi pubblica/privata.|  
|[Metodo StrongNameHashSize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamehashsize-method.md)|Ottiene le dimensioni del buffer necessarie per generare un hash, utilizzando l'algoritmo hash specificato.|  
|[Metodo StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)|Elimina il contenitore di chiavi specificato.|  
|[Metodo StrongNameKeyGen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)|Crea una nuova coppia di chiavi pubblica/privata per l'utilizzo con nome sicuro.|  
|[Metodo StrongNameKeyGenEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)|Genera una nuova coppia di chiavi pubblica/privata con la dimensione della chiave specificata per l'utilizzo con nome sicuro.|  
|[Metodo StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)|Importa una coppia di chiavi pubblica/privata in un contenitore.|  
|[Metodo StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)|Genera una firma nome sicuro per l'assembly specificato.|  
|[Metodo StrongNameSignatureGenerationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)|Genera una firma nome sicuro per l'assembly specificato, in base ai flag specificati.|  
|[Metodo StrongNameSignatureSize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturesize-method.md)|Restituisce la dimensione della firma con nome sicuro.|  
|[Metodo StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)|Ottiene un valore che indica se il manifesto dell'assembly nel percorso specificato contiene una firma nome sicuro, che viene verificata in base ai flag specificati.|  
|[Metodo StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)|Ottiene un valore che indica se il manifesto dell'assembly nel percorso specificato contiene una firma con nome sicuro.|  
|[Metodo StrongNameSignatureVerificationFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md)|Verifica che un assembly che è già stato mappato alla memoria sia valido per la chiave pubblica associata.|  
|[Metodo StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md)|Crea un token con nome sicuro dal file di assembly specificato.|  
|[Metodo StrongNameTokenFromAssemblyEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)|Crea un token con nome sicuro dal file di assembly specificato e restituisce la chiave pubblica.|  
|[Metodo StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)|Ottiene un token che rappresenta una chiave pubblica.|  
  
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
