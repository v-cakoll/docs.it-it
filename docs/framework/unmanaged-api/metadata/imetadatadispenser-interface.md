---
title: Interfaccia IMetaDataDispenser
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser
helpviewer_keywords:
- IMetaDataDispenser interface [.NET Framework metadata]
ms.assetid: 989840b3-9822-4ce5-a6c5-b375d3340a7a
topic_type:
- apiref
ms.openlocfilehash: 2bdfe65dbf923ec61d91a259b5257d892fef53da
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007338"
---
# <a name="imetadatadispenser-interface"></a><span data-ttu-id="49d45-102">Interfaccia IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="49d45-102">IMetaDataDispenser Interface</span></span>
<span data-ttu-id="49d45-103">Fornisce metodi per creare un nuovo ambito di metadati o per aprirne uno esistente.</span><span class="sxs-lookup"><span data-stu-id="49d45-103">Provides methods to create a new metadata scope, or open an existing one.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="49d45-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="49d45-104">Methods</span></span>  
  
|<span data-ttu-id="49d45-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="49d45-105">Method</span></span>|<span data-ttu-id="49d45-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="49d45-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="49d45-107">Metodo DefineScope</span><span class="sxs-lookup"><span data-stu-id="49d45-107">DefineScope Method</span></span>](imetadatadispenser-definescope-method.md)|<span data-ttu-id="49d45-108">Crea una nuova area in memoria in cui è possibile creare nuovi metadati.</span><span class="sxs-lookup"><span data-stu-id="49d45-108">Creates a new area in memory where you can create new metadata.</span></span>|  
|[<span data-ttu-id="49d45-109">Metodo OpenScope</span><span class="sxs-lookup"><span data-stu-id="49d45-109">OpenScope Method</span></span>](imetadatadispenser-openscope-method.md)|<span data-ttu-id="49d45-110">Apre un file su disco esistente ed esegue il mapping dei relativi metadati in memoria.</span><span class="sxs-lookup"><span data-stu-id="49d45-110">Opens an existing, on-disk file and maps its metadata into memory.</span></span>|  
|[<span data-ttu-id="49d45-111">Metodo OpenScopeOnMemory</span><span class="sxs-lookup"><span data-stu-id="49d45-111">OpenScopeOnMemory Method</span></span>](imetadatadispenser-openscopeonmemory-method.md)|<span data-ttu-id="49d45-112">Apre un'area di memoria contenente i metadati esistenti.</span><span class="sxs-lookup"><span data-stu-id="49d45-112">Opens an area of memory that contains existing metadata.</span></span> <span data-ttu-id="49d45-113">Questo metodo apre un'area di memoria specificata in cui i dati esistenti vengono considerati come metadati.</span><span class="sxs-lookup"><span data-stu-id="49d45-113">That is, this method opens a specified area of memory in which the existing data is treated as metadata.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="49d45-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="49d45-114">Requirements</span></span>  
 <span data-ttu-id="49d45-115">**Piattaforma:** Vedere [requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49d45-115">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49d45-116">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="49d45-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="49d45-117">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="49d45-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="49d45-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49d45-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49d45-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49d45-119">See also</span></span>

- [<span data-ttu-id="49d45-120">Interfaccia IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="49d45-120">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="49d45-121">Interfacce di metadati</span><span class="sxs-lookup"><span data-stu-id="49d45-121">Metadata Interfaces</span></span>](metadata-interfaces.md)
