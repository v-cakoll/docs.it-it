---
title: Metodo IMetaDataAssemblyEmit::DefineAssembly
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
- IMetaDataAssemblyEmit.DefineAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineAssembly
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineAssembly method [.NET Framework metadata]
- DefineAssembly method [.NET Framework metadata]
ms.assetid: a0637d66-74bf-4f2d-8137-9ff838bccece
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 35bc85cdc4380ee112b7095866c05e5d7639200b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyemitdefineassembly-method"></a>Metodo IMetaDataAssemblyEmit::DefineAssembly
Crea un `Assembly` struttura che contiene i metadati per l'assembly specificato e restituisce il token di metadati associato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT DefineAssembly (  
    [in]  void                 *pbPublicKey,  
    [in]  ULONG                cbPublicKey,  
    [in]  ULONG                uHashAlgId,  
    [in]  LPCWSTR              szName,   
    [in]  ASSEMBLYMETADATA     *pMetaData,  
    [in]  DWORD                dwAssemblyFlags,  
    [out] mdAssembly           *pmda  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pbPublicKey`  
 [in] La chiave pubblica che identifica l'autore dell'assembly, o NULL se l'assembly non è sicuro.  
  
 `cbPublicKey`  
 [in] Le dimensioni in byte di `pbPublicKey`.  
  
 `uHashAlgId`  
 [in] Identificatore dell'algoritmo hash da utilizzare per crittografare i file nell'assembly, o NULL per specificare l'algoritmo SHA-1.  
  
 `szName`  
 [in] Il nome di un testo leggibile dell'assembly. Questo valore non deve superare i 1024 caratteri.  
  
 `pMetaData`  
 [in] Un puntatore a un'istanza ASSEMBLYMETADATA che contiene le informazioni sulla versione, piattaforma e delle impostazioni locali per l'assembly.  
  
 `dwAssemblyFlags`  
 [in] Una combinazione di [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) valori che descrivono le funzionalità dell'assembly.  
  
 `pmda`  
 [out] Puntatore al token di metadati.  
  
## <a name="remarks"></a>Note  
 Un solo `Assembly` struttura dei metadati può essere definito all'interno di un manifesto.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** inclusa come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
