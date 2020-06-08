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
ms.openlocfilehash: 910c40413075131765a37e00703ac892e3f39641
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492200"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a>Metodo IMetaDataImport::EnumInterfaceImpls
Enumera tutte le interfacce implementate dall'oggetto specificato `TypeDef` .
  
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
 in Lunghezza massima della `rImpls` matrice.  
  
 `pcImpls`  
 out Numero effettivo di token restituiti in `rImpls` .  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|`S_OK`|`EnumInterfaceImpls`la restituzione è riuscita.|  
|`S_FALSE`|Nessun token MethodDef da enumerare. In tal caso, `pcImpls` è impostato su zero.|  

## <a name="remarks"></a>Osservazioni

L'enumerazione restituisce una raccolta di `mdInterfaceImpl` token per ogni interfaccia implementata dall'oggetto specificato `TypeDef` . I token di interfaccia vengono restituiti nell'ordine in cui sono state specificate le interfacce (tramite `DefineTypeDef` o `SetTypeDefProps` ). `mdInterfaceImpl`È possibile eseguire query sulle proprietà dei token restituiti usando [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md).
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](imetadataimport2-interface.md)
