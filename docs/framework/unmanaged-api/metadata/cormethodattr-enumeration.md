---
title: Enumerazione CorMethodAttr
ms.date: 03/30/2017
api_name:
- CorMethodAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodAttr
helpviewer_keywords:
- CorMethodAttr enumeration [.NET Framework metadata]
ms.assetid: 4e0c3521-e54d-43c1-9857-cc76b49b8ffc
topic_type:
- apiref
ms.openlocfilehash: 779a8f88b7521aa4b0a75594552981b41714ee3f
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007676"
---
# <a name="cormethodattr-enumeration"></a><span data-ttu-id="f72b1-102">Enumerazione CorMethodAttr</span><span class="sxs-lookup"><span data-stu-id="f72b1-102">CorMethodAttr Enumeration</span></span>
<span data-ttu-id="f72b1-103">Contiene valori che descrivono le funzionalità di un metodo.</span><span class="sxs-lookup"><span data-stu-id="f72b1-103">Contains values that describe the features of a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f72b1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f72b1-104">Syntax</span></span>  
  
```cpp  
typedef enum CorMethodAttr {  
  
    mdMemberAccessMask          =   0x0007,  
    mdPrivateScope              =   0x0000,  
    mdPrivate                   =   0x0001,  
    mdFamANDAssem               =   0x0002,  
    mdAssem                     =   0x0003,  
    mdFamily                    =   0x0004,  
    mdFamORAssem                =   0x0005,  
    mdPublic                    =   0x0006,  
  
    mdStatic                    =   0x0010,  
    mdFinal                     =   0x0020,  
    mdVirtual                   =   0x0040,  
    mdHideBySig                 =   0x0080,  
  
    mdVtableLayoutMask          =   0x0100,  
    mdReuseSlot                 =   0x0000,  
    mdNewSlot                   =   0x0100,  
  
    mdCheckAccessOnOverride     =   0x0200,  
    mdAbstract                  =   0x0400,  
    mdSpecialName               =   0x0800,  
  
    mdPinvokeImpl               =   0x2000,  
    mdUnmanagedExport           =   0x0008,  
  
    mdReservedMask              =   0xd000,  
    mdRTSpecialName             =   0x1000,  
    mdHasSecurity               =   0x4000,  
    mdRequireSecObject          =   0x8000,  
  
} CorMethodAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="f72b1-105">Membri</span><span class="sxs-lookup"><span data-stu-id="f72b1-105">Members</span></span>  
  
|<span data-ttu-id="f72b1-106">Membro</span><span class="sxs-lookup"><span data-stu-id="f72b1-106">Member</span></span>|<span data-ttu-id="f72b1-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f72b1-107">Description</span></span>|  
|------------|-----------------|  
|`mdMemberAccessMask`|<span data-ttu-id="f72b1-108">Specifica l'accesso ai membri.</span><span class="sxs-lookup"><span data-stu-id="f72b1-108">Specifies member access.</span></span>|  
|`mdPrivateScope`|<span data-ttu-id="f72b1-109">Specifica che non è possibile fare riferimento al membro.</span><span class="sxs-lookup"><span data-stu-id="f72b1-109">Specifies that the member cannot be referenced.</span></span>|  
|`mdPrivate`|<span data-ttu-id="f72b1-110">Specifica che il membro è accessibile solo dal tipo padre.</span><span class="sxs-lookup"><span data-stu-id="f72b1-110">Specifies that the member is accessible only by the parent type.</span></span>|  
|`mdFamANDAssem`|<span data-ttu-id="f72b1-111">Specifica che il membro è accessibile dai sottotipi solo nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="f72b1-111">Specifies that the member is accessible by subtypes only in this assembly.</span></span>|  
|`mdAssem`|<span data-ttu-id="f72b1-112">Specifica che il membro è accessibilmente da chiunque nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="f72b1-112">Specifies that the member is accessibly by anyone in the assembly.</span></span>|  
|`mdFamily`|<span data-ttu-id="f72b1-113">Specifica che il membro è accessibile solo dal tipo e dai sottotipi.</span><span class="sxs-lookup"><span data-stu-id="f72b1-113">Specifies that the member is accessible only by type and subtypes.</span></span>|  
|`mdFamORAssem`|<span data-ttu-id="f72b1-114">Specifica che il membro è accessibile dalle classi derivate e da altri tipi nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="f72b1-114">Specifies that the member is accessible by derived classes and by other types in its assembly.</span></span>|  
|`mdPublic`|<span data-ttu-id="f72b1-115">Specifica che il membro è accessibile da tutti i tipi con accesso all'ambito.</span><span class="sxs-lookup"><span data-stu-id="f72b1-115">Specifies that the member is accessible by all types with access to the scope.</span></span>|  
|`mdStatic`|<span data-ttu-id="f72b1-116">Specifica che il membro è definito come parte del tipo anziché come membro di un'istanza di.</span><span class="sxs-lookup"><span data-stu-id="f72b1-116">Specifies that the member is defined as part of the type rather than as a member of an instance.</span></span>|  
|`mdFinal`|<span data-ttu-id="f72b1-117">Specifica che non è possibile eseguire l'override del metodo.</span><span class="sxs-lookup"><span data-stu-id="f72b1-117">Specifies that the method cannot be overridden.</span></span>|  
|`mdVirtual`|<span data-ttu-id="f72b1-118">Specifica che il metodo può essere sottoposto a override.</span><span class="sxs-lookup"><span data-stu-id="f72b1-118">Specifies that the method can be overridden.</span></span>|  
|`mdHideBySig`|<span data-ttu-id="f72b1-119">Specifica che il metodo viene nascosto in base al nome e alla firma, anziché semplicemente al nome.</span><span class="sxs-lookup"><span data-stu-id="f72b1-119">Specifies that the method hides by name and signature, rather than just by name.</span></span>|  
|`mdVtableLayoutMask`|<span data-ttu-id="f72b1-120">Specifica il layout della tabella virtuale.</span><span class="sxs-lookup"><span data-stu-id="f72b1-120">Specifies virtual table layout.</span></span>|  
|`mdReuseSlot`|<span data-ttu-id="f72b1-121">Specifica che lo slot utilizzato per questo metodo nella tabella virtuale deve essere riutilizzato.</span><span class="sxs-lookup"><span data-stu-id="f72b1-121">Specifies that the slot used for this method in the virtual table be reused.</span></span> <span data-ttu-id="f72b1-122">Questo è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="f72b1-122">This is the default.</span></span>|  
|`mdNewSlot`|<span data-ttu-id="f72b1-123">Specifica che il metodo ottiene sempre un nuovo slot nella tabella virtuale.</span><span class="sxs-lookup"><span data-stu-id="f72b1-123">Specifies that the method always gets a new slot in the virtual table.</span></span>|  
|`mdCheckAccessOnOverride`|<span data-ttu-id="f72b1-124">Specifica che il metodo può essere sottoposto a override dagli stessi tipi a cui è visibile.</span><span class="sxs-lookup"><span data-stu-id="f72b1-124">Specifies that the method can be overridden by the same types to which it is visible.</span></span>|  
|`mdAbstract`|<span data-ttu-id="f72b1-125">Specifica che il metodo non è implementato.</span><span class="sxs-lookup"><span data-stu-id="f72b1-125">Specifies that the method is not implemented.</span></span>|  
|`mdSpecialName`|<span data-ttu-id="f72b1-126">Specifica che il metodo è speciale e che il nome descrive come.</span><span class="sxs-lookup"><span data-stu-id="f72b1-126">Specifies that the method is special, and that its name describes how.</span></span>|  
|`mdPinvokeImpl`|<span data-ttu-id="f72b1-127">Specifica che l'implementazione del metodo viene trasmessa mediante PInvoke.</span><span class="sxs-lookup"><span data-stu-id="f72b1-127">Specifies that the method implementation is forwarded using PInvoke.</span></span>|  
|`mdUnmanagedExport`|<span data-ttu-id="f72b1-128">Specifica che il metodo è un metodo gestito esportato nel codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="f72b1-128">Specifies that the method is a managed method exported to unmanaged code.</span></span>|  
|`mdReservedMask`|<span data-ttu-id="f72b1-129">Riservato per uso interno da parte del Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="f72b1-129">Reserved for internal use by the common language runtime.</span></span>|  
|`mdRTSpecialName`|<span data-ttu-id="f72b1-130">Specifica che il Common Language Runtime deve controllare la codifica del nome del metodo.</span><span class="sxs-lookup"><span data-stu-id="f72b1-130">Specifies that the common language runtime should check the encoding of the method name.</span></span>|  
|`mdHasSecurity`|<span data-ttu-id="f72b1-131">Specifica che al metodo è associata una sicurezza.</span><span class="sxs-lookup"><span data-stu-id="f72b1-131">Specifies that the method has security associated with it.</span></span>|  
|`mdRequireSecObject`|<span data-ttu-id="f72b1-132">Specifica che il metodo chiama un altro metodo che contiene il codice di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="f72b1-132">Specifies that the method calls another method containing security code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f72b1-133">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f72b1-133">Requirements</span></span>  
 <span data-ttu-id="f72b1-134">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f72b1-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f72b1-135">**Intestazione:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="f72b1-135">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="f72b1-136">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f72b1-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f72b1-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f72b1-137">See also</span></span>

- [<span data-ttu-id="f72b1-138">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="f72b1-138">Metadata Enumerations</span></span>](metadata-enumerations.md)
