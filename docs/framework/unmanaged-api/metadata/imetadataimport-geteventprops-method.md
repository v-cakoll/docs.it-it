---
title: Metodo IMetaDataImport::GetEventProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetEventProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetEventProps
helpviewer_keywords:
- IMetaDataImport::GetEventProps method [.NET Framework metadata]
- GetEventProps method [.NET Framework metadata]
ms.assetid: 5eaf3b4a-92b7-4d5b-97e0-1e83721e0052
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6ac1ecb73257782888c963082953ed243177a86b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataimportgeteventprops-method"></a>Metodo IMetaDataImport::GetEventProps
Ottiene informazioni sui metadati per l'evento rappresentato dal token specificato, inclusi il tipo dichiarante, add e Remove per delegati e i flag e altri dati associati.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetEventProps (  
   [in]  mdEvent       ev,  
   [out] mdTypeDef     *pClass,   
   [out] LPCWSTR       szEvent,   
   [in]  ULONG         cchEvent,   
   [out] ULONG         *pchEvent,   
   [out] DWORD         *pdwEventFlags,  
   [out] mdToken       *ptkEventType,  
   [out] mdMethodDef   *pmdAddOn,   
   [out] mdMethodDef   *pmdRemoveOn,   
   [out] mdMethodDef   *pmdFire,   
   [out] mdMethodDef   rmdOtherMethod[],   
   [in]  ULONG         cMax,  
   [out] ULONG         *pcOtherMethod  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `ev`  
 [in] Token di metadati che rappresenta l'evento per ottenere i metadati.  
  
 `pClass`  
 [out] Un puntatore al token TypeDef che rappresenta la classe che dichiara l'evento.  
  
 `szEvent`  
 [out] Il nome dell'evento a cui fa riferimento `ev`.  
  
 `pchEvent`  
 [in] La lunghezza in caratteri wide della richiesta `szEvent`.  
  
 `pdwEventFlags`  
 [out] La lunghezza restituita in caratteri wide di `szEvent`.  
  
 `ptkEventType`  
 [out] Un puntatore a un TypeRef o TypeDef metadati token che rappresenta il <xref:System.Delegate> tipo dell'evento.  
  
 `pmdAddOn`  
 [out] Puntatore al token di metadati che rappresenta il metodo che consente di aggiungere gestori eventi per l'evento.  
  
 `pmdRemoveOn`  
 [out] Puntatore al token di metadati che rappresenta il metodo rimuove i gestori per l'evento.  
  
 `pmdFire`  
 [out] Puntatore al token di metadati che rappresenta il metodo che genera l'evento.  
  
 `rmdOtherMethod`  
 [out] Una matrice di puntatori token ad altri metodi associati all'evento.  
  
 `cMax`  
 [in] Dimensione massima della matrice `rmdOtherMethod`.  
  
 `pcOtherMethod`  
 [out] Il numero di token restituiti in `rmdOtherMethod`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
