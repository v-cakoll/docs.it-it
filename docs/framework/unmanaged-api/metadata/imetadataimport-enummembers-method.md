---
title: Metodo IMetaDataImport::EnumMembers
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMembers
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMembers
helpviewer_keywords:
- IMetaDataImport::EnumMembers method [.NET Framework metadata]
- EnumMembers method [.NET Framework metadata]
ms.assetid: 3fb8e178-342b-4c89-9bcf-f7f834e6cb77
topic_type:
- apiref
ms.openlocfilehash: cc3bc5140da0634b5172f6253de3de37bff487f1
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492034"
---
# <a name="imetadataimportenummembers-method"></a>Metodo IMetaDataImport::EnumMembers
Enumera i token MemberDef che rappresentano i membri del tipo specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT EnumMembers (
   [in, out]  HCORENUM    *phEnum,
   [in]  mdTypeDef   cl,
   [out] mdToken     rMembers[],
   [in]  ULONG       cMax,
   [out] ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `phEnum`  
 [in, out] Puntatore all'enumeratore.  
  
 `cl`  
 in Token TypeDef che rappresenta il tipo di cui è necessario enumerare i membri.  
  
 `rMembers`  
 out Matrice utilizzata per conservare i token MemberDef.  
  
 `cMax`  
 [in] Dimensione massima della matrice `rMembers`.  
  
 `pcTokens`  
 out Numero effettivo di token MemberDef restituiti in `rMembers` .  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|`S_OK`|`EnumMembers`la restituzione è riuscita.|  
|`S_FALSE`|Nessun token MemberDef da enumerare. In tal caso, `pcTokens` è zero.|  
  
## <a name="remarks"></a>Osservazioni  
 Quando si enumerano raccolte di membri per una classe, `EnumMembers` restituisce solo i membri (campi e metodi, ma **non** le proprietà o gli eventi) definiti direttamente nella classe. Non restituisce i membri ereditati dalla classe, anche se la classe fornisce un'implementazione per i membri ereditati. Per enumerare i membri ereditati, il chiamante deve esaminare in modo esplicito la catena di ereditarietà. Si noti che le regole per la catena di ereditarietà possono variare a seconda del linguaggio o del compilatore che ha emesso i metadati originali.

 Proprietà ed eventi non vengono enumerati da `EnumMembers` . Per enumerare tali, utilizzare [EnumProperties](imetadataimport-enumproperties-method.md) o [EnumEvents](imetadataimport-enumevents-method.md).
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](imetadataimport2-interface.md)
