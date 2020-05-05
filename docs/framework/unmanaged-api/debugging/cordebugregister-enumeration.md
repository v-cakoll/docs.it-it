---
title: Enumerazione CorDebugRegister
ms.date: 03/30/2017
api_name:
- CorDebugRegister
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugRegister
helpviewer_keywords:
- CorDebugRegister enumeration [.NET Framework debugging]
ms.assetid: 003bb138-7960-4291-ac88-0d87e470ff70
topic_type:
- apiref
ms.openlocfilehash: 19d0dcf8a5633371765861fcc29df4ef8c91ebc4
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795716"
---
# <a name="cordebugregister-enumeration"></a>Enumerazione CorDebugRegister
Specifica i registri associati a un'architettura di processore specifica.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum CorDebugRegister {  
  
    REGISTER_INSTRUCTION_POINTER = 0,  
    REGISTER_STACK_POINTER,  
    REGISTER_FRAME_POINTER,  
  
    REGISTER_X86_EIP = 0,  
    REGISTER_X86_ESP,  
    REGISTER_X86_EBP,  
  
    REGISTER_X86_EAX,  
    REGISTER_X86_ECX,  
    REGISTER_X86_EDX,  
    REGISTER_X86_EBX,  
  
    REGISTER_X86_ESI,  
    REGISTER_X86_EDI,  
  
    REGISTER_X86_FPSTACK_0,  
    REGISTER_X86_FPSTACK_1,  
    REGISTER_X86_FPSTACK_2,  
    REGISTER_X86_FPSTACK_3,  
    REGISTER_X86_FPSTACK_4,  
    REGISTER_X86_FPSTACK_5,  
    REGISTER_X86_FPSTACK_6,  
    REGISTER_X86_FPSTACK_7,  
  
    REGISTER_AMD64_RIP = 0,  
    REGISTER_AMD64_RSP,  
    REGISTER_AMD64_RBP,  
    REGISTER_AMD64_RAX,  
    REGISTER_AMD64_RCX,  
    REGISTER_AMD64_RDX,  
    REGISTER_AMD64_RBX,  
    REGISTER_AMD64_RSI,  
    REGISTER_AMD64_RDI,  
    REGISTER_AMD64_R8,  
    REGISTER_AMD64_R9,  
    REGISTER_AMD64_R10,  
    REGISTER_AMD64_R11,  
    REGISTER_AMD64_R12,  
    REGISTER_AMD64_R13,  
    REGISTER_AMD64_R14,  
    REGISTER_AMD64_R15,  
  
    REGISTER_AMD64_XMM0,  
    REGISTER_AMD64_XMM1,  
    REGISTER_AMD64_XMM2,  
    REGISTER_AMD64_XMM3,  
    REGISTER_AMD64_XMM4,  
    REGISTER_AMD64_XMM5,  
    REGISTER_AMD64_XMM6,  
    REGISTER_AMD64_XMM7,  
    REGISTER_AMD64_XMM8,  
    REGISTER_AMD64_XMM9,  
    REGISTER_AMD64_XMM10,  
    REGISTER_AMD64_XMM11,  
    REGISTER_AMD64_XMM12,  
    REGISTER_AMD64_XMM13,  
    REGISTER_AMD64_XMM14,  
    REGISTER_AMD64_XMM15,  
  
    REGISTER_IA64_BSP = REGISTER_FRAME_POINTER,  
    REGISTER_IA64_R0  = REGISTER_IA64_BSP + 1,  
    REGISTER_IA64_F0  = REGISTER_IA64_R0  + 128,  
    REGISTER_ARM_PC = 0,  
    REGISTER_ARM_SP,  
    REGISTER_ARM_R0,  
    REGISTER_ARM_R1,  
    REGISTER_ARM_R2,  
    REGISTER_ARM_R3,  
    REGISTER_ARM_R4,  
    REGISTER_ARM_R5,  
    REGISTER_ARM_R6,  
    REGISTER_ARM_R7,  
    REGISTER_ARM_R8,  
    REGISTER_ARM_R9,  
    REGISTER_ARM_R10,  
    REGISTER_ARM_R11,  
    REGISTER_ARM_R12,  
    REGISTER_ARM_LR,  
  
} CorDebugRegister;  
```  
  
## <a name="members"></a>Members  
  
|Membro|Description|  
|------------|-----------------|  
|`REGISTER_INSTRUCTION_POINTER`|Un registro dei puntatori alle istruzioni in qualsiasi processore.|  
|`REGISTER_STACK_POINTER`|Un registro dei puntatori agli stack in qualsiasi processore.|  
|`REGISTER_FRAME_POINTER`|Registro dei puntatori ai frame in qualsiasi processore.|  
|`REGISTER_X86_EIP`|Registro dei puntatori alle istruzioni nel processore x86.|  
|`REGISTER_X86_ESP`|Registro dei puntatori agli stack nel processore x86.|  
|`REGISTER_X86_EBP`|Registro dei puntatori di base nel processore x86.|  
|`REGISTER_X86_EAX`|Registro dei dati A nel processore x86.|  
|`REGISTER_X86_ECX`|Registro dei dati C nel processore x86.|  
|`REGISTER_X86_EDX`|Registro dei dati D nel processore x86.|  
|`REGISTER_X86_EBX`|Registro dei dati B nel processore x86.|  
|`REGISTER_X86_ESI`|Registro dell'indice di origine nel processore x86.|  
|`REGISTER_X86_EDI`|Registro dell'indice di destinazione nel processore x86.|  
|`REGISTER_X86_FPSTACK_0`|Registro dello stack 0 nel processore a virgola mobile x86.|  
|`REGISTER_X86_FPSTACK_1`|Registro dello stack 1 nel processore a virgola mobile x86.|  
|`REGISTER_X86_FPSTACK_2`|Registro dello stack 2 nel processore a virgola mobile x86.|  
|`REGISTER_X86_FPSTACK_3`|Registro dello stack 3 nel processore a virgola mobile x86.|  
|`REGISTER_X86_FPSTACK_4`|Registro dello stack 4 nel processore a virgola mobile x86.|  
|`REGISTER_X86_FPSTACK_5`|Registro dello stack 5 nel processore a virgola mobile x86.|  
|`REGISTER_X86_FPSTACK_6`|Registro dello stack 6 nel processore a virgola mobile x86.|  
|`REGISTER_X86_FPSTACK_7`|Registro dello stack 7 nel processore a virgola mobile x86.|  
|`REGISTER_AMD64_RIP`|Registro dei puntatori alle istruzioni nel processore AMD64.|  
|`REGISTER_AMD64_RSP`|Registro dei puntatori agli stack nel processore AMD64.|  
|`REGISTER_AMD64_RBP`|Registro dei puntatori di base nel processore AMD64.|  
|`REGISTER_AMD64_RAX`|Registro dei dati A nel processore AMD64.|  
|`REGISTER_AMD64_RCX`|Registro dei dati C nel processore AMD64.|  
|`REGISTER_AMD64_RDX`|Registro dei dati D nel processore AMD64.|  
|`REGISTER_AMD64_RBX`|Registro dei dati B nel processore AMD64.|  
|`REGISTER_AMD64_RSI`|Registro dell'indice di origine nel processore AMD64.|  
|`REGISTER_AMD64_RDI`|Registro dell'indice di destinazione nel processore AMD64.|  
|`REGISTER_AMD64_R8`|Registro dei dati 8 nel processore AMD64.|  
|`REGISTER_AMD64_R9`|Registro dei dati 9 nel processore AMD64.|  
|`REGISTER_AMD64_R10`|Registro dei dati 10 nel processore AMD64.|  
|`REGISTER_AMD64_R11`|Registro dei dati 11 nel processore AMD64.|  
|`REGISTER_AMD64_R12`|Registro dei dati 12 nel processore AMD64.|  
|`REGISTER_AMD64_R13`|Registro dei dati 13 nel processore AMD64.|  
|`REGISTER_AMD64_R14`|Registro dei dati 14 nel processore AMD64.|  
|`REGISTER_AMD64_R15`|Registro dei dati 15 nel processore AMD64.|  
|`REGISTER_AMD64_XMM0`|Registro dei dati multimediali 0 nel processore AMD64.|  
|`REGISTER_AMD64_XMM1`|Registro dei dati multimediali 1 nel processore AMD64.|  
|`REGISTER_AMD64_XMM2`|Registro dei dati multimediali 2 nel processore AMD64.|  
|`REGISTER_AMD64_XMM3`|Registro dei dati multimediali 3 nel processore AMD64.|  
|`REGISTER_AMD64_XMM4`|Registro dei dati multimediali 4 nel processore AMD64.|  
|`REGISTER_AMD64_XMM5`|Registro dei dati multimediali 5 nel processore AMD64.|  
|`REGISTER_AMD64_XMM6`|Registro dei dati multimediali 6 nel processore AMD64.|  
|`REGISTER_AMD64_XMM7`|Registro dei dati multimediali 7 nel processore AMD64.|  
|`REGISTER_AMD64_XMM8`|Registro dei dati multimediali 8 nel processore AMD64.|  
|`REGISTER_AMD64_XMM9`|Registro dei dati multimediali 9 nel processore AMD64.|  
|`REGISTER_AMD64_XMM10`|Registro dei dati multimediali 10 nel processore AMD64.|  
|`REGISTER_AMD64_XMM11`|Registro dei dati multimediali 11 nel processore AMD64.|  
|`REGISTER_AMD64_XMM12`|Registro dei dati multimediali 12 nel processore AMD64.|  
|`REGISTER_AMD64_XMM13`|Registro dei dati multimediali 13 nel processore AMD64.|  
|`REGISTER_AMD64_XMM14`|Registro dei dati multimediali 14 nel processore AMD64.|  
|`REGISTER_AMD64_XMM15`|Registro dei dati multimediali 15 nel processore AMD64.|  
|`REGISTER_IA64_BSP`|Registro dei puntatori agli stack nel processore IA-64.|  
|`REGISTER_IA64_R0`|Registro dei dati 0 nel processore IA-64.|  
|`REGISTER_IA64_F0`|Registro dei dati a virgola mobile 0 nel processore IA-64.|  
|`REGISTER_ARM_PC`|Registro dei contatori di programma (R15) nel processore ARM.|  
|`REGISTER_ARM_SP`|Registro dei puntatori agli stack (R13) nel processore ARM.|  
|`REGISTER_ARM_R0`|Registro dei dati R0 nel processore ARM.|  
|`REGISTER_ARM_R1`|Registro dei dati R1 nel processore ARM.|  
|`REGISTER_ARM_R2`|Registro dei dati R2 nel processore ARM.|  
|`REGISTER_ARM_R3`|Registro dei dati R3 nel processore ARM.|  
|`REGISTER_ARM_R4`|Registro R4 nel processore ARM.|  
|`REGISTER_ARM_R5`|Registro R5 nel processore ARM.|  
|`REGISTER_ARM_R6`|Registro R6 nel processore ARM.|  
|`REGISTER_ARM_R7`|Registro R7 (puntatore ai frame THUMB) nel processore ARM.|  
|`REGISTER_ARM_R8`|Registro R8 nel processore ARM.|  
|`REGISTER_ARM_R9`|Registro R9 nel processore ARM.|  
|`REGISTER_ARM_R10`|Registro R10 nel processore ARM.|  
|`REGISTER_ARM_R11`|Puntatore ai frame nel processore ARM.|  
|`REGISTER_ARM_R12`|Registro R12 nel processore ARM.|  
|`REGISTER_ARM_LR`|Registro dei collegamenti (R14) nel processore ARM.|  
  
## <a name="remarks"></a>Osservazioni  
 Esistono 128 registri dei dati per l'utilizzo generico e 128 registri dei dati a virgola mobile nel processore IA-64, ma vengono forniti solo i valori `REGISTER_IA64_R0` e `REGISTER_IA64_F0`. Gli altri valori possono essere determinati come descritto di seguito:  
  
- Aggiungere il numero del registro a `REGISTER_IA64_R0` per i valori da `REGISTER_IA64_R1` a `REGISTER_IA64_R127`, che corrispondono al registro dei dati dal numero 1 al numero 127 nel processore IA-64.  
  
- Aggiungere il numero del registro a `REGISTER_IA64_F0` per i valori da `REGISTER_IA64_F1` a `REGISTER_IA64_F127`, che corrispondono al registro dei dati a virgola mobile dal numero 1 al numero 127 nel processore IA-64.  
  
 Ad esempio, se occorre specificare il registro dei dati 83 nel processore IA-64, usare `REGISTER_IA64_R0` + 83.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di debug](debugging-enumerations.md)
