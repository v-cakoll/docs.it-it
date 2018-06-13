---
title: Ottimizzazione per l'hosting Web condiviso
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- garbage collection, Web hosting
- garbage collection, optimizing
- garbage collection, shared Web hosting
ms.assetid: be98c0ab-7ef8-409f-8a0d-cb6e5b75ff20
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c3c979477f0928c9c3d2a393042867c84df33ecf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571969"
---
# <a name="optimization-for-shared-web-hosting"></a><span data-ttu-id="8b765-102">Ottimizzazione per l'hosting Web condiviso</span><span class="sxs-lookup"><span data-stu-id="8b765-102">Optimization for Shared Web Hosting</span></span>
<span data-ttu-id="8b765-103">L'amministratore di un server condiviso che ospita più siti Web di piccole dimensioni può ottimizzare le prestazioni e aumentare la capacità del sito aggiungendo l'impostazione `gcTrimCommitOnLowMemory` seguente al nodo `runtime` nel file Aspnet.config nella directory .NET:</span><span class="sxs-lookup"><span data-stu-id="8b765-103">If you are the administrator for a server that is shared by hosting several small Web sites, you can optimize performance and increase site capacity by adding the following `gcTrimCommitOnLowMemory` setting to the `runtime` node in the Aspnet.config file in the .NET directory:</span></span>  
  
 `<gcTrimCommitOnLowMemory enabled="true|false"/>`  
  
> [!NOTE]
>  <span data-ttu-id="8b765-104">Questa impostazione è consigliata solo per scenari di hosting Web condivisi.</span><span class="sxs-lookup"><span data-stu-id="8b765-104">This setting is recommended only for shared Web hosting scenarios.</span></span>  
  
 <span data-ttu-id="8b765-105">Dato che il Garbage Collector riserva memoria per le allocazioni future, lo spazio di cui viene eseguito il commit può essere maggiore di quello strettamente necessario.</span><span class="sxs-lookup"><span data-stu-id="8b765-105">Because the garbage collector retains memory for future allocations, its committed space can be more than what is strictly needed.</span></span> <span data-ttu-id="8b765-106">È possibile ridurre questo spazio per gestire i momenti in cui è presente un carico pesante sulla memoria di sistema.</span><span class="sxs-lookup"><span data-stu-id="8b765-106">You can reduce this space to accommodate times when there is a heavy load on system memory.</span></span> <span data-ttu-id="8b765-107">La riduzione di questo spazio migliora le prestazioni e aumenta la capacità di ospitare più siti.</span><span class="sxs-lookup"><span data-stu-id="8b765-107">Reducing this committed space improves performance and expands the capacity to host more sites.</span></span>  
  
 <span data-ttu-id="8b765-108">Quando l'impostazione `gcTrimCommitOnLowMemory` è abilitata, il Garbage Collector valuta il carico di memoria di sistema e attiva la modalità trimming quando il carico raggiunge il 90%.</span><span class="sxs-lookup"><span data-stu-id="8b765-108">When the `gcTrimCommitOnLowMemory` setting is enabled, the garbage collector evaluates the system memory load and enters a trimming mode when the load reaches 90%.</span></span> <span data-ttu-id="8b765-109">La modalità trimming viene mantenuta fino a quando il carico non scende sotto l'85%.</span><span class="sxs-lookup"><span data-stu-id="8b765-109">It maintains the trimming mode until the load drops under 85%.</span></span>  
  
 <span data-ttu-id="8b765-110">Quando le condizioni lo consentono, il Garbage Collector può decidere che l'impostazione `gcTrimCommitOnLowMemory` non sarà utile per l'applicazione corrente e ignorarla.</span><span class="sxs-lookup"><span data-stu-id="8b765-110">When conditions permit, the garbage collector can decide that the `gcTrimCommitOnLowMemory` setting will not help the current application and ignore it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b765-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="8b765-111">Example</span></span>  
 <span data-ttu-id="8b765-112">Il frammento XML seguente mostra come abilitare l'impostazione `gcTrimCommitOnLowMemory`.</span><span class="sxs-lookup"><span data-stu-id="8b765-112">The following XML fragment shows how to enable the `gcTrimCommitOnLowMemory` setting.</span></span> <span data-ttu-id="8b765-113">I puntini di sospensione indicano altre impostazioni che sarebbero disponibili nel nodo `runtime`.</span><span class="sxs-lookup"><span data-stu-id="8b765-113">Ellipses indicate other settings that would be in the `runtime` node.</span></span>  
  
```xml  
<?xml version="1.0" encoding="UTF-8"?>  
<configuration>  
    <runtime>  
    . . .  
    <gcTrimCommitOnLowMemory enabled="true"/>  
    </runtime>  
    . . .  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8b765-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8b765-114">See Also</span></span>  
 [<span data-ttu-id="8b765-115">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="8b765-115">Garbage Collection</span></span>](../../../docs/standard/garbage-collection/index.md)
