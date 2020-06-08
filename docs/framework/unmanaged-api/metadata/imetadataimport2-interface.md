---
title: Interfaccia IMetaDataImport2
ms.date: 03/30/2017
api_name:
- IMetaDataImport2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2
helpviewer_keywords:
- IMetaDataImport2 interface [.NET Framework metadata]
ms.assetid: d39b2b87-ba53-4771-ae53-952a68452511
topic_type:
- apiref
ms.openlocfilehash: fe9e87618291218a41e52f80198ce9068c9c56e2
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490394"
---
# <a name="imetadataimport2-interface"></a><span data-ttu-id="49328-102">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="49328-102">IMetaDataImport2 Interface</span></span>
<span data-ttu-id="49328-103">Estende l'interfaccia [IMetaDataImport](imetadataimport-interface.md) per fornire la funzionalità di utilizzo di tipi generici.</span><span class="sxs-lookup"><span data-stu-id="49328-103">Extends the [IMetaDataImport](imetadataimport-interface.md) interface to provide the capability of working with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="49328-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="49328-104">Methods</span></span>  
  
|<span data-ttu-id="49328-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="49328-105">Method</span></span>|<span data-ttu-id="49328-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="49328-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="49328-107">Metodo EnumGenericParamConstraints</span><span class="sxs-lookup"><span data-stu-id="49328-107">EnumGenericParamConstraints Method</span></span>](imetadataimport2-enumgenericparamconstraints-method.md)|<span data-ttu-id="49328-108">Ottiene un enumeratore per una matrice di vincoli di parametri generici associati al parametro generico rappresentato dal token specificato.</span><span class="sxs-lookup"><span data-stu-id="49328-108">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="49328-109">Metodo EnumGenericParams</span><span class="sxs-lookup"><span data-stu-id="49328-109">EnumGenericParams Method</span></span>](imetadataimport2-enumgenericparams-method.md)|<span data-ttu-id="49328-110">Ottiene un enumeratore per una matrice di token di parametro generici associati al token TypeDef o MethodDef specificato.</span><span class="sxs-lookup"><span data-stu-id="49328-110">Gets an enumerator for an array of generic parameter tokens associated with the specified TypeDef or MethodDef token.</span></span>|  
|[<span data-ttu-id="49328-111">Metodo EnumMethodSpecs</span><span class="sxs-lookup"><span data-stu-id="49328-111">EnumMethodSpecs Method</span></span>](imetadataimport2-enummethodspecs-method.md)|<span data-ttu-id="49328-112">Ottiene un enumeratore per una matrice di token MethodSpec associati al token MethodDef o MemberRef specificato.</span><span class="sxs-lookup"><span data-stu-id="49328-112">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>|  
|[<span data-ttu-id="49328-113">Metodo GetGenericParamConstraintProps</span><span class="sxs-lookup"><span data-stu-id="49328-113">GetGenericParamConstraintProps Method</span></span>](imetadataimport2-getgenericparamconstraintprops-method.md)|<span data-ttu-id="49328-114">Ottiene i metadati associati al vincolo del parametro generico rappresentato dal token di vincolo specificato.</span><span class="sxs-lookup"><span data-stu-id="49328-114">Gets the metadata associated with the generic parameter constraint represented by the specified constraint token.</span></span>|  
|[<span data-ttu-id="49328-115">Metodo GetGenericParamProps</span><span class="sxs-lookup"><span data-stu-id="49328-115">GetGenericParamProps Method</span></span>](imetadataimport2-getgenericparamprops-method.md)|<span data-ttu-id="49328-116">Ottiene i metadati associati al parametro generico rappresentato dal token specificato.</span><span class="sxs-lookup"><span data-stu-id="49328-116">Gets the metadata associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="49328-117">Metodo GetMethodSpecProps</span><span class="sxs-lookup"><span data-stu-id="49328-117">GetMethodSpecProps Method</span></span>](imetadataimport2-getmethodspecprops-method.md)|<span data-ttu-id="49328-118">Ottiene la firma dei metadati del metodo a cui fa riferimento il token MethodSpec specificato.</span><span class="sxs-lookup"><span data-stu-id="49328-118">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>|  
|[<span data-ttu-id="49328-119">Metodo GetPEKind</span><span class="sxs-lookup"><span data-stu-id="49328-119">GetPEKind Method</span></span>](imetadataimport2-getpekind-method.md)|<span data-ttu-id="49328-120">Ottiene un valore che identifica la natura del codice in un file eseguibile portabile (PE, Portable Executable), in genere un file DLL o EXE, definito nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="49328-120">Gets a value identifying the nature of the code in a portable executable (PE) file, typically a DLL or EXE file, defined in the current metadata scope</span></span>|  
|[<span data-ttu-id="49328-121">Metodo GetVersionString</span><span class="sxs-lookup"><span data-stu-id="49328-121">GetVersionString Method</span></span>](imetadataimport2-getversionstring-method.md)|<span data-ttu-id="49328-122">Ottiene il numero di versione del runtime utilizzato per compilare l'assembly.</span><span class="sxs-lookup"><span data-stu-id="49328-122">Gets the version number of the runtime that was used to build the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="49328-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="49328-123">Requirements</span></span>  
 <span data-ttu-id="49328-124">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49328-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49328-125">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="49328-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="49328-126">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="49328-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="49328-127">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49328-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49328-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49328-128">See also</span></span>

- <xref:System.Reflection.PortableExecutableKinds>
- [<span data-ttu-id="49328-129">Interfacce di metadati</span><span class="sxs-lookup"><span data-stu-id="49328-129">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="49328-130">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="49328-130">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
