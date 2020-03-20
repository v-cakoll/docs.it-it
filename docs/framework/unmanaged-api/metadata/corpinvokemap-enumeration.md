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
ms.openlocfilehash: 8216dc3030b18428ab52fbf8385d392f81057aa0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176149"
---
# <a name="corpinvokemap-enumeration"></a>Enumerazione CorPinvokeMap
Specifica le opzioni per una chiamata PInvoke.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
  
## <a name="members"></a>Members  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`pmNoMangle`|Utilizzare ogni nome di membro come specificato.|  
|`pmCharSetMask`|Riservato.|  
|`pmCharSetNotSpec`|Riservato.|  
|`pmCharSetAnsi`|Esegue il marshalling delle stringhe come stringhe di caratteri a più byte.|  
|`pmCharSetUnicode`|Esegue il marshalling delle stringhe come caratteri Unicode a 2 byte.|  
|`pmCharSetAuto`|Esegue automaticamente il marshalling delle stringhe in modo appropriato per il sistema operativo di destinazione. Il valore predefinito è Unicode in Windows NT, Windows 2000, Windows XP e nella famiglia Windows Server 2003. l'impostazione predefinita è ANSI in Windows 98 e Windows Me.|  
|`pmBestFitUseAssem`|Riservato.|  
|`pmBestFitEnabled`|Eseguire il mapping ottimale dei caratteri Unicode che non dispongono di una corrispondenza esatta nel set di caratteri ANSI.|  
|`pmBestFitDisabled`|Non eseguire il mapping più adatto dei caratteri Unicode. In questo caso, tutti i caratteri di cui non è possibile mappare verranno sostituiti da un '?'.|  
|`pmBestFitMask`|Riservato.|  
|`pmThrowOnUnmappableCharUseAssem`|Riservato.|  
|`pmThrowOnUnmappableCharEnabled`|Generare un'eccezione quando il gestore di marshalling di interoperabilità rileva un carattere di cui non è possibile eseguire il marshalling.|  
|`pmThrowOnUnmappableCharDisabled`|Non generare un'eccezione quando il gestore di marshalling di interoperabilità rileva un carattere di cui non è possibile eseguire il codificatore.|  
|`pmThrowOnUnmappableCharMask`|Riservato|  
|`pmSupportsLastError`|Consentire al chiamato di chiamare la `SetLastError` funzione Win32 prima di restituire dal metodo con attributi.|  
|`pmCallConvMask`|Riservato|  
|`pmCallConvWinapi`|Utilizzare la convenzione di chiamata della piattaforma predefinita. In Windows, ad esempio, l'impostazione predefinita è `StdCall` e in Windows CE .NET è `Cdecl`.|  
|`pmCallConvCdecl`|Utilizzare `Cdecl` la convenzione di chiamata. In questo caso, il chiamante pulisce lo stack. In questo modo `varargs` le funzioni di chiamata con (vale a dire, funzioni che accettano un numero variabile di parametri).|  
|`pmCallConvStdcall`|Utilizzare `StdCall` la convenzione di chiamata. In questo caso, il chiamato pulisce lo stack. Si tratta della convenzione predefinita per chiamare funzioni non gestite tramite platform invoke.|  
|`pmCallConvThiscall`|Utilizzare `ThisCall` la convenzione di chiamata. In questo caso, il `this` primo parametro è il puntatore e viene archiviato nel registro ECX. Altri parametri vengono inseriti nello stack. La `ThisCall` convenzione di chiamata viene utilizzata per chiamare metodi su classi esportate da una DLL non gestita.|  
|`pmCallConvFastcall`|Riservato.|  
|`pmMaxValue`|Riservato.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr.h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
