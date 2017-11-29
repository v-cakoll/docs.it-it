---
title: Denominazione sicura (riferimenti alle API non gestite)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- strong naming [.NET Framework], using the unmanaged API
- native API reference [.NET Framework], strong naming
- unmanaged API reference [.NET Framework], strong naming
ms.assetid: 428c68b6-a7b4-44be-b280-75905f46612c
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 86d741a16a0293892d0d6d90f1763d744ed3675d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="strong-naming-unmanaged-api-reference"></a>Denominazione sicura (riferimenti alle API non gestite)
L'API di denominazione sicura consente a un client di amministrare la firma degli assembly con nome sicuro.  
  
 La firma di un assembly con un nome sicuro comporta l'aggiunta di una crittografia con chiave pubblica al file che contiene il manifesto dell'assembly. Firma con nome sicuro consente di verificare l'univocità dei nomi, impedisce l'utilizzo fraudolento e fornisce con un'identità univoca quando un riferimento viene risolto. Tuttavia, nessun livello di attendibilità è associata a un nome sicuro.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Funzioni statiche globali di denominazione sicura](http://msdn.microsoft.com/en-us/efa715df-e8cc-48f2-9ec4-26586f0dc8d0)  
 Descrive le funzioni statiche globali non gestite usate dall'API di denominazione sicuro.  
  
> [!NOTE]
>  Tutte queste funzioni sono deprecate a partire dal [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]. Per le alternative suggerite, vedere il [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) interfaccia.  
  
 [GetHashFromAssemblyFile (funzione)](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromassemblyfile-function.md)  
 Ottiene un hash del file di assembly specificato, usando l'algoritmo hash specificato. Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [GetHashFromAssemblyFileW (funzione)](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromassemblyfilew-function.md)  
 Ottiene un hash del file di assembly specificato come stringa Unicode, utilizzando l'algoritmo hash specificato. Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [GetHashFromBlob (funzione)](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromblob-function.md)  
 Ottiene un hash dell'assembly nell'indirizzo di memoria specificata, utilizzando l'algoritmo hash specificato. Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [GetHashFromFile (funzione)](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfile-function.md)  
 Genera un hash per il contenuto del file specificato.  Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [GetHashFromFileW (funzione)](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfilew-function.md)  
 Genera un hash per il contenuto del file specificato da una stringa Unicode. Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [GetHashFromHandle (funzione)](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromhandle-function.md)  
 Genera un hash per il contenuto del file con l'handle di file specificato, usando l'algoritmo hash specificato.  Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameCompareAssemblies (funzione)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamecompareassemblies-function.md)  
 Determina se due assembly differiscono solo per le firme con nome sicuro. Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameErrorInfo (funzione)](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)  
 Ottiene l'ultimo codice di errore che è stato generato da una delle funzioni con nome sicuro.  
  
 [StrongNameFreeBuffer (funzione)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md)  
 Libera la memoria allocata con una precedente chiamata a una funzione con nome sicuro, ad esempio [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md), o [StrongNameSignatureGeneration ](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md).   Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameGetBlob (funzione)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetblob-function.md)  
 Riempie il buffer specificato con la rappresentazione binaria del file eseguibile all'indirizzo specificato. Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameGetBlobFromImage (funzione)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetblobfromimage-function.md)  
 Ottiene una rappresentazione binaria dell'immagine di assembly in corrispondenza dell'indirizzo di memoria specificata. Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameGetPublicKey (funzione)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)  
 Ottiene la chiave pubblica da una coppia di chiavi pubblica/privata. Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameHashSize (funzione)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamehashsize-function.md)  
 Ottiene le dimensioni del buffer necessarie per generare un hash, utilizzando l'algoritmo hash specificato.  Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameKeyDelete (funzione)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeydelete-function.md)  
 Elimina il contenitore di chiavi specificato. Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameKeyGen (funzione)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeygen-function.md)  
 Crea una nuova coppia di chiavi pubblica/privata per l'utilizzo con nome sicuro.  Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameKeyGenEx (funzione)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeygenex-function.md)  
 Genera una nuova coppia di chiavi pubblica/privata con la dimensione della chiave specificata per l'utilizzo con nome sicuro. Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameKeyInstall (funzione)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeyinstall-function.md)  
 Importa una coppia di chiavi pubblica/privata in un contenitore.  Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameSignatureGeneration (funzione)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)  
 Genera una firma nome sicuro per l'assembly specificato.   Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameSignatureGenerationEx (funzione)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegenerationex-function.md)  
 Genera una firma nome sicuro per l'assembly specificato, in base ai flag specificati.    Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameSignatureSize (funzione)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md)  
 Restituisce la dimensione della firma con nome sicuro. Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameSignatureVerification (funzione)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverification-function.md)  
 Ottiene un valore che indica se il manifesto dell'assembly nel percorso specificato contiene una firma nome sicuro, che viene verificata in base ai flag specificati. Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameSignatureVerificationEx (funzione)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverificationex-function.md)  
 Ottiene un valore che indica se il manifesto dell'assembly nel percorso specificato contiene una firma con nome sicuro.  Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameSignatureVerificationFromImage (funzione)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverificationfromimage-function.md)  
 Verifica che un assembly che è già stato mappato alla memoria sia valido per la chiave pubblica associata. Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameTokenFromAssembly (funzione)](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md)  
 Crea un token con nome sicuro dal file di assembly specificato.  Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameTokenFromAssemblyEx (funzione)](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassemblyex-function.md)  
 Crea un token con nome sicuro dal file di assembly specificato e restituisce la chiave pubblica. Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameTokenFromPublicKey (funzione)](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md)  
 Ottiene un token che rappresenta una chiave pubblica. Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Struttura di denominazione sicuro](http://msdn.microsoft.com/en-us/4b041a2f-fd12-4b91-aacd-bc3b34a5124d)  
 Descrive la struttura non gestita che usa l'API di denominazione sicura per amministrare firma degli assembly con nome sicuro...  
  
 [PublicKeyBlob (struttura)](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)  
 Rappresenta la chiave pubblica di una coppia di chiavi pubblica/privata in formato binario.  
  
## <a name="see-also"></a>Vedere anche  
 [ICLRStrongName (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)  
 [Riferimenti alle API non gestite](../../../../docs/framework/unmanaged-api/index.md)
