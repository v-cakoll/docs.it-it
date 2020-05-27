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
ms.openlocfilehash: 199a649b0481c2a740926636345eefbda6831ef2
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007546"
---
# <a name="corpinvokemap-enumeration"></a><span data-ttu-id="f1caf-102">Enumerazione CorPinvokeMap</span><span class="sxs-lookup"><span data-stu-id="f1caf-102">CorPinvokeMap Enumeration</span></span>
<span data-ttu-id="f1caf-103">Specifica le opzioni per una chiamata PInvoke.</span><span class="sxs-lookup"><span data-stu-id="f1caf-103">Specifies options for a PInvoke call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1caf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f1caf-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="f1caf-105">Membri</span><span class="sxs-lookup"><span data-stu-id="f1caf-105">Members</span></span>  
  
|<span data-ttu-id="f1caf-106">Membro</span><span class="sxs-lookup"><span data-stu-id="f1caf-106">Member</span></span>|<span data-ttu-id="f1caf-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f1caf-107">Description</span></span>|  
|------------|-----------------|  
|`pmNoMangle`|<span data-ttu-id="f1caf-108">Usare il nome di ogni membro come specificato.</span><span class="sxs-lookup"><span data-stu-id="f1caf-108">Use each member name as specified.</span></span>|  
|`pmCharSetMask`|<span data-ttu-id="f1caf-109">Riservato.</span><span class="sxs-lookup"><span data-stu-id="f1caf-109">Reserved.</span></span>|  
|`pmCharSetNotSpec`|<span data-ttu-id="f1caf-110">Riservato.</span><span class="sxs-lookup"><span data-stu-id="f1caf-110">Reserved.</span></span>|  
|`pmCharSetAnsi`|<span data-ttu-id="f1caf-111">Esegue il marshalling delle stringhe come stringhe di caratteri a più byte.</span><span class="sxs-lookup"><span data-stu-id="f1caf-111">Marshal strings as multiple-byte character strings.</span></span>|  
|`pmCharSetUnicode`|<span data-ttu-id="f1caf-112">Esegue il marshalling delle stringhe come caratteri Unicode a 2 byte.</span><span class="sxs-lookup"><span data-stu-id="f1caf-112">Marshal strings as Unicode 2-byte characters.</span></span>|  
|`pmCharSetAuto`|<span data-ttu-id="f1caf-113">Esegue automaticamente il marshalling delle stringhe in modo appropriato per il sistema operativo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="f1caf-113">Automatically marshal strings appropriately for the target operating system.</span></span> <span data-ttu-id="f1caf-114">Il valore predefinito è Unicode in Windows NT, Windows 2000, Windows XP e la famiglia Windows Server 2003; il valore predefinito è ANSI in Windows 98 e Windows me.</span><span class="sxs-lookup"><span data-stu-id="f1caf-114">The default is Unicode on Windows NT, Windows 2000, Windows XP, and the Windows Server 2003 family; the default is ANSI on Windows 98 and Windows Me.</span></span>|  
|`pmBestFitUseAssem`|<span data-ttu-id="f1caf-115">Riservato.</span><span class="sxs-lookup"><span data-stu-id="f1caf-115">Reserved.</span></span>|  
|`pmBestFitEnabled`|<span data-ttu-id="f1caf-116">Eseguire il mapping più appropriato di caratteri Unicode privi di una corrispondenza esatta nel set di caratteri ANSI.</span><span class="sxs-lookup"><span data-stu-id="f1caf-116">Perform best-fit mapping of Unicode characters that lack an exact match in the ANSI character set.</span></span>|  
|`pmBestFitDisabled`|<span data-ttu-id="f1caf-117">Non eseguire il mapping più appropriato di caratteri Unicode.</span><span class="sxs-lookup"><span data-stu-id="f1caf-117">Do not perform best-fit mapping of Unicode characters.</span></span> <span data-ttu-id="f1caf-118">In questo caso, tutti i caratteri unmappable verranno sostituiti da'?'.</span><span class="sxs-lookup"><span data-stu-id="f1caf-118">In this case, all unmappable characters will be replaced by a ‘?’.</span></span>|  
|`pmBestFitMask`|<span data-ttu-id="f1caf-119">Riservato.</span><span class="sxs-lookup"><span data-stu-id="f1caf-119">Reserved.</span></span>|  
|`pmThrowOnUnmappableCharUseAssem`|<span data-ttu-id="f1caf-120">Riservato.</span><span class="sxs-lookup"><span data-stu-id="f1caf-120">Reserved.</span></span>|  
|`pmThrowOnUnmappableCharEnabled`|<span data-ttu-id="f1caf-121">Genera un'eccezione quando il gestore di marshalling di interoperabilità rileva un carattere unmappable.</span><span class="sxs-lookup"><span data-stu-id="f1caf-121">Throw an exception when the interop marshaler encounters an unmappable character.</span></span>|  
|`pmThrowOnUnmappableCharDisabled`|<span data-ttu-id="f1caf-122">Non generare un'eccezione quando il gestore di marshalling di interoperabilità rileva un carattere unmappable.</span><span class="sxs-lookup"><span data-stu-id="f1caf-122">Do not throw an exception when the interop marshaler encounters an unmappable character.</span></span>|  
|`pmThrowOnUnmappableCharMask`|<span data-ttu-id="f1caf-123">Riservato</span><span class="sxs-lookup"><span data-stu-id="f1caf-123">Reserved</span></span>|  
|`pmSupportsLastError`|<span data-ttu-id="f1caf-124">Consentire al chiamato di chiamare la funzione Win32 `SetLastError` prima di restituire dal metodo con attributi.</span><span class="sxs-lookup"><span data-stu-id="f1caf-124">Allow the callee to call the Win32 `SetLastError` function before returning from the attributed method.</span></span>|  
|`pmCallConvMask`|<span data-ttu-id="f1caf-125">Riservato</span><span class="sxs-lookup"><span data-stu-id="f1caf-125">Reserved</span></span>|  
|`pmCallConvWinapi`|<span data-ttu-id="f1caf-126">Usare la convenzione di chiamata della piattaforma predefinita.</span><span class="sxs-lookup"><span data-stu-id="f1caf-126">Use the default platform calling convention.</span></span> <span data-ttu-id="f1caf-127">In Windows, ad esempio, il valore predefinito è `StdCall` e Windows CE .NET è `Cdecl` .</span><span class="sxs-lookup"><span data-stu-id="f1caf-127">For example, on Windows the default is `StdCall` and on Windows CE .NET it is `Cdecl`.</span></span>|  
|`pmCallConvCdecl`|<span data-ttu-id="f1caf-128">Utilizzare la `Cdecl` convenzione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="f1caf-128">Use the `Cdecl` calling convention.</span></span> <span data-ttu-id="f1caf-129">In questo caso, il chiamante pulisce lo stack.</span><span class="sxs-lookup"><span data-stu-id="f1caf-129">In this case, the caller cleans the stack.</span></span> <span data-ttu-id="f1caf-130">In questo modo è possibile chiamare funzioni con `varargs` , ovvero funzioni che accettano un numero variabile di parametri.</span><span class="sxs-lookup"><span data-stu-id="f1caf-130">This enables calling functions with `varargs` (that is, functions that accept a variable number of parameters).</span></span>|  
|`pmCallConvStdcall`|<span data-ttu-id="f1caf-131">Utilizzare la `StdCall` convenzione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="f1caf-131">Use the `StdCall` calling convention.</span></span> <span data-ttu-id="f1caf-132">In questo caso, il chiamato pulisce lo stack.</span><span class="sxs-lookup"><span data-stu-id="f1caf-132">In this case, the callee cleans the stack.</span></span> <span data-ttu-id="f1caf-133">Si tratta della convenzione predefinita per chiamare funzioni non gestite tramite platform invoke.</span><span class="sxs-lookup"><span data-stu-id="f1caf-133">This is the default convention for calling unmanaged functions with platform invoke.</span></span>|  
|`pmCallConvThiscall`|<span data-ttu-id="f1caf-134">Utilizzare la `ThisCall` convenzione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="f1caf-134">Use the `ThisCall` calling convention.</span></span> <span data-ttu-id="f1caf-135">In questo caso, il primo parametro è il `this` puntatore e viene archiviato nel registro ecx.</span><span class="sxs-lookup"><span data-stu-id="f1caf-135">In this case, the first parameter is the `this` pointer and is stored in register ECX.</span></span> <span data-ttu-id="f1caf-136">Altri parametri vengono inseriti nello stack.</span><span class="sxs-lookup"><span data-stu-id="f1caf-136">Other parameters are pushed on the stack.</span></span> <span data-ttu-id="f1caf-137">La `ThisCall` convenzione di chiamata viene utilizzata per chiamare metodi sulle classi esportate da una dll non gestita.</span><span class="sxs-lookup"><span data-stu-id="f1caf-137">The `ThisCall` calling convention is used to call methods on classes exported from an unmanaged DLL.</span></span>|  
|`pmCallConvFastcall`|<span data-ttu-id="f1caf-138">Riservato.</span><span class="sxs-lookup"><span data-stu-id="f1caf-138">Reserved.</span></span>|  
|`pmMaxValue`|<span data-ttu-id="f1caf-139">Riservato.</span><span class="sxs-lookup"><span data-stu-id="f1caf-139">Reserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f1caf-140">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f1caf-140">Requirements</span></span>  
 <span data-ttu-id="f1caf-141">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1caf-141">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1caf-142">**Intestazione:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="f1caf-142">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="f1caf-143">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1caf-143">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1caf-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1caf-144">See also</span></span>

- [<span data-ttu-id="f1caf-145">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="f1caf-145">Metadata Enumerations</span></span>](metadata-enumerations.md)
