---
title: Funzioni di supporto Tlbexp (Riferimenti alle API non gestite)
ms.date: 03/30/2017
helpviewer_keywords:
- exporter tool [.NET Framework]
- TlbRef.dll
- Tlbexp.exe
- Type Library Exporter
ms.assetid: 5c0a3d14-5f26-4267-94a9-82c30f8db09a
ms.openlocfilehash: cbde2af9c8a03e6c41f571120027030713f1b8d5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73104121"
---
# <a name="tlbexp-helper-functions-unmanaged-api-reference"></a><span data-ttu-id="4c653-102">Funzioni di supporto Tlbexp (Riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="4c653-102">Tlbexp Helper Functions (Unmanaged API Reference)</span></span>
<span data-ttu-id="4c653-103">Lo [strumento Utilità di esportazione della libreria dei tipi](../../tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) carica una libreria a collegamento dinamico denominata TlbRef.</span><span class="sxs-lookup"><span data-stu-id="4c653-103">The [Type Library Exporter tool](../../tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) loads a dynamic link library named TlbRef.dll.</span></span> <span data-ttu-id="4c653-104">Questa DLL contiene due funzioni di supporto e un'interfaccia usata dall'utilità di esportazione durante il processo di conversione da assembly a libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="4c653-104">This DLL contains two helper functions and an interface that the exporter tool uses during the assembly-to-type-library conversion process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4c653-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="4c653-105">In This Section</span></span>  
 [<span data-ttu-id="4c653-106">Funzione GetTypeLibInfo</span><span class="sxs-lookup"><span data-stu-id="4c653-106">GetTypeLibInfo Function</span></span>](gettypelibinfo-function.md)  
 <span data-ttu-id="4c653-107">Fornisce informazioni sulla localizzazione e il sistema operativo per una libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="4c653-107">Provides localization and operating system information for a type library.</span></span>  
  
 [<span data-ttu-id="4c653-108">Funzione LoadTypeLibWithResolver</span><span class="sxs-lookup"><span data-stu-id="4c653-108">LoadTypeLibWithResolver Function</span></span>](loadtypelibwithresolver-function.md)  
 <span data-ttu-id="4c653-109">Carica una libreria dei tipi usando un'implementazione dell'[interfaccia ITypeLibResolver](itypelibresolver-interface.md) per risolvere le librerie dei tipi a cui viene fatto riferimento.</span><span class="sxs-lookup"><span data-stu-id="4c653-109">Loads a type library by using an implementation of the [ITypeLibResolver interface](itypelibresolver-interface.md) to resolve any referenced type libraries.</span></span>  
  
 [<span data-ttu-id="4c653-110">Interfaccia ITypeLibResolver</span><span class="sxs-lookup"><span data-stu-id="4c653-110">ITypeLibResolver Interface</span></span>](itypelibresolver-interface.md)  
 <span data-ttu-id="4c653-111">Fornisce il [metodo ResolveTypeLib](resolvetypelib-method.md), che restituisce il percorso completo di una libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="4c653-111">Provides the [ResolveTypeLib method](resolvetypelib-method.md), which returns the fully qualified path of a type library.</span></span>
