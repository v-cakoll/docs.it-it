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
ms.openlocfilehash: 3b47d1559300a462ccda42bc88da43f66c1043ec
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491303"
---
# <a name="imetadataimportgeteventprops-method"></a>Metodo IMetaDataImport::GetEventProps
Ottiene le informazioni sui metadati per l'evento rappresentato dal token di evento specificato, inclusi il tipo dichiarante, i metodi di aggiunta e rimozione per i delegati e tutti i flag e altri dati associati.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
  
## <a name="parameters"></a>Parametri  
 `ev`  
 in Token di metadati dell'evento che rappresenta l'evento per il quale ottenere i metadati.  
  
 `pClass`  
 out Puntatore al token TypeDef che rappresenta la classe che dichiara l'evento.  
  
 `szEvent`  
 out Nome dell'evento a cui fa riferimento `ev` .  
  
 `pchEvent`  
 in Lunghezza richiesta in caratteri wide di `szEvent` .  
  
 `pdwEventFlags`  
 out Lunghezza restituita in caratteri wide di `szEvent` .  
  
 `ptkEventType`  
 out Puntatore a un token di metadati TypeRef o TypeDef che rappresenta il <xref:System.Delegate> tipo dell'evento.  
  
 `pmdAddOn`  
 out Puntatore al token di metadati che rappresenta il metodo che aggiunge gestori per l'evento.  
  
 `pmdRemoveOn`  
 out Puntatore al token di metadati che rappresenta il metodo che rimuove i gestori per l'evento.  
  
 `pmdFire`  
 out Puntatore al token di metadati che rappresenta il metodo che genera l'evento.  
  
 `rmdOtherMethod`  
 out Matrice di puntatori del token ad altri metodi associati all'evento.  
  
 `cMax`  
 [in] Dimensione massima della matrice `rmdOtherMethod`.  
  
 `pcOtherMethod`  
 out Numero di token restituiti in `rmdOtherMethod` .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](imetadataimport2-interface.md)
