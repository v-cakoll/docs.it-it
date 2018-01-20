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
ms.workload: dotnet
ms.openlocfilehash: ce89e27089ea2f0c918d0fe37c4eea141698f9be
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="strong-naming-unmanaged-api-reference"></a>Denominazione sicura (riferimenti alle API non gestite)
L'API di denominazione sicura consente a un client di amministrare la firma degli assembly con nome sicuro.  
  
 La firma di un assembly con un nome sicuro comporta l'aggiunta di una crittografia con chiave pubblica al file che contiene il manifesto dell'assembly. Firma con nome sicuro consente di verificare l'univocità dei nomi, impedisce l'utilizzo fraudolento e fornisce con un'identità univoca quando un riferimento viene risolto. Tuttavia, nessun livello di attendibilità è associata a un nome sicuro.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Funzioni statiche globali di denominazione sicura](http://msdn.microsoft.com/library/efa715df-e8cc-48f2-9ec4-26586f0dc8d0)  
 Descrive le funzioni statiche globali non gestite usate dall'API di denominazione sicuro.  
  
> [!NOTE]
>  Tutte queste funzioni sono deprecate a partire dal [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]. Per le alternative suggerite, vedere il [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) interfaccia.  
  
 [Funzione GetHashFromAssemblyFile](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromassemblyfile-function.md)  
 Ottiene un hash del file di assembly specificato, usando l'algoritmo hash specificato. Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Funzione GetHashFromAssemblyFileW](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromassemblyfilew-function.md)  
 Ottiene un hash del file di assembly specificato come stringa Unicode, utilizzando l'algoritmo hash specificato. Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Funzione GetHashFromBlob](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromblob-function.md)  
 Ottiene un hash dell'assembly nell'indirizzo di memoria specificata, utilizzando l'algoritmo hash specificato. Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Funzione GetHashFromFile](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfile-function.md)  
 Genera un hash per il contenuto del file specificato.  Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Funzione GetHashFromFileW](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfilew-function.md)  
 Genera un hash per il contenuto del file specificato da una stringa Unicode. Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Funzione GetHashFromHandle](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromhandle-function.md)  
 Genera un hash per il contenuto del file con l'handle di file specificato, usando l'algoritmo hash specificato.  Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Funzione StrongNameCompareAssemblies](../../../../docs/framework/unmanaged-api/strong-naming/strongnamecompareassemblies-function.md)  
 Determina se due assembly differiscono solo per le firme con nome sicuro. Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Funzione StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)  
 Ottiene l'ultimo codice di errore che è stato generato da una delle funzioni con nome sicuro.  
  
 [Funzione StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md)  
 Libera la memoria allocata con una precedente chiamata a una funzione con nome sicuro, ad esempio [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md), o [StrongNameSignatureGeneration ](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md).   Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Funzione StrongNameGetBlob](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetblob-function.md)  
 Riempie il buffer specificato con la rappresentazione binaria del file eseguibile all'indirizzo specificato. Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Funzione StrongNameGetBlobFromImage](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetblobfromimage-function.md)  
 Ottiene una rappresentazione binaria dell'immagine di assembly in corrispondenza dell'indirizzo di memoria specificata. Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Funzione StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)  
 Ottiene la chiave pubblica da una coppia di chiavi pubblica/privata. Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Funzione StrongNameHashSize](../../../../docs/framework/unmanaged-api/strong-naming/strongnamehashsize-function.md)  
 Ottiene le dimensioni del buffer necessarie per generare un hash, utilizzando l'algoritmo hash specificato.  Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Funzione StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeydelete-function.md)  
 Elimina il contenitore di chiavi specificato. Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Funzione StrongNameKeyGen](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeygen-function.md)  
 Crea una nuova coppia di chiavi pubblica/privata per l'utilizzo con nome sicuro.  Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Funzione StrongNameKeyGenEx](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeygenex-function.md)  
 Genera una nuova coppia di chiavi pubblica/privata con la dimensione della chiave specificata per l'utilizzo con nome sicuro. Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Funzione StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeyinstall-function.md)  
 Importa una coppia di chiavi pubblica/privata in un contenitore.  Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Funzione StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)  
 Genera una firma nome sicuro per l'assembly specificato.   Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Funzione StrongNameSignatureGenerationEx](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegenerationex-function.md)  
 Genera una firma nome sicuro per l'assembly specificato, in base ai flag specificati.    Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Funzione StrongNameSignatureSize](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md)  
 Restituisce la dimensione della firma con nome sicuro. Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Funzione StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverification-function.md)  
 Ottiene un valore che indica se il manifesto dell'assembly nel percorso specificato contiene una firma nome sicuro, che viene verificata in base ai flag specificati. Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Funzione StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverificationex-function.md)  
 Ottiene un valore che indica se il manifesto dell'assembly nel percorso specificato contiene una firma con nome sicuro.  Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Funzione StrongNameSignatureVerificationFromImage](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverificationfromimage-function.md)  
 Verifica che un assembly che è già stato mappato alla memoria sia valido per la chiave pubblica associata. Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Funzione StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md)  
 Crea un token con nome sicuro dal file di assembly specificato.  Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Funzione StrongNameTokenFromAssemblyEx](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassemblyex-function.md)  
 Crea un token con nome sicuro dal file di assembly specificato e restituisce la chiave pubblica. Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Funzione StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md)  
 Ottiene un token che rappresenta una chiave pubblica. Deprecate a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [Struttura di denominazione sicuro](http://msdn.microsoft.com/library/4b041a2f-fd12-4b91-aacd-bc3b34a5124d)  
 Descrive la struttura non gestita che usa l'API di denominazione sicura per amministrare firma degli assembly con nome sicuro...  
  
 [Struttura PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)  
 Rappresenta la chiave pubblica di una coppia di chiavi pubblica/privata in formato binario.  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)  
 [Riferimenti alle API non gestite](../../../../docs/framework/unmanaged-api/index.md)
