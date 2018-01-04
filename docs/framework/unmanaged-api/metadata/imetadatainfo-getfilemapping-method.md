---
title: Metodo IMetaDataInfo::GetFileMapping
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataInfo.GetFileMapping
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataInfo::GetFileMapping
helpviewer_keywords:
- IMetaDataInfo::GetFileMapping method [.NET Framework metadata]
- GetFileMapping method [.NET Framework metadata]
ms.assetid: 2868dfec-c992-4606-88bb-a8e0b6b18271
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f974230dc5ddf2a663f05fc06850f49f1de6e773
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatainfogetfilemapping-method"></a>Metodo IMetaDataInfo::GetFileMapping
Ottiene l'area di memoria del file mappato e il tipo di mapping.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetFileMapping (  
    [out] const void           **ppvData,   
    [out] ULONGLONG            *pcbData,   
    [out] DWORD                *pdwMappingType  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `ppvData`  
 [out] Un puntatore all'inizio del file mappato.  
  
 `pcbData`  
 [out] Le dimensioni dell'area mappato. Se `pdwMappingType` è `fmFlat`, si tratta della dimensione del file.  
  
 `pdwMappingType`  
 [out] Oggetto [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) valore che indica il tipo di mapping. Restituisce sempre l'implementazione corrente di common language runtime (CLR) `fmFlat`. Altri valori sono riservati per utilizzi futuri. Tuttavia, è necessario verificare sempre il valore restituito, perché possono essere abilitate nelle versioni future o service release di altri valori.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|`S_OK`|Tutti gli output vengono compilati.|  
|`E_INVALIDARG`|NULL passato come un valore dell'argomento.|  
|`COR_E_NOTSUPPORTED`|L'implementazione di Common Language Runtime non può fornire informazioni sull'area di memoria. Questa situazione può verificarsi per i motivi seguenti:<br /><br /> -L'ambito dei metadati è stato aperto con il `ofWrite` o `ofCopyMemory` flag.<br />-L'ambito dei metadati è stato aperto senza il `ofReadOnly` flag.<br />-La [IMetaDataDispenser::](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) metodo utilizzato per aprire solo la parte di metadati del file.<br />-Il file non è un file eseguibile portabile (PE). **Nota:** tali condizioni dipendono dall'implementazione CLR e venga potrebbero essere ridotte in versioni future di CLR.|  
  
## <a name="remarks"></a>Note  
 La memoria che `ppvData` punta è valida solo fino a quando l'ambito dei metadati sottostante è aperto.  
  
 Affinché il metodo funzioni, quando si esegue il mapping i metadati di un file su disco in memoria chiamando la [IMetaDataDispenser::](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) metodo, è necessario specificare il `ofReadOnly` flag e non è necessario specificare il `ofWrite` o `ofCopyMemory` flag.  
  
 La scelta del tipo di mapping di file per ogni ambito è specifica per una determinata implementazione di CLR. Non può essere impostata dall'utente. Restituisce sempre l'implementazione corrente di CLR `fmFlat` in `pdwMappingType`, ma si può cambiare nelle future versioni di CLR o nelle future versioni di servizio di una determinata versione. Controllare sempre il valore restituito `pdwMappingType`, poiché saranno necessario diversi tipi di layout e offset diversi.  
  
 Non è possibile passare NULL per uno dei tre parametri. Il metodo restituisce `E_INVALIDARG`, e nessuno degli output viene riempito. Verrà ignorato il tipo di mapping o le dimensioni dell'area può comportare una chiusura anomala del programma.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IMetaDataInfo](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-interface.md)  
 [Enumerazione CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md)
