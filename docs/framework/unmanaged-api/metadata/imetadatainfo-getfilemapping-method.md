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
ms.openlocfilehash: 0f5bdf97132c05e765cd6fa423a19bb996105d28
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175265"
---
# <a name="imetadatainfogetfilemapping-method"></a>Metodo IMetaDataInfo::GetFileMapping
Ottiene l'area di memoria del file mappato e il tipo di mapping.  
  
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
 out Puntatore all'inizio del file mappato.  
  
 `pcbData`  
 out Dimensioni dell'area mappata. Se `pdwMappingType` è `fmFlat`, si tratta della dimensione del file.  
  
 `pdwMappingType`  
 out Valore [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) che indica il tipo di mapping. L'implementazione corrente del Common Language Runtime (CLR) restituisce `fmFlat`sempre. Altri valori sono riservati per utilizzi futuri. Tuttavia, è sempre necessario verificare il valore restituito, perché gli altri valori possono essere abilitati nelle versioni future o nei rilasci del servizio.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Description|  
|-------------|-----------------|  
|`S_OK`|Tutti gli output sono pieni.|  
|`E_INVALIDARG`|NULL è stato passato come valore dell'argomento.|  
|`COR_E_NOTSUPPORTED`|L'implementazione CLR non è in grado di fornire informazioni sull'area di memoria. Ciò può verificarsi per i seguenti motivi:<br /><br /> -L'ambito dei metadati è stato aperto `ofWrite` con `ofCopyMemory` il flag o.<br />-L'ambito dei metadati è stato aperto `ofReadOnly` senza il flag.<br />-Il metodo [IMetaDataDispenser:: OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) è stato usato per aprire solo la parte di metadati del file.<br />-Il file non è un file eseguibile portabile (PE). **Nota:**  Queste condizioni dipendono dall'implementazione di CLR e probabilmente verranno indebolite nelle versioni future di CLR.|  
  
## <a name="remarks"></a>Osservazioni  
 La memoria a `ppvData` cui punta è valida solo fino a quando l'ambito dei metadati sottostante è aperto.  
  
 Per consentire il funzionamento di questo metodo, quando si esegue il mapping dei metadati di un file su disco in memoria chiamando il metodo [IMetaDataDispenser:: OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) , è necessario specificare il `ofReadOnly` flag e non è necessario specificare il `ofWrite` flag `ofCopyMemory` o.  
  
 La scelta del tipo di mapping dei file per ogni ambito è specifica di una determinata implementazione di CLR. Non può essere impostata dall'utente. L'implementazione corrente di CLR restituisce `fmFlat` sempre in `pdwMappingType`, ma può cambiare nelle versioni future di CLR o nelle versioni future del servizio di una determinata versione. È consigliabile controllare sempre il valore restituito in `pdwMappingType`, perché tipi diversi avranno layout e offset diversi.  
  
 Il passaggio di un valore NULL per uno dei tre parametri non è supportato. Il metodo restituisce `E_INVALIDARG`e nessuno degli output viene compilato. Ignorando il tipo di mapping o la dimensione dell'area può verificarsi una chiusura anomala del programma.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedi anche

- [Interfaccia IMetaDataInfo](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-interface.md)
- [Enumerazione CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md)
