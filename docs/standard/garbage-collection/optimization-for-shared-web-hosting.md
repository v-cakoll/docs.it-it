---
title: Ottimizzazione per l'hosting Web condiviso
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- garbage collection, Web hosting
- garbage collection, optimizing
- garbage collection, shared Web hosting
ms.assetid: be98c0ab-7ef8-409f-8a0d-cb6e5b75ff20
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1f423d867d4fada075800650627c94f9d09e9e7a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="optimization-for-shared-web-hosting"></a><span data-ttu-id="12b58-102">Ottimizzazione per l'hosting Web condiviso</span><span class="sxs-lookup"><span data-stu-id="12b58-102">Optimization for Shared Web Hosting</span></span>
<span data-ttu-id="12b58-103">Se si è l'amministratore per un server condiviso che ospita più siti Web di piccole dimensioni, è possibile ottimizzare le prestazioni e aumentare la capacità del sito ad aggiungere le seguenti `gcTrimCommitOnLowMemory` impostazione il `runtime` nodo nel file Aspnet. config in .NET Directory:</span><span class="sxs-lookup"><span data-stu-id="12b58-103">If you are the administrator for a server that is shared by hosting several small Web sites, you can optimize performance and increase site capacity by adding the following `gcTrimCommitOnLowMemory` setting to the `runtime` node in the Aspnet.config file in the .NET directory:</span></span>  
  
 `<gcTrimCommitOnLowMemory enabled="true|false"/>`  
  
> [!NOTE]
>  <span data-ttu-id="12b58-104">Questa impostazione è consigliata solo per il Web condiviso scenari di hosting.</span><span class="sxs-lookup"><span data-stu-id="12b58-104">This setting is recommended only for shared Web hosting scenarios.</span></span>  
  
 <span data-ttu-id="12b58-105">Perché il garbage collector riserva memoria per le future allocazioni, lo spazio può essere maggiore di quello effettivamente necessario.</span><span class="sxs-lookup"><span data-stu-id="12b58-105">Because the garbage collector retains memory for future allocations, its committed space can be more than what is strictly needed.</span></span> <span data-ttu-id="12b58-106">È possibile ridurre i tempi di tale spazio quando è presente un carico pesante in memoria di sistema.</span><span class="sxs-lookup"><span data-stu-id="12b58-106">You can reduce this space to accommodate times when there is a heavy load on system memory.</span></span> <span data-ttu-id="12b58-107">La riduzione di tale spazio migliora le prestazioni e si espande la capacità di ospitare più siti.</span><span class="sxs-lookup"><span data-stu-id="12b58-107">Reducing this committed space improves performance and expands the capacity to host more sites.</span></span>  
  
 <span data-ttu-id="12b58-108">Quando il `gcTrimCommitOnLowMemory` è attivata, il garbage collector valuta il carico di memoria di sistema e attiva la modalità trimming quando il carico raggiunge il 90%.</span><span class="sxs-lookup"><span data-stu-id="12b58-108">When the `gcTrimCommitOnLowMemory` setting is enabled, the garbage collector evaluates the system memory load and enters a trimming mode when the load reaches 90%.</span></span> <span data-ttu-id="12b58-109">La modalità di rimozione viene mantenuta fino a quando il carico scende sotto l'85%.</span><span class="sxs-lookup"><span data-stu-id="12b58-109">It maintains the trimming mode until the load drops under 85%.</span></span>  
  
 <span data-ttu-id="12b58-110">Quando le condizioni lo consentono, il garbage collector può decidere che la `gcTrimCommitOnLowMemory` impostazione non consentono l'applicazione corrente e Ignora.</span><span class="sxs-lookup"><span data-stu-id="12b58-110">When conditions permit, the garbage collector can decide that the `gcTrimCommitOnLowMemory` setting will not help the current application and ignore it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="12b58-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="12b58-111">Example</span></span>  
 <span data-ttu-id="12b58-112">Il frammento XML seguente viene illustrato come abilitare il `gcTrimCommitOnLowMemory` impostazione.</span><span class="sxs-lookup"><span data-stu-id="12b58-112">The following XML fragment shows how to enable the `gcTrimCommitOnLowMemory` setting.</span></span> <span data-ttu-id="12b58-113">Puntini di sospensione indicano altre impostazioni che verrebbero il `runtime` nodo.</span><span class="sxs-lookup"><span data-stu-id="12b58-113">Ellipses indicate other settings that would be in the `runtime` node.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="12b58-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12b58-114">See Also</span></span>  
 [<span data-ttu-id="12b58-115">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="12b58-115">Garbage Collection</span></span>](../../../docs/standard/garbage-collection/index.md)
