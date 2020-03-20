---
title: Metodo IMetaDataConverter::GetMetaDataFromTypeLib
ms.date: 03/30/2017
api_name:
- IMetaDataConverter.GetMetaDataFromTypeLib
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter::GetMetaDataFromTypeLib
helpviewer_keywords:
- IMetaDataConverter::GetMetaDataFromTypeLib method [.NET Framework metadata]
- GetMetaDataFromTypeLib method [.NET Framework metadata]
ms.assetid: 97dc3a56-adfa-431f-889e-06a35ac84d51
topic_type:
- apiref
ms.openlocfilehash: 09a1605deda5b51be604c3b8f0c69fa5adcf9dc0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175954"
---
# <a name="imetadataconvertergetmetadatafromtypelib-method"></a>Metodo IMetaDataConverter::GetMetaDataFromTypeLib
Ottiene un puntatore a interfaccia a [un'istanza iMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) che `ITypeLib` rappresenta la firma dei metadati della libreria dei tipi rappresentata dall'istanza specificata.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetMetaDataFromTypeLib (  
    [in]  ITypeLib        *pITL,
    [out] IMetaDataImport **ppMDI  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pITL`  
 [in] Puntatore `ITypeLib` a un oggetto che rappresenta la libreria dei tipi.  
  
 `ppMDI`  
 [fuori] Puntatore a una posizione che `IMetaDataImport` riceve l'indirizzo dell'istanza che rappresenta la firma dei metadati.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforma:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor.h  
  
 **Biblioteca:** Utilizzato come risorsa in MsCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
