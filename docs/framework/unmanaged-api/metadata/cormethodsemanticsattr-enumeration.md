---
title: Enumerazione CorMethodSemanticsAttr
ms.date: 03/30/2017
api_name:
- CorMethodSemanticsAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodSemanticsAttr
helpviewer_keywords:
- CorMethodSemanticsAttr enumeration [.NET Framework metadata]
ms.assetid: ca2af325-eb9d-4a91-90e4-267e45b98611
topic_type:
- apiref
ms.openlocfilehash: 1572c206f4a5a5fe0fd189ca84d0bcda2249c6d4
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007650"
---
# <a name="cormethodsemanticsattr-enumeration"></a>Enumerazione CorMethodSemanticsAttr
Contiene valori che descrivono la relazione tra un metodo e una proprietà o evento associato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum CorMethodSemanticsAttr {  
  
    msSetter    =   0x0001,  
    msGetter    =   0x0002,  
    msOther     =   0x0004,  
    msAddOn     =   0x0008,  
    msRemoveOn  =   0x0010,  
    msFire      =   0x0020,  
  
} CorMethodSemanticsAttr;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`msSetter`|Specifica che il metodo è una `set` funzione di accesso per una proprietà.|  
|`msGetter`|Specifica che il metodo è una `get` funzione di accesso per una proprietà.|  
|`msOther`|Specifica che il metodo ha una relazione con una proprietà o un evento diverso da quelli definiti qui.|  
|`msAddOn`|Specifica che il metodo aggiunge metodi di gestione per un evento.|  
|`msRemoveOn`|Specifica che il metodo rimuove i metodi del gestore per un evento.|  
|`msFire`|Specifica che il metodo genera un evento.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr. h  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](metadata-enumerations.md)
