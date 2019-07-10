---
title: Metodo IMetaDataAssemblyEmit::SetAssemblyRefProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetAssemblyRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetAssemblyRefProps
helpviewer_keywords:
- SetAssemblyRefProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetAssemblyRefProps method [.NET Framework metadata]
ms.assetid: 70a32bf3-9051-4f96-ae87-11356d06a073
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 984ec5dea757971081ce05c858788473a0f616e7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775268"
---
# <a name="imetadataassemblyemitsetassemblyrefprops-method"></a>Metodo IMetaDataAssemblyEmit::SetAssemblyRefProps
Modifica la struttura dei metadati `AssemblyRef` specificata.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetAssemblyRefProps (  
    [in] mdAssemblyRef              ar,  
    [in] const void                 *pbPublicKeyOrToken,  
    [in] ULONG                      cbPublicKeyOrToken,  
    [in] LPCWSTR                    szName,   
    [in] const ASSEMBLYMETADATA     *pMetaData,   
    [in] const void                 *pbHashValue,  
    [in] ULONG                      cbHashValue,  
    [in] DWORD                      dwAssemblyRefFlags  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ar`  
 [in] Il token di metadati che specifica il `AssemblyRef` modifica della struttura dei metadati.  
  
 `pbPublicKeyOrToken`  
 [in] La chiave pubblica del server di pubblicazione dell'assembly di riferimento.  
  
 `cbPublicKeyOrToken`  
 [in] La dimensione in byte di `pbPublicKeyOrToken`.  
  
 `szName`  
 [in] Il nome di testo leggibile dell'assembly.  
  
 `pMetaData`  
 [in] Un puntatore a un'istanza ASSEMBLYMETADATA che contiene le informazioni di versione, piattaforma e delle impostazioni locali per l'assembly.  
  
 `pbHashValue`  
 [in] Un puntatore per il valore hash dei dati associati all'assembly.  
  
 `cbHashValue`  
 [in] La dimensione in byte di `pbHashValue`.  
  
 `dwAssemblyRefFlags`  
 [in] Una combinazione bit per bit di [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) valori che specificano gli attributi dell'assembly di riferimento.  
  
## <a name="remarks"></a>Note  
 Per creare un `AssemblyRef` struttura dei metadati, usare il [DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md) (metodo).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
