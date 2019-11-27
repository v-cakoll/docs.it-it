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
ms.openlocfilehash: 17b7af7016cf88fd3ae263dd952502d515b0c833
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74441553"
---
# <a name="corpinvokemap-enumeration"></a><span data-ttu-id="38709-102">Enumerazione CorPinvokeMap</span><span class="sxs-lookup"><span data-stu-id="38709-102">CorPinvokeMap Enumeration</span></span>
<span data-ttu-id="38709-103">Specifica le opzioni per una chiamata PInvoke.</span><span class="sxs-lookup"><span data-stu-id="38709-103">Specifies options for a PInvoke call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38709-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="38709-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="38709-105">Membri</span><span class="sxs-lookup"><span data-stu-id="38709-105">Members</span></span>  
  
|<span data-ttu-id="38709-106">Membro</span><span class="sxs-lookup"><span data-stu-id="38709-106">Member</span></span>|<span data-ttu-id="38709-107">description</span><span class="sxs-lookup"><span data-stu-id="38709-107">Description</span></span>|  
|------------|-----------------|  
|`pmNoMangle`|<span data-ttu-id="38709-108">Usare il nome di ogni membro come specificato.</span><span class="sxs-lookup"><span data-stu-id="38709-108">Use each member name as specified.</span></span>|  
|`pmCharSetMask`|<span data-ttu-id="38709-109">Riservato.</span><span class="sxs-lookup"><span data-stu-id="38709-109">Reserved.</span></span>|  
|`pmCharSetNotSpec`|<span data-ttu-id="38709-110">Riservato.</span><span class="sxs-lookup"><span data-stu-id="38709-110">Reserved.</span></span>|  
|`pmCharSetAnsi`|<span data-ttu-id="38709-111">Eseguire il marshalling delle stringhe come stringhe di caratteri a più byte.</span><span class="sxs-lookup"><span data-stu-id="38709-111">Marshal strings as multiple-byte character strings.</span></span>|  
|`pmCharSetUnicode`|<span data-ttu-id="38709-112">Eseguire il marshalling delle stringhe come caratteri Unicode a 2 byte.</span><span class="sxs-lookup"><span data-stu-id="38709-112">Marshal strings as Unicode 2-byte characters.</span></span>|  
|`pmCharSetAuto`|<span data-ttu-id="38709-113">Eseguire automaticamente il marshalling delle stringhe appropriate per il sistema operativo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="38709-113">Automatically marshal strings appropriately for the target operating system.</span></span> <span data-ttu-id="38709-114">Il valore predefinito è Unicode in Windows NT, Windows 2000, Windows XP e la famiglia Windows Server 2003; il valore predefinito è ANSI in Windows 98 e Windows me.</span><span class="sxs-lookup"><span data-stu-id="38709-114">The default is Unicode on Windows NT, Windows 2000, Windows XP, and the Windows Server 2003 family; the default is ANSI on Windows 98 and Windows Me.</span></span>|  
|`pmBestFitUseAssem`|<span data-ttu-id="38709-115">Riservato.</span><span class="sxs-lookup"><span data-stu-id="38709-115">Reserved.</span></span>|  
|`pmBestFitEnabled`|<span data-ttu-id="38709-116">Eseguire il mapping più appropriato di caratteri Unicode privi di una corrispondenza esatta nel set di caratteri ANSI.</span><span class="sxs-lookup"><span data-stu-id="38709-116">Perform best-fit mapping of Unicode characters that lack an exact match in the ANSI character set.</span></span>|  
|`pmBestFitDisabled`|<span data-ttu-id="38709-117">Non eseguire il mapping più appropriato di caratteri Unicode.</span><span class="sxs-lookup"><span data-stu-id="38709-117">Do not perform best-fit mapping of Unicode characters.</span></span> <span data-ttu-id="38709-118">In questo caso, tutti i caratteri unmappable verranno sostituiti da'?'.</span><span class="sxs-lookup"><span data-stu-id="38709-118">In this case, all unmappable characters will be replaced by a ‘?’.</span></span>|  
|`pmBestFitMask`|<span data-ttu-id="38709-119">Riservato.</span><span class="sxs-lookup"><span data-stu-id="38709-119">Reserved.</span></span>|  
|`pmThrowOnUnmappableCharUseAssem`|<span data-ttu-id="38709-120">Riservato.</span><span class="sxs-lookup"><span data-stu-id="38709-120">Reserved.</span></span>|  
|`pmThrowOnUnmappableCharEnabled`|<span data-ttu-id="38709-121">Genera un'eccezione quando il gestore di marshalling di interoperabilità rileva un carattere unmappable.</span><span class="sxs-lookup"><span data-stu-id="38709-121">Throw an exception when the interop marshaler encounters an unmappable character.</span></span>|  
|`pmThrowOnUnmappableCharDisabled`|<span data-ttu-id="38709-122">Non generare un'eccezione quando il gestore di marshalling di interoperabilità rileva un carattere unmappable.</span><span class="sxs-lookup"><span data-stu-id="38709-122">Do not throw an exception when the interop marshaler encounters an unmappable character.</span></span>|  
|`pmThrowOnUnmappableCharMask`|<span data-ttu-id="38709-123">Riservata</span><span class="sxs-lookup"><span data-stu-id="38709-123">Reserved</span></span>|  
|`pmSupportsLastError`|<span data-ttu-id="38709-124">Consentire al chiamato di chiamare la funzione Win32 `SetLastError` prima di restituire dal metodo con attributi.</span><span class="sxs-lookup"><span data-stu-id="38709-124">Allow the callee to call the Win32 `SetLastError` function before returning from the attributed method.</span></span>|  
|`pmCallConvMask`|<span data-ttu-id="38709-125">Riservata</span><span class="sxs-lookup"><span data-stu-id="38709-125">Reserved</span></span>|  
|`pmCallConvWinapi`|<span data-ttu-id="38709-126">Usare la convenzione di chiamata della piattaforma predefinita.</span><span class="sxs-lookup"><span data-stu-id="38709-126">Use the default platform calling convention.</span></span> <span data-ttu-id="38709-127">In Windows, ad esempio, il valore predefinito è `StdCall` e Windows CE .NET è `Cdecl`.</span><span class="sxs-lookup"><span data-stu-id="38709-127">For example, on Windows the default is `StdCall` and on Windows CE .NET it is `Cdecl`.</span></span>|  
|`pmCallConvCdecl`|<span data-ttu-id="38709-128">Utilizzare la convenzione di chiamata `Cdecl`.</span><span class="sxs-lookup"><span data-stu-id="38709-128">Use the `Cdecl` calling convention.</span></span> <span data-ttu-id="38709-129">In questo caso, il chiamante pulisce lo stack.</span><span class="sxs-lookup"><span data-stu-id="38709-129">In this case, the caller cleans the stack.</span></span> <span data-ttu-id="38709-130">In questo modo è possibile chiamare funzioni con `varargs`, ovvero funzioni che accettano un numero variabile di parametri.</span><span class="sxs-lookup"><span data-stu-id="38709-130">This enables calling functions with `varargs` (that is, functions that accept a variable number of parameters).</span></span>|  
|`pmCallConvStdcall`|<span data-ttu-id="38709-131">Utilizzare la convenzione di chiamata `StdCall`.</span><span class="sxs-lookup"><span data-stu-id="38709-131">Use the `StdCall` calling convention.</span></span> <span data-ttu-id="38709-132">In questo caso, il chiamato pulisce lo stack.</span><span class="sxs-lookup"><span data-stu-id="38709-132">In this case, the callee cleans the stack.</span></span> <span data-ttu-id="38709-133">Si tratta della convenzione predefinita per la chiamata di funzioni non gestite con platform invoke.</span><span class="sxs-lookup"><span data-stu-id="38709-133">This is the default convention for calling unmanaged functions with platform invoke.</span></span>|  
|`pmCallConvThiscall`|<span data-ttu-id="38709-134">Utilizzare la convenzione di chiamata `ThisCall`.</span><span class="sxs-lookup"><span data-stu-id="38709-134">Use the `ThisCall` calling convention.</span></span> <span data-ttu-id="38709-135">In questo caso, il primo parametro è il puntatore `this` e viene archiviato nel registro ECX.</span><span class="sxs-lookup"><span data-stu-id="38709-135">In this case, the first parameter is the `this` pointer and is stored in register ECX.</span></span> <span data-ttu-id="38709-136">Gli altri parametri vengono inseriti nello stack.</span><span class="sxs-lookup"><span data-stu-id="38709-136">Other parameters are pushed on the stack.</span></span> <span data-ttu-id="38709-137">La convenzione di chiamata `ThisCall` viene utilizzata per chiamare metodi sulle classi esportate da una DLL non gestita.</span><span class="sxs-lookup"><span data-stu-id="38709-137">The `ThisCall` calling convention is used to call methods on classes exported from an unmanaged DLL.</span></span>|  
|`pmCallConvFastcall`|<span data-ttu-id="38709-138">Riservato.</span><span class="sxs-lookup"><span data-stu-id="38709-138">Reserved.</span></span>|  
|`pmMaxValue`|<span data-ttu-id="38709-139">Riservato.</span><span class="sxs-lookup"><span data-stu-id="38709-139">Reserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="38709-140">Requisiti</span><span class="sxs-lookup"><span data-stu-id="38709-140">Requirements</span></span>  
 <span data-ttu-id="38709-141">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38709-141">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38709-142">**Intestazione:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="38709-142">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="38709-143">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38709-143">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38709-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38709-144">See also</span></span>

- [<span data-ttu-id="38709-145">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="38709-145">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
