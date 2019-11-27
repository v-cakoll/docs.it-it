---
title: Metodo IMetaDataImport::EnumMethodSemantics
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethodSemantics
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodSemantics
helpviewer_keywords:
- EnumMethodSemantics method [.NET Framework metadata]
- IMetaDataImport::EnumMethodSemantics method [.NET Framework metadata]
ms.assetid: e7e3c630-9691-46d6-94df-b5593a7bb08a
topic_type:
- apiref
ms.openlocfilehash: ff6932b6040a19e0ccda2f8d2140fa131cdd9224
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450072"
---
# <a name="imetadataimportenummethodsemantics-method"></a>Metodo IMetaDataImport::EnumMethodSemantics
Enumera le proprietà e gli eventi di modifica delle proprietà a cui è correlato il metodo specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT EnumMethodSemantics (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,   
   [out] mdToken         rEventProp[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcEventProp  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `phEnum`  
 [in, out] Puntatore all'enumeratore. Deve essere NULL per la prima chiamata di questo metodo.  
  
 `mb`  
 in Token MethodDef che limita l'ambito dell'enumerazione.  
  
 `rEventProp`  
 out Matrice utilizzata per archiviare gli eventi o le proprietà.  
  
 `cMax`  
 [in] Dimensione massima della matrice `rEventProp`.  
  
 `pcEventProp`  
 out Numero di eventi o proprietà restituiti in `rEventProp`.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|`S_OK`|`EnumMethodSemantics` ha restituito un esito positivo.|  
|`S_FALSE`|Nessun evento o proprietà da enumerare. In tal caso, `pcEventProp` è zero.|  
  
## <a name="remarks"></a>Note  
 Molti tipi di Common Language Runtime definiscono gli eventi`Changed` della *Proprietà* e `On`metodi`Changed` di *Proprietà* correlati alle relative proprietà. Ad esempio, il tipo di <xref:System.Windows.Forms.Control?displayProperty=nameWithType> definisce una proprietà <xref:System.Windows.Forms.Control.Font%2A>, un evento <xref:System.Windows.Forms.Control.FontChanged> e un metodo <xref:System.Windows.Forms.Control.OnFontChanged%2A>. Il metodo della funzione di accesso set della proprietà <xref:System.Windows.Forms.Control.Font%2A> chiama <xref:System.Windows.Forms.Control.OnFontChanged%2A> metodo, che a sua volta genera l'evento <xref:System.Windows.Forms.Control.FontChanged>. È possibile chiamare `EnumMethodSemantics` usando MethodDef per <xref:System.Windows.Forms.Control.OnFontChanged%2A> per ottenere riferimenti alla proprietà <xref:System.Windows.Forms.Control.Font%2A> e all'evento <xref:System.Windows.Forms.Control.FontChanged>.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
