---
title: Metodo IMetaDataInfo::GetFileMapping
ms.date: 03/30/2017
api_name:
- IMetaDataInfo.GetFileMapping
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataInfo::GetFileMapping
helpviewer_keywords:
- IMetaDataInfo::GetFileMapping method [.NET Framework metadata]
- GetFileMapping method [.NET Framework metadata]
ms.assetid: 2868dfec-c992-4606-88bb-a8e0b6b18271
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 22af95ef4bd1fca0a8253faa6ce0e1c7a862054d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782653"
---
# <a name="imetadatainfogetfilemapping-method"></a>Metodo IMetaDataInfo::GetFileMapping
Ottiene l'area della memoria del file mappato e il tipo di mapping.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetFileMapping (  
    [out] const void           **ppvData,   
    [out] ULONGLONG            *pcbData,   
    [out] DWORD                *pdwMappingType  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppvData`  
 [out] Un puntatore all'inizio del file mappato.  
  
 `pcbData`  
 [out] Le dimensioni dell'area mappata. Se `pdwMappingType` è `fmFlat`, questa è la dimensione del file.  
  
 `pdwMappingType`  
 [out] Oggetto [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) valore che indica il tipo di mapping. Restituisce sempre l'implementazione corrente di common language runtime (CLR) `fmFlat`. Altri valori sono riservati per utilizzi futuri. Tuttavia, è necessario verificare sempre il valore restituito, poiché gli altri valori possono essere abilitati nelle versioni future o versioni del servizio.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|`S_OK`|Tutti gli output sono pieni.|  
|`E_INVALIDARG`|È stato passato NULL come valore dell'argomento.|  
|`COR_E_NOTSUPPORTED`|L'implementazione CLR non può fornire informazioni sull'area della memoria. Questa situazione può verificarsi per i motivi seguenti:<br /><br /> -L'ambito dei metadati è stato aperto con il `ofWrite` o `ofCopyMemory` flag.<br />-L'ambito dei metadati è stato aperto senza il `ofReadOnly` flag.<br />-il [IMetaDataDispenser](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) metodo utilizzato per aprire solo la parte dei metadati del file.<br />-Il file non è un file eseguibile portabile (PE). **Nota:**  Tali condizioni dipendono dall'implementazione CLR e sono probabilmente saranno ridotte nelle future versioni di CLR.|  
  
## <a name="remarks"></a>Note  
 La memoria che `ppvData` punti è valida solo finché è aperta nell'ambito dei metadati sottostanti.  
  
 Affinché il metodo funzioni, quando si esegue il mapping ai metadati di un file su disco in memoria chiamando la [IMetaDataDispenser::](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) metodo, è necessario specificare il `ofReadOnly` flag e non deve specificare il `ofWrite` o `ofCopyMemory` flag.  
  
 La scelta del tipo di mapping di file per ogni ambito è specifica per una determinata implementazione di CLR. Non può essere impostata dall'utente. Restituisce sempre l'implementazione corrente di CLR `fmFlat` in `pdwMappingType`, ma questo può cambiare nelle future versioni di CLR o future service release di una determinata versione. È consigliabile controllare sempre il valore restituito `pdwMappingType`, poiché tipi diversi disporranno di layout diversi e gli offset.  
  
 Non è possibile passare NULL per uno qualsiasi dei tre parametri. Il metodo restituisce `E_INVALIDARG`, e nessuno degli output viene riempito. Verrà ignorato il tipo di mapping o le dimensioni dell'area può comportare anomala del programma.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataInfo](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-interface.md)
- [Enumerazione CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md)
