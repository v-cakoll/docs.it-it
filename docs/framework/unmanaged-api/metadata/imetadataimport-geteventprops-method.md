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
ms.openlocfilehash: a9d156d7c7ada8309e501ba44720dfa285ce50d2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54552359"
---
# <a name="imetadataimportgeteventprops-method"></a>Metodo IMetaDataImport::GetEventProps
Ottiene le informazioni sui metadati per l'evento rappresentato dal token di evento specificato, incluso il tipo dichiarante, add e i metodi di installazione per i delegati, i flag e gli altri dati associati.  
  
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
 [in] Il token di metadati di evento che rappresenta l'evento per ottenere i metadati.  
  
 `pClass`  
 [out] Puntatore al token TypeDef che rappresenta la classe che dichiara l'evento.  
  
 `szEvent`  
 [out] Il nome dell'evento a cui fanno riferimento `ev`.  
  
 `pchEvent`  
 [in] La lunghezza in caratteri wide della richiesta `szEvent`.  
  
 `pdwEventFlags`  
 [out] La lunghezza in caratteri wide di restituita `szEvent`.  
  
 `ptkEventType`  
 [out] Un puntatore a oggetto TypeRef o TypeDef metadati token che rappresenta il <xref:System.Delegate> tipo dell'evento.  
  
 `pmdAddOn`  
 [out] Puntatore al token di metadati che rappresenta il metodo che aggiunge i gestori dell'evento.  
  
 `pmdRemoveOn`  
 [out] Puntatore al token di metadati che rappresenta il metodo che rimuove gestori dell'evento.  
  
 `pmdFire`  
 [out] Puntatore al token di metadati che rappresenta il metodo che genera l'evento.  
  
 `rmdOtherMethod`  
 [out] Una matrice di puntatori token agli altri metodi associati all'evento.  
  
 `cMax`  
 [in] Dimensione massima della matrice `rmdOtherMethod`.  
  
 `pcOtherMethod`  
 [out] Il numero di token restituito nel `rmdOtherMethod`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
