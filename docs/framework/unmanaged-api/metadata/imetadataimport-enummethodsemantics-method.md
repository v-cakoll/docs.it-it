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
ms.openlocfilehash: f20652a7f86576e64646a1f63c3e2c48b55cf811
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175460"
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
 [in] Token MethodDef che limita l'ambito dell'enumerazione.  
  
 `rEventProp`  
 [fuori] Matrice utilizzata per archiviare gli eventi o le proprietà.  
  
 `cMax`  
 [in] Dimensione massima della matrice `rEventProp`.  
  
 `pcEventProp`  
 [fuori] Numero di eventi o proprietà `rEventProp`restituiti in .  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|`S_OK`|`EnumMethodSemantics`restituito con successo.|  
|`S_FALSE`|Non sono presenti eventi o proprietà da enumerare. In tal `pcEventProp` caso, è zero.|  
  
## <a name="remarks"></a>Osservazioni  
 Molti tipi di Common Language `On`Runtime definiscono gli eventi *Property* `Changed` e i metodi *Property* `Changed` correlati alle relative proprietà. Ad esempio, <xref:System.Windows.Forms.Control?displayProperty=nameWithType> il tipo <xref:System.Windows.Forms.Control.Font%2A> definisce <xref:System.Windows.Forms.Control.FontChanged> una proprietà, un evento e un <xref:System.Windows.Forms.Control.OnFontChanged%2A> metodo. Il metodo della funzione <xref:System.Windows.Forms.Control.Font%2A> di <xref:System.Windows.Forms.Control.OnFontChanged%2A> accesso set della <xref:System.Windows.Forms.Control.FontChanged> proprietà chiama il metodo, che a sua volta genera l'evento. È necessario `EnumMethodSemantics` chiamare utilizzando <xref:System.Windows.Forms.Control.OnFontChanged%2A> MethodDef per <xref:System.Windows.Forms.Control.Font%2A> ottenere riferimenti <xref:System.Windows.Forms.Control.FontChanged> alla proprietà e all'evento.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor.h  
  
 **Biblioteca:** Incluso come risorsa in MsCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
