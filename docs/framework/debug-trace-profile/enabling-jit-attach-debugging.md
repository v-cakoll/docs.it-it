---
title: Attivazione dell'esecuzione del debug ad associazione JIT
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JIT-attach debugging
- debugging [.NET Framework], JIT-attach debugging
ms.assetid: f91fc5f7-de5a-4f23-b6ac-f450e63c662e
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ae0b692c99f6682c6854292c230490637ad45727
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="enabling-jit-attach-debugging"></a><span data-ttu-id="a9dd9-102">Attivazione dell'esecuzione del debug ad associazione JIT</span><span class="sxs-lookup"><span data-stu-id="a9dd9-102">Enabling JIT-Attach Debugging</span></span>
<span data-ttu-id="a9dd9-103">Il termine debug ad associazione JIT indica l'associazione di un debugger a un processo in caso di errori. Può anche essere attivato da specifici metodi o funzioni.</span><span class="sxs-lookup"><span data-stu-id="a9dd9-103">JIT-attach debugging is the phrase used to describe attaching a debugger to a process when you encounter errors, or it can be triggered by specific methods or functions.</span></span>  
  
 <span data-ttu-id="a9dd9-104">Il debug ad associazione JIT viene usato con le condizioni di errore seguenti:</span><span class="sxs-lookup"><span data-stu-id="a9dd9-104">JIT-attach debugging is used under the following fault conditions:</span></span>  
  
-   <span data-ttu-id="a9dd9-105">Eccezioni non gestite (sia nel codice gestito che in quello nativo).</span><span class="sxs-lookup"><span data-stu-id="a9dd9-105">Unhandled exceptions (in both native and managed code).</span></span>  
  
-   <span data-ttu-id="a9dd9-106">Metodo <xref:System.Environment.FailFast%2A?displayProperty=nameWithType> o funzione [RaiseFailFastException](http://go.microsoft.com/fwlink/?LinkId=182107) (famiglia Windows 7).</span><span class="sxs-lookup"><span data-stu-id="a9dd9-106"><xref:System.Environment.FailFast%2A?displayProperty=nameWithType> method or [RaiseFailFastException](http://go.microsoft.com/fwlink/?LinkId=182107) function (Windows 7 family).</span></span>  
  
-   <span data-ttu-id="a9dd9-107">Errori irreversibili di runtime.</span><span class="sxs-lookup"><span data-stu-id="a9dd9-107">Runtime fatal errors.</span></span>  
  
 <span data-ttu-id="a9dd9-108">Il debug ad associazione JIT viene attivato anche dalle chiamate ai metodi e alle funzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a9dd9-108">JIT-attach debugging is also triggered by calls to the following methods and functions:</span></span>  
  
-   <span data-ttu-id="a9dd9-109">Metodo <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a9dd9-109"><xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> method.</span></span>  
  
-   <span data-ttu-id="a9dd9-110">Metodo <xref:System.Diagnostics.Debugger.Break%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a9dd9-110"><xref:System.Diagnostics.Debugger.Break%2A?displayProperty=nameWithType> method.</span></span>  
  
-   <span data-ttu-id="a9dd9-111">Funzione [DebugBreak](http://go.microsoft.com/fwlink/?LinkId=182106) (Win32).</span><span class="sxs-lookup"><span data-stu-id="a9dd9-111">[DebugBreak](http://go.microsoft.com/fwlink/?LinkId=182106) function (Win32).</span></span>  
  
 <span data-ttu-id="a9dd9-112">Prima di [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], .NET Framework forniva chiavi del Registro di sistema separate per controllare il comportamento dei debugger nativi e gestiti.</span><span class="sxs-lookup"><span data-stu-id="a9dd9-112">Before the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], the .NET Framework provided separate registry keys to control the behavior of native and managed debuggers.</span></span> <span data-ttu-id="a9dd9-113">A partire [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], il controllo viene consolidato in una singola chiave del Registro di sistema: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\Current Version\AeDebug.</span><span class="sxs-lookup"><span data-stu-id="a9dd9-113">Starting with the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], control is consolidated under a single registry key: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\Current Version\AeDebug.</span></span> <span data-ttu-id="a9dd9-114">I valori che è possibile impostare per tale chiave determinano se un debugger viene richiamato e, in tal caso, se viene richiamato con una finestra di dialogo che richiede l'intervento dell'utente.</span><span class="sxs-lookup"><span data-stu-id="a9dd9-114">The values you can set for that key determine whether a debugger is invoked, and, if so, whether it is invoked with a dialog box that requires user interaction.</span></span> <span data-ttu-id="a9dd9-115">Per informazioni sull'impostazione di questa chiave del Registro di sistema, vedere [configurazione debug automatico](http://go.microsoft.com/fwlink/?LinkId=181767).</span><span class="sxs-lookup"><span data-stu-id="a9dd9-115">For information about setting this registry key, see [Configuring Automatic Debugging](http://go.microsoft.com/fwlink/?LinkId=181767).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9dd9-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a9dd9-116">See Also</span></span>  
 [<span data-ttu-id="a9dd9-117">Debug, traccia e profilatura</span><span class="sxs-lookup"><span data-stu-id="a9dd9-117">Debugging, Tracing, and Profiling</span></span>](../../../docs/framework/debug-trace-profile/index.md)  
 [<span data-ttu-id="a9dd9-118">Semplificazione del debug di un'immagine</span><span class="sxs-lookup"><span data-stu-id="a9dd9-118">Making an Image Easier to Debug</span></span>](../../../docs/framework/debug-trace-profile/making-an-image-easier-to-debug.md)  
 [<span data-ttu-id="a9dd9-119">Abilitazione della funzione di profilatura</span><span class="sxs-lookup"><span data-stu-id="a9dd9-119">Enabling Profiling</span></span>](http://msdn.microsoft.com/en-us/3b669676-f0e0-4ebf-8674-68986dd2020d)
