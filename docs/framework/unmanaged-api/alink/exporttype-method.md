---
title: Metodo ExportType
ms.date: 03/30/2017
api_name:
- IALink.ExportType
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportType
helpviewer_keywords:
- ExportType method
ms.assetid: 91a7ce63-f5b8-4f16-b2c4-e1d0baa88944
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 455f71c5b576d1b57db591dab2a3e59f8a5eed67
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777293"
---
# <a name="exporttype-method"></a><span data-ttu-id="1080c-102">Metodo ExportType</span><span class="sxs-lookup"><span data-stu-id="1080c-102">ExportType Method</span></span>
<span data-ttu-id="1080c-103">Specifica che un tipo può essere esportato.</span><span class="sxs-lookup"><span data-stu-id="1080c-103">Specifies that a type is exportable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1080c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1080c-104">Syntax</span></span>  
  
```cpp  
HRESULT ExportType(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="1080c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1080c-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="1080c-106">ID dell'assembly da cui eseguire l'esportazione.</span><span class="sxs-lookup"><span data-stu-id="1080c-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="1080c-107">Token file o ID assembly del file che definisce il tipo esportabile.</span><span class="sxs-lookup"><span data-stu-id="1080c-107">File token or assembly ID of file that defines the exportable type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="1080c-108">Token di tipo da rendere esportabile.</span><span class="sxs-lookup"><span data-stu-id="1080c-108">Token of type to be made exportable.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="1080c-109">Nome completo del tipo da rendere esportabile.</span><span class="sxs-lookup"><span data-stu-id="1080c-109">Fully qualified type name to be made exportable.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="1080c-110">`ComType`flag come `tdPublic` o `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="1080c-110">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="1080c-111">Questo parametro può essere passato al [Metodo DefineExportedType](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="1080c-111">This parameter may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="1080c-112">Riceve il token per il tipo esportato.</span><span class="sxs-lookup"><span data-stu-id="1080c-112">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1080c-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1080c-113">Return Value</span></span>  
 <span data-ttu-id="1080c-114">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="1080c-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1080c-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1080c-115">Requirements</span></span>  
 <span data-ttu-id="1080c-116">Richiede ALink. h</span><span class="sxs-lookup"><span data-stu-id="1080c-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1080c-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1080c-117">See also</span></span>

- [<span data-ttu-id="1080c-118">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="1080c-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="1080c-119">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="1080c-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="1080c-120">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="1080c-120">ALink API</span></span>](index.md)
