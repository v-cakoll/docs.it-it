---
title: Enumerazione CorSymSearchPolicyAttributes
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorSymSearchPolicyAttributes
api_location: mscoree.dll
api_type: COM
f1_keywords: CorSymSearchPolicyAttributes
helpviewer_keywords: CorSymSearchPolicyAttributes enumeration [.NET Framework debugging]
ms.assetid: 03abde84-930a-49d3-bac3-23abb34a0184
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 016378de8d4ba4b6f16f7e7b91b6427f73c9687d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="corsymsearchpolicyattributes-enumeration"></a><span data-ttu-id="3e6e6-102">Enumerazione CorSymSearchPolicyAttributes</span><span class="sxs-lookup"><span data-stu-id="3e6e6-102">CorSymSearchPolicyAttributes Enumeration</span></span>
<span data-ttu-id="3e6e6-103">Specifica i criteri da utilizzare quando si esegue una ricerca di un lettore di simboli.</span><span class="sxs-lookup"><span data-stu-id="3e6e6-103">Specifies the policy to be used when doing a search for a symbol reader.</span></span> <span data-ttu-id="3e6e6-104">Queste costanti vengono utilizzate per la [ISymUnmanagedBinder2:: Getreaderforfile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) e [ISymUnmanagedBinder3:: GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) metodi.</span><span class="sxs-lookup"><span data-stu-id="3e6e6-104">These constants are used by the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) and [ISymUnmanagedBinder3::GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) methods.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3e6e6-105">È un rischio per la sicurezza per aprire un file di programma (PDB) di database da un'origine non attendibile.</span><span class="sxs-lookup"><span data-stu-id="3e6e6-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e6e6-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3e6e6-106">Syntax</span></span>  
  
```  
typedef enum CorSymSearchPolicyAttributes  
{  
    AllowRegistryAccess      = 0x1,       
    AllowSymbolServerAccess  = 0x2,  
    AllowOriginalPathAccess  = 0x4,     //      
    AllowReferencePathAccess = 0x8  
} CorSymSearchPolicyAttributes;  
```  
  
## <a name="members"></a><span data-ttu-id="3e6e6-107">Membri</span><span class="sxs-lookup"><span data-stu-id="3e6e6-107">Members</span></span>  
  
|<span data-ttu-id="3e6e6-108">Membro</span><span class="sxs-lookup"><span data-stu-id="3e6e6-108">Member</span></span>|<span data-ttu-id="3e6e6-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3e6e6-109">Description</span></span>|  
|------------|-----------------|  
|`AllowRegistryAccess`|<span data-ttu-id="3e6e6-110">Esegue una query del Registro di sistema per i percorsi di ricerca di simboli.</span><span class="sxs-lookup"><span data-stu-id="3e6e6-110">Queries the registry for symbol search paths.</span></span>|  
|`AllowSymbolServerAccess`|<span data-ttu-id="3e6e6-111">Accede a un server di simboli.</span><span class="sxs-lookup"><span data-stu-id="3e6e6-111">Accesses a symbol server.</span></span>|  
|`AllowOriginalPathAccess`|<span data-ttu-id="3e6e6-112">Cerca nel percorso specificato nella directory di Debug.</span><span class="sxs-lookup"><span data-stu-id="3e6e6-112">Searches the path specified in the Debug directory.</span></span>|  
|`AllowReferencePathAccess`|<span data-ttu-id="3e6e6-113">Cerca il file PDB in luogo in cui il file .exe.</span><span class="sxs-lookup"><span data-stu-id="3e6e6-113">Searches for the PDB in the place where the .exe file is.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3e6e6-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3e6e6-114">Requirements</span></span>  
 <span data-ttu-id="3e6e6-115">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3e6e6-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e6e6-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3e6e6-116">See Also</span></span>  
 [<span data-ttu-id="3e6e6-117">Enumerazioni dell'archivio di simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="3e6e6-117">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
