---
title: Enumerazione CorFieldAttr
ms.date: 03/30/2017
api_name:
- CorFieldAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorFieldAttr
helpviewer_keywords:
- CorFieldAttr enumeration [.NET Framework metadata]
ms.assetid: 6ae2c4be-212c-4e74-9288-40a11dc26522
topic_type:
- apiref
ms.openlocfilehash: dea69e18fc517eddddc5b99950a6f3b16ee3e426
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007403"
---
# <a name="corfieldattr-enumeration"></a>Enumerazione CorFieldAttr
Contiene valori che descrivono i metadati relativi a un campo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum CorFieldAttr {  
  
    fdFieldAccessMask           =   0x0007,  
    fdPrivateScope              =   0x0000,  
    fdPrivate                   =   0x0001,  
    fdFamANDAssem               =   0x0002,  
    fdAssembly                  =   0x0003,  
    fdFamily                    =   0x0004,  
    fdFamORAssem                =   0x0005,  
    fdPublic                    =   0x0006,  
  
    fdStatic                    =   0x0010,  
    fdInitOnly                  =   0x0020,  
    fdLiteral                   =   0x0040,  
    fdNotSerialized             =   0x0080,  
  
    fdSpecialName               =   0x0200,  
  
    fdPinvokeImpl               =   0x2000,  
  
    fdReservedMask              =   0x9500,  
    fdRTSpecialName             =   0x0400,  
    fdHasFieldMarshal           =   0x1000,  
    fdHasDefault                =   0x8000,  
    fdHasFieldRVA               =   0x0100  
  
} CorFieldAttr;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`fdFieldAccessMask`|Specifica le informazioni di accessibilità.|  
|`fdPrivateScope`|Specifica che non è possibile fare riferimento al campo.|  
|`fdPrivate`|Specifica che il campo è accessibile solo dal tipo padre.|  
|`fdFamANDAssem`|Specifica che il campo è accessibile dalle classi derivate nell'assembly.|  
|`fdAssembly`|Specifica che il campo è accessibile da tutti i tipi nell'assembly.|  
|`fdFamily`|Specifica che il campo è accessibile solo dal tipo e dalle classi derivate.|  
|`fdFamORAssem`|Specifica che il campo è accessibile dalle classi derivate e da tutti i tipi nell'assembly.|  
|`fdPublic`|Specifica che il campo è accessibile da tutti i tipi con visibilità di questo ambito.|  
|`fdStatic`|Specifica che il campo è un membro del tipo anziché di un membro di istanza.|  
|`fdInitOnly`|Specifica che il campo non può essere modificato dopo l'inizializzazione.|  
|`fdLiteral`|Specifica che il valore del campo è una costante in fase di compilazione.|  
|`fdNotSerialized`|Specifica che il campo non viene serializzato quando il tipo è remoto.|  
|`fdSpecialName`|Specifica che il campo è speciale e che il nome descrive come.|  
|`fdPinvokeImpl`|Specifica che l'implementazione del campo viene trasmessa tramite PInvoke.|  
|`fdReservedMask`|Riservato per uso interno da parte del Common Language Runtime.|  
|`fdRTSpecialName`|Specifica che le API interne dei metadati di Common Language Runtime devono verificare la codifica del nome.|  
|`fdHasFieldMarshal`|Specifica che il campo contiene informazioni di marshalling.|  
|`fdHasDefault`|Specifica che il campo ha un valore predefinito.|  
|`fdHasFieldRVA`|Specifica che il campo dispone di un indirizzo virtuale relativo.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr. h  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](metadata-enumerations.md)
