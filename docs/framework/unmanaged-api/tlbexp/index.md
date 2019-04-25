---
title: Funzioni di supporto Tlbexp (Riferimenti alle API non gestite)
ms.date: 03/30/2017
helpviewer_keywords:
- exporter tool [.NET Framework]
- TlbRef.dll
- Tlbexp.exe
- Type Library Exporter
ms.assetid: 5c0a3d14-5f26-4267-94a9-82c30f8db09a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f41a233e9b5338bdb0a324ff9af267a97821d4e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967700"
---
# <a name="tlbexp-helper-functions-unmanaged-api-reference"></a><span data-ttu-id="40eef-102">Funzioni di supporto Tlbexp (Riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="40eef-102">Tlbexp Helper Functions (Unmanaged API Reference)</span></span>
<span data-ttu-id="40eef-103">Lo [strumento Utilità di esportazione della libreria dei tipi](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) carica una libreria a collegamento dinamico denominata TlbRef.</span><span class="sxs-lookup"><span data-stu-id="40eef-103">The [Type Library Exporter tool](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) loads a dynamic link library named TlbRef.dll.</span></span> <span data-ttu-id="40eef-104">Questa DLL contiene due funzioni di supporto e un'interfaccia usata dall'utilità di esportazione durante il processo di conversione da assembly a libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="40eef-104">This DLL contains two helper functions and an interface that the exporter tool uses during the assembly-to-type-library conversion process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="40eef-105">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="40eef-105">In This Section</span></span>  
 [<span data-ttu-id="40eef-106">Funzione GetTypeLibInfo</span><span class="sxs-lookup"><span data-stu-id="40eef-106">GetTypeLibInfo Function</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/gettypelibinfo-function.md)  
 <span data-ttu-id="40eef-107">Fornisce informazioni sulla localizzazione e il sistema operativo per una libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="40eef-107">Provides localization and operating system information for a type library.</span></span>  
  
 [<span data-ttu-id="40eef-108">Funzione LoadTypeLibWithResolver</span><span class="sxs-lookup"><span data-stu-id="40eef-108">LoadTypeLibWithResolver Function</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md)  
 <span data-ttu-id="40eef-109">Carica una libreria dei tipi usando un'implementazione dell'[interfaccia ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) per risolvere le librerie dei tipi a cui viene fatto riferimento.</span><span class="sxs-lookup"><span data-stu-id="40eef-109">Loads a type library by using an implementation of the [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) to resolve any referenced type libraries.</span></span>  
  
 [<span data-ttu-id="40eef-110">Interfaccia ITypeLibResolver</span><span class="sxs-lookup"><span data-stu-id="40eef-110">ITypeLibResolver Interface</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md)  
 <span data-ttu-id="40eef-111">Fornisce il [metodo ResolveTypeLib](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md), che restituisce il percorso completo di una libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="40eef-111">Provides the [ResolveTypeLib method](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md), which returns the fully qualified path of a type library.</span></span>
