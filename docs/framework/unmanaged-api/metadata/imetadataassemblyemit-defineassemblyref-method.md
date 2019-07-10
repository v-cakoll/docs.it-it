---
title: Metodo IMetaDataAssemblyEmit::DefineAssemblyRef
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineAssemblyRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineAssemblyRef
helpviewer_keywords:
- DefineAssemblyRef method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineAssemblyRef method [.NET Framework metadata]
ms.assetid: 0b284b18-0084-4b3a-912a-5ebe9f29c88b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c150f4bda901627fc21ed54926c3cf959bb829a3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776296"
---
# <a name="imetadataassemblyemitdefineassemblyref-method"></a>Metodo IMetaDataAssemblyEmit::DefineAssemblyRef
Crea una struttura `AssemblyRef` che contiene i metadati per l'assembly a cui fa riferimento questo assembly e restituisce il token di metadati associato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT DefineAssemblyRef (  
    [in]  void                *pbPublicKeyOrToken,  
    [in]  ULONG               cbPublicKeyOrToken,  
    [in]  LPCWSTR             szName,  
    [in]  ASSEMBLYMETADATA    pMetaData,  
    [in]  void                *pbHashValue,  
    [in]  ULONG               cbHashValue,  
    [in]  DWORD               dwAssemblyRefFlags,  
    [out] mdAssemblyRef       *pmdar  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pbPublicKeyOrToken`  
 [in] La chiave pubblica del server di pubblicazione dell'assembly di riferimento. La funzione helper [StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md) utilizzabile per ottenere l'hash della chiave pubblica da passare come parametro.  
  
 `cbPublicKeyOrToken`  
 [in] La dimensione in byte di `pbPublicKeyOrToken`.  
  
 `szName`  
 [in] Il nome di testo leggibile dell'assembly. Questo valore non deve superare 1024 caratteri.  
  
 `pMetaData`  
 [in] Istanza ASSEMBLYMETADATA che contiene le informazioni di versione, piattaforma e delle impostazioni locali dell'assembly di riferimento.  
  
 `pbHashValue`  
 [in] I dati di hash associati con l'assembly di riferimento. Facoltativo.  
  
 `cbHashValue`  
 [in] La dimensione in byte di `pbHashValue`.  
  
 `dwAssemblyRefFlags`  
 [in] Una combinazione bit per bit di [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) valori che influenzano il comportamento del motore di esecuzione.  
  
 `pmdar`  
 [out] Un puntatore all'oggetto restituito `AssemblyRef` token di metadati.  
  
## <a name="remarks"></a>Note  
 Uno `AssemblyRef` struttura dei metadati deve essere definita per ogni assembly che fa riferimento questo assembly.  
  
 In fase di esecuzione, i dettagli di un assembly di riferimento vengono passati al resolver di assembly con un valore che indica che essi rappresentano le informazioni "così come compilato". Il resolver dell'assembly applica quindi i criteri.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
