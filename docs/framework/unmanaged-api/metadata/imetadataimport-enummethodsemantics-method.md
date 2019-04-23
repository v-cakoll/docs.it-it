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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 16cfa6df6251cd67860155cb8092e77a835eaaef
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59223270"
---
# <a name="imetadataimportenummethodsemantics-method"></a>Metodo IMetaDataImport::EnumMethodSemantics
Enumera le proprietà e gli eventi di modifica delle proprietà a cui è correlato il metodo specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
 [in, out] Un puntatore all'enumeratore. Per la prima chiamata di questo metodo deve essere NULL.  
  
 `mb`  
 [in] Token MethodDef che limita l'ambito dell'enumerazione.  
  
 `rEventProp`  
 [out] Matrice utilizzata per archiviare le proprietà o eventi.  
  
 `cMax`  
 [in] Dimensione massima della matrice `rEventProp`.  
  
 `pcEventProp`  
 [out] Il numero di eventi o proprietà restituite `rEventProp`.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|`S_OK`|`EnumMethodSemantics` stato restituito correttamente.|  
|`S_FALSE`|Non esistono eventi o proprietà da enumerare. In tal caso, `pcEventProp` è uguale a zero.|  
  
## <a name="remarks"></a>Note  
 Molti tipi di common language runtime definiscono *proprietà* `Changed` eventi e `On` *proprietà* `Changed` metodi correlati nelle relative proprietà. Ad esempio, il <xref:System.Windows.Forms.Control?displayProperty=nameWithType> tipo definisce un <xref:System.Windows.Forms.Control.Font%2A> proprietà, un <xref:System.Windows.Forms.Control.FontChanged> evento e un <xref:System.Windows.Forms.Control.OnFontChanged%2A> (metodo). Il metodo della funzione di accesso set della <xref:System.Windows.Forms.Control.Font%2A> proprietà chiamate <xref:System.Windows.Forms.Control.OnFontChanged%2A> metodo, che a sua volta genera il <xref:System.Windows.Forms.Control.FontChanged> evento. È necessario chiamare `EnumMethodSemantics` utilizzando MethodDef per <xref:System.Windows.Forms.Control.OnFontChanged%2A> per ottenere riferimenti al <xref:System.Windows.Forms.Control.Font%2A> proprietà e il <xref:System.Windows.Forms.Control.FontChanged> evento.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
