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
ms.openlocfilehash: 5ef5d9ae3da4dff13a461162f0ba3466d3d8192c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501261"
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
 out Dimensioni dell'area mappata. Se `pdwMappingType` è `fmFlat` , si tratta della dimensione del file.  
  
 `pdwMappingType`  
 out Valore [CorFileMapping](corfilemapping-enumeration.md) che indica il tipo di mapping. L'implementazione corrente del Common Language Runtime (CLR) restituisce sempre `fmFlat` . Altri valori sono riservati per utilizzi futuri. Tuttavia, è sempre necessario verificare il valore restituito, perché gli altri valori possono essere abilitati nelle versioni future o nei rilasci del servizio.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|`S_OK`|Tutti gli output sono pieni.|  
|`E_INVALIDARG`|NULL è stato passato come valore dell'argomento.|  
|`COR_E_NOTSUPPORTED`|L'implementazione CLR non è in grado di fornire informazioni sull'area di memoria. Ciò può verificarsi per i seguenti motivi:<br /><br /> -L'ambito dei metadati è stato aperto con il `ofWrite` `ofCopyMemory` flag o.<br />-L'ambito dei metadati è stato aperto senza il `ofReadOnly` flag.<br />-Il metodo [IMetaDataDispenser:: OpenScopeOnMemory](imetadatadispenser-openscopeonmemory-method.md) è stato usato per aprire solo la parte di metadati del file.<br />-Il file non è un file eseguibile portabile (PE). **Nota:**  Queste condizioni dipendono dall'implementazione di CLR e probabilmente verranno indebolite nelle versioni future di CLR.|  
  
## <a name="remarks"></a>Osservazioni  
 La memoria `ppvData` a cui punta è valida solo fino a quando l'ambito dei metadati sottostante è aperto.  
  
 Per consentire il funzionamento di questo metodo, quando si esegue il mapping dei metadati di un file su disco in memoria chiamando il metodo [IMetaDataDispenser:: OpenScope](imetadatadispenser-openscope-method.md) , è necessario specificare il `ofReadOnly` flag e non è necessario specificare il `ofWrite` `ofCopyMemory` flag o.  
  
 La scelta del tipo di mapping dei file per ogni ambito è specifica di una determinata implementazione di CLR. Non può essere impostata dall'utente. L'implementazione corrente di CLR restituisce sempre `fmFlat` in `pdwMappingType` , ma può cambiare nelle versioni future di CLR o nelle versioni future del servizio di una determinata versione. È consigliabile controllare sempre il valore restituito in `pdwMappingType` , perché tipi diversi avranno layout e offset diversi.  
  
 Il passaggio di un valore NULL per uno dei tre parametri non è supportato. Il metodo restituisce `E_INVALIDARG` e nessuno degli output viene compilato. Ignorando il tipo di mapping o la dimensione dell'area può verificarsi una chiusura anomala del programma.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataInfo](imetadatainfo-interface.md)
- [Enumerazione CorFileMapping](corfilemapping-enumeration.md)
