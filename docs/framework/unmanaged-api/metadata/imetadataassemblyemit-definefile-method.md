---
title: Metodo IMetaDataAssemblyEmit::DefineFile
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
- IMetaDataAssemblyEmit.DefineFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineFile
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineFile method [.NET Framework metadata]
- DefineFile method [.NET Framework metadata]
ms.assetid: c065aadf-c1ca-4981-bde6-597042cb29c4
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 48584822d7a2f31c466401db3a24156a71ad7011
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyemitdefinefile-method"></a>Metodo IMetaDataAssemblyEmit::DefineFile
Crea una struttura dei metadati `File` che contiene i metadati per l'assembly a cui fa riferimento questo assembly e restituisce il token di metadati associato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT DefineFile (  
    [in]  LPCWSTR        szName,   
    [in]  const void     *pbHashValue,   
    [in]  ULONG          cbHashValue,  
    [in]  DWORD          dwFileFlags,  
    [out] mdFile         *pmdf  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `szName`  
 [in] Il nome del file deve essere utilizzato.  
  
 `pbHashValue`  
 [in] Un puntatore per il valore hash dei dati associati all'assembly.  
  
 `cbHashValue`  
 [in] Le dimensioni in byte di `pbHashValue`.  
  
 `dwFileFlags`  
 [in] Combinazione bit per bit di `FileFlags` valori che specificano le impostazioni delle proprietà.  
  
 `pmdf`  
 [out] Un puntatore all'oggetto restituito `File` token.  
  
## <a name="remarks"></a>Note  
 Una `File` struttura dei metadati deve essere definita per ogni file che faceva parte di questo assembly nel momento in cui questo assembly è stato compilato, escluso il file che contiene i metadati.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforma:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
