---
title: Metodo IMetaDataAssemblyEmit::SetAssemblyRefProps
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyEmit.SetAssemblyRefProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyEmit::SetAssemblyRefProps
helpviewer_keywords:
- SetAssemblyRefProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetAssemblyRefProps method [.NET Framework metadata]
ms.assetid: 70a32bf3-9051-4f96-ae87-11356d06a073
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 84b6c0d748578b717a128ff3b808977ba902c6dc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyemitsetassemblyrefprops-method"></a>Metodo IMetaDataAssemblyEmit::SetAssemblyRefProps
Modifica la struttura dei metadati `AssemblyRef` specificata.  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
  
#### <a name="parameters"></a>Parametri  
 `ar`  
 [in] Il token di metadati che specifica il `AssemblyRef` struttura dei metadati da modificare.  
  
 `pbPublicKeyOrToken`  
 [in] La chiave pubblica del server di pubblicazione dell'assembly di riferimento.  
  
 `cbPublicKeyOrToken`  
 [in] Le dimensioni in byte di `pbPublicKeyOrToken`.  
  
 `szName`  
 [in] Il nome di un testo leggibile dell'assembly.  
  
 `pMetaData`  
 [in] Un puntatore a un'istanza ASSEMBLYMETADATA che contiene le informazioni sulla versione, piattaforma e delle impostazioni locali per l'assembly.  
  
 `pbHashValue`  
 [in] Un puntatore per il valore hash dei dati associati all'assembly.  
  
 `cbHashValue`  
 [in] Le dimensioni in byte di `pbHashValue`.  
  
 `dwAssemblyRefFlags`  
 [in] Combinazione bit per bit di [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) valori che specificano gli attributi dell'assembly di riferimento.  
  
## <a name="remarks"></a>Note  
 Per creare un `AssemblyRef` struttura dei metadati, usare il [IMetaDataAssemblyEmit:: DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md) metodo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
