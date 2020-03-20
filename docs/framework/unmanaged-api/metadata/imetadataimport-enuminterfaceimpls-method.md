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
ms.openlocfilehash: b535fdd5027a26cc4dd0eafec9883f0186773dd1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175499"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a>Metodo IMetaDataImport::EnumInterfaceImpls
Enumera tutte le interfacce `TypeDef`implementate dall'oggetto specificato.
  
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
 [in] Token del TypeDef i cui token MethodDef rappresentano le implementazioni dell'interfaccia devono essere enumerati.  
  
 `rImpls`  
 [fuori] Matrice utilizzata per archiviare i token MethodDef.  
  
 `cMax`  
 [in] Lunghezza massima della `rImpls` matrice.  
  
 `pcImpls`  
 [fuori] Numero effettivo di token restituiti in `rImpls`.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|`S_OK`|`EnumInterfaceImpls`restituito con successo.|  
|`S_FALSE`|Non sono presenti token MethodDef da enumerare. In tal `pcImpls` caso, è impostato su zero.|  

## <a name="remarks"></a>Osservazioni

L'enumerazione restituisce una raccolta di `mdInterfaceImpl` token `TypeDef`per ogni interfaccia implementata dall'oggetto specificato. I token di interfaccia vengono restituiti nell'ordine `DefineTypeDef` `SetTypeDefProps`in cui sono state specificate le interfacce (tramite o ). È possibile eseguire `mdInterfaceImpl` una query sulle proprietà dei token restituiti utilizzando [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md).
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor.h  
  
 **Biblioteca:** Incluso come risorsa in MsCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
