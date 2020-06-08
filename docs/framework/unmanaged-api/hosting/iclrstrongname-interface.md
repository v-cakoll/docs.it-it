---
title: Interfaccia ICLRStrongName
ms.date: 03/30/2017
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
ms.openlocfilehash: 0b6efcbe4458977e8e938afabd7ae59171bc065a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501651"
---
# <a name="iclrstrongname-interface"></a>Interfaccia ICLRStrongName
Fornisce funzioni statiche globali di base per la firma di assembly con nomi sicuri. Tutti i `ICLRStrongName` metodi restituiscono HRESULT COM standard.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetHashFromAssemblyFile](iclrstrongname-gethashfromassemblyfile-method.md)|Ottiene un hash del file di assembly specificato usando l'algoritmo hash specificato.|  
|[Metodo GetHashFromAssemblyFileW](iclrstrongname-gethashfromassemblyfilew-method.md)|Ottiene un hash del file di assembly specificato come stringa Unicode usando l'algoritmo hash specificato.|  
|[Metodo GetHashFromBlob](iclrstrongname-gethashfromblob-method.md)|Ottiene un hash dell'assembly all'indirizzo di memoria specificato usando l'algoritmo hash specificato.|  
|[Metodo GetHashFromFile](iclrstrongname-gethashfromfile-method.md)|Genera un hash basato sul contenuto del file specificato.|  
|[Metodo GetHashFromFileW](iclrstrongname-gethashfromfilew-method.md)|Genera un hash basato sul contenuto del file specificato da una stringa Unicode.|  
|[Metodo GetHashFromHandle](iclrstrongname-gethashfromhandle-method.md)|Genera un hash basato sul contenuto del file con l'handle di file specificato, usando l'algoritmo hash specificato.|  
|[Metodo StrongNameCompareAssemblies](iclrstrongname-strongnamecompareassemblies-method.md)|Determina se due assembly differiscono solo per le firme con nome sicuro.|  
|[Metodo StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md)|Libera la memoria allocata con una precedente chiamata a un metodo con nome sicuro, ad esempio [StrongNameGetPublicKey](iclrstrongname-strongnamegetpublickey-method.md), [StrongNameTokenFromPublicKey](iclrstrongname-strongnametokenfrompublickey-method.md)o [StrongNameSignatureGeneration](iclrstrongname-strongnamesignaturegeneration-method.md).|  
|[Metodo StrongNameGetBlob](iclrstrongname-strongnamegetblob-method.md)|Completa il buffer specificato con la rappresentazione binaria del file eseguibile presente all'indirizzo specificato.|  
|[Metodo StrongNameGetBlobFromImage](iclrstrongname-strongnamegetblobfromimage-method.md)|Ottiene una rappresentazione binaria dell'immagine dell'assembly in corrispondenza dell'indirizzo di memoria specificato.|  
|[Metodo StrongNameGetPublicKey](iclrstrongname-strongnamegetpublickey-method.md)|Ottiene la chiave pubblica da una coppia di chiavi pubblica/privata.|  
|[Metodo StrongNameHashSize](iclrstrongname-strongnamehashsize-method.md)|Ottiene le dimensioni del buffer necessarie per un hash usando l'algoritmo hash specificato.|  
|[Metodo StrongNameKeyDelete](iclrstrongname-strongnamekeydelete-method.md)|Elimina il contenitore di chiavi specificato.|  
|[Metodo StrongNameKeyGen](iclrstrongname-strongnamekeygen-method.md)|Crea una nuova coppia di chiavi pubblica/privata per l'uso come nome sicuro.|  
|[Metodo StrongNameKeyGenEx](iclrstrongname-strongnamekeygenex-method.md)|Genera una nuova coppia di chiavi pubblica/privata con le dimensioni chiave specificate per l'uso come nome sicuro.|  
|[Metodo StrongNameKeyInstall](iclrstrongname-strongnamekeyinstall-method.md)|Importa una coppia di chiavi pubblica/privata in un contenitore.|  
|[Metodo StrongNameSignatureGeneration](iclrstrongname-strongnamesignaturegeneration-method.md)|Genera una firma con nome sicuro per l'assembly specificato.|  
|[Metodo StrongNameSignatureGenerationEx](iclrstrongname-strongnamesignaturegenerationex-method.md)|Genera una firma con nome sicuro per l'assembly specificato, in base ai flag specificati.|  
|[Metodo StrongNameSignatureSize](iclrstrongname-strongnamesignaturesize-method.md)|Restituisce le dimensioni della firma con nome sicuro.|  
|[Metodo StrongNameSignatureVerification](iclrstrongname-strongnamesignatureverification-method.md)|Ottiene un valore che indica se il manifesto dell'assembly nel percorso specificato contiene una firma con nome sicuro, che viene verificata in base ai flag specificati.|  
|[Metodo StrongNameSignatureVerificationEx](iclrstrongname-strongnamesignatureverificationex-method.md)|Ottiene un valore che indica se il manifesto dell'assembly nel percorso specificato contiene una firma con nome sicuro.|  
|[Metodo StrongNameSignatureVerificationFromImage](iclrstrongname-strongnamesignatureverificationfromimage-method.md)|Verifica che un assembly di cui è già stato eseguito il mapping in memoria sia valido per la chiave pubblica associata.|  
|[Metodo StrongNameTokenFromAssembly](iclrstrongname-strongnametokenfromassembly-method.md)|Crea un token con nome sicuro dal file di assembly specificato.|  
|[Metodo StrongNameTokenFromAssemblyEx](iclrstrongname-strongnametokenfromassemblyex-method.md)|Crea un token con nome sicuro dal file di assembly specificato e restituisce la chiave pubblica.|  
|[Metodo StrongNameTokenFromPublicKey](iclrstrongname-strongnametokenfrompublickey-method.md)|Ottiene un token che rappresenta una chiave pubblica.|  
  
## <a name="remarks"></a>Osservazioni  
 È possibile ottenere un'istanza di `ICLRStrongName` chiamando il metodo [ICLRRuntimeInfo:: GetInterface](iclrruntimeinfo-getinterface-method.md) usando `CLSID_CLRStrongName` e `IID_ICLRStrongName` come parametri.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di hosting](hosting-interfaces.md)
- [Hosting](index.md)
