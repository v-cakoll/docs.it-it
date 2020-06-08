---
title: Interfacce di metadati
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], metadata
- metadata interfaces [.NET Framework]
- interfaces (.NET Framework metadata]
ms.assetid: f5cdac93-a28c-48ef-8a19-5773376e9e7c
ms.openlocfilehash: 4d947388afb8d7f8f935ae3b8e8aff81efaf2ee4
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84489594"
---
# <a name="metadata-interfaces"></a><span data-ttu-id="5f30e-102">Interfacce di metadati</span><span class="sxs-lookup"><span data-stu-id="5f30e-102">Metadata Interfaces</span></span>
<span data-ttu-id="5f30e-103">Questa sezione descrive le interfacce non gestite che forniscono l'accesso ai metadati esposti dai tipi di .NET Framework, metodi, campi e così via.</span><span class="sxs-lookup"><span data-stu-id="5f30e-103">This section describes the unmanaged interfaces that provide access to the metadata exposed by the .NET Framework types, methods, fields, and so on.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5f30e-104">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="5f30e-104">In This Section</span></span>  
 [<span data-ttu-id="5f30e-105">Interfaccia ICeeGen</span><span class="sxs-lookup"><span data-stu-id="5f30e-105">ICeeGen Interface</span></span>](iceegen-interface.md)  
 <span data-ttu-id="5f30e-106">Fornisce metodi per la compilazione dinamica del codice.</span><span class="sxs-lookup"><span data-stu-id="5f30e-106">Provides methods for dynamic code compilation.</span></span>  
  
 [<span data-ttu-id="5f30e-107">Interfaccia IHostFilter</span><span class="sxs-lookup"><span data-stu-id="5f30e-107">IHostFilter Interface</span></span>](ihostfilter-interface.md)  
 <span data-ttu-id="5f30e-108">Fornisce un metodo per l'host di runtime per contrassegnare i token di metadati per l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="5f30e-108">Provides a method for the run-time host to mark metadata tokens for processing.</span></span>  
  
 [<span data-ttu-id="5f30e-109">Interfaccia IMapToken</span><span class="sxs-lookup"><span data-stu-id="5f30e-109">IMapToken Interface</span></span>](imaptoken-interface.md)  
 <span data-ttu-id="5f30e-110">Fornisce funzionalità per il mapping tra le firme di metadati importate e generate.</span><span class="sxs-lookup"><span data-stu-id="5f30e-110">Provides mapping capabilities between imported and emitted metadata signatures.</span></span>  
  
 [<span data-ttu-id="5f30e-111">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="5f30e-111">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)  
 <span data-ttu-id="5f30e-112">Fornisce metodi che supportano il modello autodescrittivo usato da Common Language Runtime (CLR) per risolvere e usare le risorse.</span><span class="sxs-lookup"><span data-stu-id="5f30e-112">Provides methods that support the self-description model used by the common language runtime (CLR) to resolve and consume resources.</span></span>  
  
 [<span data-ttu-id="5f30e-113">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="5f30e-113">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)  
 <span data-ttu-id="5f30e-114">Fornisce metodi per accedere ed esaminare il contenuto di un manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="5f30e-114">Provides methods to access and examine the contents of an assembly manifest.</span></span>  
  
 [<span data-ttu-id="5f30e-115">Interfaccia IMetaDataConverter</span><span class="sxs-lookup"><span data-stu-id="5f30e-115">IMetaDataConverter Interface</span></span>](imetadataconverter-interface.md)  
 <span data-ttu-id="5f30e-116">Fornisce metodi per eseguire il mapping delle librerie dei tipi alle relative firme di metadati e per eseguire la conversione da una all'altra.</span><span class="sxs-lookup"><span data-stu-id="5f30e-116">Provides methods to map type libraries to their metadata signatures, and to convert from one to the other.</span></span>  
  
 [<span data-ttu-id="5f30e-117">Interfaccia IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="5f30e-117">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)  
 <span data-ttu-id="5f30e-118">`IMetaDataDispenser` è obsoleto.</span><span class="sxs-lookup"><span data-stu-id="5f30e-118">`IMetaDataDispenser` is obsolete.</span></span> <span data-ttu-id="5f30e-119">Usare invece `IMetaDataDispenserEx`.</span><span class="sxs-lookup"><span data-stu-id="5f30e-119">Use `IMetaDataDispenserEx` instead.</span></span>  
  
 [<span data-ttu-id="5f30e-120">Interfaccia IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="5f30e-120">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)  
 <span data-ttu-id="5f30e-121">Fornisce metodi che eseguono il mapping di aree di memoria per la creazione o modifica dei metadati.</span><span class="sxs-lookup"><span data-stu-id="5f30e-121">Provides methods that map areas of memory for creating or modifying metadata.</span></span>  
  
 [<span data-ttu-id="5f30e-122">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="5f30e-122">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)  
 <span data-ttu-id="5f30e-123">Fornisce metodi per creare, modificare e archiviare i metadati sull'assembly nell'ambito attualmente definito.</span><span class="sxs-lookup"><span data-stu-id="5f30e-123">Provides methods to create, modify and store metadata about the assembly in the currently defined scope.</span></span>  
  
 [<span data-ttu-id="5f30e-124">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="5f30e-124">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)  
 <span data-ttu-id="5f30e-125">Fornisce metodi per la definizione e la modifica delle firme di metadati dei metodi e costruttori con parametri di tipo <xref:System.Type?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5f30e-125">Provides methods for defining and modifying the metadata signatures of methods and constructors with parameters of type <xref:System.Type?displayProperty=nameWithType>.</span></span>  
  
 [<span data-ttu-id="5f30e-126">Interfaccia IMetaDataError</span><span class="sxs-lookup"><span data-stu-id="5f30e-126">IMetaDataError Interface</span></span>](imetadataerror-interface.md)  
 <span data-ttu-id="5f30e-127">Fornisce un meccanismo di callback per la segnalazione di errori durante la risoluzione della firma dei metadati per un assembly.</span><span class="sxs-lookup"><span data-stu-id="5f30e-127">Provides a callback mechanism for reporting errors during the resolution of the metadata signature for an assembly.</span></span>  
  
 [<span data-ttu-id="5f30e-128">Interfaccia IMetaDataFilter</span><span class="sxs-lookup"><span data-stu-id="5f30e-128">IMetaDataFilter Interface</span></span>](imetadatafilter-interface.md)  
 <span data-ttu-id="5f30e-129">Fornisce metodi per contrassegnare e filtrare i token di metadati per evitare la ripetizione di azioni che sono già state eseguite.</span><span class="sxs-lookup"><span data-stu-id="5f30e-129">Provides methods for marking and filtering metadata tokens to avoid repeating actions that have already been taken.</span></span>  
  
 [<span data-ttu-id="5f30e-130">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="5f30e-130">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)  
 <span data-ttu-id="5f30e-131">Fornisce metodi per l'importazione e la modifica di tipi da altri assembly.</span><span class="sxs-lookup"><span data-stu-id="5f30e-131">Provides methods for importing and manipulating types from other assemblies.</span></span>  
  
 [<span data-ttu-id="5f30e-132">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="5f30e-132">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)  
 <span data-ttu-id="5f30e-133">Estende `IMetaDataImport` per consentire l'uso dei tipi generici.</span><span class="sxs-lookup"><span data-stu-id="5f30e-133">Extends `IMetaDataImport` to provide the capability of working with generic types.</span></span>  
  
 [<span data-ttu-id="5f30e-134">Interfaccia IMetaDataInfo</span><span class="sxs-lookup"><span data-stu-id="5f30e-134">IMetaDataInfo Interface</span></span>](imetadatainfo-interface.md)  
 <span data-ttu-id="5f30e-135">Fornisce un metodo che ottiene informazioni sul mapping dei metadati da un file su disco in memoria.</span><span class="sxs-lookup"><span data-stu-id="5f30e-135">Provides a method that gets information about the mapping of metadata from an on-disk file into memory.</span></span>  
  
 [<span data-ttu-id="5f30e-136">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="5f30e-136">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)  
 <span data-ttu-id="5f30e-137">Fornisce metodi per l'archiviazione e il recupero dei metadati nelle tabelle.</span><span class="sxs-lookup"><span data-stu-id="5f30e-137">Provides methods for the storage and retrieval of metadata information in tables.</span></span>  
  
 [<span data-ttu-id="5f30e-138">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="5f30e-138">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)  
 <span data-ttu-id="5f30e-139">Estende `IMetaDataTables` per includere i metodi per l'uso di flussi di metadati.</span><span class="sxs-lookup"><span data-stu-id="5f30e-139">Extends `IMetaDataTables` to include methods for working with metadata streams.</span></span>  
  
 [<span data-ttu-id="5f30e-140">Interfaccia IMetaDataValidate</span><span class="sxs-lookup"><span data-stu-id="5f30e-140">IMetaDataValidate Interface</span></span>](imetadatavalidate-interface.md)  
 <span data-ttu-id="5f30e-141">Fornisce i metodi da usare per la convalida delle firme di metadati.</span><span class="sxs-lookup"><span data-stu-id="5f30e-141">Provides methods to use for validation of metadata signatures.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5f30e-142">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="5f30e-142">Related Sections</span></span>  
 [<span data-ttu-id="5f30e-143">Funzioni statiche globali dei metadati</span><span class="sxs-lookup"><span data-stu-id="5f30e-143">Metadata Global Static Functions</span></span>](metadata-global-static-functions.md)  
  
 [<span data-ttu-id="5f30e-144">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="5f30e-144">Metadata Enumerations</span></span>](metadata-enumerations.md)  
  
 [<span data-ttu-id="5f30e-145">Strutture di metadati</span><span class="sxs-lookup"><span data-stu-id="5f30e-145">Metadata Structures</span></span>](metadata-structures.md)  
  
 [<span data-ttu-id="5f30e-146">Unioni di metadati</span><span class="sxs-lookup"><span data-stu-id="5f30e-146">Metadata Unions</span></span>](metadata-unions.md)
