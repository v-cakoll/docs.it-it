---
title: Metodo IMetaDataDispenserEx::GetOption
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.GetOption
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::GetOption
helpviewer_keywords:
- GetOption method [.NET Framework metadata]
- IMetaDataDispenserEx::GetOption method [.NET Framework metadata]
ms.assetid: d7f794e5-8e25-4d65-850a-7c34fbfce87d
topic_type:
- apiref
ms.openlocfilehash: 832adacac4a6df9ccf21578538a1c557150f3ba1
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008781"
---
# <a name="imetadatadispenserexgetoption-method"></a>Metodo IMetaDataDispenserEx::GetOption
Ottiene il valore dell'opzione specificata per l'ambito dei metadati corrente. L'opzione consente di controllare il modo in cui vengono gestite le chiamate all'ambito dei metadati corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetOption (  
    [in]  REFGUID         optionId,
    [out] const VARIANT   *pValue  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `optionId`  
 in Puntatore a un GUID che specifica l'opzione da recuperare. Vedere la sezione Osservazioni per un elenco di GUID supportati.  
  
 `pValue`  
 out Valore dell'opzione restituita. Il tipo di questo valore sarà una variante del tipo dell'opzione specificata.  
  
## <a name="remarks"></a>Commenti  
 Nell'elenco seguente sono illustrati i GUID supportati per questo metodo. Per le descrizioni, vedere il metodo [IMetaDataDispenserEx:: SetOption](imetadatadispenserex-setoption-method.md) . Se `optionId` non è presente nell'elenco, questo metodo restituisce HRESULT `E_INVALIDARG` , che indica un parametro errato.  
  
- MetaDataCheckDuplicatesFor  
  
- MetaDataRefToDefCheck  
  
- MetaDataNotificationForTokenMovement  
  
- MetaDataSetENC  
  
- MetaDataErrorIfEmitOutOfOrder  
  
- MetaDataGenerateTCEAdapters  
  
- MetaDataLinkerOptions  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforma:** Vedere [requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataDispenserEx](imetadatadispenserex-interface.md)
- [Interfaccia IMetaDataDispenser](imetadatadispenser-interface.md)
