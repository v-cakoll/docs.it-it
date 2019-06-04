---
title: Denominazione sicura (riferimenti alle API non gestite)
ms.date: 03/30/2017
helpviewer_keywords:
- strong naming [.NET Framework], using the unmanaged API
- native API reference [.NET Framework], strong naming
- unmanaged API reference [.NET Framework], strong naming
ms.assetid: 428c68b6-a7b4-44be-b280-75905f46612c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 45f3e8533bf7400566304ddb0fdd9d8e5a9b4280
ms.sourcegitcommit: 518e7634b86d3980ec7da5f8c308cc1054daedb7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2019
ms.locfileid: "66456131"
---
# <a name="strong-naming-unmanaged-api-reference"></a>Denominazione sicura (riferimenti alle API non gestite)
L'API di denominazione sicura consente a un client di amministrare la firma con nome sicuro per gli assembly.  
  
 La firma di un assembly con un nome sicuro comporta l'aggiunta di una crittografia con chiave pubblica al file che contiene il manifesto dell'assembly. La firma con nome sicuro garantisce l'univocità del nome, ne impedisce l'utilizzo fraudolento e fornisce un'identità univoca al chiamante quando viene risolto un riferimento. I nomi sicuri non garantiscono tuttavia nessun grado di attendibilità.  
  
## <a name="in-this-section"></a>In questa sezione  
  
> [!NOTE]
>  Tutte queste funzioni sono state deprecate a partire da [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]. Per le proposte alternative, vedere l'interfaccia [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md).  
  
 [Funzione GetHashFromAssemblyFile](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromassemblyfile-function.md)  
 Ottiene un hash del file di assembly specificato usando l'algoritmo hash specificato. Deprecata a partire da .NET Framework 4.  
  
 [Funzione GetHashFromAssemblyFileW](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromassemblyfilew-function.md)  
 Ottiene un hash del file di assembly specificato come stringa Unicode usando l'algoritmo hash specificato. Deprecata a partire da .NET Framework 4.  
  
 [Funzione GetHashFromBlob](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromblob-function.md)  
 Ottiene un hash dell'assembly all'indirizzo di memoria specificato usando l'algoritmo hash specificato. Deprecata a partire da .NET Framework 4.  
  
 [Funzione GetHashFromFile](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfile-function.md)  
 Genera un hash basato sul contenuto del file specificato.  Deprecata a partire da .NET Framework 4.  
  
 [Funzione GetHashFromFileW](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfilew-function.md)  
 Genera un hash basato sul contenuto del file specificato da una stringa Unicode. Deprecata a partire da .NET Framework 4.  
  
 [Funzione GetHashFromHandle](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromhandle-function.md)  
 Genera un hash basato sul contenuto del file con l'handle di file specificato, usando l'algoritmo hash specificato.  Deprecata a partire da .NET Framework 4.  
  
 [Funzione StrongNameCompareAssemblies](../../../../docs/framework/unmanaged-api/strong-naming/strongnamecompareassemblies-function.md)  
 Determina se due assembly differiscono solo per le firme con nome sicuro. Deprecata a partire da .NET Framework 4.  
  
 [Funzione StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)  
 Ottiene l'ultimo codice di errore che è stato generato da una delle funzioni con nome sicuro.  
  
 [Funzione StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md)  
 Libera la memoria allocata con una precedente chiamata a una funzione con nome sicuro, ad esempio [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md) o [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md).   Deprecata a partire da .NET Framework 4.  
  
 [Funzione StrongNameGetBlob](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetblob-function.md)  
 Completa il buffer specificato con la rappresentazione binaria del file eseguibile presente all'indirizzo specificato. Deprecata a partire da .NET Framework 4.  
  
 [Funzione StrongNameGetBlobFromImage](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetblobfromimage-function.md)  
 Ottiene una rappresentazione binaria dell'immagine dell'assembly in corrispondenza dell'indirizzo di memoria specificato. Deprecata a partire da .NET Framework 4.  
  
 [Funzione StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)  
 Ottiene la chiave pubblica da una coppia di chiavi pubblica/privata. Deprecata a partire da .NET Framework 4.  
  
 [Funzione StrongNameHashSize](../../../../docs/framework/unmanaged-api/strong-naming/strongnamehashsize-function.md)  
 Ottiene le dimensioni del buffer necessarie per un hash usando l'algoritmo hash specificato.  Deprecata a partire da .NET Framework 4.  
  
 [Funzione StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeydelete-function.md)  
 Elimina il contenitore di chiavi specificato. Deprecata a partire da .NET Framework 4.  
  
 [Funzione StrongNameKeyGen](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeygen-function.md)  
 Crea una nuova coppia di chiavi pubblica/privata per l'uso come nome sicuro.  Deprecata a partire da .NET Framework 4.  
  
 [Funzione StrongNameKeyGenEx](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeygenex-function.md)  
 Genera una nuova coppia di chiavi pubblica/privata con le dimensioni chiave specificate per l'uso come nome sicuro. Deprecata a partire da .NET Framework 4.  
  
 [Funzione StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeyinstall-function.md)  
 Importa una coppia di chiavi pubblica/privata in un contenitore.  Deprecata a partire da .NET Framework 4.  
  
 [Funzione StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)  
 Genera una firma con nome sicuro per l'assembly specificato.   Deprecata a partire da .NET Framework 4.  
  
 [Funzione StrongNameSignatureGenerationEx](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegenerationex-function.md)  
 Genera una firma con nome sicuro per l'assembly specificato, in base ai flag specificati.    Deprecata a partire da .NET Framework 4.  
  
 [Funzione StrongNameSignatureSize](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md)  
 Restituisce le dimensioni della firma con nome sicuro. Deprecata a partire da .NET Framework 4.  
  
 [Funzione StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverification-function.md)  
 Ottiene un valore che indica se il manifesto dell'assembly nel percorso specificato contiene una firma con nome sicuro, che viene verificata in base ai flag specificati. Deprecata a partire da .NET Framework 4.  
  
 [Funzione StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverificationex-function.md)  
 Ottiene un valore che indica se il manifesto dell'assembly nel percorso specificato contiene una firma con nome sicuro.  Deprecata a partire da .NET Framework 4.  
  
 [Funzione StrongNameSignatureVerificationFromImage](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverificationfromimage-function.md)  
 Verifica che un assembly di cui è già stato eseguito il mapping in memoria sia valido per la chiave pubblica associata. Deprecata a partire da .NET Framework 4.  
  
 [Funzione StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md)  
 Crea un token con nome sicuro dal file di assembly specificato.  Deprecata a partire da .NET Framework 4.  
  
 [Funzione StrongNameTokenFromAssemblyEx](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassemblyex-function.md)  
 Crea un token con nome sicuro dal file di assembly specificato e restituisce la chiave pubblica. Deprecata a partire da .NET Framework 4.  
  
 [Funzione StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md)  
 Ottiene un token che rappresenta una chiave pubblica. Deprecata a partire da .NET Framework 4.  
  
 [Struttura PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)  
 Rappresenta la chiave pubblica di una coppia di chiavi pubblica/privata in formato binario.  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
- [Riferimenti alle API non gestite](../../../../docs/framework/unmanaged-api/index.md)
