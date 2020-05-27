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
# <a name="corfieldattr-enumeration"></a><span data-ttu-id="3756e-102">Enumerazione CorFieldAttr</span><span class="sxs-lookup"><span data-stu-id="3756e-102">CorFieldAttr Enumeration</span></span>
<span data-ttu-id="3756e-103">Contiene valori che descrivono i metadati relativi a un campo.</span><span class="sxs-lookup"><span data-stu-id="3756e-103">Contains values that describe metadata about a field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3756e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3756e-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="3756e-105">Membri</span><span class="sxs-lookup"><span data-stu-id="3756e-105">Members</span></span>  
  
|<span data-ttu-id="3756e-106">Membro</span><span class="sxs-lookup"><span data-stu-id="3756e-106">Member</span></span>|<span data-ttu-id="3756e-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3756e-107">Description</span></span>|  
|------------|-----------------|  
|`fdFieldAccessMask`|<span data-ttu-id="3756e-108">Specifica le informazioni di accessibilità.</span><span class="sxs-lookup"><span data-stu-id="3756e-108">Specifies accessibility information.</span></span>|  
|`fdPrivateScope`|<span data-ttu-id="3756e-109">Specifica che non è possibile fare riferimento al campo.</span><span class="sxs-lookup"><span data-stu-id="3756e-109">Specifies that the field cannot be referenced.</span></span>|  
|`fdPrivate`|<span data-ttu-id="3756e-110">Specifica che il campo è accessibile solo dal tipo padre.</span><span class="sxs-lookup"><span data-stu-id="3756e-110">Specifies that the field is accessible only by its parent type.</span></span>|  
|`fdFamANDAssem`|<span data-ttu-id="3756e-111">Specifica che il campo è accessibile dalle classi derivate nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="3756e-111">Specifies that the field is accessible by derived classes in its assembly.</span></span>|  
|`fdAssembly`|<span data-ttu-id="3756e-112">Specifica che il campo è accessibile da tutti i tipi nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="3756e-112">Specifies that the field is accessible by all types in its assembly.</span></span>|  
|`fdFamily`|<span data-ttu-id="3756e-113">Specifica che il campo è accessibile solo dal tipo e dalle classi derivate.</span><span class="sxs-lookup"><span data-stu-id="3756e-113">Specifies that the field is accessible only by its type and derived classes.</span></span>|  
|`fdFamORAssem`|<span data-ttu-id="3756e-114">Specifica che il campo è accessibile dalle classi derivate e da tutti i tipi nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="3756e-114">Specifies that the field is accessible by derived classes and by all types in its assembly.</span></span>|  
|`fdPublic`|<span data-ttu-id="3756e-115">Specifica che il campo è accessibile da tutti i tipi con visibilità di questo ambito.</span><span class="sxs-lookup"><span data-stu-id="3756e-115">Specifies that the field is accessible by all types with visibility of this scope.</span></span>|  
|`fdStatic`|<span data-ttu-id="3756e-116">Specifica che il campo è un membro del tipo anziché di un membro di istanza.</span><span class="sxs-lookup"><span data-stu-id="3756e-116">Specifies that the field is a member of its type rather than an instance member.</span></span>|  
|`fdInitOnly`|<span data-ttu-id="3756e-117">Specifica che il campo non può essere modificato dopo l'inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="3756e-117">Specifies that the field cannot be changed after it is initialized.</span></span>|  
|`fdLiteral`|<span data-ttu-id="3756e-118">Specifica che il valore del campo è una costante in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="3756e-118">Specifies that the field value is a compile-time constant.</span></span>|  
|`fdNotSerialized`|<span data-ttu-id="3756e-119">Specifica che il campo non viene serializzato quando il tipo è remoto.</span><span class="sxs-lookup"><span data-stu-id="3756e-119">Specifies that the field is not serialized when its type is remoted.</span></span>|  
|`fdSpecialName`|<span data-ttu-id="3756e-120">Specifica che il campo è speciale e che il nome descrive come.</span><span class="sxs-lookup"><span data-stu-id="3756e-120">Specifies that the field is special, and that its name describes how.</span></span>|  
|`fdPinvokeImpl`|<span data-ttu-id="3756e-121">Specifica che l'implementazione del campo viene trasmessa tramite PInvoke.</span><span class="sxs-lookup"><span data-stu-id="3756e-121">Specifies that the field implementation is forwarded through PInvoke.</span></span>|  
|`fdReservedMask`|<span data-ttu-id="3756e-122">Riservato per uso interno da parte del Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="3756e-122">Reserved for internal use by the common language runtime.</span></span>|  
|`fdRTSpecialName`|<span data-ttu-id="3756e-123">Specifica che le API interne dei metadati di Common Language Runtime devono verificare la codifica del nome.</span><span class="sxs-lookup"><span data-stu-id="3756e-123">Specifies that the common language runtime metadata internal APIs should check the encoding of the name.</span></span>|  
|`fdHasFieldMarshal`|<span data-ttu-id="3756e-124">Specifica che il campo contiene informazioni di marshalling.</span><span class="sxs-lookup"><span data-stu-id="3756e-124">Specifies that the field contains marshaling information.</span></span>|  
|`fdHasDefault`|<span data-ttu-id="3756e-125">Specifica che il campo ha un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="3756e-125">Specifies that the field has a default value.</span></span>|  
|`fdHasFieldRVA`|<span data-ttu-id="3756e-126">Specifica che il campo dispone di un indirizzo virtuale relativo.</span><span class="sxs-lookup"><span data-stu-id="3756e-126">Specifies that the field has a relative virtual address.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3756e-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3756e-127">Requirements</span></span>  
 <span data-ttu-id="3756e-128">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3756e-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3756e-129">**Intestazione:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="3756e-129">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="3756e-130">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3756e-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3756e-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3756e-131">See also</span></span>

- [<span data-ttu-id="3756e-132">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="3756e-132">Metadata Enumerations</span></span>](metadata-enumerations.md)
