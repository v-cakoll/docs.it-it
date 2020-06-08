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
ms.openlocfilehash: 213cbd955e3d47a49abde579a54af48641e225ec
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491914"
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
 out Numero di eventi o proprietà restituiti in `rEventProp` .  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|`S_OK`|`EnumMethodSemantics`la restituzione è riuscita.|  
|`S_FALSE`|Nessun evento o proprietà da enumerare. In tal caso, `pcEventProp` è zero.|  
  
## <a name="remarks"></a>Osservazioni  
 Molti tipi di Common Language Runtime *definiscono* `Changed` gli eventi e `On` *Property* `Changed` i metodi delle proprietà correlati alle relative proprietà. Il tipo, ad esempio, <xref:System.Windows.Forms.Control?displayProperty=nameWithType> definisce una <xref:System.Windows.Forms.Control.Font%2A> proprietà, un <xref:System.Windows.Forms.Control.FontChanged> evento e un <xref:System.Windows.Forms.Control.OnFontChanged%2A> metodo. Il metodo della funzione di accesso set della <xref:System.Windows.Forms.Control.Font%2A> proprietà chiama il <xref:System.Windows.Forms.Control.OnFontChanged%2A> metodo, che a sua volta genera l' <xref:System.Windows.Forms.Control.FontChanged> evento. È possibile chiamare `EnumMethodSemantics` utilizzando MethodDef per per <xref:System.Windows.Forms.Control.OnFontChanged%2A> ottenere riferimenti alla <xref:System.Windows.Forms.Control.Font%2A> proprietà e all' <xref:System.Windows.Forms.Control.FontChanged> evento.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](imetadataimport2-interface.md)
