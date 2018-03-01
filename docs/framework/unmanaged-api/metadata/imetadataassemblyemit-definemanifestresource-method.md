---
title: Metodo IMetaDataAssemblyEmit::DefineManifestResource
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
- IMetaDataAssemblyEmit.DefineManifestResource
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineManifestResource
helpviewer_keywords:
- DefineManifestResource method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineManifestResource method [.NET Framework metadata]
ms.assetid: 27f6d295-0fe9-4cda-b77e-6e7d5c53df09
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a435c946e13950faad7545e3da78ce373ee7fa0d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyemitdefinemanifestresource-method"></a>Metodo IMetaDataAssemblyEmit::DefineManifestResource
Crea una struttura `ManifestResource` che contiene i metadati per la risorsa di manifesto specificata e restituisce il token di metadati associato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT DefineManifestResource (  
    [in] LPCWSTR                szName,   
    [in] mdToken                tkImplementation,   
    [in] DWORD                  dwOffset,   
    [in] DWORD                  dwResourceFlags,  
    [out] mdManifestResource    *pmdmr  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `szName`  
 [in] Il nome della risorsa.  
  
 `tkImplementation`  
 [in] Un token di metadati del tipo `mdtFile` o `mdtAssemblyRef` che esegue il mapping al provider di risorse. Un valore NULL indica che il file in cui sono incorporato i metadati sia il provider di risorse.  
  
 `dwOffset`  
 [in] L'offset all'inizio della risorsa all'interno del file. Per le risorse nei file autonomi, questo valore sarà sempre zero. Se la risorsa è incorporata in un file di PE (eseguibile), si tratta di un offset del BLOB, che inizia nella posizione specificata nel file di intestazione Cor. h della risorsa.  
  
 `dwResourceFlags`  
 [in] Combinazione bit per bit dei valori di flag che specificano le impostazioni delle proprietà per la definizione di risorsa.  
  
 `pmdmr`  
 [out] Un puntatore al token di metadati restituiti.  
  
## <a name="remarks"></a>Note  
 Una `ManifestResource` struttura dei metadati deve essere definita per ogni risorsa è implementata in ognuno dei file dell'assembly.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforma:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
