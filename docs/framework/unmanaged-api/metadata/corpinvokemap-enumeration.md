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
ms.openlocfilehash: a876ff1ba0d2342f7975bf5adfc8ec03d21578f5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781649"
---
# <a name="corpinvokemap-enumeration"></a><span data-ttu-id="ae90c-102">Enumerazione CorPinvokeMap</span><span class="sxs-lookup"><span data-stu-id="ae90c-102">CorPinvokeMap Enumeration</span></span>
<span data-ttu-id="ae90c-103">Specifica le opzioni per una chiamata PInvoke.</span><span class="sxs-lookup"><span data-stu-id="ae90c-103">Specifies options for a PInvoke call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae90c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ae90c-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="ae90c-105">Membri</span><span class="sxs-lookup"><span data-stu-id="ae90c-105">Members</span></span>  
  
|<span data-ttu-id="ae90c-106">Member</span><span class="sxs-lookup"><span data-stu-id="ae90c-106">Member</span></span>|<span data-ttu-id="ae90c-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ae90c-107">Description</span></span>|  
|------------|-----------------|  
|`pmNoMangle`|<span data-ttu-id="ae90c-108">Usare ogni nome di membro specificate.</span><span class="sxs-lookup"><span data-stu-id="ae90c-108">Use each member name as specified.</span></span>|  
|`pmCharSetMask`|<span data-ttu-id="ae90c-109">Riservato.</span><span class="sxs-lookup"><span data-stu-id="ae90c-109">Reserved.</span></span>|  
|`pmCharSetNotSpec`|<span data-ttu-id="ae90c-110">Riservato.</span><span class="sxs-lookup"><span data-stu-id="ae90c-110">Reserved.</span></span>|  
|`pmCharSetAnsi`|<span data-ttu-id="ae90c-111">Eseguire il marshalling di stringhe come stringhe di caratteri a byte multiplo.</span><span class="sxs-lookup"><span data-stu-id="ae90c-111">Marshal strings as multiple-byte character strings.</span></span>|  
|`pmCharSetUnicode`|<span data-ttu-id="ae90c-112">Eseguire il marshalling di stringhe come caratteri Unicode a 2 byte.</span><span class="sxs-lookup"><span data-stu-id="ae90c-112">Marshal strings as Unicode 2-byte characters.</span></span>|  
|`pmCharSetAuto`|<span data-ttu-id="ae90c-113">Eseguire automaticamente il marshalling di stringhe in modo appropriato per il sistema operativo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="ae90c-113">Automatically marshal strings appropriately for the target operating system.</span></span> <span data-ttu-id="ae90c-114">Il valore predefinito è Unicode su Windows NT, Windows 2000, Windows XP e in Windows Server 2003; l'impostazione predefinita è ANSI in Windows 98 e Windows Me.</span><span class="sxs-lookup"><span data-stu-id="ae90c-114">The default is Unicode on Windows NT, Windows 2000, Windows XP, and the Windows Server 2003 family; the default is ANSI on Windows 98 and Windows Me.</span></span>|  
|`pmBestFitUseAssem`|<span data-ttu-id="ae90c-115">Riservato.</span><span class="sxs-lookup"><span data-stu-id="ae90c-115">Reserved.</span></span>|  
|`pmBestFitEnabled`|<span data-ttu-id="ae90c-116">Eseguire il mapping di caratteri Unicode che non dispongono di una corrispondenza esatta nel set di caratteri ANSI.</span><span class="sxs-lookup"><span data-stu-id="ae90c-116">Perform best-fit mapping of Unicode characters that lack an exact match in the ANSI character set.</span></span>|  
|`pmBestFitDisabled`|<span data-ttu-id="ae90c-117">Non eseguire il mapping di caratteri Unicode.</span><span class="sxs-lookup"><span data-stu-id="ae90c-117">Do not perform best-fit mapping of Unicode characters.</span></span> <span data-ttu-id="ae90c-118">In questo caso, tutti i caratteri verranno sostituiti da un '?'.</span><span class="sxs-lookup"><span data-stu-id="ae90c-118">In this case, all unmappable characters will be replaced by a ‘?’.</span></span>|  
|`pmBestFitMask`|<span data-ttu-id="ae90c-119">Riservato.</span><span class="sxs-lookup"><span data-stu-id="ae90c-119">Reserved.</span></span>|  
|`pmThrowOnUnmappableCharUseAssem`|<span data-ttu-id="ae90c-120">Riservato.</span><span class="sxs-lookup"><span data-stu-id="ae90c-120">Reserved.</span></span>|  
|`pmThrowOnUnmappableCharEnabled`|<span data-ttu-id="ae90c-121">Generare un'eccezione durante il marshalling di interoperabilità rileva un carattere possibile eseguire il mapping.</span><span class="sxs-lookup"><span data-stu-id="ae90c-121">Throw an exception when the interop marshaler encounters an unmappable character.</span></span>|  
|`pmThrowOnUnmappableCharDisabled`|<span data-ttu-id="ae90c-122">Non generare un'eccezione durante il marshalling di interoperabilità rileva un carattere possibile eseguire il mapping.</span><span class="sxs-lookup"><span data-stu-id="ae90c-122">Do not throw an exception when the interop marshaler encounters an unmappable character.</span></span>|  
|`pmThrowOnUnmappableCharMask`|<span data-ttu-id="ae90c-123">Riservata</span><span class="sxs-lookup"><span data-stu-id="ae90c-123">Reserved</span></span>|  
|`pmSupportsLastError`|<span data-ttu-id="ae90c-124">Consentire al chiamato di chiamare Win32 `SetLastError` funzione prima di restituire il metodo con attributi.</span><span class="sxs-lookup"><span data-stu-id="ae90c-124">Allow the callee to call the Win32 `SetLastError` function before returning from the attributed method.</span></span>|  
|`pmCallConvMask`|<span data-ttu-id="ae90c-125">Riservata</span><span class="sxs-lookup"><span data-stu-id="ae90c-125">Reserved</span></span>|  
|`pmCallConvWinapi`|<span data-ttu-id="ae90c-126">Usare la piattaforma predefinita la convenzione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="ae90c-126">Use the default platform calling convention.</span></span> <span data-ttu-id="ae90c-127">In Windows, ad esempio, il valore predefinito è `StdCall` e su Windows CE .NET è `Cdecl`.</span><span class="sxs-lookup"><span data-stu-id="ae90c-127">For example, on Windows the default is `StdCall` and on Windows CE .NET it is `Cdecl`.</span></span>|  
|`pmCallConvCdecl`|<span data-ttu-id="ae90c-128">Usare il `Cdecl` convenzione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="ae90c-128">Use the `Cdecl` calling convention.</span></span> <span data-ttu-id="ae90c-129">In questo caso, il chiamante esegue la pulizia dello stack.</span><span class="sxs-lookup"><span data-stu-id="ae90c-129">In this case, the caller cleans the stack.</span></span> <span data-ttu-id="ae90c-130">Questa operazione attiva funzioni chiamanti con `varargs` (vale a dire, le funzioni che accettano un numero variabile di parametri).</span><span class="sxs-lookup"><span data-stu-id="ae90c-130">This enables calling functions with `varargs` (that is, functions that accept a variable number of parameters).</span></span>|  
|`pmCallConvStdcall`|<span data-ttu-id="ae90c-131">Usare il `StdCall` convenzione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="ae90c-131">Use the `StdCall` calling convention.</span></span> <span data-ttu-id="ae90c-132">In questo caso, il chiamato pulisce lo stack.</span><span class="sxs-lookup"><span data-stu-id="ae90c-132">In this case, the callee cleans the stack.</span></span> <span data-ttu-id="ae90c-133">Questa è la convenzione predefinita per chiamare funzioni non gestite con platform invoke.</span><span class="sxs-lookup"><span data-stu-id="ae90c-133">This is the default convention for calling unmanaged functions with platform invoke.</span></span>|  
|`pmCallConvThiscall`|<span data-ttu-id="ae90c-134">Usare il `ThisCall` convenzione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="ae90c-134">Use the `ThisCall` calling convention.</span></span> <span data-ttu-id="ae90c-135">In questo caso, il primo parametro è il `this` puntatore e viene archiviato in ECX.</span><span class="sxs-lookup"><span data-stu-id="ae90c-135">In this case, the first parameter is the `this` pointer and is stored in register ECX.</span></span> <span data-ttu-id="ae90c-136">Altri parametri vengono inseriti nello stack.</span><span class="sxs-lookup"><span data-stu-id="ae90c-136">Other parameters are pushed on the stack.</span></span> <span data-ttu-id="ae90c-137">Il `ThisCall` convenzione di chiamata viene usato per chiamare metodi su classi esportate da una DLL non gestita.</span><span class="sxs-lookup"><span data-stu-id="ae90c-137">The `ThisCall` calling convention is used to call methods on classes exported from an unmanaged DLL.</span></span>|  
|`pmCallConvFastcall`|<span data-ttu-id="ae90c-138">Riservato.</span><span class="sxs-lookup"><span data-stu-id="ae90c-138">Reserved.</span></span>|  
|`pmMaxValue`|<span data-ttu-id="ae90c-139">Riservato.</span><span class="sxs-lookup"><span data-stu-id="ae90c-139">Reserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ae90c-140">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ae90c-140">Requirements</span></span>  
 <span data-ttu-id="ae90c-141">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae90c-141">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae90c-142">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="ae90c-142">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="ae90c-143">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae90c-143">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae90c-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae90c-144">See also</span></span>

- [<span data-ttu-id="ae90c-145">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="ae90c-145">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
