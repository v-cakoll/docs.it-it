---
title: Interfaccia IMetaDataFilter
ms.date: 03/30/2017
api_name:
- IMetaDataFilter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataFilter
helpviewer_keywords:
- IMetaDataFilter interface [.NET Framework metadata]
ms.assetid: ec0856ef-8c56-40ba-bf60-86e0ce8b337f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ad77aba02c819749794534ca2ecd478661bc363f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444981"
---
# <a name="imetadatafilter-interface"></a>Interfaccia IMetaDataFilter
Fornisce metodi per contrassegnare e filtrare i token di metadati per evitare la ripetizione di azioni che sono già state eseguite.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo IsTokenMarked](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-istokenmarked-method.md)|Ottiene un valore che indica se il token di metadati specificato è stato elaborato.|  
|[Metodo MarkToken](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-marktoken-method.md)|Imposta un valore che indica che il token di metadati specificato è stato elaborato.|  
|[Metodo UnmarkAll](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-unmarkall-method.md)|Rimuove gli indicatori di elaborazione da tutti i token nell'ambito dei metadati corrente.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
