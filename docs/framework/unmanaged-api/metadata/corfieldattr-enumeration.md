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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7b07388b7f7385e93a6ca891e8ea98a2ce69763c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54576015"
---
# <a name="corfieldattr-enumeration"></a><span data-ttu-id="2a292-102">Enumerazione CorFieldAttr</span><span class="sxs-lookup"><span data-stu-id="2a292-102">CorFieldAttr Enumeration</span></span>
<span data-ttu-id="2a292-103">Contiene valori che descrivono i metadati relativi a un campo.</span><span class="sxs-lookup"><span data-stu-id="2a292-103">Contains values that describe metadata about a field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a292-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2a292-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="2a292-105">Membri</span><span class="sxs-lookup"><span data-stu-id="2a292-105">Members</span></span>  
  
|<span data-ttu-id="2a292-106">Membro</span><span class="sxs-lookup"><span data-stu-id="2a292-106">Member</span></span>|<span data-ttu-id="2a292-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2a292-107">Description</span></span>|  
|------------|-----------------|  
|`fdFieldAccessMask`|<span data-ttu-id="2a292-108">Specifica le informazioni sull'accessibilità.</span><span class="sxs-lookup"><span data-stu-id="2a292-108">Specifies accessibility information.</span></span>|  
|`fdPrivateScope`|<span data-ttu-id="2a292-109">Specifica che il campo non può far riferimento.</span><span class="sxs-lookup"><span data-stu-id="2a292-109">Specifies that the field cannot be referenced.</span></span>|  
|`fdPrivate`|<span data-ttu-id="2a292-110">Specifica che il campo è accessibile solo dal relativo tipo padre.</span><span class="sxs-lookup"><span data-stu-id="2a292-110">Specifies that the field is accessible only by its parent type.</span></span>|  
|`fdFamANDAssem`|<span data-ttu-id="2a292-111">Specifica che il campo è accessibile dalle classi derivate nel relativo assembly.</span><span class="sxs-lookup"><span data-stu-id="2a292-111">Specifies that the field is accessible by derived classes in its assembly.</span></span>|  
|`fdAssembly`|<span data-ttu-id="2a292-112">Specifica che il campo è accessibile da tutti i tipi nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="2a292-112">Specifies that the field is accessible by all types in its assembly.</span></span>|  
|`fdFamily`|<span data-ttu-id="2a292-113">Specifica che il campo è accessibile solo dal relativo tipo e le classi derivate.</span><span class="sxs-lookup"><span data-stu-id="2a292-113">Specifies that the field is accessible only by its type and derived classes.</span></span>|  
|`fdFamORAssem`|<span data-ttu-id="2a292-114">Specifica che il campo è accessibile dalle classi derivate e da tutti i tipi nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="2a292-114">Specifies that the field is accessible by derived classes and by all types in its assembly.</span></span>|  
|`fdPublic`|<span data-ttu-id="2a292-115">Specifica che il campo è accessibile da tutti i tipi con visibilità dell'ambito.</span><span class="sxs-lookup"><span data-stu-id="2a292-115">Specifies that the field is accessible by all types with visibility of this scope.</span></span>|  
|`fdStatic`|<span data-ttu-id="2a292-116">Specifica che il campo è un membro del suo tipo anziché un membro di istanza.</span><span class="sxs-lookup"><span data-stu-id="2a292-116">Specifies that the field is a member of its type rather than an instance member.</span></span>|  
|`fdInitOnly`|<span data-ttu-id="2a292-117">Specifica che il campo non può essere modificato dopo l'inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="2a292-117">Specifies that the field cannot be changed after it is initialized.</span></span>|  
|`fdLiteral`|<span data-ttu-id="2a292-118">Specifica che il valore del campo è una costante in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="2a292-118">Specifies that the field value is a compile-time constant.</span></span>|  
|`fdNotSerialized`|<span data-ttu-id="2a292-119">Specifica che il campo non è serializzato quando il relativo tipo viene eseguita in modalità remota.</span><span class="sxs-lookup"><span data-stu-id="2a292-119">Specifies that the field is not serialized when its type is remoted.</span></span>|  
|`fdSpecialName`|<span data-ttu-id="2a292-120">Specifica che il campo è speciale e che il relativo nome viene descritto come.</span><span class="sxs-lookup"><span data-stu-id="2a292-120">Specifies that the field is special, and that its name describes how.</span></span>|  
|`fdPinvokeImpl`|<span data-ttu-id="2a292-121">Specifica che l'implementazione del campo è inoltrata tramite PInvoke.</span><span class="sxs-lookup"><span data-stu-id="2a292-121">Specifies that the field implementation is forwarded through PInvoke.</span></span>|  
|`fdReservedMask`|<span data-ttu-id="2a292-122">Riservato per uso interno da common language runtime.</span><span class="sxs-lookup"><span data-stu-id="2a292-122">Reserved for internal use by the common language runtime.</span></span>|  
|`fdRTSpecialName`|<span data-ttu-id="2a292-123">Specifica che i metadati di common language runtime le API interne devono verificare la codifica del nome.</span><span class="sxs-lookup"><span data-stu-id="2a292-123">Specifies that the common language runtime metadata internal APIs should check the encoding of the name.</span></span>|  
|`fdHasFieldMarshal`|<span data-ttu-id="2a292-124">Specifica che il campo contiene informazioni di marshalling.</span><span class="sxs-lookup"><span data-stu-id="2a292-124">Specifies that the field contains marshaling information.</span></span>|  
|`fdHasDefault`|<span data-ttu-id="2a292-125">Specifica che il campo ha un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="2a292-125">Specifies that the field has a default value.</span></span>|  
|`fdHasFieldRVA`|<span data-ttu-id="2a292-126">Specifica che il campo ha un indirizzo virtuale relativo.</span><span class="sxs-lookup"><span data-stu-id="2a292-126">Specifies that the field has a relative virtual address.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2a292-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2a292-127">Requirements</span></span>  
 <span data-ttu-id="2a292-128">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a292-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a292-129">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="2a292-129">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="2a292-130">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a292-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a292-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a292-131">See also</span></span>
- [<span data-ttu-id="2a292-132">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="2a292-132">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
