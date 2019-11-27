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
ms.openlocfilehash: 5434aa2d12bd9a29a8c2fc784421442469ceb1ce
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440556"
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
 in Token di metadati che specifica la struttura dei metadati `AssemblyRef` da modificare.  
  
 `pbPublicKeyOrToken`  
 in Chiave pubblica del server di pubblicazione dell'assembly a cui si fa riferimento.  
  
 `cbPublicKeyOrToken`  
 in Dimensioni in byte del `pbPublicKeyOrToken`.  
  
 `szName`  
 in Nome di testo leggibile dell'assembly.  
  
 `pMetaData`  
 in Puntatore a un'istanza di ASSEMBLYMETADATA che contiene le informazioni relative alla versione, alla piattaforma e alle impostazioni locali per l'assembly.  
  
 `pbHashValue`  
 in Puntatore ai dati hash associati all'assembly.  
  
 `cbHashValue`  
 in Dimensioni in byte del `pbHashValue`.  
  
 `dwAssemblyRefFlags`  
 in Combinazione bit per bit di valori [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) che specificano gli attributi dell'assembly a cui si fa riferimento.  
  
## <a name="remarks"></a>Note  
 Per creare una struttura di metadati `AssemblyRef`, usare il metodo [IMetaDataAssemblyEmit::D efineassemblyref](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md) .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
