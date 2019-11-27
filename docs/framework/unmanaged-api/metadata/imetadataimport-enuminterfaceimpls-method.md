---
title: Metodo IMetaDataImport::EnumInterfaceImpls
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumInterfaceImpls
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumInterfaceImpls
helpviewer_keywords:
- IMetaDataImport::EnumInterfaceImpls method [.NET Framework metadata]
- EnumInterfaceImpls method [.NET Framework metadata]
ms.assetid: ba6e178f-128b-4e47-a13c-b4be73eb106c
topic_type:
- apiref
ms.openlocfilehash: 4c819bff50e6644a733374e9863d670d3323ee68
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449529"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a>Metodo IMetaDataImport::EnumInterfaceImpls
Enumera tutte le interfacce implementate dal `TypeDef`specificato. 
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,   
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],   
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `phEnum`  
 [in, out] Puntatore all'enumeratore.  
  
 `td`  
 in Token del TypeDef i cui token MethodDef che rappresentano le implementazioni dell'interfaccia devono essere enumerati.  
  
 `rImpls`  
 out Matrice utilizzata per archiviare i token MethodDef.  
  
 `cMax`  
 [in] Dimensione massima della matrice `rImpls`.  
  
 `pcImpls`  
 out Numero effettivo di token restituiti in `rImpls`.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|`S_OK`|`EnumInterfaceImpls` ha restituito un esito positivo.|  
|`S_FALSE`|Nessun token MethodDef da enumerare. In tal caso, `pcImpls` è impostato su zero.|  

## <a name="remarks"></a>Osservazioni

L'enumerazione restituisce una raccolta di token di `mdInterfaceImpl` per ogni interfaccia implementata dalla `TypeDef`specificata. I token di interfaccia vengono restituiti nell'ordine in cui sono state specificate le interfacce (tramite `DefineTypeDef` o `SetTypeDefProps`). È possibile eseguire query sulle proprietà dei token `mdInterfaceImpl` restituiti usando [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md).
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
