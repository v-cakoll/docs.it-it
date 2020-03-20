---
title: Denominazione sicura (riferimenti alle API non gestite)
ms.date: 03/30/2017
helpviewer_keywords:
- strong naming [.NET Framework], using the unmanaged API
- native API reference [.NET Framework], strong naming
- unmanaged API reference [.NET Framework], strong naming
ms.assetid: 428c68b6-a7b4-44be-b280-75905f46612c
ms.openlocfilehash: 7d18513450111d58b5d26fd834addd465cfc4267
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73140642"
---
# <a name="strong-naming-unmanaged-api-reference"></a>Denominazione sicura (riferimenti alle API non gestite)
L'API di denominazione sicura consente a un client di amministrare la firma con nome sicuro per gli assembly.  
  
 La firma di un assembly con un nome sicuro comporta l'aggiunta di una crittografia con chiave pubblica al file che contiene il manifesto dell'assembly. La firma con nome sicuro garantisce l'univocità del nome, ne impedisce l'utilizzo fraudolento e fornisce un'identità univoca al chiamante quando viene risolto un riferimento. I nomi sicuri non garantiscono tuttavia nessun grado di attendibilità.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
  
> [!NOTE]
> Tutte queste funzioni sono state deprecate a partire da .NET Framework 4. Per le proposte alternative, vedere l'interfaccia [ICLRStrongName](../hosting/iclrstrongname-interface.md).  
  
 [Funzione GetHashFromAssemblyFile](gethashfromassemblyfile-function.md)  
 Ottiene un hash del file di assembly specificato usando l'algoritmo hash specificato. Deprecata a partire da .NET Framework 4.  
  
 [Funzione GetHashFromAssemblyFileW](gethashfromassemblyfilew-function.md)  
 Ottiene un hash del file di assembly specificato come stringa Unicode usando l'algoritmo hash specificato. Deprecata a partire da .NET Framework 4.  
  
 [Funzione GetHashFromBlob](gethashfromblob-function.md)  
 Ottiene un hash dell'assembly all'indirizzo di memoria specificato usando l'algoritmo hash specificato. Deprecata a partire da .NET Framework 4.  
  
 [Funzione GetHashFromFile](gethashfromfile-function.md)  
 Genera un hash basato sul contenuto del file specificato.  Deprecata a partire da .NET Framework 4.  
  
 [Funzione GetHashFromFileW](gethashfromfilew-function.md)  
 Genera un hash basato sul contenuto del file specificato da una stringa Unicode. Deprecata a partire da .NET Framework 4.  
  
 [Funzione GetHashFromHandle](gethashfromhandle-function.md)  
 Genera un hash basato sul contenuto del file con l'handle di file specificato, usando l'algoritmo hash specificato.  Deprecata a partire da .NET Framework 4.  
  
 [Funzione StrongNameCompareAssemblies](strongnamecompareassemblies-function.md)  
 Determina se due assembly differiscono solo per le firme con nome sicuro. Deprecata a partire da .NET Framework 4.  
  
 [Funzione StrongNameErrorInfo](strongnameerrorinfo-function.md)  
 Ottiene l'ultimo codice di errore che è stato generato da una delle funzioni con nome sicuro.  
  
 [Funzione StrongNameFreeBuffer](strongnamefreebuffer-function.md)  
 Libera la memoria allocata con una precedente chiamata a una funzione con nome sicuro, ad esempio [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md) o [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md).   Deprecata a partire da .NET Framework 4.  
  
 [Funzione StrongNameGetBlob](strongnamegetblob-function.md)  
 Completa il buffer specificato con la rappresentazione binaria del file eseguibile presente all'indirizzo specificato. Deprecata a partire da .NET Framework 4.  
  
 [Funzione StrongNameGetBlobFromImage](strongnamegetblobfromimage-function.md)  
 Ottiene una rappresentazione binaria dell'immagine dell'assembly in corrispondenza dell'indirizzo di memoria specificato. Deprecata a partire da .NET Framework 4.  
  
 [Funzione StrongNameGetPublicKey](strongnamegetpublickey-function.md)  
 Ottiene la chiave pubblica da una coppia di chiavi pubblica/privata. Deprecata a partire da .NET Framework 4.  
  
 [Funzione StrongNameHashSize](strongnamehashsize-function.md)  
 Ottiene le dimensioni del buffer necessarie per un hash usando l'algoritmo hash specificato.  Deprecata a partire da .NET Framework 4.  
  
 [Funzione StrongNameKeyDelete](strongnamekeydelete-function.md)  
 Elimina il contenitore di chiavi specificato. Deprecata a partire da .NET Framework 4.  
  
 [Funzione StrongNameKeyGen](strongnamekeygen-function.md)  
 Crea una nuova coppia di chiavi pubblica/privata per l'uso come nome sicuro.  Deprecata a partire da .NET Framework 4.  
  
 [Funzione StrongNameKeyGenEx](strongnamekeygenex-function.md)  
 Genera una nuova coppia di chiavi pubblica/privata con le dimensioni chiave specificate per l'uso come nome sicuro. Deprecata a partire da .NET Framework 4.  
  
 [Funzione StrongNameKeyInstall](strongnamekeyinstall-function.md)  
 Importa una coppia di chiavi pubblica/privata in un contenitore.  Deprecata a partire da .NET Framework 4.  
  
 [Funzione StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md)  
 Genera una firma con nome sicuro per l'assembly specificato.   Deprecata a partire da .NET Framework 4.  
  
 [Funzione StrongNameSignatureGenerationEx](strongnamesignaturegenerationex-function.md)  
 Genera una firma con nome sicuro per l'assembly specificato, in base ai flag specificati.    Deprecata a partire da .NET Framework 4.  
  
 [Funzione StrongNameSignatureSize](strongnamesignaturesize-function.md)  
 Restituisce le dimensioni della firma con nome sicuro. Deprecata a partire da .NET Framework 4.  
  
 [Funzione StrongNameSignatureVerification](strongnamesignatureverification-function.md)  
 Ottiene un valore che indica se il manifesto dell'assembly nel percorso specificato contiene una firma con nome sicuro, che viene verificata in base ai flag specificati. Deprecata a partire da .NET Framework 4.  
  
 [Funzione StrongNameSignatureVerificationEx](strongnamesignatureverificationex-function.md)  
 Ottiene un valore che indica se il manifesto dell'assembly nel percorso specificato contiene una firma con nome sicuro.  Deprecata a partire da .NET Framework 4.  
  
 [Funzione StrongNameSignatureVerificationFromImage](strongnamesignatureverificationfromimage-function.md)  
 Verifica che un assembly di cui è già stato eseguito il mapping in memoria sia valido per la chiave pubblica associata. Deprecata a partire da .NET Framework 4.  
  
 [Funzione StrongNameTokenFromAssembly](strongnametokenfromassembly-function.md)  
 Crea un token con nome sicuro dal file di assembly specificato.  Deprecata a partire da .NET Framework 4.  
  
 [Funzione StrongNameTokenFromAssemblyEx](strongnametokenfromassemblyex-function.md)  
 Crea un token con nome sicuro dal file di assembly specificato e restituisce la chiave pubblica. Deprecata a partire da .NET Framework 4.  
  
 [Funzione StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md)  
 Ottiene un token che rappresenta una chiave pubblica. Deprecata a partire da .NET Framework 4.  
  
 [Struttura PublicKeyBlob](publickeyblob-structure.md)  
 Rappresenta la chiave pubblica di una coppia di chiavi pubblica/privata in formato binario.  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRStrongName](../hosting/iclrstrongname-interface.md)
- [Informazioni di riferimento sulle API non gestiteUnmanaged API Reference](../index.md)
