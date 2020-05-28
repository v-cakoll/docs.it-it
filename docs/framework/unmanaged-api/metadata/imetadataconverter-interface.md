---
title: Interfaccia IMetaDataConverter
ms.date: 03/30/2017
api_name:
- IMetaDataConverter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter
helpviewer_keywords:
- IMetaDataConverter interface [.NET Framework metadata]
ms.assetid: 9caea662-0167-4267-b14a-2fa42c3be4ea
topic_type:
- apiref
ms.openlocfilehash: b6ca7c619d32e69ffac20b80561171d0320db2d4
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008378"
---
# <a name="imetadataconverter-interface"></a><span data-ttu-id="d19b2-102">Interfaccia IMetaDataConverter</span><span class="sxs-lookup"><span data-stu-id="d19b2-102">IMetaDataConverter Interface</span></span>
<span data-ttu-id="d19b2-103">Fornisce metodi per eseguire il mapping delle librerie dei tipi alle relative firme di metadati e per eseguire la conversione da una all'altra.</span><span class="sxs-lookup"><span data-stu-id="d19b2-103">Provides methods to map type libraries to their metadata signatures, and to convert from one to the other.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d19b2-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="d19b2-104">Methods</span></span>  
  
|<span data-ttu-id="d19b2-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="d19b2-105">Method</span></span>|<span data-ttu-id="d19b2-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d19b2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d19b2-107">Metodo GetMetaDataFromTypeInfo</span><span class="sxs-lookup"><span data-stu-id="d19b2-107">GetMetaDataFromTypeInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-getmetadatafromtypeinfo-method.md)|<span data-ttu-id="d19b2-108">Ottiene un puntatore a un'istanza di [IMetaDataImport](imetadataimport-interface.md) che rappresenta la firma dei metadati per la libreria dei tipi a cui fa riferimento l' `ITypeInfo` istanza specificata.</span><span class="sxs-lookup"><span data-stu-id="d19b2-108">Gets a pointer to an [IMetaDataImport](imetadataimport-interface.md) instance that represents the metadata signature for the type library referenced by the specified `ITypeInfo` instance.</span></span>|  
|[<span data-ttu-id="d19b2-109">Metodo GetMetaDataFromTypeLib</span><span class="sxs-lookup"><span data-stu-id="d19b2-109">GetMetaDataFromTypeLib Method</span></span>](imetadataconverter-getmetadatafromtypelib-method.md)|<span data-ttu-id="d19b2-110">Ottiene un puntatore a un' `IMetaDataImport` istanza di che rappresenta la firma dei metadati per la libreria dei tipi rappresentata dall'istanza di specificata `ITypeLib` .</span><span class="sxs-lookup"><span data-stu-id="d19b2-110">Gets a pointer to an `IMetaDataImport` instance that represents the metadata signature for the type library represented by the specified `ITypeLib` instance.</span></span>|  
|[<span data-ttu-id="d19b2-111">Metodo GetTypeLibFromMetaData</span><span class="sxs-lookup"><span data-stu-id="d19b2-111">GetTypeLibFromMetaData Method</span></span>](imetadataconverter-gettypelibfrommetadata-method.md)|<span data-ttu-id="d19b2-112">Ottiene un puntatore a un' `ITypeLib` istanza di che rappresenta la libreria dei tipi con i nomi di modulo e di libreria specificati.</span><span class="sxs-lookup"><span data-stu-id="d19b2-112">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified module and library names.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d19b2-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d19b2-113">Requirements</span></span>  
 <span data-ttu-id="d19b2-114">**Piattaforma:** Vedere [requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d19b2-114">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d19b2-115">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d19b2-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d19b2-116">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d19b2-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d19b2-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d19b2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d19b2-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d19b2-118">See also</span></span>

- [<span data-ttu-id="d19b2-119">Interfacce di metadati</span><span class="sxs-lookup"><span data-stu-id="d19b2-119">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="d19b2-120">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="d19b2-120">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
