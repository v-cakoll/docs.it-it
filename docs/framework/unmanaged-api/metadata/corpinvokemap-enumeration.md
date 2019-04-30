---
title: Enumerazione CorPinvokeMap
ms.date: 03/30/2017
api_name:
- CorPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPinvokeMap
helpviewer_keywords:
- CorPinvokeMap enumeration [.NET Framework metadata]
ms.assetid: f14f986e-f6ce-42bc-aa23-18150c46d28c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 951941092f67f66c5b17c8ae592569c2a8e6a675
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045396"
---
# <a name="corpinvokemap-enumeration"></a>Enumerazione CorPinvokeMap
Specifica le opzioni per una chiamata PInvoke.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum  CorPinvokeMap {  
  
    pmNoMangle          = 0x0001,  
  
    pmCharSetMask       = 0x0006,  
    pmCharSetNotSpec    = 0x0000,  
    pmCharSetAnsi       = 0x0002,  
    pmCharSetUnicode    = 0x0004,  
    pmCharSetAuto       = 0x0006,  
  
    pmBestFitUseAssem   = 0x0000,  
    pmBestFitEnabled    = 0x0010,  
    pmBestFitDisabled   = 0x0020,  
    pmBestFitMask       = 0x0030,  
  
    pmThrowOnUnmappableCharUseAssem   = 0x0000,  
    pmThrowOnUnmappableCharEnabled    = 0x1000,  
    pmThrowOnUnmappableCharDisabled   = 0x2000,  
    pmThrowOnUnmappableCharMask       = 0x3000,  
  
    pmSupportsLastError = 0x0040,   
  
    pmCallConvMask      = 0x0700,  
    pmCallConvWinapi    = 0x0100,  
    pmCallConvCdecl     = 0x0200,  
    pmCallConvStdcall   = 0x0300,  
    pmCallConvThiscall  = 0x0400,  
    pmCallConvFastcall  = 0x0500,  
  
    pmMaxValue          = 0xFFFF  
  
} CorPinvokeMap;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`pmNoMangle`|Usare ogni nome di membro specificate.|  
|`pmCharSetMask`|Riservato.|  
|`pmCharSetNotSpec`|Riservato.|  
|`pmCharSetAnsi`|Eseguire il marshalling di stringhe come stringhe di caratteri a byte multiplo.|  
|`pmCharSetUnicode`|Eseguire il marshalling di stringhe come caratteri Unicode a 2 byte.|  
|`pmCharSetAuto`|Eseguire automaticamente il marshalling di stringhe in modo appropriato per il sistema operativo di destinazione. Il valore predefinito è Unicode su Windows NT, Windows 2000, Windows XP e in Windows Server 2003; l'impostazione predefinita è ANSI in Windows 98 e Windows Me.|  
|`pmBestFitUseAssem`|Riservato.|  
|`pmBestFitEnabled`|Eseguire il mapping di caratteri Unicode che non dispongono di una corrispondenza esatta nel set di caratteri ANSI.|  
|`pmBestFitDisabled`|Non eseguire il mapping di caratteri Unicode. In questo caso, tutti i caratteri verranno sostituiti da un '?'.|  
|`pmBestFitMask`|Riservato.|  
|`pmThrowOnUnmappableCharUseAssem`|Riservato.|  
|`pmThrowOnUnmappableCharEnabled`|Generare un'eccezione durante il marshalling di interoperabilità rileva un carattere possibile eseguire il mapping.|  
|`pmThrowOnUnmappableCharDisabled`|Non generare un'eccezione durante il marshalling di interoperabilità rileva un carattere possibile eseguire il mapping.|  
|`pmThrowOnUnmappableCharMask`|Riservata|  
|`pmSupportsLastError`|Consentire al chiamato di chiamare Win32 `SetLastError` funzione prima di restituire il metodo con attributi.|  
|`pmCallConvMask`|Riservata|  
|`pmCallConvWinapi`|Usare la piattaforma predefinita la convenzione di chiamata. In Windows, ad esempio, il valore predefinito è `StdCall` e su Windows CE .NET è `Cdecl`.|  
|`pmCallConvCdecl`|Usare il `Cdecl` convenzione di chiamata. In questo caso, il chiamante esegue la pulizia dello stack. Questa operazione attiva funzioni chiamanti con `varargs` (vale a dire, le funzioni che accettano un numero variabile di parametri).|  
|`pmCallConvStdcall`|Usare il `StdCall` convenzione di chiamata. In questo caso, il chiamato pulisce lo stack. Questa è la convenzione predefinita per chiamare funzioni non gestite con platform invoke.|  
|`pmCallConvThiscall`|Usare il `ThisCall` convenzione di chiamata. In questo caso, il primo parametro è il `this` puntatore e viene archiviato in ECX. Altri parametri vengono inseriti nello stack. Il `ThisCall` convenzione di chiamata viene usato per chiamare metodi su classi esportate da una DLL non gestita.|  
|`pmCallConvFastcall`|Riservato.|  
|`pmMaxValue`|Riservato.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr. H  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
