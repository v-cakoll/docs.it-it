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
ms.openlocfilehash: 306c1748b4997309ee15fb7751bc818b0287aaf0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177261"
---
# <a name="imetadataimportgeteventprops-method"></a>Metodo IMetaDataImport::GetEventProps
Ottiene informazioni sui metadati per l'evento rappresentato dal token di evento specificato, inclusi il tipo dichiarante, i metodi di aggiunta e rimozione per i delegati ed eventuali flag e altri dati associati.  
  
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
 [in] Token dei metadati dell'evento che rappresenta l'evento per cui ottenere i metadati.  
  
 `pClass`  
 [fuori] Puntatore al token TypeDef che rappresenta la classe che dichiara l'evento.  
  
 `szEvent`  
 [fuori] Nome dell'evento a `ev`cui fa riferimento .  
  
 `pchEvent`  
 [in] Lunghezza richiesta in caratteri `szEvent`di tipo "wide" di .  
  
 `pdwEventFlags`  
 [fuori] Lunghezza restituita in caratteri `szEvent`di tipo "wide" di .  
  
 `ptkEventType`  
 [fuori] Puntatore a un token di metadati <xref:System.Delegate> TypeRef o TypeDef che rappresenta il tipo dell'evento.  
  
 `pmdAddOn`  
 [fuori] Puntatore al token di metadati che rappresenta il metodo che aggiunge gestori per l'evento.  
  
 `pmdRemoveOn`  
 [fuori] Puntatore al token di metadati che rappresenta il metodo che rimuove i gestori per l'evento.  
  
 `pmdFire`  
 [fuori] Puntatore al token di metadati che rappresenta il metodo che genera l'evento.  
  
 `rmdOtherMethod`  
 [fuori] Matrice di puntatori token ad altri metodi associati all'evento.  
  
 `cMax`  
 [in] Dimensione massima della matrice `rmdOtherMethod`.  
  
 `pcOtherMethod`  
 [fuori] Numero di token restituiti `rmdOtherMethod`in .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor.h  
  
 **Biblioteca:** Incluso come risorsa in MsCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
